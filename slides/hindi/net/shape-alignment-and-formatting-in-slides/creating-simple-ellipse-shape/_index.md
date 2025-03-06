---
title: Aspose.Slides .NET के साथ आसानी से दीर्घवृत्त आकार बनाएं
linktitle: Aspose.Slides के साथ प्रेजेंटेशन स्लाइड में सरल दीर्घवृत्त आकार बनाना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET का उपयोग करके प्रेजेंटेशन स्लाइड्स में शानदार दीर्घवृत्त आकार बनाना सीखें। गतिशील डिज़ाइन के लिए आसान कदम!
weight: 11
url: /hi/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
प्रेजेंटेशन डिज़ाइन की गतिशील दुनिया में, दीर्घवृत्त जैसी आकृतियों को शामिल करने से रचनात्मकता और व्यावसायिकता का स्पर्श जुड़ सकता है। Aspose.Slides for .NET प्रेजेंटेशन फ़ाइलों को प्रोग्रामेटिक रूप से मैनिपुलेट करने के लिए एक शक्तिशाली समाधान प्रदान करता है। यह ट्यूटोरियल आपको Aspose.Slides for .NET का उपयोग करके प्रेजेंटेशन स्लाइड में एक सरल दीर्घवृत्त आकार बनाने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपने .NET के लिए Aspose.Slides लाइब्रेरी स्थापित की है। आप इसे यहाँ से डाउनलोड कर सकते हैं[विज्ञप्ति पृष्ठ](https://releases.aspose.com/slides/net/).
- विकास वातावरण: अपनी मशीन पर .NET विकास वातावरण स्थापित करें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, आवश्यक नामस्थानों को आयात करके प्रारंभ करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
ये नामस्थान प्रस्तुति स्लाइडों और आकृतियों के साथ काम करने के लिए आवश्यक कक्षाएं और विधियां प्रदान करते हैं।
## चरण 1: प्रस्तुति सेट करें
एक नया प्रेजेंटेशन बनाकर और पहली स्लाइड तक पहुँचकर शुरुआत करें। इसे प्राप्त करने के लिए निम्न कोड जोड़ें:
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// प्रस्तुतिकरण क्लास को तत्कालित करें
using (Presentation pres = new Presentation())
{
    // पहली स्लाइड प्राप्त करें
    ISlide sld = pres.Slides[0];
```
यह कोड एक नई प्रस्तुति आरंभ करता है तथा आगे के परिवर्तन के लिए पहली स्लाइड का चयन करता है।
## चरण 2: दीर्घवृत्त आकार जोड़ें
 अब, आइए स्लाइड में एक दीर्घवृत्त आकार जोड़ें`AddAutoShape` तरीका:
```csharp
// दीर्घवृत्त प्रकार का स्वतः आकार जोड़ें
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
कोड की यह पंक्ति निर्देशांक (50, 150) पर 150 इकाई की चौड़ाई और 50 इकाई की ऊंचाई के साथ एक दीर्घवृत्त आकार बनाती है।
## चरण 3: प्रस्तुति सहेजें
अंत में, निम्नलिखित कोड का उपयोग करके संशोधित प्रस्तुति को निर्दिष्ट फ़ाइल नाम के साथ डिस्क पर सहेजें:
```csharp
// PPTX फ़ाइल को डिस्क पर लिखें
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
यह चरण सुनिश्चित करता है कि आपके परिवर्तन बरकरार रहें, और आप परिणामी प्रस्तुति को नए जोड़े गए दीर्घवृत्त आकार के साथ देख सकें।
## निष्कर्ष
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## पूछे जाने वाले प्रश्न
### क्या मैं दीर्घवृत्त आकार को और अधिक अनुकूलित कर सकता हूँ?
हां, आप अपनी विशिष्ट डिज़ाइन आवश्यकताओं को पूरा करने के लिए दीर्घवृत्त आकार के विभिन्न गुणों, जैसे रंग, आकार और स्थिति को संशोधित कर सकते हैं।
### क्या Aspose.Slides नवीनतम .NET फ्रेमवर्क के साथ संगत है?
हां, नवीनतम .NET फ्रेमवर्क के साथ संगतता सुनिश्चित करने के लिए Aspose.Slides को नियमित रूप से अपडेट किया जाता है।
### मैं Aspose.Slides के लिए और अधिक ट्यूटोरियल और उदाहरण कहां पा सकता हूं?
 दौरा करना[प्रलेखन](https://reference.aspose.com/slides/net/) विस्तृत मार्गदर्शिका और उदाहरण के लिए.
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 का पीछा करो[अस्थायी लाइसेंस लिंक](https://purchase.aspose.com/temporary-license/) परीक्षण प्रयोजनों के लिए अस्थायी लाइसेंस का अनुरोध करना।
### क्या आपको सहायता की आवश्यकता है या आपके पास विशिष्ट प्रश्न हैं?
 दौरा करना[Aspose.Slides समर्थन मंच](https://forum.aspose.com/c/slides/11) समुदाय और विशेषज्ञों से सहायता प्राप्त करना।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
