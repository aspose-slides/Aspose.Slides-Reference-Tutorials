---
title: प्रस्तुतियों में मेल मर्ज निष्पादित करें
linktitle: प्रस्तुतियों में मेल मर्ज निष्पादित करें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: इस चरण-दर-चरण मार्गदर्शिका में Aspose.Slides for .NET का उपयोग करके प्रेजेंटेशन में मेल मर्ज करना सीखें। आसानी से गतिशील, वैयक्तिकृत प्रेजेंटेशन बनाएँ।
weight: 21
url: /hi/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रस्तुतियों में मेल मर्ज निष्पादित करें

## परिचय
.NET विकास की दुनिया में, गतिशील और व्यक्तिगत प्रस्तुतियाँ बनाना एक सामान्य आवश्यकता है। एक शक्तिशाली उपकरण जो इस प्रक्रिया को सरल बनाता है वह है Aspose.Slides for .NET। इस ट्यूटोरियल में, हम Aspose.Slides for .NET का उपयोग करके प्रस्तुतियों में मेल मर्ज करने के आकर्षक क्षेत्र में गहराई से उतरेंगे।
## आवश्यक शर्तें
इससे पहले कि हम इस यात्रा पर निकलें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- Aspose.Slides for .NET लाइब्रेरी: सुनिश्चित करें कि आपके पास Aspose.Slides for .NET लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- दस्तावेज़ टेम्पलेट: एक प्रस्तुति टेम्पलेट तैयार करें (उदाहरण के लिए, PresentationTemplate.pptx) जो मेल मर्ज के लिए आधार के रूप में काम करेगा।
- डेटा स्रोत: मेल मर्ज के लिए आपको डेटा स्रोत की आवश्यकता होती है। हमारे उदाहरण में, हम XML डेटा (TestData.xml) का उपयोग करेंगे, लेकिन Aspose.Slides RDBMS जैसे विभिन्न डेटा स्रोतों का समर्थन करता है।
अब, आइए Aspose.Slides for .NET का उपयोग करके प्रस्तुतियों में मेल मर्ज करने के चरणों पर नजर डालें।
## नामस्थान आयात करें
सबसे पहले, सुनिश्चित करें कि आप Aspose.Slides द्वारा प्रदान की गई कार्यक्षमताओं का लाभ उठाने के लिए आवश्यक नामस्थानों को आयात करें:
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
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// जाँचें कि क्या परिणाम पथ मौजूद है
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## चरण 2: XML डेटा का उपयोग करके डेटासेट बनाएं
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## चरण 3: रिकॉर्ड्स के माध्यम से लूप करें और व्यक्तिगत प्रस्तुतियाँ बनाएँ
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // परिणाम बनाएं (व्यक्तिगत) प्रस्तुति नाम
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // प्रस्तुति टेम्पलेट लोड करें
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // मुख्य तालिका से डेटा के साथ टेक्स्ट बॉक्स भरें
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // डेटाबेस से छवि प्राप्त करें
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //प्रस्तुति के चित्र फ़्रेम में छवि डालें
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // डेटा से भरने के लिए टेक्स्ट फ़्रेम प्राप्त करें और उसे तैयार करें
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // स्टाफ डेटा भरें
        FillStaffList(textFrame, userRow, staffListTable);
        // योजना तथ्य डेटा भरें
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## चरण 4: टेक्स्ट फ़्रेम को सूची के रूप में डेटा से भरें
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
## चरण 5: द्वितीयक योजना तथ्य तालिका से डेटा चार्ट भरें
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
    // रेखा श्रृंखला के लिए डेटा बिंदु जोड़ें
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
ये चरण Aspose.Slides for .NET का उपयोग करके प्रस्तुतियों में मेल मर्ज करने के बारे में एक व्यापक मार्गदर्शिका प्रदर्शित करते हैं। अब, आइए कुछ अक्सर पूछे जाने वाले प्रश्नों पर ध्यान दें।
## अक्सर पूछे जाने वाले प्रश्नों
### 1. क्या Aspose.Slides for .NET विभिन्न डेटा स्रोतों के साथ संगत है?
हां, Aspose.Slides for .NET विभिन्न डेटा स्रोतों का समर्थन करता है, जिसमें XML, RDBMS, आदि शामिल हैं।
### 2. क्या मैं तैयार प्रस्तुति में बुलेट पॉइंट्स के स्वरूप को अनुकूलित कर सकता हूँ?
 निश्चित रूप से! बुलेट पॉइंट्स की उपस्थिति पर आपका पूरा नियंत्रण है, जैसा कि दिखाया गया है`FillStaffList` तरीका।
### 3. मैं .NET के लिए Aspose.Slides का उपयोग करके किस प्रकार के चार्ट बना सकता हूँ?
.NET के लिए Aspose.Slides चार्ट की एक विस्तृत श्रृंखला का समर्थन करता है, जिसमें हमारे उदाहरण में दिखाए गए लाइन चार्ट, बार चार्ट, पाई चार्ट और बहुत कुछ शामिल हैं।
### 4. मैं Aspose.Slides for .NET के लिए समर्थन कैसे प्राप्त करूं या सहायता कैसे प्राप्त करूं?
 समर्थन और सहायता के लिए, आप यहां जा सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### 5. क्या मैं खरीदने से पहले Aspose.Slides for .NET आज़मा सकता हूँ?
 ज़रूर! आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
## निष्कर्ष
इस ट्यूटोरियल में, हमने प्रेजेंटेशन में मेल मर्ज करने में Aspose.Slides for .NET की रोमांचक क्षमताओं का पता लगाया। चरण-दर-चरण गाइड का पालन करके, आप आसानी से गतिशील और वैयक्तिकृत प्रेजेंटेशन बना सकते हैं। सहज प्रेजेंटेशन निर्माण के लिए Aspose.Slides के साथ अपने .NET विकास अनुभव को बढ़ाएँ।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
