---
title: PowerPoint में सारांश ज़ूम बनाएँ
linktitle: PowerPoint में सारांश ज़ूम बनाएँ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: इस व्यापक चरण-दर-चरण ट्यूटोरियल के साथ Java के लिए Aspose.Slides का उपयोग करके PowerPoint में सारांश ज़ूम बनाना सीखें।
weight: 16
url: /hi/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint में सारांश ज़ूम बनाएँ

## परिचय
Aspose.Slides for Java का उपयोग करके PowerPoint में सारांश ज़ूम बनाने पर हमारे व्यापक ट्यूटोरियल में आपका स्वागत है। यदि आप अपनी प्रस्तुतियों में एक गतिशील और इंटरैक्टिव तत्व जोड़ना चाहते हैं, तो सारांश ज़ूम एक शानदार सुविधा है। यह आपको एक ऐसी एकल स्लाइड बनाने की अनुमति देता है जो आपकी प्रस्तुति के विभिन्न अनुभागों में ज़ूम कर सकती है, जो आपके दर्शकों के लिए अधिक आकर्षक और नेविगेट करने योग्य अनुभव प्रदान करती है।
इस चरण-दर-चरण मार्गदर्शिका में, हम आपको संपूर्ण प्रक्रिया से परिचित कराएँगे, जिसमें आपके विकास परिवेश को सेट करने से लेकर सारांश ज़ूम फ़्रेम बनाने और उसे अनुकूलित करने तक शामिल है। चाहे आप एक अनुभवी जावा डेवलपर हों या अभी शुरुआत कर रहे हों, आपको यह मार्गदर्शिका अनुसरण करने में आसान लगेगी और इसमें बहुमूल्य जानकारी भरी हुई है।
## आवश्यक शर्तें
कोड में गोता लगाने से पहले, आइए सुनिश्चित करें कि आपके पास आरंभ करने के लिए आवश्यक सभी चीजें हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपकी मशीन पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: लाइब्रेरी को यहाँ से डाउनलोड करें[Aspose रिलीज़ पेज](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): अधिक निर्बाध विकास अनुभव के लिए IntelliJ IDEA, Eclipse, या NetBeans जैसे IDE का उपयोग करें।
4. जावा का बुनियादी ज्ञान: जावा प्रोग्रामिंग अवधारणाओं से परिचित होने से आपको इस गाइड में दिए गए चरणों को समझने और कार्यान्वित करने में मदद मिलेगी।
## पैकेज आयात करें
शुरू करने से पहले, आपको आवश्यक पैकेज आयात करने होंगे। सुनिश्चित करें कि आपने अपनी परियोजना निर्भरताओं में Aspose.Slides for Java को शामिल किया है।
```java
import com.aspose.slides.*;

import java.awt.*;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
सबसे पहले, सुनिश्चित करें कि आपका विकास वातावरण सही तरीके से सेट किया गया है। अपने प्रोजेक्ट को कॉन्फ़िगर करने के लिए इन चरणों का पालन करें:
### एक नया प्रोजेक्ट बनाएं
1. अपना आईडीई खोलें.
2. एक नया जावा प्रोजेक्ट बनाएं.
3.  अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides for Java लाइब्रेरी जोड़ें। आप JAR फ़ाइल को यहाँ से डाउनलोड कर सकते हैं।[Aspose रिलीज़ पेज](https://releases.aspose.com/slides/java/) और इसे अपने प्रोजेक्ट में शामिल करें.
### प्रस्तुति आरंभ करें
इसके बाद, एक नया प्रेजेंटेशन ऑब्जेक्ट आरंभ करें जहां आप अपनी स्लाइडें और अनुभाग जोड़ेंगे।
```java
Presentation pres = new Presentation();
```
## चरण 2: स्लाइड और अनुभाग जोड़ें
इस चरण में, हम प्रस्तुति में स्लाइड जोड़ेंगे और उन्हें अनुभागों में व्यवस्थित करेंगे। सारांश ज़ूम बनाने के लिए यह संगठन महत्वपूर्ण है।
### नई स्लाइड और अनुभाग जोड़ें
1. खाली स्लाइड जोड़ें: प्रस्तुति में एक नई स्लाइड जोड़ें।
2. स्लाइड पृष्ठभूमि अनुकूलित करें: स्लाइड पृष्ठभूमि के लिए एक ठोस भरण रंग सेट करें।
3. अनुभाग जोड़ें: स्लाइड को अनुभाग में समूहित करें.
इसे प्राप्त करने के लिए कोड इस प्रकार है:
```java
// पहली स्लाइड जोड़ें
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// पहला अनुभाग जोड़ें
pres.getSections().addSection("Section 1", slide);
```
### अतिरिक्त अनुभागों के लिए दोहराएँ
अधिक स्लाइड और अनुभाग जोड़ने के लिए प्रक्रिया को दोहराएं:
```java
// दूसरी स्लाइड और अनुभाग जोड़ें
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 2", slide);
// तीसरी स्लाइड और अनुभाग जोड़ें
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 3", slide);
// चौथी स्लाइड और अनुभाग जोड़ें
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 4", slide);
```
## चरण 3: सारांश ज़ूम फ़्रेम बनाएँ
अब, हम पहली स्लाइड पर एक सारांश ज़ूम फ़्रेम बनाएंगे। यह फ़्रेम एक इंटरैक्टिव तत्व के रूप में कार्य करेगा जो उपयोगकर्ताओं को विभिन्न अनुभागों में ज़ूम करने की अनुमति देता है।

1. प्रथम स्लाइड का पता लगाएं: प्रथम स्लाइड को पुनः प्राप्त करें जहां आप सारांश ज़ूम फ्रेम जोड़ेंगे।
2.  सारांश ज़ूम फ़्रेम जोड़ें: का उपयोग करें`addSummaryZoomFrame` फ्रेम जोड़ने की विधि.
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## चरण 4: प्रस्तुति सहेजें
अंत में, प्रेजेंटेशन को अपनी इच्छित जगह पर सेव करें। यह चरण सुनिश्चित करता है कि आपके सभी परिवर्तन एक फ़ाइल में लिखे गए हैं।
### फ़ाइल सहेजें
1. आउटपुट पथ परिभाषित करें: वह पथ निर्दिष्ट करें जहां प्रस्तुति सहेजी जाएगी।
2.  प्रस्तुति सहेजें: का उपयोग करें`save` फ़ाइल को PPTX प्रारूप में सहेजने की विधि।
```java
String resultPath = "Your Output Directory" + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### प्रेजेंटेशन ऑब्जेक्ट का निपटान करें
प्रस्तुति ऑब्जेक्ट का निपटान करें ताकि उसके द्वारा उपयोग किए जा रहे किसी भी संसाधन को मुक्त किया जा सके:
```java
if (pres != null) pres.dispose();
```
## निष्कर्ष
 बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint में सारांश ज़ूम सफलतापूर्वक बनाया है। यह सुविधा आपकी प्रस्तुतियों को अधिक इंटरैक्टिव और आकर्षक बनाकर उन्हें बेहतर बनाती है। इस गाइड का पालन करके, अब आपके पास अपने प्रोजेक्ट में इस सुविधा को लागू करने का कौशल है।[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/)अधिक उन्नत सुविधाओं और अनुकूलन विकल्पों के लिए.
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को जावा का उपयोग करके प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और हेरफेर करने की अनुमति देती है।
### क्या मैं PowerPoint में अन्य प्रकार की सामग्री बनाने के लिए Aspose.Slides for Java का उपयोग कर सकता हूँ?
हां, Java के लिए Aspose.Slides कई प्रकार की सुविधाओं का समर्थन करता है, जिसमें स्लाइड बनाना, आकृतियां, चार्ट, तालिकाएं जोड़ना और बहुत कुछ शामिल है।
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
हां, आप जावा के लिए Aspose.Slides का निःशुल्क परीक्षण डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[Aspose खरीद पृष्ठ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides for Java के लिए और अधिक उदाहरण और समर्थन कहां पा सकता हूं?
 आप अधिक उदाहरण पा सकते हैं और सहायता प्राप्त कर सकते हैं[Aspose.Slides समर्थन मंच](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
