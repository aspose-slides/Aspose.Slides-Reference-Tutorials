---
"date": "2025-04-15"
"description": "जानें कि .NET के लिए Aspose.Slides का उपयोग करके आकर्षक प्रतिशत-आधारित स्टैक्ड कॉलम चार्ट कैसे बनाएं। स्पष्ट डेटा विज़ुअलाइज़ेशन के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"title": "Aspose.Slides का उपयोग करके .NET में प्रतिशत-आधारित स्टैक्ड कॉलम चार्ट कैसे बनाएं"
"url": "/hi/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# .NET के लिए Aspose.Slides का उपयोग करके प्रतिशत-आधारित स्टैक्ड कॉलम चार्ट कैसे बनाएं

## परिचय

डेटा विज़ुअलाइज़ेशन के क्षेत्र में, प्रभावशाली निर्णय लेने के लिए जानकारी को स्पष्ट और प्रभावी ढंग से प्रस्तुत करना महत्वपूर्ण है। जटिल डेटासेट को सहज रूप से प्रदर्शित करने के लिए, प्रतिशत-आधारित स्टैक्ड कॉलम चार्ट आदर्श हैं। यह मार्गदर्शिका आपको .NET के लिए Aspose.Slides का उपयोग करके इन चार्ट को बनाने में मदद करेगी, जो प्रस्तुति फ़ाइलों में हेरफेर करने के लिए डिज़ाइन की गई एक मज़बूत लाइब्रेरी है।

इस ट्यूटोरियल का अनुसरण करके आप सीखेंगे:
- चार्ट डेटा सेट करना और संख्या प्रारूप कॉन्फ़िगर करना.
- श्रृंखला जोड़ना और उनका स्वरूप अनुकूलित करना।
- पठनीयता बढ़ाने के लिए लेबलों को प्रारूपित करना।

क्या आप इसमें शामिल होने के लिए तैयार हैं? आइए उन पूर्व-आवश्यकताओं से शुरुआत करें जिनकी आपको आवश्यकता है!

## आवश्यक शर्तें

अपने प्रतिशत-आधारित स्टैक्ड कॉलम चार्ट बनाने से पहले, सुनिश्चित करें कि आपका वातावरण सही तरीके से सेट किया गया है। आपको निम्न की आवश्यकता होगी:

### आवश्यक लाइब्रेरी, संस्करण और निर्भरताएँ
- **.NET के लिए Aspose.Slides**: सुनिश्चित करें कि यह लाइब्रेरी स्थापित है.

### पर्यावरण सेटअप आवश्यकताएँ
- .NET SDK स्थापित एक विकास वातावरण.
- C# कोड चलाने के लिए विजुअल स्टूडियो या कोई भी संगत IDE.

### ज्ञान पूर्वापेक्षाएँ
- C# प्रोग्रामिंग की बुनियादी समझ.
- .NET परियोजना सेटअप और पैकेज प्रबंधन से परिचित होना।

## .NET के लिए Aspose.Slides सेट अप करना

Aspose.Slides के साथ चार्ट बनाना शुरू करने के लिए, पहले इनमें से किसी एक विधि का उपयोग करके लाइब्रेरी स्थापित करें:

**.NET सीएलआई**
```bash
dotnet add package Aspose.Slides
```

**पैकेज प्रबंधक**
```powershell
Install-Package Aspose.Slides
```

**NuGet पैकेज मैनेजर UI**
- "Aspose.Slides" खोजें और नवीनतम संस्करण स्थापित करें।

### लाइसेंस प्राप्ति चरण

से एक अस्थायी लाइसेंस डाउनलोड करके निःशुल्क परीक्षण शुरू करें [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/)निरंतर उपयोग के लिए, पूर्ण लाइसेंस खरीदने पर विचार करें। 

एक बार सेटअप हो जाने पर, अपने प्रोजेक्ट में Aspose.Slides आरंभ करें:
```csharp
using Aspose.Slides;
```

## कार्यान्वयन मार्गदर्शिका

परिवेश तैयार होने के बाद, आइए प्रतिशत-आधारित स्टैक्ड कॉलम चार्ट बनाने को चरणों में विभाजित करें।

### चार्ट बनाना और कॉन्फ़िगर करना

#### अवलोकन
इसका एक उदाहरण बनाएं `Presentation` क्लास, जो स्लाइड के साथ काम करने के लिए आवश्यक है। फिर, अपनी स्लाइड पर एक स्टैक्ड कॉलम चार्ट जोड़ें और कॉन्फ़िगर करें।

