---
"date": "2025-04-15"
"description": "Aspose.Slides के साथ .NET प्रस्तुतियों में पाई चार्ट निर्माण को स्वचालित करने का तरीका जानें, जिससे डेटा विज़ुअलाइज़ेशन को आसानी से बढ़ाया जा सके।"
"title": "Aspose.Slides का उपयोग करके .NET प्रस्तुतियों में पाई चार्ट कैसे बनाएं और अनुकूलित करें"
"url": "/hi/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides का उपयोग करके .NET प्रस्तुतियों में पाई चार्ट कैसे बनाएं और अनुकूलित करें

## परिचय
प्रभावी संचार के लिए आकर्षक और जानकारीपूर्ण प्रस्तुतियाँ बनाना महत्वपूर्ण है, चाहे आप काम पर डेटा प्रस्तुत कर रहे हों या अपने नवीनतम प्रोजेक्ट निष्कर्षों को प्रदर्शित कर रहे हों। डेटा को विज़ुअलाइज़ करने का एक शक्तिशाली तरीका पाई चार्ट के माध्यम से है, जो संक्षेप में पूरे के कुछ हिस्सों का प्रतिनिधित्व कर सकता है। हालाँकि, PowerPoint जैसे प्रेजेंटेशन सॉफ़्टवेयर में इन चार्ट को मैन्युअल रूप से तैयार करना समय लेने वाला हो सकता है और इसमें गतिशील अपडेट के लिए आवश्यक लचीलेपन की कमी हो सकती है।

यहीं पर Aspose.Slides for .NET काम आता है। यह व्यापक लाइब्रेरी आपको प्रोग्रामेटिक रूप से प्रेजेंटेशन बनाने, संशोधित करने और स्टाइल करने की अनुमति देती है, जिससे यह उन डेवलपर्स के लिए एक अमूल्य उपकरण बन जाता है जो अपने वर्कफ़्लो को स्वचालित करना चाहते हैं और प्रेजेंटेशन में एकरूपता सुनिश्चित करना चाहते हैं।

इस ट्यूटोरियल में, हम यह जानेंगे कि अपने प्रेजेंटेशन में पाई चार्ट बनाने और कस्टमाइज़ करने के लिए Aspose.Slides for .NET का उपयोग कैसे करें। आप सीखेंगे कि कैसे:
- **प्रस्तुति बनाएं और स्लाइड तक पहुंचें**
- **पाई चार्ट जोड़ें और कॉन्फ़िगर करें**
- **चार्ट डेटा और श्रृंखला को अनुकूलित करें**
- **शैली पाई चार्ट सेक्टर**
- **कस्टम लेबल जोड़ें**
- **प्रदर्शन गुण कॉन्फ़िगर करें और प्रस्तुति सहेजें**

क्या आप आसानी से शानदार पाई चार्ट बनाने के लिए तैयार हैं? चलिए शुरू करते हैं!

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित सेटअप मौजूद है:

### आवश्यक पुस्तकालय
- .NET के लिए Aspose.Slides (संस्करण 21.11 या बाद का संस्करण अनुशंसित)

### पर्यावरण सेटअप
- .NET फ्रेमवर्क या .NET Core/5+/6+ चलाने वाला विकास वातावरण
- एक कोड संपादक जैसे कि Visual Studio

### ज्ञान पूर्वापेक्षाएँ
- C# प्रोग्रामिंग की बुनियादी समझ
- वस्तु-उन्मुख अवधारणाओं से परिचित होना

## .NET के लिए Aspose.Slides सेट अप करना
आरंभ करने के लिए, आपको Aspose.Slides लाइब्रेरी स्थापित करनी होगी। आप निम्न में से किसी भी विधि का उपयोग करके ऐसा कर सकते हैं:

**.NET सीएलआई**
```bash
dotnet add package Aspose.Slides
```

**पैकेज प्रबंधक कंसोल**
```powershell
Install-Package Aspose.Slides
```

**NuGet पैकेज मैनेजर UI**
- अपना प्रोजेक्ट Visual Studio में खोलें.
- "टूल्स" > "NuGet पैकेज मैनेजर" > "समाधान के लिए NuGet पैकेज प्रबंधित करें" पर जाएं।
- "Aspose.Slides" खोजें और नवीनतम संस्करण स्थापित करें।

### लाइसेंस प्राप्ति चरण
Aspose.Slides का उपयोग करने के लिए, आप एक अस्थायी लाइसेंस डाउनलोड करके निःशुल्क परीक्षण के साथ शुरू कर सकते हैं। [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/) इसे प्राप्त करने के लिए। निरंतर उपयोग के लिए, पूर्ण लाइसेंस खरीदने पर विचार करें।

