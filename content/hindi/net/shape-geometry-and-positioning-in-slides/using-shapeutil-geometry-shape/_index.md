---
title: शेपयूटिल के साथ ज्योमेट्री आकृतियों में महारत हासिल करना - Aspose.Slides .NET
linktitle: प्रेजेंटेशन स्लाइड्स में ज्योमेट्री शेप के लिए शेपयूटिल का उपयोग करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: गतिशील ज्यामिति आकृतियों के लिए शेपयूटिल के साथ .NET के लिए Aspose.Slides की शक्ति का अन्वेषण करें। सहजता से आकर्षक प्रस्तुतियाँ बनाएँ। अभी डाउनलोड करें! Aspose.Slides के साथ PowerPoint प्रस्तुतियों को बेहतर बनाने का तरीका जानें। ज्यामिति आकृतियों में हेरफेर के लिए शेपयूटिल का अन्वेषण करें। .NET स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका। प्रस्तुतियों को प्रभावी ढंग से अनुकूलित करें.
type: docs
weight: 17
url: /hi/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---
## परिचय
देखने में आकर्षक और गतिशील प्रस्तुति स्लाइड बनाना एक आवश्यक कौशल है, और .NET के लिए Aspose.Slides इसे प्राप्त करने के लिए एक शक्तिशाली टूलकिट प्रदान करता है। इस ट्यूटोरियल में, हम प्रस्तुति स्लाइड में ज्यामिति आकृतियों को संभालने के लिए शेपयूटिल के उपयोग का पता लगाएंगे। चाहे आप एक अनुभवी डेवलपर हों या बस Aspose.Slides से शुरुआत कर रहे हों, यह मार्गदर्शिका आपको अपनी प्रस्तुतियों को बेहतर बनाने के लिए शेपयूटिल का उपयोग करने की प्रक्रिया के बारे में बताएगी।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- C# और .NET प्रोग्रामिंग की बुनियादी समझ।
-  .NET लाइब्रेरी के लिए Aspose.Slides इंस्टॉल किया गया। यदि नहीं, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- .NET अनुप्रयोगों को चलाने के लिए एक विकास वातावरण स्थापित किया गया है।
## नामस्थान आयात करें
अपने C# कोड में, सुनिश्चित करें कि आप Aspose.Slides कार्यात्मकताओं तक पहुंचने के लिए आवश्यक नेमस्पेस आयात करते हैं। अपनी स्क्रिप्ट की शुरुआत में निम्नलिखित जोड़ें:
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
अब, प्रस्तुति स्लाइड में ज्यामिति आकृतियों के लिए शेपयूटिल का उपयोग करने के लिए चरण-दर-चरण मार्गदर्शिका बनाने के लिए दिए गए उदाहरण को कई चरणों में विभाजित करें।
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
सुनिश्चित करें कि आप "आपकी दस्तावेज़ निर्देशिका" को उस वास्तविक पथ से बदल दें जहाँ आप अपनी प्रस्तुति को सहेजना चाहते हैं।
## चरण 2: आउटपुट फ़ाइल नाम परिभाषित करें
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
फ़ाइल एक्सटेंशन सहित वांछित आउटपुट फ़ाइल नाम निर्दिष्ट करें।
## चरण 3: एक प्रेजेंटेशन बनाएं
```csharp
using (Presentation pres = new Presentation())
```
Aspose.Slides लाइब्रेरी का उपयोग करके एक नई प्रस्तुति ऑब्जेक्ट प्रारंभ करें।
## चरण 4: एक ज्यामिति आकृति जोड़ें
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
प्रेजेंटेशन की पहली स्लाइड में एक आयताकार आकार जोड़ें।
## चरण 5: मूल ज्यामिति पथ प्राप्त करें
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
आकृति का ज्यामिति पथ पुनः प्राप्त करें और भरण मोड सेट करें।
## चरण 6: टेक्स्ट के साथ एक ग्राफ़िक्स पथ बनाएं
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
आकृति में जोड़े जाने वाले टेक्स्ट के साथ एक ग्राफ़िक्स पथ बनाएं।
## चरण 7: ग्राफ़िक्स पथ को ज्यामिति पथ में बदलें
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
ग्राफ़िक्स पथ को ज्यामिति पथ में बदलने और भरण मोड सेट करने के लिए शेपयूटिल का उपयोग करें।
## चरण 8: संयुक्त ज्यामिति पथ को आकार में सेट करें
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
नए ज्यामिति पथ को मूल पथ के साथ संयोजित करें और इसे आकार में सेट करें।
## चरण 9: प्रस्तुति सहेजें
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
संशोधित प्रस्तुति को नई ज्यामिति आकृति के साथ सहेजें।
## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में ज्यामिति आकृतियों को संभालने के लिए शेपयूटिल के उपयोग का सफलतापूर्वक पता लगाया है। यह शक्तिशाली सुविधा आपको आसानी से गतिशील और आकर्षक प्रस्तुतियाँ बनाने की अनुमति देती है।
## पूछे जाने वाले प्रश्न
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
Aspose.Slides मुख्य रूप से .NET भाषाओं का समर्थन करता है। हालाँकि, Aspose अन्य प्लेटफ़ॉर्म और भाषाओं के लिए समान लाइब्रेरी प्रदान करता है।
### मुझे .NET के लिए Aspose.Slides के लिए विस्तृत दस्तावेज़ कहाँ मिल सकते हैं?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/slides/net/).
### क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप निःशुल्क परीक्षण पा सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 सामुदायिक सहायता मंच पर जाएँ[यहाँ](https://forum.aspose.com/c/slides/11).
### क्या मैं .NET के लिए Aspose.Slides के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).