---
title: Aspose.Slides के साथ PowerPoint में शानदार ग्रेडिएंट बनाएं
linktitle: Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में ग्रेडिएंट के साथ आकृतियाँ भरना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ! आकृतियों को ग्रेडिएंट से भरने की चरण-दर-चरण प्रक्रिया जानें। अपना निःशुल्क परीक्षण अभी डाउनलोड करें!
weight: 21
url: /hi/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
अपने दर्शकों का ध्यान आकर्षित करने और बनाए रखने के लिए आकर्षक प्रस्तुति स्लाइड तैयार करना आवश्यक है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for .NET का उपयोग करके ग्रेडिएंट के साथ दीर्घवृत्त आकार भरकर अपनी स्लाइड को बेहतर बनाने की प्रक्रिया से अवगत कराएँगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- C# प्रोग्रामिंग भाषा का मूलभूत ज्ञान।
- आपके मशीन पर Visual Studio स्थापित है.
-  Aspose.Slides for .NET लाइब्रेरी। इसे डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/net/).
- आपकी फ़ाइलों को व्यवस्थित करने के लिए एक परियोजना निर्देशिका.
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, Aspose.Slides के लिए आवश्यक नामस्थान शामिल करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## चरण 1: एक प्रस्तुति बनाएं
Aspose.Slides लाइब्रेरी का उपयोग करके एक नई प्रस्तुति बनाना शुरू करें:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // आपका कोड यहां है...
}
```
## चरण 2: एक दीर्घवृत्त आकार जोड़ें
अपनी प्रस्तुति की पहली स्लाइड में दीर्घवृत्ताकार आकृति डालें:
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
ग्रेडिएंट स्टॉप के रंग और स्थिति निर्धारित करें:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## चरण 5: प्रस्तुति सहेजें
अपनी प्रस्तुति को नए जोड़े गए ग्रेडिएंट-भरे आकार के साथ सहेजें:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
अपने C# कोड में इन चरणों को दोहराएँ, उचित अनुक्रम और पैरामीटर मान सुनिश्चित करें। इसके परिणामस्वरूप एक प्रस्तुति फ़ाइल बनेगी जिसमें ग्रेडिएंट से भरा एक आकर्षक दीर्घवृत्त आकार होगा।
## निष्कर्ष
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं दीर्घवृत्त के अलावा अन्य आकृतियों पर भी ग्रेडिएंट लागू कर सकता हूँ?
उत्तर: निश्चित रूप से! Aspose.Slides for .NET विभिन्न आकृतियों जैसे आयतों, बहुभुजों आदि के लिए ग्रेडिएंट फिलिंग का समर्थन करता है।
### प्रश्न: मैं अतिरिक्त उदाहरण और विस्तृत दस्तावेज कहां पा सकता हूं?
 उत्तर: अन्वेषण करें[.NET दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/net/) विस्तृत मार्गदर्शिका और उदाहरण के लिए.
### प्रश्न: क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हां, आप निःशुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं .NET के लिए Aspose.Slides का समर्थन कैसे प्राप्त कर सकता हूं?
 उत्तर: सहायता प्राप्त करें और समुदाय के साथ जुड़ें।[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### प्रश्न: क्या मैं .NET के लिए Aspose.Slides हेतु अस्थायी लाइसेंस खरीद सकता हूँ?
 उत्तर: निश्चित रूप से, आप एक अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