#### स्टैक्ड कॉलम चार्ट जोड़ना
```csharp
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
document = new Presentation();

// पहली स्लाइड का संदर्भ प्राप्त करें
slide = document.Slides[0];

// PercentsStackedColumn चार्ट को स्थिति (20, 20) पर आकार (500x400) के साथ जोड़ें
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### संख्या प्रारूप कॉन्फ़िगर करना
सुनिश्चित करें कि आपका डेटा प्रतिशत के रूप में प्रदर्शित हो:
```csharp
// ऊर्ध्वाधर अक्ष के लिए संख्या प्रारूप कॉन्फ़िगर करें
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // संख्या प्रारूप को प्रतिशत पर सेट करें
```

#### डेटा श्रृंखला और अंक जोड़ना
मौजूदा श्रृंखला डेटा साफ़ करें और नया जोड़ें:
```csharp
// किसी भी मौजूदा श्रृंखला डेटा को साफ़ करें
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// चार्ट डेटा कार्यपुस्तिका तक पहुँचें
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// एक नई डेटा श्रृंखला "रेड्स" जोड़ें
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// श्रृंखला के लिए भरण रंग को लाल पर सेट करें
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// "रेड्स" श्रृंखला के लिए लेबल प्रारूप गुण कॉन्फ़िगर करें
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // प्रतिशत प्रारूप सेट करें
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// एक और श्रृंखला "ब्लूज़" जोड़ें
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// श्रृंखला के लिए भरण रंग को नीला पर सेट करें
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // प्रतिशत प्रारूप सेट करें
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### प्रस्तुति को सहेजना
अपनी प्रस्तुति को किसी फ़ाइल में सहेजें:
```csharp
// प्रस्तुति को PPTX प्रारूप में सहेजें
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### समस्या निवारण युक्तियों
- सुनिश्चित करें कि सभी नामस्थान सही ढंग से आयातित हैं.
- संपत्ति नामों और विधि कॉल में टाइपो की जाँच करें।
- सत्यापित करें कि फ़ाइलें सहेजने के लिए आपके पथ मौजूद हैं और उनमें सही अनुमतियाँ हैं।

## व्यावहारिक अनुप्रयोगों

यहां कुछ परिदृश्य दिए गए हैं जहां प्रतिशत-आधारित स्टैक्ड कॉलम चार्ट मूल्यवान हो सकते हैं:
1. **बिक्री विश्लेषण**कुल बिक्री के अनुपात के रूप में विभिन्न क्षेत्रों में उत्पाद प्रदर्शन की कल्पना करें।
2. **बजट आवंटन**: दिखाएँ कि विभाग समग्र कंपनी व्यय के संबंध में अपना बजट कैसे आवंटित करते हैं।
3. **बाजार अनुसंधान**: समय के साथ विभिन्न उत्पाद श्रेणियों के लिए उपभोक्ता वरीयताओं की तुलना करें।
4. **शैक्षिक डेटा**: विभिन्न विषयों में छात्रों के ग्रेड का वितरण प्रदर्शित करें।
5. **स्वास्थ्य देखभाल सांख्यिकी**: विभिन्न स्वास्थ्य स्थितियों में रोगियों की जनसांख्यिकी का प्रतिनिधित्व करना।

## प्रदर्शन संबंधी विचार

इष्टतम प्रदर्शन के लिए, विचार करें:
- डेटा बिंदुओं की संख्या को आवश्यक तक सीमित रखना।
- रनटाइम प्रसंस्करण को न्यूनतम करने के लिए डेटा को पूर्व-लोड करना।
- .NET के लिए Aspose.Slides के साथ कुशल मेमोरी प्रबंधन प्रथाओं का उपयोग करना।

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि Aspose.Slides for .NET का उपयोग करके प्रतिशत-आधारित स्टैक्ड कॉलम चार्ट कैसे बनाया जाता है। यह टूल जटिल डेटा को अधिक समझने योग्य और नेत्रहीन आकर्षक बनाकर प्रस्तुतियों को बेहतर बनाता है।

अगला कदम? Aspose.Slides में उपलब्ध अन्य चार्ट प्रकारों का अन्वेषण करें या इस कार्यक्षमता को बड़े अनुप्रयोगों में एकीकृत करें। हैप्पी कोडिंग!

## अक्सर पूछे जाने वाले प्रश्न अनुभाग

**प्रश्न 1: क्या मैं Aspose.Slides का निःशुल्क उपयोग कर सकता हूँ?**
A1: हां, आप Aspose.Slides की सुविधाओं का परीक्षण करने के लिए एक निःशुल्क परीक्षण के साथ शुरुआत कर सकते हैं।

**प्रश्न 2: Aspose.Slides for .NET द्वारा कौन से चार्ट प्रकार समर्थित हैं?**
A2: यह विभिन्न चार्ट जैसे पाई, बार, कॉलम, लाइन आदि का समर्थन करता है।

**प्रश्न 3: मैं .NET के लिए Aspose.Slides का उपयोग कैसे शुरू करूं?**
A3: ऊपर बताए अनुसार NuGet या .NET CLI का उपयोग करके लाइब्रेरी स्थापित करें। अपना पहला चार्ट बनाने के लिए हमारे दस्तावेज़ों का पालन करें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}