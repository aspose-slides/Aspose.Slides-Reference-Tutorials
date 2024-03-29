---
title: Aspose.Slides .NET के साथ आसानी से दीर्घवृत्त आकार बनाएं
linktitle: Aspose.Slides के साथ प्रस्तुति स्लाइड में सरल दीर्घवृत्त आकार बनाना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में आश्चर्यजनक दीर्घवृत्त आकार बनाने का तरीका जानें। गतिशील डिज़ाइन के लिए आसान चरण!
type: docs
weight: 11
url: /hi/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---
## परिचय
प्रेजेंटेशन डिज़ाइन की गतिशील दुनिया में, दीर्घवृत्त जैसी आकृतियों को शामिल करने से रचनात्मकता और व्यावसायिकता का स्पर्श जोड़ा जा सकता है। .NET के लिए Aspose.Slides प्रोग्रामेटिक रूप से प्रेजेंटेशन फ़ाइलों में हेरफेर करने के लिए एक शक्तिशाली समाधान प्रदान करता है। यह ट्यूटोरियल आपको .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में एक सरल दीर्घवृत्त आकार बनाने की प्रक्रिया में मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपने .NET के लिए Aspose.Slides लाइब्रेरी स्थापित की है। आप इसे यहां से डाउनलोड कर सकते हैं[पृष्ठ जारी करता है](https://releases.aspose.com/slides/net/).
- विकास परिवेश: अपनी मशीन पर एक .NET विकास परिवेश स्थापित करें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
ये नामस्थान प्रस्तुति स्लाइड और आकृतियों के साथ काम करने के लिए आवश्यक आवश्यक कक्षाएं और विधियाँ प्रदान करते हैं।
## चरण 1: प्रेजेंटेशन सेट करें
एक नई प्रस्तुति बनाकर और पहली स्लाइड तक पहुंच कर शुरुआत करें। इसे प्राप्त करने के लिए निम्नलिखित कोड जोड़ें:
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "Your Document Directory";
// यदि यह पहले से मौजूद नहीं है तो निर्देशिका बनाएं।
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// त्वरित प्रस्तुति वर्ग
using (Presentation pres = new Presentation())
{
    // पहली स्लाइड प्राप्त करें
    ISlide sld = pres.Slides[0];
```
यह कोड एक नई प्रस्तुति को आरंभ करता है और आगे के हेरफेर के लिए पहली स्लाइड का चयन करता है।
## चरण 2: दीर्घवृत्त आकार जोड़ें
अब, आइए इसका उपयोग करके स्लाइड में एक दीर्घवृत्त आकार जोड़ें`AddAutoShape` तरीका:
```csharp
// दीर्घवृत्त प्रकार का ऑटोशेप जोड़ें
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
कोड की यह पंक्ति निर्देशांक (50, 150) पर 150 इकाइयों की चौड़ाई और 50 इकाइयों की ऊंचाई के साथ एक दीर्घवृत्त आकार बनाती है।
## चरण 3: प्रस्तुति सहेजें
अंत में, निम्नलिखित कोड का उपयोग करके संशोधित प्रस्तुति को एक निर्दिष्ट फ़ाइल नाम के साथ डिस्क पर सहेजें:
```csharp
// पीपीटीएक्स फ़ाइल को डिस्क पर लिखें
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
यह चरण सुनिश्चित करता है कि आपके परिवर्तन कायम हैं, और आप परिणामी प्रस्तुति को नए जोड़े गए दीर्घवृत्त आकार के साथ देख सकते हैं।
## निष्कर्ष
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## पूछे जाने वाले प्रश्न
### क्या मैं दीर्घवृत्त आकार को और अधिक अनुकूलित कर सकता हूँ?
हां, आप अपनी विशिष्ट डिज़ाइन आवश्यकताओं को पूरा करने के लिए दीर्घवृत्त आकार के विभिन्न गुणों, जैसे रंग, आकार और स्थिति को संशोधित कर सकते हैं।
### क्या Aspose.Slides नवीनतम .NET फ्रेमवर्क के साथ संगत है?
हां, नवीनतम .NET फ्रेमवर्क के साथ अनुकूलता सुनिश्चित करने के लिए Aspose.Slides को नियमित रूप से अपडेट किया जाता है।
### मुझे Aspose.Slides के लिए और अधिक ट्यूटोरियल और उदाहरण कहां मिल सकते हैं?
 दौरा करना[प्रलेखन](https://reference.aspose.com/slides/net/) व्यापक मार्गदर्शिकाओं और उदाहरणों के लिए।
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 का पीछा करो[अस्थायी लाइसेंस लिंक](https://purchase.aspose.com/temporary-license/) परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस का अनुरोध करना।
### सहायता की आवश्यकता है या आपके पास विशिष्ट प्रश्न हैं?
 दौरा करना[Aspose.Slides समर्थन मंच](https://forum.aspose.com/c/slides/11) समुदाय और विशेषज्ञों से सहायता प्राप्त करने के लिए।