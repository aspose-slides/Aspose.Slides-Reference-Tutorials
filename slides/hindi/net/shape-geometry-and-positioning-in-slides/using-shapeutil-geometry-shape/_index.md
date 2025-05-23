---
"description": "गतिशील ज्यामिति आकृतियों के लिए ShapeUtil के साथ .NET के लिए Aspose.Slides की शक्ति का अन्वेषण करें। आसानी से आकर्षक प्रस्तुतियाँ बनाएँ। अभी डाउनलोड करें! Aspose.Slides के साथ PowerPoint प्रस्तुतियों को बेहतर बनाने का तरीका जानें। ज्यामिति आकृतियों में हेरफेर के लिए ShapeUtil का अन्वेषण करें। .NET स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका। प्रस्तुतियों को प्रभावी ढंग से अनुकूलित करें।"
"linktitle": "प्रेजेंटेशन स्लाइड्स में ज्यामिति आकार के लिए ShapeUtil का उपयोग करना"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "ShapeUtil के साथ ज्यामिति आकृतियों में महारत हासिल करें - Aspose.Slides .NET"
"url": "/hi/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ShapeUtil के साथ ज्यामिति आकृतियों में महारत हासिल करें - Aspose.Slides .NET

## परिचय
दिखने में आकर्षक और गतिशील प्रेजेंटेशन स्लाइड बनाना एक आवश्यक कौशल है, और .NET के लिए Aspose.Slides इसे प्राप्त करने के लिए एक शक्तिशाली टूलकिट प्रदान करता है। इस ट्यूटोरियल में, हम प्रेजेंटेशन स्लाइड में ज्यामिति आकृतियों को संभालने के लिए ShapeUtil के उपयोग का पता लगाएंगे। चाहे आप एक अनुभवी डेवलपर हों या Aspose.Slides के साथ अभी शुरुआत कर रहे हों, यह गाइड आपको अपनी प्रेजेंटेशन को बेहतर बनाने के लिए ShapeUtil का उपयोग करने की प्रक्रिया से गुजारेगी।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- C# और .NET प्रोग्रामिंग की बुनियादी समझ।
- Aspose.Slides for .NET लाइब्रेरी इंस्टॉल की गई है। यदि नहीं, तो आप इसे डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/net/).
- .NET अनुप्रयोगों को चलाने के लिए स्थापित एक विकास वातावरण.
## नामस्थान आयात करें
अपने C# कोड में, सुनिश्चित करें कि आप Aspose.Slides कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करें। अपनी स्क्रिप्ट की शुरुआत में निम्नलिखित जोड़ें:
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
अब, आइए प्रस्तुत उदाहरण को कई चरणों में विभाजित करके प्रस्तुति स्लाइडों में ज्यामिति आकृतियों के लिए ShapeUtil का उपयोग करने के लिए चरण-दर-चरण मार्गदर्शिका बनाएं।
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
सुनिश्चित करें कि आपने "आपकी दस्तावेज़ निर्देशिका" को उस वास्तविक पथ से प्रतिस्थापित कर दिया है जहां आप अपनी प्रस्तुति को सहेजना चाहते हैं।
## चरण 2: आउटपुट फ़ाइल का नाम निर्धारित करें
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
फ़ाइल एक्सटेंशन सहित वांछित आउटपुट फ़ाइल नाम निर्दिष्ट करें।
## चरण 3: एक प्रस्तुति बनाएं
```csharp
using (Presentation pres = new Presentation())
```
Aspose.Slides लाइब्रेरी का उपयोग करके एक नया प्रस्तुति ऑब्जेक्ट आरंभ करें।
## चरण 4: ज्यामिति आकार जोड़ें
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
प्रस्तुति की पहली स्लाइड में एक आयताकार आकार जोड़ें।
## चरण 5: मूल ज्यामिति पथ प्राप्त करें
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
आकृति का ज्यामिति पथ प्राप्त करें और भरण मोड सेट करें।
## चरण 6: टेक्स्ट के साथ ग्राफ़िक्स पथ बनाएँ
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
आकृति में जोड़े जाने वाले पाठ के साथ एक ग्राफ़िक्स पथ उत्पन्न करें।
## चरण 7: ग्राफ़िक्स पथ को ज्यामिति पथ में बदलें
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
ग्राफ़िक्स पथ को ज्यामिति पथ में परिवर्तित करने और भरण मोड सेट करने के लिए ShapeUtil का उपयोग करें।
## चरण 8: आकृति के लिए संयुक्त ज्यामिति पथ सेट करें
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
नए ज्यामिति पथ को मूल पथ के साथ संयोजित करें और इसे आकार पर सेट करें।
## चरण 9: प्रस्तुति सहेजें
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
संशोधित प्रस्तुति को नए ज्यामिति आकार के साथ सहेजें.
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके प्रेजेंटेशन स्लाइड में ज्यामिति आकृतियों को संभालने के लिए ShapeUtil के उपयोग को सफलतापूर्वक समझा है। यह शक्तिशाली सुविधा आपको आसानी से गतिशील और आकर्षक प्रेजेंटेशन बनाने की अनुमति देती है।
## पूछे जाने वाले प्रश्न
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
Aspose.Slides मुख्य रूप से .NET भाषाओं का समर्थन करता है। हालाँकि, Aspose अन्य प्लेटफ़ॉर्म और भाषाओं के लिए समान लाइब्रेरी प्रदान करता है।
### मैं Aspose.Slides for .NET के लिए विस्तृत दस्तावेज़ कहां पा सकता हूं?
दस्तावेज़ उपलब्ध है [यहाँ](https://reference.aspose.com/slides/net/).
### क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
हां, आप निशुल्क परीक्षण पा सकते हैं [यहाँ](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Slides का समर्थन कैसे प्राप्त कर सकता हूं?
समुदाय सहायता फ़ोरम पर जाएँ [यहाँ](https://forum.aspose.com/c/slides/11).
### क्या मैं Aspose.Slides for .NET के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं [यहाँ](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}