---
title: Aspose.Slides में स्लाइड टिप्पणियाँ प्रस्तुत करना
linktitle: Aspose.Slides में स्लाइड टिप्पणियाँ प्रस्तुत करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: हमारे चरण-दर-चरण ट्यूटोरियल के साथ Aspose.Slides for .NET में स्लाइड टिप्पणियाँ प्रस्तुत करने का तरीका जानें। टिप्पणी की उपस्थिति को अनुकूलित करें और अपने PowerPoint स्वचालन को उन्नत करें।
weight: 12
url: /hi/net/printing-and-rendering-in-slides/rendering-slide-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
.NET के लिए Aspose.Slides का उपयोग करके स्लाइड टिप्पणियाँ प्रस्तुत करने पर हमारे व्यापक ट्यूटोरियल में आपका स्वागत है! Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों में PowerPoint प्रस्तुतियों के साथ सहजता से काम करने में सक्षम बनाती है। इस गाइड में, हम एक विशिष्ट कार्य पर ध्यान केंद्रित करेंगे - स्लाइड टिप्पणियाँ प्रस्तुत करना - और आपको चरण दर चरण प्रक्रिया के माध्यम से चलना होगा।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित चीजें मौजूद हैं:
-  Aspose.Slides for .NET लाइब्रेरी: सुनिश्चित करें कि आपके विकास परिवेश में Aspose.Slides लाइब्रेरी for .NET स्थापित है। यदि आपने पहले से ऐसा नहीं किया है, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- विकास परिवेश: एक कार्यशील .NET विकास परिवेश स्थापित करें, तथा C# की बुनियादी समझ रखें।
अब, आइए ट्यूटोरियल शुरू करें!
## नामस्थान आयात करें
अपने C# कोड में, आपको Aspose.Slides सुविधाओं का उपयोग करने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है। अपनी फ़ाइल की शुरुआत में निम्न पंक्तियाँ जोड़ें:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
अपने दस्तावेज़ निर्देशिका का पथ निर्दिष्ट करके आरंभ करें जहां PowerPoint प्रस्तुति स्थित है:
```csharp
string dataDir = "Your Document Directory";
```
## चरण 2: आउटपुट पथ निर्दिष्ट करें
टिप्पणियों के साथ वह पथ परिभाषित करें जहां आप रेंडर की गई छवि को सहेजना चाहते हैं:
```csharp
string resultPath = Path.Combine(dataDir, "OutPresBitmap_Comments.png");
```
## चरण 3: प्रस्तुति लोड करें
Aspose.Slides लाइब्रेरी का उपयोग करके PowerPoint प्रस्तुति लोड करें:
```csharp
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```
## चरण 4: रेंडरिंग के लिए बिटमैप बनाएं
इच्छित आयामों के साथ एक बिटमैप ऑब्जेक्ट बनाएं:
```csharp
Bitmap bmp = new Bitmap(740, 960);
```
## चरण 5: रेंडरिंग विकल्प कॉन्फ़िगर करें
नोट्स और टिप्पणियों के लिए लेआउट विकल्पों सहित रेंडरिंग विकल्पों को कॉन्फ़िगर करें:
```csharp
IRenderingOptions renderOptions = new RenderingOptions();
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.CommentsAreaColor = Color.Red;
notesOptions.CommentsAreaWidth = 200;
notesOptions.CommentsPosition = CommentsPositions.Right;
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderOptions.SlidesLayoutOptions = notesOptions;
```
## चरण 6: ग्राफ़िक्स में रेंडर करें
निर्दिष्ट ग्राफ़िक्स ऑब्जेक्ट पर टिप्पणियों के साथ पहली स्लाइड प्रस्तुत करें:
```csharp
using (Graphics graphics = Graphics.FromImage(bmp))
{
    pres.Slides[0].RenderToGraphics(renderOptions, graphics);
}
```
## चरण 7: परिणाम सहेजें
रेंडर की गई छवि को टिप्पणियों के साथ निर्दिष्ट पथ पर सहेजें:
```csharp
bmp.Save(resultPath, ImageFormat.Png);
```
## चरण 8: परिणाम प्रदर्शित करें
डिफ़ॉल्ट छवि व्यूअर का उपयोग करके रेंडर की गई छवि खोलें:
```csharp
System.Diagnostics.Process.Start(resultPath);
```
बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके स्लाइड टिप्पणियाँ सफलतापूर्वक प्रस्तुत की हैं।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Slides का उपयोग करके स्लाइड टिप्पणियाँ प्रस्तुत करने की प्रक्रिया का पता लगाया। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप आसानी से अपनी PowerPoint स्वचालन क्षमताओं को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या Aspose.Slides नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगत है?
उत्तर: हां, Aspose.Slides को नवीनतम .NET फ्रेमवर्क संस्करणों का समर्थन करने के लिए नियमित रूप से अपडेट किया जाता है।
### प्रश्न: क्या मैं प्रस्तुत टिप्पणियों के स्वरूप को अनुकूलित कर सकता हूँ?
उत्तर: बिल्कुल! ट्यूटोरियल में टिप्पणी क्षेत्र का रंग, चौड़ाई और स्थिति अनुकूलित करने के विकल्प शामिल हैं।
### प्रश्न: मैं .NET के लिए Aspose.Slides पर अधिक दस्तावेज़ कहां पा सकता हूं?
 उत्तर: दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/slides/net/).
### प्रश्न: मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
 उत्तर: आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मैं Aspose.Slides के लिए सहायता और समर्थन कहां से प्राप्त कर सकता हूं?
 उत्तर: यहाँ जाएँ[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन के लिए.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
