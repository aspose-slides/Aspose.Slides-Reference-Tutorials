---
"description": "Pelajari penggabungan surat dalam presentasi menggunakan Aspose.Slides untuk .NET dalam panduan langkah demi langkah ini. Buat presentasi yang dinamis dan personal dengan mudah."
"linktitle": "Melakukan Mail Merge dalam Presentasi"
"second_title": "API Pemrosesan PowerPoint Aspose.Slides .NET"
"title": "Melakukan Mail Merge dalam Presentasi"
"url": "/id/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Melakukan Mail Merge dalam Presentasi

## Perkenalan
Dalam dunia pengembangan .NET, membuat presentasi yang dinamis dan personal merupakan persyaratan umum. Salah satu alat canggih yang menyederhanakan proses ini adalah Aspose.Slides for .NET. Dalam tutorial ini, kita akan menyelami ranah menarik dalam melakukan penggabungan surat dalam presentasi menggunakan Aspose.Slides for .NET.
## Prasyarat
Sebelum kita memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
- Pustaka Aspose.Slides untuk .NET: Pastikan Anda telah menginstal pustaka Aspose.Slides untuk .NET. Anda dapat mengunduhnya dari [Di Sini](https://releases.aspose.com/slides/net/).
- Templat Dokumen: Siapkan templat presentasi (misalnya, PresentationTemplate.pptx) yang akan berfungsi sebagai dasar untuk gabungan surat.
- Sumber Data: Anda memerlukan sumber data untuk gabungan surat. Dalam contoh kami, kami akan menggunakan data XML (TestData.xml), tetapi Aspose.Slides mendukung berbagai sumber data seperti RDBMS.
Sekarang, mari selami langkah-langkah melakukan gabungan surat dalam presentasi menggunakan Aspose.Slides for .NET.
## Mengimpor Ruang Nama
Pertama, pastikan Anda mengimpor namespace yang diperlukan untuk memanfaatkan fungsionalitas yang disediakan oleh Aspose.Slides:
```csharp
using System;
using System.Collections.Generic;
using System.Data;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Export;
using DataTable = System.Data.DataTable;
```
## Langkah 1: Siapkan Direktori Dokumen Anda
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Periksa apakah jalur hasil ada
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Langkah 2: Buat DataSet Menggunakan Data XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Langkah 3: Ulangi Rekaman dan Buat Presentasi Individual
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // buat hasil (individual) nama presentasi
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Muat template presentasi
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Isi kotak teks dengan data dari tabel utama
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Dapatkan gambar dari database
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Masukkan gambar ke dalam bingkai gambar presentasi
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Dapatkan dan siapkan bingkai teks untuk mengisinya dengan data
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Isi data staf
        FillStaffList(textFrame, userRow, staffListTable);
        // Isi data fakta rencana
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Langkah 4: Isi Bingkai Teks dengan Data sebagai Daftar
```csharp
static void FillStaffList(ITextFrame textFrame, DataRow userRow, DataTable staffListTable)
{
    foreach (DataRow listRow in staffListTable.Rows)
    {
        if (listRow["UserId"].ToString() == userRow["Id"].ToString())
        {
            Paragraph para = new Paragraph();
            para.ParagraphFormat.Bullet.Type = BulletType.Symbol;
            para.ParagraphFormat.Bullet.Char = Convert.ToChar(8226);
            para.Text = listRow["Name"].ToString();
            para.ParagraphFormat.Bullet.Color.ColorType = ColorType.RGB;
            para.ParagraphFormat.Bullet.Color.Color = Color.Black;
            para.ParagraphFormat.Bullet.IsBulletHardColor = NullableBool.True;
            para.ParagraphFormat.Bullet.Height = 100;
            textFrame.Paragraphs.Add(para);
        }
    }
}
```
## Langkah 5: Isi Bagan Data dari Tabel PlanFact Sekunder
```csharp
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";
    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();
    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;
    // Tambahkan titik data untuk seri garis
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries
(cellsFactory.GetCell(worksheetIndex, 1, 1, double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2, double.Parse(selRows[0]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1, double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2, double.Parse(selRows[1]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[2]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[3]["FactData"].ToString())));
    chart.ChartData.SetRange(range);
}
```
Langkah-langkah ini menunjukkan panduan lengkap tentang cara melakukan penggabungan surat dalam presentasi menggunakan Aspose.Slides for .NET. Sekarang, mari kita bahas beberapa pertanyaan yang sering diajukan.
## Pertanyaan yang Sering Diajukan
### 1. Apakah Aspose.Slides untuk .NET kompatibel dengan sumber data yang berbeda?
Ya, Aspose.Slides untuk .NET mendukung berbagai sumber data, termasuk XML, RDBMS, dan banyak lagi.
### 2. Dapatkah saya menyesuaikan tampilan poin-poin penting dalam presentasi yang dihasilkan?
Tentu saja! Anda memiliki kontrol penuh atas tampilan poin-poin, seperti yang ditunjukkan dalam `FillStaffList` metode.
### 3. Jenis bagan apa yang dapat saya buat menggunakan Aspose.Slides untuk .NET?
Aspose.Slides untuk .NET mendukung berbagai macam bagan, termasuk bagan garis seperti ditunjukkan dalam contoh kami, bagan batang, bagan pai, dan banyak lagi.
### 4. Bagaimana cara mendapatkan dukungan atau mencari bantuan dengan Aspose.Slides untuk .NET?
Untuk dukungan dan bantuan, Anda dapat mengunjungi [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Dapatkah saya mencoba Aspose.Slides untuk .NET sebelum membeli?
Tentu saja! Anda dapat memanfaatkan uji coba gratis Aspose.Slides untuk .NET dari [Di Sini](https://releases.aspose.com/).
## Kesimpulan
Dalam tutorial ini, kami mengeksplorasi kemampuan Aspose.Slides for .NET yang menarik dalam melakukan penggabungan surat dalam presentasi. Dengan mengikuti panduan langkah demi langkah, Anda dapat membuat presentasi yang dinamis dan personal dengan mudah. Tingkatkan pengalaman pengembangan .NET Anda dengan Aspose.Slides untuk pembuatan presentasi yang lancar.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}