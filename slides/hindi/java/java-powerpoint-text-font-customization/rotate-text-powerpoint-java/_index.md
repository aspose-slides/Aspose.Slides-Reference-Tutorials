---
title: जावा का उपयोग करके पावरपॉइंट में टेक्स्ट घुमाएँ
linktitle: जावा का उपयोग करके पावरपॉइंट में टेक्स्ट घुमाएँ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ जावा का उपयोग करके PowerPoint में टेक्स्ट को घुमाना सीखें। शुरुआती से लेकर उन्नत उपयोगकर्ताओं के लिए चरण-दर-चरण ट्यूटोरियल।
weight: 10
url: /hi/java/java-powerpoint-text-font-customization/rotate-text-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि जावा और Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में टेक्स्ट को प्रोग्रामेटिक रूप से कैसे घुमाया जाए। स्लाइड्स को डिज़ाइन करते समय टेक्स्ट को घुमाना एक उपयोगी सुविधा हो सकती है, जिससे आकर्षक प्रस्तुतियाँ बनाई जा सकें।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर JDK स्थापित है.
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- आपके मशीन पर IDE (एकीकृत विकास वातावरण) जैसे कि IntelliJ IDEA या Eclipse स्थापित है।
## पैकेज आयात करें
सबसे पहले, आपको जावा में पावरपॉइंट फ़ाइलों के साथ काम करने के लिए आवश्यक Aspose.Slides क्लासेस को आयात करना होगा:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने IDE में एक नया Java प्रोजेक्ट बनाकर और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides JAR फ़ाइल जोड़कर आरंभ करें।
## चरण 2: प्रस्तुति और स्लाइड ऑब्जेक्ट्स को आरंभ करें
```java
// उस निर्देशिका का पथ जहाँ आप प्रस्तुति को सहेजना चाहते हैं
String dataDir = "Your_Document_Directory/";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
// पहली स्लाइड प्राप्त करें
ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 3: एक आयताकार आकार जोड़ें
```java
// आयत प्रकार का एक ऑटोशेप जोड़ें
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## चरण 4: आयत आकार में टेक्स्ट जोड़ें
```java
// आयत में टेक्स्टफ़्रेम जोड़ें
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
// टेक्स्ट फ़्रेम तक पहुँचना
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setTextVerticalType(TextVerticalType.Vertical270);
```
## चरण 5: टेक्स्ट सामग्री और स्टाइलिंग सेट करें
```java
// टेक्स्ट फ़्रेम के लिए पैराग्राफ़ ऑब्जेक्ट बनाएँ
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// पैराग्राफ़ के लिए पोर्शन ऑब्जेक्ट बनाएँ
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## चरण 6: प्रेजेंटेशन सहेजें
```java
// प्रस्तुति सहेजें
presentation.save(dataDir + "RotateText_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि जावा और Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में टेक्स्ट को कैसे घुमाया जाए। इन चरणों का पालन करके, आप दृश्य प्रभाव को बढ़ाने के लिए अपनी स्लाइड्स में टेक्स्ट ओरिएंटेशन को गतिशील रूप से बदल सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Java के लिए Aspose.Slides का उपयोग करके PowerPoint में टेक्स्ट को किसी भी कोण पर घुमा सकता हूँ?
हां, आप प्रोग्रामेटिक रूप से पाठ रोटेशन के लिए कोई भी वांछित कोण निर्दिष्ट कर सकते हैं।
### क्या Aspose.Slides फ़ॉन्ट आकार और संरेखण जैसे अन्य पाठ स्वरूपण विकल्पों का समर्थन करता है?
बिल्कुल, Aspose.Slides विभिन्न पाठ स्वरूपण आवश्यकताओं को संभालने के लिए व्यापक API प्रदान करता है।
### मैं Java के लिए Aspose.Slides के साथ कैसे शुरुआत कर सकता हूं?
 आप Aspose.Slides का निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/) इसकी विशेषताओं का पता लगाने के लिए।
### मैं Aspose.Slides के लिए अधिक दस्तावेज़ और समर्थन कहां पा सकता हूं?
 विस्तृत दस्तावेज़ीकरण के लिए, यहां जाएं[Aspose.Slides for Java दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) . आप समुदाय से भी सहायता प्राप्त कर सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
 आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/)Aspose.Slides का बिना किसी सीमा के मूल्यांकन करने के लिए.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
