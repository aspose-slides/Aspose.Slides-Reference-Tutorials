---
title: .NET के लिए Aspose.Slides के साथ सुंदर चार्ट बनाना
linktitle: चार्ट इकाइयाँ और स्वरूपण
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides के साथ शानदार चार्ट बनाना सीखें। हमारे चरण-दर-चरण मार्गदर्शिका के साथ अपने डेटा विज़ुअलाइज़ेशन गेम को उन्नत करें।
type: docs
weight: 13
url: /hi/net/advanced-chart-customization/chart-entities/
---

आज की डेटा-संचालित दुनिया में, प्रभावी डेटा विज़ुअलाइज़ेशन आपके दर्शकों तक जानकारी पहुंचाने की कुंजी है। .NET के लिए Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो आपको आकर्षक चार्ट सहित शानदार प्रस्तुतियाँ और स्लाइड बनाने में सक्षम बनाती है। इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Slides का उपयोग करके सुंदर चार्ट बनाने की प्रक्रिया के बारे में बताएंगे। चार्ट इकाइयों और फ़ॉर्मेटिंग को समझने और लागू करने में आपकी सहायता के लिए हम प्रत्येक उदाहरण को कई चरणों में विभाजित करेंगे। तो चलो शुरू हो जाओ!

## आवश्यक शर्तें

इससे पहले कि हम .NET के लिए Aspose.Slides के साथ सुंदर चार्ट बनाने में लग जाएं, आपको यह सुनिश्चित करना होगा कि आपके पास निम्नलिखित शर्तें मौजूद हैं:

1.  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Slides स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/slides/net/).

2. विकास वातावरण: आपके पास विजुअल स्टूडियो या किसी अन्य आईडीई के साथ एक कार्यशील विकास वातावरण होना चाहिए जो .NET विकास का समर्थन करता हो।

3. बुनियादी सी# ज्ञान: इस ट्यूटोरियल के लिए सी# प्रोग्रामिंग से परिचित होना आवश्यक है।

अब जब हमने अपनी पूर्वापेक्षाएँ व्यवस्थित कर ली हैं, तो आइए .NET के लिए Aspose.Slides के साथ सुंदर चार्ट बनाने के लिए आगे बढ़ें।

## नामस्थान आयात करें

सबसे पहले, आपको .NET के लिए Aspose.Slides के साथ काम करने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## चरण 1: एक प्रेजेंटेशन बनाएं

हम काम करने के लिए एक नई प्रस्तुति बनाकर शुरुआत करते हैं। यह प्रस्तुति हमारे चार्ट के लिए कैनवास के रूप में काम करेगी।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";

// यदि यह पहले से मौजूद नहीं है तो निर्देशिका बनाएं।
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// त्वरित प्रस्तुति
Presentation pres = new Presentation();
```

## चरण 2: पहली स्लाइड तक पहुंचें

आइए प्रेजेंटेशन में पहली स्लाइड तक पहुंचें जहां हम अपना चार्ट रखेंगे।

```csharp
// पहली स्लाइड तक पहुँचना
ISlide slide = pres.Slides[0];
```

## चरण 3: एक नमूना चार्ट जोड़ें

अब, हम अपनी स्लाइड में एक नमूना चार्ट जोड़ेंगे। इस उदाहरण में, हम मार्करों के साथ एक लाइन चार्ट बनाएंगे।

```csharp
// नमूना चार्ट जोड़ा जा रहा है
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## चरण 4: चार्ट शीर्षक सेट करें

हम अपने चार्ट को एक शीर्षक देंगे, जिससे यह अधिक जानकारीपूर्ण और देखने में आकर्षक बनेगा।

```csharp
// चार्ट शीर्षक सेट करना
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## चरण 5: लंबवत अक्ष ग्रिड लाइनों को अनुकूलित करें

इस चरण में, हम अपने चार्ट को अधिक आकर्षक बनाने के लिए ऊर्ध्वाधर अक्ष ग्रिड लाइनों को अनुकूलित करेंगे।

```csharp
// मान अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// मान अक्ष के लिए माइनर ग्रिड लाइन प्रारूप सेट करना
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// मान अक्ष संख्या स्वरूप सेट करना
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## चरण 6: वर्टिकल एक्सिस रेंज को परिभाषित करें

