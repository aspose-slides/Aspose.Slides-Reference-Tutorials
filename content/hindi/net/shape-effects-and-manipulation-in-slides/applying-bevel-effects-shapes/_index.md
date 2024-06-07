---
title: Aspose.Slides में बेवल प्रभाव में महारत हासिल करना - चरण दर चरण ट्यूटोरियल
linktitle: Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में आकृतियों पर बेवल प्रभाव लागू करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET के साथ अपनी प्रस्तुति स्लाइड्स को बेहतर बनाएँ! इस चरण-दर-चरण मार्गदर्शिका में आकर्षक बेवल प्रभाव लागू करना सीखें।
type: docs
weight: 24
url: /hi/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/
---
## परिचय
प्रस्तुतियों की गतिशील दुनिया में, अपनी स्लाइड्स में दृश्य अपील जोड़ना आपके संदेश के प्रभाव को काफी हद तक बढ़ा सकता है। Aspose.Slides for .NET आपके प्रस्तुति स्लाइड्स को प्रोग्रामेटिक रूप से हेरफेर करने और सुंदर बनाने के लिए एक शक्तिशाली टूलकिट प्रदान करता है। ऐसी ही एक आकर्षक विशेषता आकृतियों पर बेवल प्रभाव लागू करने की क्षमता है, जो आपके दृश्यों में गहराई और आयाम जोड़ती है।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
-  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास Aspose.Slides लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/slides/net/).
- विकास परिवेश: अपना .NET विकास परिवेश स्थापित करें, और C# की बुनियादी समझ प्राप्त करें।
- दस्तावेज़ निर्देशिका: अपने दस्तावेज़ों के लिए एक निर्देशिका बनाएँ जहाँ उत्पन्न प्रस्तुति फ़ाइलें सहेजी जाएँगी।
## नामस्थान आयात करें
अपने C# कोड में, Aspose.Slides कार्यात्मकताओं तक पहुँचने के लिए आवश्यक नामस्थान शामिल करें।
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
सुनिश्चित करें कि दस्तावेज़ निर्देशिका मौजूद है, यदि वह पहले से मौजूद नहीं है तो उसे बनाएं।
## चरण 2: एक प्रेजेंटेशन इंस्टेंस बनाएं
```csharp
Presentation pres = new Presentation();
ISlide slide = pres.Slides[0];
```
एक प्रस्तुतिकरण इंस्टैंस आरंभ करें और कार्य करने के लिए एक स्लाइड जोड़ें.
## चरण 3: स्लाइड में आकृति जोड़ें
```csharp
IAutoShape shape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.FillFormat.FillType = FillType.Solid;
shape.FillFormat.SolidFillColor.Color = Color.Green;
ILineFillFormat format = shape.LineFormat.FillFormat;
format.FillType = FillType.Solid;
format.SolidFillColor.Color = Color.Orange;
shape.LineFormat.Width = 2.0;
```
एक स्वचालित आकार (इस उदाहरण में दीर्घवृत्त) बनाएं और इसके भरण और रेखा गुणों को अनुकूलित करें।
## चरण 4: ThreeDFormat गुण सेट करें
```csharp
shape.ThreeDFormat.Depth = 4;
shape.ThreeDFormat.BevelTop.BevelType = BevelPresetType.Circle;
shape.ThreeDFormat.BevelTop.Height = 6;
shape.ThreeDFormat.BevelTop.Width = 6;
shape.ThreeDFormat.Camera.CameraType = CameraPresetType.OrthographicFront;
shape.ThreeDFormat.LightRig.LightType = LightRigPresetType.ThreePt;
shape.ThreeDFormat.LightRig.Direction = LightingDirection.Top;
```
बेवल प्रकार, ऊंचाई, चौड़ाई, कैमरा प्रकार, प्रकाश प्रकार और दिशा सहित त्रि-आयामी गुण निर्दिष्ट करें।
## चरण 5: प्रस्तुति सहेजें
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
लागू बेवल प्रभाव के साथ प्रस्तुति को PPTX फ़ाइल में सहेजें।
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके अपनी प्रस्तुति में आकृति पर बेवल प्रभाव सफलतापूर्वक लागू किया है। अपनी स्लाइड्स में दृश्य संवर्द्धन की पूरी क्षमता को उजागर करने के लिए विभिन्न मापदंडों के साथ प्रयोग करें।
## अक्सर पूछे जाने वाले प्रश्नों
### 1. क्या मैं अन्य आकृतियों पर बेवल प्रभाव लागू कर सकता हूँ?
हां, आप आकृति के प्रकार और गुणों को तदनुसार समायोजित करके विभिन्न आकृतियों पर बेवल प्रभाव लागू कर सकते हैं।
### 2. मैं बेवल का रंग कैसे बदल सकता हूँ?
 संशोधित करें`SolidFillColor.Color` के भीतर संपत्ति`BevelTop` बेवल का रंग बदलने के लिए संपत्ति.
### 3. क्या Aspose.Slides नवीनतम .NET फ्रेमवर्क के साथ संगत है?
हां, नवीनतम .NET फ्रेमवर्क के साथ संगतता सुनिश्चित करने के लिए Aspose.Slides को नियमित रूप से अपडेट किया जाता है।
### 4. क्या मैं एक ही आकृति पर एकाधिक बेवल प्रभाव लागू कर सकता हूँ?
हालांकि यह सामान्य नहीं है, लेकिन आप समान प्रभाव प्राप्त करने के लिए कई आकृतियों को एक साथ रखकर या बेवल गुणों में हेरफेर करके प्रयोग कर सकते हैं।
### 5. क्या Aspose.Slides में अन्य 3D प्रभाव उपलब्ध हैं?
बिल्कुल! Aspose.Slides आपके प्रस्तुतिकरण तत्वों में गहराई और यथार्थवाद जोड़ने के लिए विभिन्न प्रकार के 3D प्रभाव प्रदान करता है।