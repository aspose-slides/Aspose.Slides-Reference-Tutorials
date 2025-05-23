---
"date": "2025-04-15"
"description": "जानें कि .NET के लिए Aspose.Slides का उपयोग करके गतिशील डोनट चार्ट कैसे बनाएं। सेटअप और उन्नत सुविधाओं सहित चरण-दर-चरण निर्देशों के लिए इस गाइड का पालन करें।"
"title": "चरण-दर-चरण मार्गदर्शिका&#58; Aspose.Slides .NET के साथ डोनट चार्ट बनाएं | चार्ट और ग्राफ़"
"url": "/hi/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# चरण-दर-चरण मार्गदर्शिका: Aspose.Slides .NET के साथ डोनट चार्ट बनाएं

## परिचय

कल्पना करें कि आपको अपनी टीम या क्लाइंट को डेटा विश्लेषण परिणाम प्रस्तुत करने का काम सौंपा गया है, और आपको जानकारी को विज़ुअलाइज़ करने के लिए एक आकर्षक तरीका चाहिए। डोनट चार्ट दर्ज करें - एक बहुमुखी उपकरण जो कच्ची संख्याओं को आसानी से पचने योग्य अंतर्दृष्टि में बदल सकता है। .NET के लिए Aspose.Slides के साथ, अपनी प्रस्तुति स्लाइड में एक कस्टम डोनट चार्ट बनाना सीधा और कुशल है। यह गाइड आपको एक आकर्षक डोनट चार्ट बनाने के लिए Aspose.Slides का उपयोग करने के बारे में बताएगा, जो कि अनुकूलित श्रृंखला कॉन्फ़िगरेशन के साथ पूरा होगा।

**आप क्या सीखेंगे:**
- .NET के लिए Aspose.Slides के साथ अपना विकास वातावरण सेट अप करना
- प्रस्तुतियों में डोनट चार्ट बनाना और उन्हें अनुकूलित करना
- श्रेणी नाम और लीडर लाइन जैसी उन्नत सुविधाओं को लागू करना
- बड़े डेटा सेट के लिए प्रदर्शन को अनुकूलित करना

आइये, आरंभ करने के लिए आवश्यक पूर्वापेक्षाओं पर नजर डालें।

## आवश्यक शर्तें

इस सुविधा को लागू करने से पहले, सुनिश्चित करें कि आपका विकास वातावरण ठीक से सेट अप है। यह ट्यूटोरियल .NET प्रोग्रामिंग का बुनियादी ज्ञान और विज़ुअल स्टूडियो या इसी तरह के IDE से परिचित होने की अपेक्षा करता है।

