---
title: Sunumlarda Adres Mektup Birleştirme Gerçekleştirme
linktitle: Sunumlarda Adres Mektup Birleştirme Gerçekleştirme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Bu adım adım kılavuzda Aspose.Slides for .NET kullanarak sunumlarda adres-mektup birleştirmeyi öğrenin. Zahmetsizce dinamik, kişiselleştirilmiş sunumlar oluşturun.
type: docs
weight: 21
url: /tr/net/presentation-manipulation/perform-mail-merge-in-presentations/
---
## giriiş
.NET geliştirme dünyasında dinamik ve kişiselleştirilmiş sunumlar oluşturmak ortak bir gerekliliktir. Bu süreci kolaylaştıran güçlü araçlardan biri Aspose.Slides for .NET'tir. Bu derste, Aspose.Slides for .NET kullanarak sunumlarda adres-mektup birleştirme işleminin büyüleyici dünyasına gireceğiz.
## Önkoşullar
Bu yolculuğa çıkmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Aspose.Slides for .NET Library: Aspose.Slides for .NET kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).
- Belge Şablonu: Adres-mektup birleştirme için temel oluşturacak bir sunum şablonu (örn., SunumTemplate.pptx) hazırlayın.
- Veri Kaynağı: Adres-mektup birleştirme için bir veri kaynağına ihtiyacınız vardır. Örneğimizde XML verilerini (TestData.xml) kullanacağız ancak Aspose.Slides, RDBMS gibi çeşitli veri kaynaklarını destekler.
Şimdi Aspose.Slides for .NET kullanarak sunumlarda adres-mektup birleştirme gerçekleştirme adımlarına geçelim.
## Ad Alanlarını İçe Aktar
Öncelikle Aspose.Slides tarafından sağlanan işlevlerden yararlanmak için gerekli ad alanlarını içe aktardığınızdan emin olun:
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
## 1. Adım: Belge Dizininizi Kurun
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Sonuç yolunun mevcut olup olmadığını kontrol edin
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Adım 2: XML Verilerini Kullanarak Veri Kümesi Oluşturun
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## 3. Adım: Kayıtlar Arasında Geçiş Yapın ve Bireysel Sunumlar Oluşturun
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // sonuç (bireysel) sunum adı oluştur
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Sunum şablonunu yükle
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Metin kutularını ana tablodaki verilerle doldurun
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Veritabanından resim alın
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Sunumun resim çerçevesine resim ekleyin
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Verilerle doldurmak için metin çerçevesini alın ve hazırlayın
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Personel verilerini doldurun
        FillStaffList(textFrame, userRow, staffListTable);
        // Plan olgusu verilerini doldurun
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Adım 4: Metin Çerçevesini Liste Olarak Verilerle Doldurun
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
## Adım 5: İkincil PlanFact Tablosundan Veri Tablosunu Doldurun
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
    // Çizgi serileri için veri noktaları ekleme
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
Bu adımlar, Aspose.Slides for .NET kullanılarak sunumlarda adres-mektup birleştirmenin gerçekleştirilmesine ilişkin kapsamlı bir kılavuzu göstermektedir. Şimdi sık sorulan bazı sorulara değinelim.
## Sıkça Sorulan Sorular
### 1. Aspose.Slides for .NET farklı veri kaynaklarıyla uyumlu mudur?
Evet, Aspose.Slides for .NET XML, RDBMS ve daha fazlası dahil olmak üzere çeşitli veri kaynaklarını destekler.
### 2. Oluşturulan sunumdaki madde işaretlerinin görünümünü özelleştirebilir miyim?
 Kesinlikle! Şekilde gösterildiği gibi, madde işaretlerinin görünümü üzerinde tam kontrole sahipsiniz.`FillStaffList` yöntem.
### 3. Aspose.Slides for .NET'i kullanarak ne tür grafikler oluşturabilirim?
Aspose.Slides for .NET, örneğimizde gösterildiği gibi çizgi grafikler, çubuk grafikler, pasta grafikler ve daha fazlasını içeren çok çeşitli grafikleri destekler.
### 4. Aspose.Slides for .NET ile ilgili nasıl destek alabilirim veya yardım alabilirim?
 Destek ve yardım için şu adresi ziyaret edebilirsiniz:[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
### 5. Satın almadan önce Aspose.Slides for .NET'i deneyebilir miyim?
 Kesinlikle! Aspose.Slides for .NET'in ücretsiz denemesinden şu adresten yararlanabilirsiniz:[Burada](https://releases.aspose.com/).
## Çözüm
Bu eğitimde Aspose.Slides for .NET'in sunumlarda adres-mektup birleştirme gerçekleştirmedeki heyecan verici yeteneklerini araştırdık. Adım adım kılavuzu takip ederek dinamik ve kişiselleştirilmiş sunumları zahmetsizce oluşturabilirsiniz. Sorunsuz sunumlar oluşturmak için .NET geliştirme deneyiminizi Aspose.Slides ile yükseltin.