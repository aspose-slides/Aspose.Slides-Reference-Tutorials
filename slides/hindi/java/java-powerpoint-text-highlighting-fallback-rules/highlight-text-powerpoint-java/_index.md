---
title: जावा के साथ पावरपॉइंट में टेक्स्ट हाइलाइट करें
linktitle: जावा के साथ पावरपॉइंट में टेक्स्ट हाइलाइट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint में टेक्स्ट हाइलाइट करना सीखें। हमारे विस्तृत गाइड के साथ आसानी से प्रेजेंटेशन को स्वचालित और बेहतर बनाएँ।
weight: 10
url: /hi/java/java-powerpoint-text-highlighting-fallback-rules/highlight-text-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
आज के डिजिटल युग में, जहाँ व्यावसायिक प्रस्तुतियों और शैक्षिक सामग्रियों में दृश्य संचार एक महत्वपूर्ण भूमिका निभाता है, PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से हेरफेर करने और बढ़ाने की क्षमता होना एक महत्वपूर्ण लाभ है। Aspose.Slides for Java डेवलपर्स को Java प्रोग्रामिंग भाषा का उपयोग करके PowerPoint स्लाइड्स को सहजता से एकीकृत और हेरफेर करने के लिए उपकरणों के एक मजबूत सेट के साथ सशक्त बनाता है। चाहे आप प्रस्तुतियों के निर्माण को स्वचालित कर रहे हों, मौजूदा लोगों को संशोधित कर रहे हों, या स्लाइड्स से डेटा निकाल रहे हों, Aspose.Slides for Java इन कार्यों को कुशलतापूर्वक पूरा करने के लिए आवश्यक कार्यक्षमताएँ प्रदान करता है।
## आवश्यक शर्तें
PowerPoint प्रस्तुतियों में टेक्स्ट हाइलाइट करने के लिए Aspose.Slides for Java का उपयोग करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ सेट अप हैं:
-  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर जावा इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं[जावा SE डेवलपमेंट किट डाउनलोड](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides for Java लाइब्रेरी: Aspose.Slides for Java लाइब्रेरी को यहाँ से प्राप्त करें[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/)अपने विकास परिवेश में लाइब्रेरी स्थापित करने के लिए स्थापना निर्देशों का पालन करें।
- एकीकृत विकास वातावरण (IDE): अपनी पसंद का कोई IDE चुनें जो जावा विकास का समर्थन करता हो, जैसे कि IntelliJ IDEA, Eclipse, या NetBeans.

## पैकेज आयात करें
Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में टेक्स्ट हाइलाइट करना आरंभ करने के लिए, आपको आवश्यक पैकेज आयात करने होंगे:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: प्रस्तुति लोड करें
सबसे पहले, पावरपॉइंट प्रेजेंटेशन को उस स्थान पर लोड करें जहां आप टेक्स्ट हाइलाइट करना चाहते हैं।
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SomePresentation.pptx");
```
 प्रतिस्थापित करें`"Your Document Directory"` वास्तविक निर्देशिका पथ के साथ जहाँ आपका पावरपॉइंट प्रस्तुतिकरण (`SomePresentation.pptx`) स्थित है।
## चरण 2: टेक्स्ट हाइलाइट करें
स्लाइड पर आकृति के भीतर विशिष्ट टेक्स्ट को हाइलाइट करें। यहाँ, हम "title" और "to" शब्द की घटनाओं को अलग-अलग रंगों से हाइलाइट करते हैं।
```java
// 'title' शब्द को हल्के नीले रंग से हाइलाइट करना
((AutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0))
    .getTextFrame().highlightText("title", new Color(PresetColor.LightBlue));
// 'to' शब्द को बैंगनी रंग से हाइलाइट करें, केवल पूरे शब्द को ही हाइलाइट करें
TextHighlightingOptions options = new TextHighlightingOptions();
options.setWholeWordsOnly(true);
((AutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0))
    .getTextFrame().highlightText("to", new Color(PresetColor.Violet), options);
```
यह कोड स्निपेट दर्शाता है कि किसी निर्दिष्ट आकार के भीतर टेक्स्ट को कैसे हाइलाइट किया जाए (`AutoShape`) पहली स्लाइड पर (`get_Item(0)`).
## चरण 3: संशोधित प्रस्तुति को सहेजें
संशोधित प्रस्तुति को हाइलाइट किए गए पाठ के साथ एक नई फ़ाइल में सहेजें।
```java
presentation.save(dataDir + "SomePresentation-out.pptx", SaveFormat.Pptx);
```
 प्रतिस्थापित करें`"SomePresentation-out.pptx"` अपनी आउटपुट फ़ाइल के लिए वांछित नाम के साथ।

## निष्कर्ष
निष्कर्ष में, जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से हेरफेर करने का कार्य सरल हो जाता है। इसके व्यापक API के साथ, डेवलपर्स उत्पादकता बढ़ाने के लिए कुशलतापूर्वक टेक्स्ट हाइलाइट कर सकते हैं, स्लाइड्स को कस्टमाइज़ कर सकते हैं और प्रस्तुति कार्यों को स्वचालित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक जावा एपीआई है जो डेवलपर्स को माइक्रोसॉफ्ट ऑफिस या पावरपॉइंट इंस्टॉलेशन की आवश्यकता के बिना पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और हेरफेर करने में सक्षम बनाता है।
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 आप दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
### मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java प्रस्तुतियों को किस प्रारूप में सहेज सकता है?
Aspose.Slides for Java, PPTX, PPT, PDF, आदि सहित विभिन्न प्रारूपों में प्रस्तुतियों को सहेजने का समर्थन करता है।
### क्या Aspose.Slides for Java, Java SE Development Kit के साथ संगत है?
हां, Aspose.Slides for Java, Java SE डेवलपमेंट किट के साथ संगत है।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