### आवश्यक लाइब्रेरी और संस्करण
- **.NET के लिए Aspose.Slides**: उनकी जाँच करके नवीनतम संस्करण के साथ संगतता सुनिश्चित करें [आधिकारिक दस्तावेज](https://reference.aspose.com/slides/net/).

### पर्यावरण सेटअप आवश्यकताएँ
- एक कार्यशील .NET वातावरण.
- किसी कोड संपादक, जैसे कि विजुअल स्टूडियो, तक पहुंच।

### ज्ञान पूर्वापेक्षाएँ
- C# और .NET फ्रेमवर्क की बुनियादी समझ।
- प्रस्तुतिकरण सॉफ्टवेयर अवधारणाओं से परिचित होना (वैकल्पिक लेकिन उपयोगी)।

## .NET के लिए Aspose.Slides सेट अप करना

अपने प्रोजेक्ट में Aspose.Slides का उपयोग शुरू करने के लिए, आपको इसे NuGet के माध्यम से इंस्टॉल करना होगा। यहाँ उपलब्ध विधियाँ दी गई हैं:

**.NET CLI का उपयोग करना:**
```bash
dotnet add package Aspose.Slides
```

**पैकेज मैनेजर का उपयोग करना:**
```powershell
Install-Package Aspose.Slides
```

**NuGet पैकेज मैनेजर UI:**
"Aspose.Slides" खोजें और नवीनतम संस्करण स्थापित करें।

### लाइसेंस प्राप्ति चरण

1. **मुफ्त परीक्षण**: एक से शुरू करें [मुफ्त परीक्षण](https://releases.aspose.com/slides/net/) बुनियादी कार्यक्षमताओं का पता लगाने के लिए.
2. **अस्थायी लाइसेंस**यदि आपको मूल्यांकन उद्देश्यों के लिए पूर्ण सुविधाओं तक पहुंच की आवश्यकता है तो कृपया यहां जाकर अस्थायी लाइसेंस प्राप्त करें [यहाँ](https://purchase.aspose.com/temporary-license/).
3. **खरीदना**: व्यावसायिक उपयोग के लिए, लाइसेंस खरीदें [Aspose वेबसाइट](https://purchase.aspose.com/buy).

एक बार इंस्टॉल और लाइसेंस प्राप्त होने के बाद, अपने प्रोजेक्ट में Aspose.Slides को प्रारंभ करें:
```csharp
using Aspose.Slides;

// .NET के लिए Aspose.Slides आरंभ करें
var presentation = new Presentation();
```

## कार्यान्वयन मार्गदर्शिका

### नया प्रेजेंटेशन बनाना और डोनट चार्ट जोड़ना

#### अवलोकन
हम एक नई प्रस्तुति बनाकर और पहली स्लाइड में डोनट चार्ट जोड़कर शुरुआत करेंगे। इस अनुभाग में मौजूदा प्रस्तुति को लोड करना, स्लाइड तक पहुँचना और चार्ट सम्मिलित करना शामिल है।

**चरण 1: प्रेजेंटेशन लोड करें या बनाएं**
सबसे पहले, अपनी दस्तावेज़ निर्देशिका निर्दिष्ट करें और एक मौजूदा प्रस्तुति लोड करें:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
यदि आपके पास कोई मौजूदा फ़ाइल नहीं है, तो एक नई फ़ाइल बनाएँ `new Presentation()`.

**चरण 2: पहली स्लाइड तक पहुंचें**
पहली स्लाइड पर पहुंचें जहां हम अपना चार्ट जोड़ेंगे:
```csharp
ISlide slide = pres.Slides[0];
```

**चरण 3: डोनट चार्ट जोड़ें**
निर्दिष्ट निर्देशांक और आयाम पर डोनट चार्ट जोड़ें:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### डेटा कार्यपुस्तिका को कॉन्फ़िगर करना

#### अवलोकन
यह अनुभाग बताता है कि अपने डोनट चार्ट से संबद्ध डेटा वर्कबुक को कैसे कॉन्फ़िगर करें।

**चरण 4: मौजूदा डेटा तक पहुंचें और उसे साफ़ करें**
चार्ट की डेटा वर्कबुक तक पहुँचें। फिर किसी भी मौजूदा श्रृंखला या श्रेणियों को साफ़ करें:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**चरण 5: लेजेंड अक्षम करें और श्रृंखला जोड़ें**
चार्ट को साफ़ रखने के लिए लेजेंड को अक्षम करें, फिर कस्टम कॉन्फ़िगरेशन के साथ 15 श्रृंखला तक जोड़ें:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### श्रेणियाँ और डेटा बिंदु जोड़ना

#### अवलोकन
अब, आइए चार्ट में प्रत्येक श्रृंखला के लिए श्रेणियां और डेटा बिंदु भरें।

**चरण 6: श्रेणियाँ जोड़ें**
15 श्रेणियां जोड़ने के लिए आगे बढ़ें:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**चरण 7: डेटा बिंदु भरें**
वर्तमान श्रेणी के अंतर्गत प्रत्येक श्रृंखला के लिए डेटा बिंदु जोड़ें:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // उपस्थिति अनुकूलित करें
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // अंतिम श्रृंखला के लिए लेबल प्रारूप कॉन्फ़िगर करें
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // लेबल प्रदर्शन कॉन्फ़िगर करें
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### प्रस्तुति को सहेजना

**चरण 8: फ़ाइल सहेजें**
अंत में, अपनी प्रस्तुति को निर्दिष्ट निर्देशिका में सहेजें:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}