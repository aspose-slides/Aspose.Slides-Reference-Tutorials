---
title: पावरपॉइंट में सापेक्ष स्केल ऊंचाई चित्र फ़्रेम जोड़ें
linktitle: पावरपॉइंट में सापेक्ष स्केल ऊंचाई चित्र फ़्रेम जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में सापेक्ष स्केल ऊंचाई चित्र फ़्रेम कैसे जोड़ें, जिससे आपकी दृश्य सामग्री में वृद्धि हो।
type: docs
weight: 15
url: /hi/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---
## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में सापेक्ष स्केल ऊंचाई के साथ चित्र फ़्रेम कैसे जोड़ें।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2. Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके Java प्रोजेक्ट में जोड़ दी गई।

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
सबसे पहले, सुनिश्चित करें कि आपके पास अपने प्रोजेक्ट के लिए एक निर्देशिका स्थापित है, और आपका जावा वातावरण ठीक से कॉन्फ़िगर किया गया है।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंशिएट करें
Aspose.Slides का उपयोग करके एक नया प्रस्तुति ऑब्जेक्ट बनाएं:
```java
Presentation presentation = new Presentation();
```
## चरण 3: जोड़ी जाने वाली छवि लोड करें
वह छवि लोड करें जिसे आप प्रस्तुति में जोड़ना चाहते हैं:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## चरण 4: स्लाइड में पिक्चर फ़्रेम जोड़ें
प्रस्तुति में किसी स्लाइड में चित्र फ़्रेम जोड़ें:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## चरण 5: सापेक्ष स्केल चौड़ाई और ऊंचाई सेट करें
चित्र फ़्रेम के लिए सापेक्ष स्केल चौड़ाई और ऊंचाई सेट करें:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## चरण 6: प्रस्तुति सहेजें
जोड़े गए चित्र फ़्रेम के साथ प्रस्तुति को सहेजें:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इन चरणों का पालन करके, आप आसानी से Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में सापेक्ष स्केल ऊंचाई के साथ एक चित्र फ़्रेम जोड़ सकते हैं। अपनी छवियों के लिए वांछित उपस्थिति प्राप्त करने के लिए विभिन्न स्केल मानों के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं इस विधि का उपयोग करके एक ही स्लाइड में एकाधिक चित्र फ़्रेम जोड़ सकता हूँ?
हां, आप प्रत्येक चित्र के लिए प्रक्रिया को दोहराकर एक स्लाइड में एकाधिक चित्र फ़्रेम जोड़ सकते हैं।
### क्या Aspose.Slides for Java PowerPoint के सभी संस्करणों के साथ संगत है?
जावा के लिए Aspose.Slides पावरपॉइंट के विभिन्न संस्करणों के साथ संगत है, जिससे प्रस्तुतियाँ बनाने में लचीलापन सुनिश्चित होता है।
### क्या मैं चित्र फ़्रेम की स्थिति और आकार को अनुकूलित कर सकता हूँ?
 बिल्कुल, आप स्थिति और आकार मापदंडों को समायोजित कर सकते हैं`addPictureFrame` अपनी आवश्यकताओं के अनुरूप विधि का चयन करें।
### क्या Java के लिए Aspose.Slides JPEG के अलावा अन्य छवि प्रारूपों का समर्थन करता है?
हां, Aspose.Slides for Java विभिन्न छवि प्रारूपों का समर्थन करता है, जिनमें PNG, GIF, BMP, आदि शामिल हैं।
### क्या Aspose.Slides उपयोगकर्ताओं के लिए कोई सामुदायिक मंच या सहायता चैनल उपलब्ध है?
हां, आप लाइब्रेरी से संबंधित किसी भी प्रश्न, चर्चा या सहायता के लिए Aspose.Slides फोरम पर जा सकते हैं।