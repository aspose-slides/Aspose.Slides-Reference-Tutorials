---
title: जावा पावरपॉइंट में पैराग्राफ इंडेंट सेट करें
linktitle: जावा पावरपॉइंट में पैराग्राफ इंडेंट सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में पैराग्राफ़ इंडेंट को प्रोग्रामेटिक रूप से सेट करना सीखें। अपनी प्रेजेंटेशन फ़ॉर्मेटिंग को आसानी से बेहतर बनाएँ।
weight: 16
url: /hi/java/java-powerpoint-text-paragraph-management/set-paragraph-indent-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से कैसे मैनिपुलेट किया जाए। विशेष रूप से, हम स्लाइड के भीतर पैराग्राफ़ इंडेंट सेट करने पर ध्यान केंद्रित करेंगे। Aspose.Slides for Java API का एक शक्तिशाली सेट प्रदान करता है जो डेवलपर्स को Microsoft Office Automation पर निर्भर किए बिना PowerPoint प्रस्तुतियों को बनाने, संशोधित करने, परिवर्तित करने और प्रबंधित करने की अनुमति देता है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित सेटअप है:
- आपकी मशीन पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई। आप इसे यहाँ से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- जावा प्रोग्रामिंग भाषा की बुनियादी समझ।
## पैकेज आयात करें
सबसे पहले, Aspose.Slides कार्यक्षमता तक पहुंचने के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
import java.io.File;
```
आइए Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में पैराग्राफ इंडेंट सेट करने की चरण-दर-चरण प्रक्रिया को देखें।
## चरण 1: एक प्रेजेंटेशन ऑब्जेक्ट बनाएँ
 उदाहरण प्रस्तुत करें`Presentation` कक्षा में एक नई पावरपॉइंट प्रस्तुति के साथ काम करना शुरू करें।
```java
// प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation pres = new Presentation();
```
## चरण 2: स्लाइड तक पहुंचें
प्रस्तुति से पहली स्लाइड प्राप्त करें। आप आवश्यकतानुसार इंडेक्स द्वारा विभिन्न स्लाइडों में बदलाव कर सकते हैं।
```java
// पहली स्लाइड प्राप्त करें
ISlide slide = pres.getSlides().get_Item(0);
```
## चरण 3: एक आयताकार आकार जोड़ें
स्लाइड में एक आयताकार आकार जोड़ें, जिसमें इंडेंटेड पैराग्राफ के साथ पाठ होगा।
```java
// एक आयताकार आकार जोड़ें
IAutoShape rect = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 500, 150);
```
## चरण 4: आयत में टेक्स्ट जोड़ें
आयताकार आकार के भीतर एक टेक्स्ट फ़्रेम बनाएं और टेक्स्ट सामग्री सेट करें।
```java
// आयत में टेक्स्टफ़्रेम जोड़ें
ITextFrame textFrame = rect.addTextFrame("This is first line \rThis is second line \rThis is third line");
```
## चरण 5: टेक्स्ट के लिए ऑटोफिट सेट करें
आकृति सीमाओं के भीतर फिट होने के लिए टेक्स्ट ऑटोफिट सेट करें.
```java
// आकृति में फिट करने के लिए पाठ सेट करें
textFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## चरण 6: पैराग्राफ़ इंडेंट समायोजित करें
टेक्स्ट फ़्रेम के भीतर प्रत्येक पैराग्राफ़ तक पहुँचें और उनका इंडेंटेशन सेट करें।
```java
// टेक्स्टफ्रेम में पहला पैराग्राफ प्राप्त करें और उसका इंडेंट सेट करें
IParagraph para1 = textFrame.getParagraphs().get_Item(0);
para1.getParagraphFormat().setIndent(30);
// टेक्स्टफ्रेम में दूसरा पैराग्राफ प्राप्त करें और उसका इंडेंट सेट करें
IParagraph para2 = textFrame.getParagraphs().get_Item(1);
para2.getParagraphFormat().setIndent(40);
//टेक्स्टफ्रेम में तीसरा पैराग्राफ प्राप्त करें और उसका इंडेंट सेट करें
IParagraph para3 = textFrame.getParagraphs().get_Item(2);
para3.getParagraphFormat().setIndent(50);
```
## चरण 7: प्रेजेंटेशन सहेजें
अंत में, संशोधित प्रस्तुति को डिस्क पर सहेजें।
```java
// प्रेजेंटेशन को डिस्क पर लिखें
String dataDir = "Your_Document_Directory_Path/";
pres.save(dataDir + "IndentedPresentation.pptx", SaveFormat.Pptx);
```
## निष्कर्ष
इन चरणों का पालन करके, आप आसानी से Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में पैराग्राफ़ इंडेंट सेट कर सकते हैं। यह क्षमता प्रोग्रामेटिक रूप से आपकी स्लाइड में टेक्स्ट के फ़ॉर्मेटिंग और प्रस्तुति पर सटीक नियंत्रण की अनुमति देती है।

## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, पावरपॉइंट प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने के लिए एक शक्तिशाली लाइब्रेरी है।
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 आप दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
### मैं Java के लिए Aspose.Slides कैसे डाउनलोड कर सकता हूँ?
 आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए समर्थन कहां से प्राप्त कर सकता हूं?
 आप सामुदायिक मंच से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
