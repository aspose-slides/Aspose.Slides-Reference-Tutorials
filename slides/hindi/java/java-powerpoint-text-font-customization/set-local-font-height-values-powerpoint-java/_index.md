---
title: जावा का उपयोग करके PowerPoint में स्थानीय फ़ॉन्ट ऊंचाई मान सेट करें
linktitle: जावा का उपयोग करके PowerPoint में स्थानीय फ़ॉन्ट ऊंचाई मान सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ Java का उपयोग करके PowerPoint प्रस्तुतियों में फ़ॉन्ट की ऊँचाई समायोजित करना सीखें। अपनी स्लाइड्स में टेक्स्ट फ़ॉर्मेटिंग को आसानी से बढ़ाएँ।
weight: 17
url: /hi/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में विभिन्न स्तरों पर फ़ॉन्ट की ऊँचाई में कैसे बदलाव किया जाए। आकर्षक और संरचित प्रस्तुतियाँ बनाने के लिए फ़ॉन्ट आकार को नियंत्रित करना महत्वपूर्ण है। हम विभिन्न टेक्स्ट तत्वों के लिए फ़ॉन्ट ऊँचाई सेट करने के तरीके को दर्शाने के लिए चरण-दर-चरण उदाहरणों के माध्यम से चलेंगे।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है
-  Aspose.Slides for Java लाइब्रेरी। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- जावा प्रोग्रामिंग और पावरपॉइंट प्रस्तुतियों की बुनियादी समझ
## पैकेज आयात करें
अपनी जावा फ़ाइल में आवश्यक Aspose.Slides पैकेज शामिल करना सुनिश्चित करें:
```java
import com.aspose.slides.*;
```
## चरण 1: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
सबसे पहले, एक नया पावरपॉइंट प्रेजेंटेशन ऑब्जेक्ट बनाएं:
```java
Presentation pres = new Presentation();
```
## चरण 2: एक आकृति और टेक्स्ट फ़्रेम जोड़ें
पहली स्लाइड में टेक्स्ट फ़्रेम के साथ एक स्वचालित आकृति जोड़ें:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## चरण 3: पाठ भाग बनाएँ
अलग-अलग फ़ॉन्ट ऊंचाइयों के साथ पाठ भाग परिभाषित करें:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## चरण 4: फ़ॉन्ट की ऊँचाई निर्धारित करें
विभिन्न स्तरों पर फ़ॉन्ट की ऊँचाई निर्धारित करें:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## चरण 5: प्रस्तुति सहेजें
संशोधित प्रस्तुति को फ़ाइल में सहेजें:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में दिखाया गया है कि Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड्स में फ़ॉन्ट की ऊँचाई को प्रोग्रामेटिक रूप से कैसे समायोजित किया जाए। विभिन्न स्तरों (प्रस्तुति-व्यापी, पैराग्राफ़ और भाग) पर फ़ॉन्ट आकारों में हेरफेर करके, आप अपनी प्रस्तुतियों में टेक्स्ट फ़ॉर्मेटिंग पर सटीक नियंत्रण प्राप्त कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, पावरपॉइंट प्रस्तुतियों को प्रोग्रामेटिक रूप से संचालित करने के लिए एक शक्तिशाली API है।
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 आप दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
### क्या मैं खरीदने से पहले Aspose.Slides for Java आज़मा सकता हूँ?
 हां, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Java के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 सहायता के लिए, यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### मैं Aspose.Slides for Java के लिए लाइसेंस कहां से खरीद सकता हूं?
 आप लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
