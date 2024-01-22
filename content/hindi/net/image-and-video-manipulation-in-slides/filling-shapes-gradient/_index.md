---
title: Aspose.Slides के साथ PowerPoint में आश्चर्यजनक ग्रेजुएट बनाएं
linktitle: Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में ग्रेडिएंट के साथ आकृतियाँ भरना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides के साथ अपनी प्रस्तुतियों को बेहतर बनाएं! आकृतियों को ग्रेडिएंट से भरने की चरण-दर-चरण प्रक्रिया सीखें। अभी अपने मुफ़्त ट्रायल को डाउनलोड करें!
type: docs
weight: 21
url: /hi/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---
## परिचय
अपने दर्शकों का ध्यान खींचने और बनाए रखने के लिए दृश्यात्मक रूप से मनोरम प्रस्तुति स्लाइड बनाना आवश्यक है। इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Slides का उपयोग करके एक ग्रेडिएंट के साथ एक दीर्घवृत्त आकार भरकर अपनी स्लाइड्स को बढ़ाने की प्रक्रिया के बारे में बताएंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपकी मशीन पर विज़ुअल स्टूडियो स्थापित है।
-  .NET लाइब्रेरी के लिए Aspose.Slides। इसे डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/net/).
- आपकी फ़ाइलों को व्यवस्थित करने के लिए एक प्रोजेक्ट निर्देशिका।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, Aspose.Slides के लिए आवश्यक नामस्थान शामिल करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## चरण 1: एक प्रेजेंटेशन बनाएं
Aspose.Slides लाइब्रेरी का उपयोग करके एक नई प्रस्तुति बनाकर शुरुआत करें:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // आपका कोड यहां जाता है...
}
```
## चरण 2: एक दीर्घवृत्त आकार जोड़ें
अपनी प्रस्तुति की पहली स्लाइड में एक दीर्घवृत्त आकार डालें:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## चरण 3: ग्रेडिएंट फ़ॉर्मेटिंग लागू करें
निर्दिष्ट करें कि आकृति को ग्रेडिएंट से भरा जाना चाहिए और ग्रेडिएंट विशेषताओं को परिभाषित करें:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## चरण 4: ग्रेडिएंट स्टॉप जोड़ें
ग्रेडिएंट स्टॉप के रंग और स्थिति को परिभाषित करें:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## चरण 5: प्रस्तुति सहेजें
अपनी प्रस्तुति को नए जोड़े गए ग्रेडिएंट-भरे आकार के साथ सहेजें:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
उचित अनुक्रम और पैरामीटर मान सुनिश्चित करते हुए, अपने C# कोड में इन चरणों को दोहराएं। इसके परिणामस्वरूप एक प्रेजेंटेशन फ़ाइल तैयार होगी जिसमें एक ग्रेडिएंट से भरा हुआ एक आकर्षक दीर्घवृत्त आकार होगा।
## निष्कर्ष
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं दीर्घवृत्त के अलावा अन्य आकृतियों पर ग्रेडिएंट लागू कर सकता हूँ?
उत्तर: निश्चित रूप से! .NET के लिए Aspose.Slides विभिन्न आकृतियों जैसे आयत, बहुभुज और अन्य के लिए ग्रेडिएंट फिलिंग का समर्थन करता है।
### प्रश्न: मुझे अतिरिक्त उदाहरण और विस्तृत दस्तावेज कहां मिल सकते हैं?
 ए: अन्वेषण करें[.NET दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/net/) व्यापक मार्गदर्शिकाओं और उदाहरणों के लिए।
### प्रश्न: क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप निःशुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं .NET के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 उत्तर: सहायता लें और समुदाय के साथ जुड़ें[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11).
### प्रश्न: क्या मैं .NET के लिए Aspose.Slides के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?
 उत्तर: निश्चित रूप से, आप एक अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).