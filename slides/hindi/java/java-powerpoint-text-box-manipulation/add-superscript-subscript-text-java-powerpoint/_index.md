---
title: जावा पावरपॉइंट में सुपरस्क्रिप्ट और सबस्क्रिप्ट टेक्स्ट जोड़ें
linktitle: जावा पावरपॉइंट में सुपरस्क्रिप्ट और सबस्क्रिप्ट टेक्स्ट जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java PowerPoint प्रस्तुतियों में सुपरस्क्रिप्ट और सबस्क्रिप्ट टेक्स्ट जोड़ना सीखें। आपकी स्लाइड्स को बेहतर बनाने के लिए बिल्कुल सही।
weight: 13
url: /hi/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
आकर्षक और जानकारीपूर्ण पावरपॉइंट प्रेजेंटेशन बनाने के लिए अक्सर सुपरस्क्रिप्ट और सबस्क्रिप्ट टेक्स्ट जैसी फ़ॉर्मेटिंग सुविधाओं का उपयोग करने की आवश्यकता होती है। यह ट्यूटोरियल आपको Aspose.Slides for Java का उपयोग करके अपने Java PowerPoint प्रेजेंटेशन में सुपरस्क्रिप्ट और सबस्क्रिप्ट टेक्स्ट को शामिल करने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- जावा विकास के लिए एक एकीकृत विकास वातावरण (आईडीई) जैसे कि इंटेलीज आईडिया या एक्लिप्स की स्थापना।
- जावा प्रोग्रामिंग और पावरपॉइंट प्रस्तुतियों से बुनियादी परिचितता।

## पैकेज आयात करें
सबसे पहले, Aspose.Slides for Java से आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
```
## चरण 1: प्रस्तुति सेट करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## चरण 2: स्लाइड तक पहुंचें
```java
// पहली स्लाइड प्राप्त करें
ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 3: एक टेक्स्ट बॉक्स बनाएं
```java
// टेक्स्ट बॉक्स के रूप में कार्य करने के लिए एक ऑटोशेप बनाएँ
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## चरण 4: सुपरस्क्रिप्ट टेक्स्ट जोड़ें
```java
// मुख्य पाठ के लिए एक पैराग्राफ़ बनाएँ
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// सुपरस्क्रिप्ट टेक्स्ट के लिए एक भाग बनाएँ
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // सुपरस्क्रिप्ट के लिए एस्केपमेंट सेट करें
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//मुख्य पैराग्राफ़ को सुपरस्क्रिप्ट के साथ टेक्स्ट बॉक्स में जोड़ें
textFrame.getParagraphs().add(mainParagraph);
```
## चरण 5: सबस्क्रिप्ट टेक्स्ट जोड़ें
```java
// सबस्क्रिप्ट टेक्स्ट के लिए एक और पैराग्राफ़ बनाएँ
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// सबस्क्रिप्ट टेक्स्ट के लिए एक भाग बनाएँ
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // सबस्क्रिप्ट के लिए एस्केपमेंट सेट करें
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// सबस्क्रिप्ट पैराग्राफ़ को टेक्स्ट बॉक्स में जोड़ें
textFrame.getParagraphs().add(subscriptParagraph);
```
## चरण 6: प्रेजेंटेशन सहेजें
```java
// प्रस्तुति सहेजें
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने Aspose.Slides for Java का उपयोग करके अपने Java PowerPoint प्रेजेंटेशन को सुपरस्क्रिप्ट और सबस्क्रिप्ट टेक्स्ट के साथ बेहतर बनाने का तरीका खोजा। इन चरणों का पालन करके, आप अधिक आकर्षक और जानकारीपूर्ण स्लाइड बना सकते हैं जो आपकी सामग्री को प्रभावी ढंग से संप्रेषित करती हैं।

## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक मजबूत लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है।
### मैं Aspose.Slides for Java पर अधिक दस्तावेज़ कहां पा सकता हूं?
 विस्तृत दस्तावेज यहां पाया जा सकता है[यहाँ](https://reference.aspose.com/slides/java/).
### मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या मैं Java के लिए Aspose.Slides निःशुल्क आज़मा सकता हूँ?
 हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए समर्थन कहां से प्राप्त कर सकता हूं?
 समर्थन और चर्चा के लिए, यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
