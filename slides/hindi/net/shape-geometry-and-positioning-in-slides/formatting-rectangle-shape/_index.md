---
title: प्रस्तुतियों को बेहतर बनाएँ - Aspose.Slides के साथ आयताकार आकृतियों को प्रारूपित करें
linktitle: Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में आयत आकार को फ़ॉर्मेट करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: .NET के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में आयताकार आकृतियों को प्रारूपित करना सीखें। गतिशील दृश्य तत्वों के साथ अपनी स्लाइड्स को बेहतर बनाएँ।
weight: 12
url: /hi/net/shape-geometry-and-positioning-in-slides/formatting-rectangle-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
Aspose.Slides for .NET एक शक्तिशाली लाइब्रेरी है जो .NET वातावरण में PowerPoint प्रस्तुतियों के साथ काम करने की सुविधा प्रदान करती है। यदि आप आयताकार आकृतियों को गतिशील रूप से प्रारूपित करके अपनी प्रस्तुतियों को बेहतर बनाना चाहते हैं, तो यह ट्यूटोरियल आपके लिए है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको Aspose.Slides for .NET का उपयोग करके प्रस्तुति में आयताकार आकृति को प्रारूपित करने की प्रक्रिया से परिचित कराएँगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- Aspose.Slides for .NET स्थापित एक विकास वातावरण.
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- पावरपॉइंट प्रस्तुतियों को बनाने और उनमें हेरफेर करने की जानकारी।
अब, आइए ट्यूटोरियल शुरू करें!
## नामस्थान आयात करें
अपने C# कोड में, आपको Aspose.Slides कार्यक्षमताओं का उपयोग करने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है। अपने कोड की शुरुआत में निम्नलिखित नामस्थान जोड़ें:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
```
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
 उस डायरेक्टरी को सेट करके शुरू करें जहाँ आप अपनी पावरपॉइंट प्रेजेंटेशन फ़ाइल को सहेजना चाहते हैं।`"Your Document Directory"` आपकी निर्देशिका के वास्तविक पथ के साथ.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## चरण 2: एक प्रेजेंटेशन ऑब्जेक्ट बनाएँ
 उदाहरण प्रस्तुत करें`Presentation` PPTX फ़ाइल को दर्शाने के लिए क्लास का उपयोग करें। यह आपके पावरपॉइंट प्रेजेंटेशन का आधार होगा।
```csharp
using (Presentation pres = new Presentation())
{
    // आपका कोड यहां जाएगा
}
```
## चरण 3: पहली स्लाइड प्राप्त करें
अपनी प्रस्तुति में पहली स्लाइड तक पहुंचें, क्योंकि यह वह कैनवास होगा जहां आप आयताकार आकार जोड़ेंगे और उसे प्रारूपित करेंगे।
```csharp
ISlide sld = pres.Slides[0];
```
## चरण 4: एक आयताकार आकार जोड़ें
 उपयोग`Shapes`स्लाइड की प्रॉपर्टी का उपयोग करके आयत प्रकार का एक स्वचालित आकार जोड़ें। आयत की स्थिति और आयाम निर्दिष्ट करें।
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
## चरण 5: आयत आकार पर फ़ॉर्मेटिंग लागू करें
अब, आइए आयताकार आकार पर कुछ फ़ॉर्मेटिंग लागू करें। आकार के स्वरूप को अनुकूलित करने के लिए भरण रंग, रेखा रंग और चौड़ाई सेट करें।
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
## चरण 6: प्रेजेंटेशन सहेजें
 संशोधित प्रस्तुति को डिस्क पर लिखें`Save` विधि, फ़ाइल प्रारूप को PPTX के रूप में निर्दिष्ट करना।
```csharp
pres.Save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके प्रस्तुति में एक आयत आकार को सफलतापूर्वक स्वरूपित किया है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Slides में आयताकार आकृतियों के साथ काम करने की मूल बातें बताई हैं। आपने सीखा कि कैसे अपना प्रोजेक्ट सेट अप करें, प्रेजेंटेशन बनाएं, आयताकार आकृति जोड़ें और इसके विज़ुअल अपील को बढ़ाने के लिए फ़ॉर्मेटिंग लागू करें। जैसे-जैसे आप Aspose.Slides को एक्सप्लोर करना जारी रखेंगे, आपको अपने PowerPoint प्रेजेंटेशन को बेहतर बनाने के और भी तरीके पता चलेंगे।
## पूछे जाने वाले प्रश्न
### प्रश्न 1: क्या मैं अन्य .NET भाषाओं के साथ .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, Aspose.Slides C# के अतिरिक्त VB.NET और F# जैसी अन्य .NET भाषाओं का भी समर्थन करता है।
### प्रश्न 2: मैं Aspose.Slides के लिए दस्तावेज़ कहां पा सकता हूं?
 आप दस्तावेज़ देख सकते हैं[यहाँ](https://reference.aspose.com/slides/net/).
### प्रश्न 3: मैं Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 समर्थन और चर्चा के लिए, यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### प्रश्न 4: क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप निःशुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न 5: मैं .NET के लिए Aspose.Slides कहां से खरीद सकता हूं?
 आप .NET के लिए Aspose.Slides खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
