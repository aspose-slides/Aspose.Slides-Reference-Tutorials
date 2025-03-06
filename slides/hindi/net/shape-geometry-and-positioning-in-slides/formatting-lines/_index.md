---
title: Aspose.Slides .NET ट्यूटोरियल के साथ प्रस्तुति पंक्तियों को प्रारूपित करें
linktitle: Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में पंक्तियों को फ़ॉर्मेट करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET के साथ अपनी प्रेजेंटेशन स्लाइड्स को बेहतर बनाएँ। लाइनों को आसानी से फ़ॉर्मेट करने के लिए हमारे चरण-दर-चरण गाइड का पालन करें। अभी निःशुल्क परीक्षण डाउनलोड करें!
weight: 10
url: /hi/net/shape-geometry-and-positioning-in-slides/formatting-lines/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
प्रभावी संचार के लिए आकर्षक प्रस्तुति स्लाइड बनाना आवश्यक है। Aspose.Slides for .NET प्रस्तुति तत्वों को प्रोग्रामेटिक रूप से हेरफेर और प्रारूपित करने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Slides for .NET का उपयोग करके प्रस्तुति स्लाइड में लाइनों को प्रारूपित करने पर ध्यान केंद्रित करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
-  Aspose.Slides for .NET लाइब्रेरी: लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[Aspose.Slides .NET दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/).
- विकास परिवेश: Visual Studio या किसी अन्य संगत IDE के साथ .NET विकास परिवेश स्थापित करें।
## नामस्थान आयात करें
अपनी C# कोड फ़ाइल में, Aspose.Slides की कार्यक्षमता का लाभ उठाने के लिए आवश्यक नामस्थान शामिल करें:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा विकास वातावरण में एक नया प्रोजेक्ट बनाएं और Aspose.Slides लाइब्रेरी में संदर्भ जोड़ें।
## चरण 2: प्रस्तुति आरंभ करें
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
```
## चरण 3: पहली स्लाइड तक पहुंचें
```csharp
ISlide sld = pres.Slides[0];
```
## चरण 4: आयत ऑटोशेप जोड़ें
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 75);
```
## चरण 5: आयत भरण रंग सेट करें
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.White;
```
## चरण 6: लाइन पर फ़ॉर्मेटिंग लागू करें
```csharp
shp.LineFormat.Style = LineStyle.ThickThin;
shp.LineFormat.Width = 7;
shp.LineFormat.DashStyle = LineDashStyle.Dash;
```
## चरण 7: लाइन का रंग सेट करें
```csharp
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Blue;
```
## चरण 8: प्रस्तुति सहेजें
```csharp
pres.Save(dataDir + "RectShpLn_out.pptx", SaveFormat.Pptx);
}
```
अब आपने .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में पंक्तियों को सफलतापूर्वक स्वरूपित कर लिया है!
## निष्कर्ष
Aspose.Slides for .NET प्रेजेंटेशन तत्वों को प्रोग्रामेटिक रूप से बदलने की प्रक्रिया को सरल बनाता है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपनी स्लाइड्स की दृश्य अपील को आसानी से बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न 1: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, Aspose.Slides जावा और पायथन सहित विभिन्न प्रोग्रामिंग भाषाओं का समर्थन करता है।
### प्रश्न 2: क्या Aspose.Slides के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[Aspose.Slides निःशुल्क परीक्षण](https://releases.aspose.com/).
### प्रश्न 3: मैं अतिरिक्त सहायता कहां पा सकता हूं या प्रश्न कहां पूछ सकता हूं?
 दौरा करना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) समर्थन और सामुदायिक सहायता के लिए।
### प्रश्न 4: मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
 आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[Aspose.Slides अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/).
### प्रश्न 5: मैं .NET के लिए Aspose.Slides कहां से खरीद सकता हूं?
 आप यह उत्पाद यहाँ से खरीद सकते हैं[Aspose.Slides खरीदें](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
