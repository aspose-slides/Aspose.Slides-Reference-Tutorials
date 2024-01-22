---
title: Aspose.Slides में स्लाइड टिप्पणियाँ प्रस्तुत करना
linktitle: Aspose.Slides में स्लाइड टिप्पणियाँ प्रस्तुत करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: हमारे चरण-दर-चरण ट्यूटोरियल के साथ जानें कि .NET के लिए Aspose.Slides में स्लाइड टिप्पणियाँ कैसे प्रस्तुत करें। टिप्पणी उपस्थिति को अनुकूलित करें और अपने PowerPoint स्वचालन को उन्नत करें।
type: docs
weight: 12
url: /hi/net/printing-and-rendering-in-slides/rendering-slide-comments/
---
## परिचय
.NET के लिए Aspose.Slides का उपयोग करके स्लाइड टिप्पणियाँ प्रस्तुत करने पर हमारे व्यापक ट्यूटोरियल में आपका स्वागत है! Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों में PowerPoint प्रस्तुतियों के साथ निर्बाध रूप से काम करने में सक्षम बनाती है। इस गाइड में, हम एक विशिष्ट कार्य पर ध्यान केंद्रित करेंगे - स्लाइड टिप्पणियाँ प्रस्तुत करना - और आपको चरण दर चरण प्रक्रिया के बारे में बताएंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित स्थान हैं:
-  .NET लाइब्रेरी के लिए Aspose.Slides: सुनिश्चित करें कि आपके विकास परिवेश में .NET के लिए Aspose.Slides लाइब्रेरी स्थापित है। यदि आपने पहले से नहीं किया है, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- विकास परिवेश: एक कार्यशील .NET विकास परिवेश स्थापित करें, और C# की बुनियादी समझ रखें।
अब, आइए ट्यूटोरियल के साथ शुरुआत करें!
## नामस्थान आयात करें
अपने C# कोड में, आपको Aspose.Slides सुविधाओं का उपयोग करने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता है। अपनी फ़ाइल की शुरुआत में निम्नलिखित पंक्तियाँ जोड़ें:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
अपनी दस्तावेज़ निर्देशिका का पथ निर्दिष्ट करके प्रारंभ करें जहां PowerPoint प्रस्तुति स्थित है:
```csharp
string dataDir = "Your Document Directory";
```
## चरण 2: आउटपुट पथ निर्दिष्ट करें
उस पथ को परिभाषित करें जहां आप प्रस्तुत छवि को टिप्पणियों के साथ सहेजना चाहते हैं:
```csharp
string resultPath = Path.Combine(dataDir, "OutPresBitmap_Comments.png");
```
## चरण 3: प्रस्तुति लोड करें
Aspose.Slides लाइब्रेरी का उपयोग करके PowerPoint प्रस्तुति लोड करें:
```csharp
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```
## चरण 4: रेंडरिंग के लिए एक बिटमैप बनाएं
वांछित आयामों के साथ एक बिटमैप ऑब्जेक्ट बनाएं:
```csharp
Bitmap bmp = new Bitmap(740, 960);
```
## चरण 5: रेंडरिंग विकल्प कॉन्फ़िगर करें
नोट्स और टिप्पणियों के लिए लेआउट विकल्पों सहित, रेंडरिंग विकल्प कॉन्फ़िगर करें:
```csharp
IRenderingOptions renderOptions = new RenderingOptions();
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.CommentsAreaColor = Color.Red;
notesOptions.CommentsAreaWidth = 200;
notesOptions.CommentsPosition = CommentsPositions.Right;
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderOptions.SlidesLayoutOptions = notesOptions;
```
## चरण 6: ग्राफ़िक्स पर प्रस्तुत करें
निर्दिष्ट ग्राफ़िक्स ऑब्जेक्ट पर टिप्पणियों के साथ पहली स्लाइड प्रस्तुत करें:
```csharp
using (Graphics graphics = Graphics.FromImage(bmp))
{
    pres.Slides[0].RenderToGraphics(renderOptions, graphics);
}
```
## चरण 7: परिणाम सहेजें
निर्दिष्ट पथ पर टिप्पणियों के साथ प्रदान की गई छवि को सहेजें:
```csharp
bmp.Save(resultPath, ImageFormat.Png);
```
## चरण 8: परिणाम प्रदर्शित करें
डिफ़ॉल्ट छवि व्यूअर का उपयोग करके प्रदान की गई छवि खोलें:
```csharp
System.Diagnostics.Process.Start(resultPath);
```
बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके सफलतापूर्वक स्लाइड टिप्पणियाँ प्रस्तुत की हैं।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Slides का उपयोग करके स्लाइड टिप्पणियों को प्रस्तुत करने की प्रक्रिया का पता लगाया। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपनी PowerPoint स्वचालन क्षमताओं को आसानी से बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या Aspose.Slides नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगत है?
उत्तर: हां, Aspose.Slides को नवीनतम .NET फ्रेमवर्क संस्करणों का समर्थन करने के लिए नियमित रूप से अपडेट किया जाता है।
### प्रश्न: क्या मैं प्रस्तुत टिप्पणियों के स्वरूप को अनुकूलित कर सकता हूँ?
उत्तर: बिल्कुल! ट्यूटोरियल में टिप्पणी क्षेत्र के रंग, चौड़ाई और स्थिति को अनुकूलित करने के विकल्प शामिल हैं।
### प्रश्न: मुझे .NET के लिए Aspose.Slides पर अधिक दस्तावेज़ कहां मिल सकते हैं?
 उ: दस्तावेज़ का अन्वेषण करें[यहाँ](https://reference.aspose.com/slides/net/).
### प्रश्न: मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
 उत्तर: आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मैं Aspose.Slides के लिए सहायता और समर्थन कहां से प्राप्त कर सकता हूं?
 ए: पर जाएँ[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन के लिए.