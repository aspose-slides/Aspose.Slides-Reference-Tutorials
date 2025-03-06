---
title: जावा का उपयोग करके स्मार्टआर्ट में बुलेट फिल फॉर्मेट सेट करें
linktitle: जावा का उपयोग करके स्मार्टआर्ट में बुलेट फिल फॉर्मेट सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ Java का उपयोग करके SmartArt में बुलेट फ़िल फ़ॉर्मेट सेट करना सीखें। कुशल प्रस्तुतिकरण हेरफेर के लिए चरण-दर-चरण मार्गदर्शिका।
weight: 18
url: /hi/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके स्मार्टआर्ट में बुलेट फिल फॉर्मेट सेट करें

## परिचय
जावा प्रोग्रामिंग के क्षेत्र में, प्रस्तुतियों का कुशल संचालन एक सामान्य आवश्यकता है, खासकर जब स्मार्टआर्ट तत्वों से निपटना हो। जावा के लिए Aspose.Slides ऐसे कार्यों के लिए एक शक्तिशाली उपकरण के रूप में उभरता है, जो प्रस्तुतियों को प्रोग्रामेटिक रूप से संभालने के लिए कई प्रकार की कार्यक्षमता प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Slides के साथ जावा का उपयोग करके स्मार्टआर्ट में बुलेट फिल फ़ॉर्मेट सेट करने की प्रक्रिया को चरण दर चरण समझेंगे।
## आवश्यक शर्तें
इससे पहले कि हम इस ट्यूटोरियल को शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
### जावा डेवलपमेंट किट (JDK)
 आपके सिस्टम पर JDK इंस्टॉल होना चाहिए। आप इसे यहाँ से डाउनलोड कर सकते हैं[वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) और स्थापना निर्देशों का पालन करें.
### जावा के लिए Aspose.Slides
 Aspose.Slides for Java को डाउनलोड करें और इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/slides/java/)अपने विशिष्ट ऑपरेटिंग सिस्टम के लिए दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#आइए Aspose.Slides के साथ जावा का उपयोग करके स्मार्टआर्ट में बुलेट भरण प्रारूप कैसे सेट करें, इसकी स्पष्ट समझ के लिए दिए गए उदाहरण को कई चरणों में विभाजित करें।
## चरण 1: प्रेजेंटेशन ऑब्जेक्ट बनाएँ
```java
Presentation presentation = new Presentation();
```
सबसे पहले, Presentation क्लास का एक नया उदाहरण बनाएं, जो PowerPoint प्रस्तुति का प्रतिनिधित्व करता है।
## चरण 2: स्मार्टआर्ट जोड़ें
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
इसके बाद, स्लाइड में एक स्मार्टआर्ट आकृति जोड़ें। कोड की यह पंक्ति निर्दिष्ट आयामों और लेआउट के साथ एक नई स्मार्टआर्ट आकृति को आरंभ करती है।
## चरण 3: स्मार्टआर्ट नोड तक पहुंचें
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
अब, स्मार्टआर्ट आकृति के भीतर पहले नोड (या किसी भी वांछित नोड) तक पहुंच कर उसके गुणों को संशोधित करें।
## चरण 4: बुलेट भरण प्रारूप सेट करें
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
यहाँ, हम जाँचते हैं कि बुलेट फ़िल फ़ॉर्मेट समर्थित है या नहीं। अगर यह समर्थित है, तो हम एक इमेज फ़ाइल लोड करते हैं और इसे स्मार्टआर्ट नोड के लिए बुलेट फ़िल के रूप में सेट करते हैं।
## चरण 5: प्रस्तुति सहेजें
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
अंत में, संशोधित प्रस्तुति को निर्दिष्ट स्थान पर सहेजें।

## निष्कर्ष
बधाई हो! आपने Aspose.Slides के साथ Java का उपयोग करके SmartArt में बुलेट फ़िल फ़ॉर्मेट सेट करना सफलतापूर्वक सीख लिया है। यह क्षमता Java अनुप्रयोगों में गतिशील और आकर्षक प्रस्तुतियों के लिए संभावनाओं की दुनिया खोलती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं स्क्रैच से प्रेजेंटेशन बनाने के लिए Aspose.Slides for Java का उपयोग कर सकता हूँ?
बिल्कुल! Aspose.Slides पूरी तरह से कोड के माध्यम से प्रस्तुतियों को बनाने, संशोधित करने और हेरफेर करने के लिए व्यापक API प्रदान करता है।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
हां, Aspose.Slides Microsoft PowerPoint के विभिन्न संस्करणों के साथ संगतता सुनिश्चित करता है, जिससे आपके वर्कफ़्लो में निर्बाध एकीकरण संभव होता है।
### क्या मैं स्मार्टआर्ट तत्वों को बुलेट भरण प्रारूप से परे अनुकूलित कर सकता हूँ?
दरअसल, Aspose.Slides आपको स्मार्टआर्ट आकृतियों के हर पहलू को अनुकूलित करने की शक्ति देता है, जिसमें लेआउट, शैली, सामग्री और बहुत कुछ शामिल है।
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप एक निःशुल्क परीक्षण के साथ Aspose.Slides की विशेषताओं का पता लगा सकते हैं। बस इसे यहाँ से डाउनलोड करें[वेबसाइट](https://releases.aspose.com/slides/java/) और अन्वेषण शुरू करें.
### मैं Aspose.Slides for Java के लिए समर्थन कहां पा सकता हूं?
 किसी भी प्रश्न या सहायता के लिए, आप Aspose.Slides फोरम पर जा सकते हैं[इस लिंक](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
