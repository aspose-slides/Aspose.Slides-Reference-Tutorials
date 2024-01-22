---
title: प्रस्तुतियों में समग्र ज्यामिति आकृतियों में महारत हासिल करना
linktitle: Aspose.Slides के साथ ज्यामिति आकार में समग्र वस्तुएँ बनाना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके समग्र ज्यामिति आकृतियों के साथ आश्चर्यजनक प्रस्तुतियाँ बनाना सीखें। प्रभावशाली परिणामों के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 14
url: /hi/net/shape-geometry-and-positioning-in-slides/creating-composite-objects-geometry-shape/
---
## परिचय
ज्यामिति आकृतियों में समग्र ऑब्जेक्ट बनाकर अपनी प्रस्तुतियों को बेहतर बनाने के लिए .NET के लिए Aspose.Slides की शक्ति को अनलॉक करें। यह ट्यूटोरियल Aspose.Slides का उपयोग करके जटिल ज्यामिति के साथ आकर्षक स्लाइड बनाने की प्रक्रिया में आपका मार्गदर्शन करेगा।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- C# प्रोग्रामिंग भाषा की बुनियादी समझ।
-  .NET लाइब्रेरी के लिए Aspose.Slides इंस्टॉल किया गया। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/).
- विज़ुअल स्टूडियो या किसी अन्य C# विकास उपकरण के साथ स्थापित एक विकास वातावरण।
## नामस्थान आयात करें
सुनिश्चित करें कि आप Aspose.Slides कार्यात्मकताओं का उपयोग करने के लिए अपने C# कोड में आवश्यक नेमस्पेस आयात करें। अपने कोड की शुरुआत में निम्नलिखित नामस्थान शामिल करें:
```csharp
using System.IO;
using Aspose.Slides.Export;
```
अब, आइए .NET के लिए Aspose.Slides का उपयोग करके ज्यामिति आकार में समग्र ऑब्जेक्ट बनाने में आपका मार्गदर्शन करने के लिए उदाहरण कोड को कई चरणों में विभाजित करें:
## चरण 1: पर्यावरण स्थापित करें
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// यदि यह पहले से मौजूद नहीं है तो निर्देशिका बनाएं।
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
string resultPath = Path.Combine(dataDir, "GeometryShapeCompositeObjects.pptx");
```
इस चरण में, हम अपनी प्रस्तुति के लिए निर्देशिका और परिणाम पथ सेट करके पर्यावरण को आरंभ करते हैं।
## चरण 2: एक प्रेजेंटेशन और ज्यामिति आकार बनाएं
```csharp
using (Presentation pres = new Presentation())
{
    // नया आकार बनाएं
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
यहां, हम एक नई प्रस्तुति बनाते हैं और एक आयत को ज्यामिति आकार के रूप में जोड़ते हैं।
## चरण 3: ज्यामिति पथ परिभाषित करें
```csharp
// पहला ज्यामिति पथ बनाएं
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.MoveTo(0, 0);
geometryPath0.LineTo(shape.Width, 0);
geometryPath0.LineTo(shape.Width, shape.Height / 3);
geometryPath0.LineTo(0, shape.Height / 3);
geometryPath0.CloseFigure();
// दूसरा ज्यामिति पथ बनाएं
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.MoveTo(0, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height);
geometryPath1.LineTo(0, shape.Height);
geometryPath1.CloseFigure();
```
इस चरण में, हम दो ज्यामिति पथों को परिभाषित करते हैं जो हमारी ज्यामिति आकृति का निर्माण करेंगे।
## चरण 4: आकार ज्यामिति सेट करें
```csharp
// आकार ज्यामिति को दो ज्यामिति पथों की संरचना के रूप में सेट करें
shape.SetGeometryPaths(new GeometryPath[] { geometryPath0, geometryPath1 });
```
अब, हम आकृति की ज्यामिति को पहले परिभाषित दो ज्यामिति पथों की संरचना के रूप में सेट करते हैं।
## चरण 5: प्रस्तुति सहेजें
```csharp
// प्रस्तुति सहेजें
pres.Save(resultPath, SaveFormat.Pptx);
}
```
अंत में, हम प्रस्तुतिकरण को समग्र ज्यामिति आकार के साथ सहेजते हैं।
## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके ज्यामिति आकार में मिश्रित ऑब्जेक्ट सफलतापूर्वक बनाए हैं। अपनी प्रस्तुतियों को जीवंत बनाने के लिए विभिन्न आकृतियों और रास्तों के साथ प्रयोग करें।
## पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ Aspose.Slides का उपयोग कर सकता हूँ?
Aspose.Slides जावा और पायथन सहित विभिन्न प्रोग्रामिंग भाषाओं का समर्थन करता है। हालाँकि, यह ट्यूटोरियल C# पर केंद्रित है।
### प्रश्न: मुझे और अधिक उदाहरण और दस्तावेज़ कहां मिल सकते हैं?
 पता लगाएं[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/) व्यापक जानकारी और उदाहरणों के लिए।
### प्रश्न: क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप .NET के लिए Aspose.Slides को आज़मा सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/).
### प्रश्न: मैं समर्थन कैसे प्राप्त कर सकता हूं या प्रश्न कैसे पूछ सकता हूं?
 दौरा करना[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन और सहायता के लिए।
### प्रश्न: क्या मैं अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).