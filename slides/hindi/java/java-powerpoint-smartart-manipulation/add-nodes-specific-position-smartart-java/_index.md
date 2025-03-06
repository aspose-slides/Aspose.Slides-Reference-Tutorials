---
title: जावा का उपयोग करके स्मार्टआर्ट में विशिष्ट स्थान पर नोड्स जोड़ें
linktitle: जावा का उपयोग करके स्मार्टआर्ट में विशिष्ट स्थान पर नोड्स जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ Java का उपयोग करके SmartArt में विशिष्ट स्थानों पर नोड्स जोड़ने का तरीका जानें। आसानी से गतिशील प्रस्तुतियाँ बनाएँ।
weight: 16
url: /hi/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, हम आपको Aspose.Slides के साथ Java का उपयोग करके SmartArt में विशिष्ट स्थानों पर नोड्स जोड़ने की प्रक्रिया के बारे में बताएंगे। SmartArt, PowerPoint में एक ऐसी सुविधा है जो आपको आकर्षक आरेख और चार्ट बनाने की अनुमति देती है।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2.  Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
3. जावा प्रोग्रामिंग भाषा का बुनियादी ज्ञान।

## पैकेज आयात करें
सबसे पहले, आइए अपने जावा कोड में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
import java.io.File;
```
## चरण 1: एक प्रेजेंटेशन इंस्टेंस बनाएं
प्रेजेंटेशन क्लास का एक उदाहरण बनाकर आरंभ करें:
```java
Presentation pres = new Presentation();
```
## चरण 2: प्रेजेंटेशन स्लाइड तक पहुंचें
उस स्लाइड तक पहुंचें जहां आप स्मार्टआर्ट जोड़ना चाहते हैं:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## चरण 3: स्मार्टआर्ट आकार जोड़ें
स्लाइड में स्मार्टआर्ट आकृति जोड़ें:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## चरण 4: स्मार्टआर्ट नोड तक पहुंचें
इच्छित इंडेक्स पर स्मार्टआर्ट नोड तक पहुंचें:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## चरण 5: विशिष्ट स्थान पर चाइल्ड नोड जोड़ें
पैरेंट नोड में किसी विशिष्ट स्थान पर नया चाइल्ड नोड जोड़ें:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## चरण 6: नोड में टेक्स्ट जोड़ें
नये जोड़े गए नोड के लिए पाठ सेट करें:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## चरण 7: प्रेजेंटेशन सहेजें
संशोधित प्रस्तुति सहेजें:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा कि Aspose.Slides के साथ Java का उपयोग करके SmartArt में विशिष्ट स्थानों पर नोड्स कैसे जोड़ें। इन चरणों का पालन करके, आप गतिशील प्रस्तुतियाँ बनाने के लिए SmartArt आकृतियों को प्रोग्रामेटिक रूप से हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं एक साथ कई नोड्स जोड़ सकता हूँ?
हां, आप वांछित स्थानों पर पुनरावृत्ति करके प्रोग्रामेटिक रूप से कई नोड्स जोड़ सकते हैं।
### क्या Aspose.Slides PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides विभिन्न PowerPoint प्रारूपों का समर्थन करता है, जो अधिकांश संस्करणों के साथ संगतता सुनिश्चित करता है।
### क्या मैं स्मार्टआर्ट नोड्स के स्वरूप को अनुकूलित कर सकता हूँ?
हां, आप नोड्स के आकार, रंग और शैली सहित उनके स्वरूप को अनुकूलित कर सकते हैं।
### क्या Aspose.Slides अन्य प्रोग्रामिंग भाषाओं के लिए समर्थन प्रदान करता है?
हां, Aspose.Slides .NET और पायथन सहित कई प्रोग्रामिंग भाषाओं के लिए लाइब्रेरी प्रदान करता है।
### क्या Aspose.Slides के लिए कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