### बुनियादी आरंभीकरण और सेटअप
एक बार इंस्टॉल हो जाने पर, प्रेजेंटेशन क्लास को आरंभ करें, जो आपकी PPTX फ़ाइल का प्रतिनिधित्व करता है:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## कार्यान्वयन मार्गदर्शिका
हम पाई चार्ट बनाने की प्रक्रिया को प्रबंधनीय भागों में विभाजित करेंगे। प्रत्येक भाग को एक विशिष्ट विशेषता पर ध्यान केंद्रित करने के लिए डिज़ाइन किया गया है, जिससे आप अपने ज्ञान को क्रमिक रूप से बढ़ा सकते हैं।

### प्रेजेंटेशन बनाएं और स्लाइड्स एक्सेस करें
**अवलोकन:** एक नया प्रेजेंटेशन बनाकर और उसकी पहली स्लाइड तक पहुँचकर शुरुआत करें। यह चार्ट और अन्य तत्वों को जोड़ने के लिए मंच तैयार करता है।

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
    Presentation presentation = new Presentation();
    
    // पहली स्लाइड तक पहुंचें
    ISlide slides = presentation.Slides[0];
}
```

### पाई चार्ट जोड़ें और कॉन्फ़िगर करें
**अवलोकन:** जानें कि अपनी स्लाइड में पाई चार्ट कैसे जोड़ें और संदर्भ के लिए उसका शीर्षक कैसे सेट करें।

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
    Presentation presentation = new Presentation();
    
    // पहली स्लाइड तक पहुंचें
    ISlide slides = presentation.Slides[0];
    
    // स्लाइड में डिफ़ॉल्ट डेटा वाला चार्ट जोड़ें
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // सेटिंग चार्ट शीर्षक
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### चार्ट डेटा और श्रृंखला को अनुकूलित करें
**अवलोकन:** अपनी विशिष्ट आवश्यकताओं के अनुरूप डेटा श्रेणियों और श्रृंखलाओं को अनुकूलित करें।

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
    Presentation presentation = new Presentation();
    
    // पहली स्लाइड तक पहुंचें
    ISlide slides = presentation.Slides[0];
    
    // स्लाइड में डिफ़ॉल्ट डेटा वाला चार्ट जोड़ें
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // पहली श्रृंखला को मान दिखाएँ पर सेट करें
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // चार्ट डेटा शीट का इंडेक्स सेट करना
    int defaultWorksheetIndex = 0;
    
    // चार्ट डेटा वर्कशीट प्राप्त करना
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // डिफ़ॉल्ट रूप से जनरेटेड श्रृंखला और श्रेणियां हटाएं
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // नई श्रेणियाँ जोड़ना
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // नई श्रृंखला जोड़ना
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // अब श्रृंखला डेटा भरा जा रहा है
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### पाई चार्ट सेक्टर शैलियों को अनुकूलित करें
**अवलोकन:** दृश्य अपील बढ़ाने और प्रमुख डेटा बिंदुओं पर जोर देने के लिए अपने पाई चार्ट के अलग-अलग क्षेत्रों को स्टाइल करें।

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
    Presentation presentation = new Presentation();
    
    // पहली स्लाइड तक पहुंचें
    ISlide slides = presentation.Slides[0];
    
    // स्लाइड में डिफ़ॉल्ट डेटा वाला चार्ट जोड़ें
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // चार्ट से श्रृंखला प्राप्त करें
    IChartSeries series = chart.ChartData.Series[0];
    
    // श्रृंखला में प्रत्येक डेटा बिंदु के लिए सेक्टर शैलियों को अनुकूलित करना
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // सेक्टर सीमा निर्धारित करना
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // सेक्टर सीमा निर्धारित करना
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // सेक्टर सीमा निर्धारित करना
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### पाई चार्ट में कस्टम लेबल जोड़ें
**अवलोकन:** स्पष्ट डेटा प्रस्तुति के लिए कस्टम लेबल जोड़कर अपने पाई चार्ट को बेहतर बनाएं।

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // आवश्यकतानुसार लेबल की स्थिति समायोजित करें
    }
}
```

### निष्कर्ष
अब आप सीख चुके हैं कि Aspose.Slides का उपयोग करके .NET प्रस्तुतियों में पाई चार्ट कैसे बनाएँ और कस्टमाइज़ करें। यह स्वचालन आपके डेटा विज़ुअलाइज़ेशन प्रयासों को महत्वपूर्ण रूप से बढ़ा सकता है, समय की बचत कर सकता है और प्रस्तुतियों में एकरूपता सुनिश्चित कर सकता है।

.NET के लिए Aspose.Slides की क्षमताओं का और अधिक पता लगाने के लिए, अतिरिक्त सुविधाओं पर विचार करें, जैसे कि अन्य चार्ट प्रकार बनाना या अपनी स्लाइड्स में अधिक जटिल डिज़ाइन तत्वों को एकीकृत करना।

हैप्पी कोडिंग!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}