इस चरण में, हम ऊर्ध्वाधर अक्ष के लिए अधिकतम, न्यूनतम और इकाई मान निर्धारित करेंगे।

```csharp
// चार्ट को अधिकतम, न्यूनतम मान सेट करना
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## चरण 7: वर्टिकल एक्सिस टेक्स्ट को कस्टमाइज़ करें

अब हम ऊर्ध्वाधर अक्ष पर पाठ की उपस्थिति को अनुकूलित करेंगे।

```csharp
// वैल्यू एक्सिस टेक्स्ट गुण सेट करना
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// मान अक्ष शीर्षक सेट करना
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## चरण 8: क्षैतिज अक्ष ग्रिड रेखाओं को अनुकूलित करें

अब, आइए क्षैतिज अक्ष के लिए ग्रिड रेखाओं को अनुकूलित करें।

```csharp
// श्रेणी अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

//श्रेणी अक्ष के लिए माइनर ग्रिड लाइन प्रारूप सेट करना
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// श्रेणी अक्ष टेक्स्ट गुण सेट करना
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## चरण 9: क्षैतिज अक्ष लेबल अनुकूलित करें

इस चरण में, हम क्षैतिज अक्ष लेबल की स्थिति और रोटेशन को समायोजित करेंगे।

```csharp
// श्रेणी अक्ष लेबल स्थिति निर्धारित करना
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// श्रेणी अक्ष लेबल रोटेशन कोण सेट करना
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## चरण 10: किंवदंतियों को अनुकूलित करें

आइए बेहतर पठनीयता के लिए अपने चार्ट में किंवदंतियों को बढ़ाएं।

```csharp
// महापुरूष पाठ गुण सेट करना
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// ओवरलैपिंग चार्ट के बिना शो चार्ट लेजेंड्स सेट करें
chart.Legend.Overlay = true;
```

## चरण 11: चार्ट पृष्ठभूमि को अनुकूलित करें

हम चार्ट, पिछली दीवार और फर्श के पृष्ठभूमि रंगों को अनुकूलित करेंगे।

```csharp
// चार्ट पीछे की दीवार का रंग सेट करना
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// प्लॉट क्षेत्र का रंग सेट करना
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## चरण 12: प्रस्तुति सहेजें

अंत में, आइए अपनी प्रस्तुति को स्वरूपित चार्ट के साथ सहेजें।

```csharp
// प्रस्तुति सहेजें
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

.NET के लिए Aspose.Slides के साथ अपनी प्रस्तुतियों में सुंदर और जानकारीपूर्ण चार्ट बनाना अब पहले से कहीं अधिक आसान है। इस ट्यूटोरियल में, हमने चार्ट के विभिन्न पहलुओं को अनुकूलित करने के लिए आवश्यक चरणों को शामिल किया है, जिससे यह देखने में आकर्षक और जानकारीपूर्ण बन सके। इन तकनीकों से, आप आश्चर्यजनक चार्ट बना सकते हैं जो आपके डेटा को प्रभावी ढंग से आपके दर्शकों तक पहुंचाते हैं।

.NET के लिए Aspose.Slides के साथ प्रयोग शुरू करें और अपने डेटा विज़ुअलाइज़ेशन को अगले स्तर पर ले जाएं!

## अक्सर पूछे जाने वाले प्रश्नों

### 1. .NET के लिए Aspose.Slides क्या है?

.NET के लिए Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो .NET डेवलपर्स को Microsoft PowerPoint प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। यह स्लाइड, आकार, चार्ट और बहुत कुछ के साथ काम करने के लिए सुविधाओं की एक विस्तृत श्रृंखला प्रदान करता है।

### 2. मैं .NET के लिए Aspose.Slides कहां से डाउनलोड कर सकता हूं?

 आप वेबसाइट से .NET के लिए Aspose.Slides डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).

### 3. क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?

हाँ, आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### 4. मैं .NET के लिए Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 यदि आपको अस्थायी लाइसेंस की आवश्यकता है, तो आप यहां से लाइसेंस प्राप्त कर सकते हैं[इस लिंक](https://purchase.aspose.com/temporary-license/).

### 5. क्या .NET के लिए Aspose.Slides के लिए कोई समुदाय या सहायता मंच है?

 हाँ, आप Aspose.Slides समुदाय और सहायता फ़ोरम पा सकते हैं[यहाँ](https://forum.aspose.com/).
