---
title: .NET के लिए Aspose.Slides के साथ सुंदर चार्ट बनाना
linktitle: चार्ट निकाय और स्वरूपण
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: .NET के लिए Aspose.Slides के साथ शानदार चार्ट बनाना सीखें। हमारे चरण-दर-चरण गाइड के साथ अपने डेटा विज़ुअलाइज़ेशन गेम को बेहतर बनाएँ।
weight: 13
url: /hi/net/advanced-chart-customization/chart-entities/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Slides के साथ सुंदर चार्ट बनाना


आज की डेटा-संचालित दुनिया में, प्रभावी डेटा विज़ुअलाइज़ेशन आपके दर्शकों तक जानकारी पहुँचाने की कुंजी है। Aspose.Slides for .NET एक शक्तिशाली लाइब्रेरी है जो आपको आकर्षक चार्ट सहित शानदार प्रस्तुतियाँ और स्लाइड बनाने में सक्षम बनाती है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for .NET का उपयोग करके सुंदर चार्ट बनाने की प्रक्रिया से परिचित कराएँगे। हम चार्ट इकाइयों और फ़ॉर्मेटिंग को समझने और लागू करने में आपकी मदद करने के लिए प्रत्येक उदाहरण को कई चरणों में विभाजित करेंगे। तो, चलिए शुरू करते हैं!

## आवश्यक शर्तें

इससे पहले कि हम .NET के लिए Aspose.Slides के साथ सुंदर चार्ट बनाना शुरू करें, आपको यह सुनिश्चित करना होगा कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1.  Aspose.Slides for .NET: सुनिश्चित करें कि आपके पास Aspose.Slides for .NET लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/slides/net/).

2. विकास परिवेश: आपके पास Visual Studio या कोई अन्य IDE के साथ कार्यशील विकास परिवेश होना चाहिए जो .NET विकास का समर्थन करता हो।

3. बुनियादी C# ज्ञान: इस ट्यूटोरियल के लिए C# प्रोग्रामिंग से परिचित होना आवश्यक है।

अब जब हमने अपनी पूर्व-आवश्यकताओं को सुलझा लिया है, तो आइए Aspose.Slides for .NET के साथ सुंदर चार्ट बनाने के लिए आगे बढ़ें।

## नामस्थान आयात करें

सबसे पहले, आपको .NET के लिए Aspose.Slides के साथ काम करने के लिए आवश्यक नामस्थानों को आयात करना होगा:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## चरण 1: एक प्रस्तुति बनाएं

हम काम करने के लिए एक नई प्रस्तुति बनाकर शुरू करते हैं। यह प्रस्तुति हमारे चार्ट के लिए कैनवास का काम करेगी।

```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";

// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// प्रस्तुतिकरण को त्वरित करना
Presentation pres = new Presentation();
```

## चरण 2: पहली स्लाइड तक पहुंचें

आइये प्रस्तुतिकरण की पहली स्लाइड पर जाएं जहां हम अपना चार्ट रखेंगे।

```csharp
// पहली स्लाइड तक पहुँचना
ISlide slide = pres.Slides[0];
```

## चरण 3: एक नमूना चार्ट जोड़ें

अब, हम अपनी स्लाइड में एक नमूना चार्ट जोड़ेंगे। इस उदाहरण में, हम मार्करों के साथ एक लाइन चार्ट बनाएंगे।

```csharp
// नमूना चार्ट जोड़ना
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## चरण 4: चार्ट शीर्षक सेट करें

हम अपने चार्ट को एक शीर्षक देंगे, जिससे यह अधिक जानकारीपूर्ण और देखने में आकर्षक बन जाएगा।

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

## चरण 5: ऊर्ध्वाधर अक्ष ग्रिड लाइनों को अनुकूलित करें

इस चरण में, हम अपने चार्ट को अधिक आकर्षक बनाने के लिए ऊर्ध्वाधर अक्ष ग्रिड लाइनों को अनुकूलित करेंगे।

```csharp
// मान अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// मान अक्ष के लिए लघु ग्रिड रेखा प्रारूप सेट करना
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// मान अक्ष संख्या प्रारूप सेट करना
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## चरण 6: ऊर्ध्वाधर अक्ष सीमा परिभाषित करें

