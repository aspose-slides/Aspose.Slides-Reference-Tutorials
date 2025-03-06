---
title: जावा पावरपॉइंट में टेक्स्ट फ़्रेम का ऑटोफ़िट सेट करें
linktitle: जावा पावरपॉइंट में टेक्स्ट फ़्रेम का ऑटोफ़िट सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java PowerPoint में टेक्स्ट फ़्रेम के लिए ऑटोफ़िट सेट करना सीखें। आसानी से गतिशील प्रस्तुतियाँ बनाएँ।
weight: 14
url: /hi/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पावरपॉइंट में टेक्स्ट फ़्रेम का ऑटोफ़िट सेट करें

## परिचय
जावा एप्लिकेशन डेवलपमेंट में, प्रोग्रामेटिक रूप से गतिशील और आकर्षक पावरपॉइंट प्रेजेंटेशन बनाना एक सामान्य आवश्यकता है। जावा के लिए Aspose.Slides इसे आसानी से प्राप्त करने के लिए API का एक शक्तिशाली सेट प्रदान करता है। एक आवश्यक विशेषता टेक्स्ट फ़्रेम के लिए ऑटोफ़िट सेट करना है, यह सुनिश्चित करना कि टेक्स्ट मैन्युअल समायोजन के बिना आकृतियों के भीतर बड़े करीने से समायोजित हो। यह ट्यूटोरियल आपको प्रक्रिया के माध्यम से चरण-दर-चरण मार्गदर्शन करेगा, पावरपॉइंट स्लाइड में टेक्स्ट फ़िटिंग को स्वचालित करने के लिए जावा के लिए Aspose.Slides का लाभ उठाएगा।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है
- Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके Java प्रोजेक्ट में संदर्भित की गई
- एकीकृत विकास वातावरण (IDE) जैसे कि IntelliJ IDEA या Eclipse
### पैकेज आयात करें
सबसे पहले, अपने जावा प्रोजेक्ट में आवश्यक Aspose.Slides क्लासेस को आयात करना सुनिश्चित करें:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: एक नई प्रस्तुति बनाएँ
एक नया पावरपॉइंट प्रेजेंटेशन इंस्टैंस बनाकर शुरुआत करें, जहां आप स्लाइड और आकृतियां जोड़ेंगे।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
```
## चरण 2: आकृतियाँ जोड़ने के लिए स्लाइड तक पहुँचें
प्रस्तुति की पहली स्लाइड तक पहुँचें जहाँ आप ऑटोफिट टेक्स्ट के साथ एक आकृति जोड़ना चाहते हैं।
```java
// पहली स्लाइड पर पहुँचें
ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 3: एक ऑटोशेप (आयताकार) जोड़ें
स्लाइड में विशिष्ट निर्देशांकों और आयामों पर एक ऑटोशेप (आयत) जोड़ें।
```java
// आयत प्रकार का एक ऑटोशेप जोड़ें
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## चरण 4: आयत में टेक्स्टफ़्रेम जोड़ें
आयताकार आकार में एक टेक्स्ट फ़्रेम जोड़ें.
```java
// आयत में टेक्स्टफ़्रेम जोड़ें
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## चरण 5: टेक्स्ट फ़्रेम के लिए ऑटोफ़िट सेट करें
आकृति के आकार के आधार पर पाठ को समायोजित करने के लिए पाठ फ़्रेम के लिए ऑटोफ़िट गुण सेट करें।
```java
// टेक्स्ट फ़्रेम तक पहुँचना
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## चरण 6: टेक्स्ट फ़्रेम में टेक्स्ट जोड़ें
आकृति के अंदर पाठ फ़्रेम में पाठ सामग्री जोड़ें.
```java
// टेक्स्ट फ़्रेम के लिए पैराग्राफ़ ऑब्जेक्ट बनाएँ
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// पैराग्राफ़ के लिए पोर्शन ऑब्जेक्ट बनाएँ
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## चरण 7: प्रेजेंटेशन सहेजें
संशोधित प्रस्तुति को ऑटोफिट टेक्स्ट फ्रेम के साथ सहेजें।
```java
// प्रस्तुति सहेजें
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा कि Aspose.Slides for Java का उपयोग करके Java PowerPoint प्रस्तुतियों में टेक्स्ट फ़्रेम के लिए ऑटोफ़िट कैसे सेट करें। इन चरणों का पालन करके, आप आकृतियों के भीतर टेक्स्ट की फ़िटिंग को स्वचालित कर सकते हैं, जिससे प्रोग्रामेटिक रूप से आपकी प्रस्तुतियों की पठनीयता और सौंदर्यबोध में वृद्धि होगी।

## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक मजबूत Java API है जो डेवलपर्स को पावरपॉइंट प्रस्तुतियों को बनाने, पढ़ने, हेरफेर करने और परिवर्तित करने की अनुमति देता है।
### मैं Java के लिए Aspose.Slides कैसे डाउनलोड करूं?
 आप Java के लिए Aspose.Slides को यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
### क्या मैं Java के लिए Aspose.Slides निःशुल्क आज़मा सकता हूँ?
 हां, आप यहां से Aspose.Slides for Java का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 आप Java के लिए Aspose.Slides के लिए विस्तृत दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
### मैं Java के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 आप Aspose.Slides for Java के लिए सामुदायिक और पेशेवर सहायता यहाँ से प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
