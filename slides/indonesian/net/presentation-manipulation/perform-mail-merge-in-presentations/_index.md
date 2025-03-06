---
title: Lakukan Mail Merge dalam Presentasi
linktitle: Lakukan Mail Merge dalam Presentasi
second_title: API Pemrosesan PowerPoint Aspose.Slides .NET
description: Pelajari gabungan surat dalam presentasi menggunakan Aspose.Slides untuk .NET dalam panduan langkah demi langkah ini. Buat presentasi yang dinamis dan dipersonalisasi dengan mudah.
weight: 21
url: /id/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Perkenalan
Dalam dunia pengembangan .NET, membuat presentasi yang dinamis dan personal merupakan kebutuhan umum. Salah satu alat canggih yang menyederhanakan proses ini adalah Aspose.Slides untuk .NET. Dalam tutorial ini, kita akan mempelajari dunia menarik dalam melakukan penggabungan surat dalam presentasi menggunakan Aspose.Slides untuk .NET.
## Prasyarat
Sebelum kita memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
- Aspose.Slides for .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Slides for .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/slides/net/).
- Templat Dokumen: Siapkan templat presentasi (misalnya, PresentationTemplate.pptx) yang akan berfungsi sebagai dasar gabungan surat.
- Sumber Data: Anda memerlukan sumber data untuk gabungan surat. Dalam contoh kita, kita akan menggunakan data XML (TestData.xml), namun Aspose.Slides mendukung berbagai sumber data seperti RDBMS.
Sekarang, mari selami langkah-langkah melakukan penggabungan surat dalam presentasi menggunakan Aspose.Slides untuk .NET.
## Impor Namespace
Pertama, pastikan Anda mengimpor namespace yang diperlukan untuk memanfaatkan fungsi yang disediakan oleh Aspose.Slides:
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
## Langkah 2: Buat Kumpulan Data Menggunakan Data XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Langkah 3: Ulangi Catatan dan Buat Presentasi Individual
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // buat nama presentasi hasil (individu).
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Muat templat presentasi
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Isi kotak teks dengan data dari tabel utama
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Dapatkan gambar dari database
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Masukkan gambar ke dalam bingkai foto presentasi
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Dapatkan dan siapkan bingkai teks untuk diisi dengan data
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
    // Tambahkan titik data untuk rangkaian garis
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
Langkah-langkah ini menunjukkan panduan komprehensif tentang cara melakukan gabungan surat dalam presentasi menggunakan Aspose.Slides untuk .NET. Sekarang, mari kita jawab beberapa pertanyaan umum.
## Pertanyaan yang Sering Diajukan
### 1. Apakah Aspose.Slides for .NET kompatibel dengan sumber data yang berbeda?
Ya, Aspose.Slides untuk .NET mendukung berbagai sumber data, termasuk XML, RDBMS, dan lainnya.
### 2. Bisakah saya menyesuaikan tampilan poin-poin dalam presentasi yang dihasilkan?
 Tentu! Anda memiliki kendali penuh atas tampilan poin-poin, seperti yang ditunjukkan di`FillStaffList` metode.
### 3. Jenis bagan apa yang dapat saya buat menggunakan Aspose.Slides untuk .NET?
Aspose.Slides untuk .NET mendukung berbagai bagan, termasuk bagan garis seperti yang ditunjukkan dalam contoh kita, bagan batang, bagan lingkaran, dan banyak lagi.
### 4. Bagaimana cara mendapatkan dukungan atau mencari bantuan dengan Aspose.Slides untuk .NET?
 Untuk dukungan dan bantuan, Anda dapat mengunjungi[Forum Aspose.Slide](https://forum.aspose.com/c/slides/11).
### 5. Bisakah saya mencoba Aspose.Slides untuk .NET sebelum membeli?
 Tentu! Anda dapat memanfaatkan uji coba gratis Aspose.Slides untuk .NET dari[Di Sini](https://releases.aspose.com/).
## Kesimpulan
Dalam tutorial ini, kita menjelajahi kemampuan menarik Aspose.Slides untuk .NET dalam melakukan penggabungan surat dalam presentasi. Dengan mengikuti panduan langkah demi langkah, Anda dapat membuat presentasi yang dinamis dan dipersonalisasi dengan mudah. Tingkatkan pengalaman pengembangan .NET Anda dengan Aspose.Slides untuk pembuatan presentasi yang lancar.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