इस चरण में, हम ऊर्ध्वाधर अक्ष के लिए अधिकतम, न्यूनतम और इकाई मान निर्धारित करेंगे।

```csharp
// चार्ट के अधिकतम, न्यूनतम मान सेट करना
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

अब हम ऊर्ध्वाधर अक्ष पर पाठ के स्वरूप को अनुकूलित करेंगे।

```csharp
// मान अक्ष पाठ गुण सेट करना
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

## चरण 8: क्षैतिज अक्ष ग्रिड लाइनों को अनुकूलित करें

अब, क्षैतिज अक्ष के लिए ग्रिड लाइनों को अनुकूलित करें।

```csharp
// श्रेणी अक्ष के लिए प्रमुख ग्रिड लाइन प्रारूप सेट करना
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// श्रेणी अक्ष के लिए लघु ग्रिड रेखा प्रारूप सेट करना
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// श्रेणी अक्ष पाठ गुण सेट करना
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

इस चरण में, हम क्षैतिज अक्ष लेबल की स्थिति और घुमाव को समायोजित करेंगे।

```csharp
// श्रेणी अक्ष लेबल स्थिति सेट करना
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// श्रेणी अक्ष लेबल रोटेशन कोण सेट करना
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## चरण 10: महापुरूषों को अनुकूलित करें

आइए बेहतर पठनीयता के लिए अपने चार्ट में लेजेंड को बढ़ाएं।

```csharp
// लेजेंड टेक्स्ट गुण सेट करना
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// चार्ट को ओवरलैप किए बिना चार्ट लेजेंड दिखाने के लिए सेट करें
chart.Legend.Overlay = true;
```

## चरण 11: चार्ट पृष्ठभूमि अनुकूलित करें

हम चार्ट, पिछली दीवार और फर्श के पृष्ठभूमि रंगों को अनुकूलित करेंगे।

```csharp
// चार्ट बैक वॉल रंग सेट करना
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//प्लॉट क्षेत्र का रंग सेट करना
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## चरण 12: प्रस्तुति सहेजें

अंत में, आइए अपनी प्रस्तुति को स्वरूपित चार्ट के साथ सेव करें।

```csharp
// प्रस्तुति सहेजें
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

Aspose.Slides for .NET के साथ अपनी प्रस्तुतियों में सुंदर और जानकारीपूर्ण चार्ट बनाना अब पहले से कहीं ज़्यादा आसान है। इस ट्यूटोरियल में, हमने चार्ट के विभिन्न पहलुओं को अनुकूलित करने के लिए आवश्यक चरणों को कवर किया है, जिससे यह दिखने में आकर्षक और जानकारीपूर्ण बन जाता है। इन तकनीकों के साथ, आप शानदार चार्ट बना सकते हैं जो आपके डेटा को आपके दर्शकों तक प्रभावी ढंग से पहुँचाते हैं।

.NET के लिए Aspose.Slides के साथ प्रयोग करना शुरू करें और अपने डेटा विज़ुअलाइज़ेशन को अगले स्तर तक ले जाएं!

## अक्सर पूछे जाने वाले प्रश्नों

### 1. .NET के लिए Aspose.Slides क्या है?

Aspose.Slides for .NET एक शक्तिशाली लाइब्रेरी है जो .NET डेवलपर्स को Microsoft PowerPoint प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। यह स्लाइड, आकृतियों, चार्ट और बहुत कुछ के साथ काम करने के लिए कई प्रकार की सुविधाएँ प्रदान करता है।

### 2. मैं .NET के लिए Aspose.Slides कहां से डाउनलोड कर सकता हूं?

 आप वेबसाइट से .NET के लिए Aspose.Slides डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).

### 3. क्या Aspose.Slides for .NET के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

 हां, आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### 4. मैं Aspose.Slides for .NET के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

 यदि आपको अस्थायी लाइसेंस की आवश्यकता है, तो आप इसे यहां से प्राप्त कर सकते हैं[इस लिंक](https://purchase.aspose.com/temporary-license/).

### 5. क्या Aspose.Slides for .NET के लिए कोई समुदाय या सहायता मंच है?

 हां, आप Aspose.Slides समुदाय और सहायता फ़ोरम पा सकते हैं[यहाँ](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
