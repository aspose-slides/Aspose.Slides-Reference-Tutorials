---
"date": "2025-04-15"
"description": "शक्तिशाली Aspose.Slides for .NET लाइब्रेरी का उपयोग करके PowerPoint प्रस्तुतियों में गतिशील और आकर्षक डोनट चार्ट बनाना सीखें।"
"title": ".NET के लिए Aspose.Slides का उपयोग करके PowerPoint में डोनट चार्ट कैसे बनाएं"
"url": "/hi/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# .NET के लिए Aspose.Slides का उपयोग करके PowerPoint में डोनट चार्ट कैसे बनाएं
प्रभावी डेटा प्रस्तुति के लिए आकर्षक चार्ट बनाना आवश्यक है। डोनट चार्ट पूरे के भागों को दर्शाने के लिए एकदम सही हैं, जो उन्हें प्रतिशत-आधारित डेटा विज़ुअलाइज़ेशन के लिए आदर्श बनाता है। यह ट्यूटोरियल आपको शक्तिशाली Aspose.Slides for .NET लाइब्रेरी का उपयोग करके PowerPoint में एक गतिशील डोनट चार्ट बनाने के माध्यम से मार्गदर्शन करेगा।

## परिचय
प्रस्तुतियों में अक्सर जटिल डेटासेट के दृश्य प्रतिनिधित्व की आवश्यकता होती है, जहाँ पारंपरिक बार या लाइन चार्ट कम पड़ सकते हैं। डोनट चार्ट शैली और स्पष्टता के साथ प्रतिशत-आधारित डेटा को प्रभावी ढंग से संप्रेषित करने के लिए एक बहुमुखी उपकरण के रूप में उभरता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Slides इन चार्ट को सीधे PowerPoint के भीतर बनाने की प्रक्रिया को कैसे सरल बनाता है।

**आप क्या सीखेंगे:**
- .NET के लिए Aspose.Slides सेट अप करना
- डोनट चार्ट बनाने के लिए चरण-दर-चरण निर्देश
- अपने चार्ट में श्रृंखला और श्रेणियाँ जोड़ना
- बेहतर स्पष्टता के लिए डेटा लेबल कॉन्फ़िगर करना
- अंतिम प्रस्तुति को सहेजना

आइए जानें कि आप कस्टम डोनट चार्ट के साथ अपनी प्रस्तुतियों को बढ़ाने के लिए Aspose.Slides for .NET का लाभ कैसे उठा सकते हैं।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित चीज़ें मौजूद हैं:
- **.NET लाइब्रेरी के लिए Aspose.Slides**: NuGet या सीधे डाउनलोड के माध्यम से उपलब्ध है।
- **विकास पर्यावरण**.NET परियोजनाओं के लिए विज़ुअल स्टूडियो की अनुशंसा की जाती है।
- C# का बुनियादी ज्ञान और पावरपॉइंट की संरचना से परिचित होना।

## .NET के लिए Aspose.Slides सेट अप करना
चार्ट बनाना शुरू करने के लिए, आपको सबसे पहले अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी सेट अप करनी होगी। इसे इंस्टॉल करने के कई तरीके हैं:

**.NET CLI का उपयोग करना:**

```bash
dotnet add package Aspose.Slides
```

**पैकेज मैनेजर कंसोल का उपयोग करना:**

```powershell
Install-Package Aspose.Slides
```

**NuGet पैकेज मैनेजर UI के माध्यम से:**
"Aspose.Slides" खोजें और नवीनतम संस्करण स्थापित करें।

एक बार इंस्टॉल हो जाने पर, आप अपना प्रोजेक्ट सेट करना शुरू कर सकते हैं। यदि आप Aspose.Slides के लिए नए हैं, तो बिना किसी सीमा के इसकी पूरी क्षमताओं का पता लगाने के लिए एक अस्थायी लाइसेंस या निःशुल्क परीक्षण प्राप्त करने पर विचार करें।

### अपना प्रोजेक्ट आरंभ करें
यहां बताया गया है कि आप अपने एप्लिकेशन में Aspose.Slides को कैसे आरंभ कर सकते हैं:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
        Presentation presentation = new Presentation();
        
        // प्रस्तुति में बदलाव करने के लिए आपका कोड यहां दिया गया है
        
        // प्रस्तुति सहेजें
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## कार्यान्वयन मार्गदर्शिका
### डोनट चार्ट बनाना
#### अवलोकन
सबसे पहले, हम पावरपॉइंट स्लाइड में एक खाली डोनट चार्ट बनाएंगे। यह डेटा जोड़ने और उसके स्वरूप को अनुकूलित करने के लिए आधार के रूप में कार्य करता है।

**चरण 1: डोनट चार्ट जोड़ें**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // पहली स्लाइड में स्थिति (10, 10) पर आकार (500, 500) के साथ डोनट चार्ट जोड़ें
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // मौजूदा श्रृंखला और श्रेणियाँ साफ़ करें
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // साफ़-सुथरे लुक के लिए लेजेंड को अक्षम करें
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**स्पष्टीकरण:**
- **चार्ट जोड़ें**: स्लाइड पर एक नया डोनट चार्ट सम्मिलित करता है।
- **getChartDataवर्कबुक**: हेरफेर के लिए चार्ट में डेटा कक्षों तक पहुंच प्रदान करता है।

### श्रृंखला और श्रेणियाँ जोड़ना
#### अवलोकन
इसके बाद, हम श्रृंखला और श्रेणियां जोड़कर आपके चार्ट को सार्थक डेटा से भर देंगे।

**चरण 2: डेटा श्रृंखला जोड़ें**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // श्रृंखला जोड़ें
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // डोनट छेद और प्रारंभिक कोण को अनुकूलित करना
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // श्रेणियाँ जोड़ें
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // डेटा बिंदु के भरण और रेखा को प्रारूपित करना
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**स्पष्टीकरण:**
- **जोड़ना**: चार्ट में नई श्रृंखलाएं और श्रेणियां सम्मिलित करता है।
- **सेटडोनटहोलसाइज़**डोनट के छेद के आकार को कॉन्फ़िगर करता है, जिससे इसकी दृश्य अपील बढ़ जाती है।

### डेटा लेबल कॉन्फ़िगर करना
#### अवलोकन
डेटा लेबल आपके चार्ट डेटा को संदर्भ प्रदान करते हैं। आइए उन्हें कस्टमाइज़ करके पठनीयता बढ़ाएँ।

**चरण 3: डेटा लेबल अनुकूलित करें**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // डेटा लेबल को अनुकूलित करना
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**स्पष्टीकरण:**
- **आईडाटालेबल**: स्पष्टता और प्रस्तुति के लिए डेटा लेबल को अनुकूलित करता है।
- **सेटसेंटरटेक्स्ट**, **प्रतिशत दिखाएं**: पाठ को केन्द्रित करके और प्रतिशत दिखाकर लेबल की पठनीयता को बढ़ाएँ।

## निष्कर्ष
इस गाइड का पालन करके, आपने सीखा है कि .NET के लिए Aspose.Slides का उपयोग करके PowerPoint में एक गतिशील डोनट चार्ट कैसे बनाया जाता है। यह शक्तिशाली लाइब्रेरी व्यापक अनुकूलन की अनुमति देती है, जिससे आप अपने चार्ट को अपनी प्रस्तुति आवश्यकताओं के अनुसार सटीक रूप से तैयार कर सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}