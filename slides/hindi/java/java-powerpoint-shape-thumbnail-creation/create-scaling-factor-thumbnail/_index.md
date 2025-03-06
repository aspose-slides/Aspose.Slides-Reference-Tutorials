---
title: स्केलिंग फैक्टर थंबनेल बनाएं
linktitle: स्केलिंग फैक्टर थंबनेल बनाएं
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java में स्केलिंग फैक्टर थंबनेल बनाना सीखें। चरण-दर-चरण निर्देशों के साथ आसान-से-अनुसरण मार्गदर्शिका।
weight: 12
url: /hi/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके स्केलिंग फ़ैक्टर थंबनेल बनाने की प्रक्रिया के बारे में बताएँगे। अपने इच्छित परिणाम प्राप्त करने के लिए इन चरण-दर-चरण निर्देशों का पालन करें।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
- Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके Java प्रोजेक्ट में सेट अप की गई।
- जावा प्रोग्रामिंग भाषा की बुनियादी समझ।

## पैकेज आयात करें
सबसे पहले, अपने जावा कोड में Aspose.Slides के साथ काम करने के लिए आवश्यक पैकेज आयात करें। 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

अब, आइए दिए गए उदाहरण को कई चरणों में विभाजित करें:
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
अपनी दस्तावेज़ निर्देशिका का पथ निर्धारित करें जहाँ PowerPoint प्रस्तुति फ़ाइल स्थित है।
```java
String dataDir = "Your Document Directory";
```
 प्रतिस्थापित करें`"Your Document Directory"` अपने वास्तविक दस्तावेज़ निर्देशिका के पथ के साथ.
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंशिएट करें
PowerPoint प्रस्तुति फ़ाइल को प्रदर्शित करने के लिए Presentation वर्ग का एक उदाहरण बनाएँ।
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 प्रतिस्थापन सुनिश्चित करें`"HelloWorld.pptx"` अपनी पावरपॉइंट प्रेजेंटेशन फ़ाइल के नाम के साथ.
## चरण 3: पूर्ण स्केल छवि बनाएँ
प्रस्तुति से वांछित स्लाइड की पूर्ण-पैमाने वाली छवि तैयार करें।
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
यह कोड प्रस्तुति की पहली स्लाइड पर पहली आकृति का थंबनेल प्राप्त करता है।
## चरण 4: छवि सहेजें
उत्पन्न छवि को PNG प्रारूप में डिस्क पर सहेजें।
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 प्रतिस्थापन सुनिश्चित करें`"Scaling Factor Thumbnail_out.png"` वांछित आउटपुट फ़ाइल नाम के साथ.

## निष्कर्ष
निष्कर्ष में, आपने Aspose.Slides for Java का उपयोग करके सफलतापूर्वक स्केलिंग फ़ैक्टर थंबनेल बनाया है। दिए गए चरणों का पालन करके, आप आसानी से इस कार्यक्षमता को अपने Java अनुप्रयोगों में एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं किसी भी Java IDE के साथ Aspose.Slides for Java का उपयोग कर सकता हूँ?
हां, Aspose.Slides for Java का उपयोग किसी भी Java एकीकृत विकास वातावरण (IDE) जैसे कि Eclipse, IntelliJ IDEA, या NetBeans के साथ किया जा सकता है।
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां जाकर Aspose.Slides for Java का निःशुल्क परीक्षण प्राप्त कर सकते हैं।[वेबसाइट](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए समर्थन कहां पा सकता हूं?
 आप Aspose.Slides for Java के लिए समर्थन यहाँ पा सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### मैं Java के लिए Aspose.Slides कैसे खरीद सकता हूँ?
 आप Java के लिए Aspose.Slides यहाँ से खरीद सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/buy).
### क्या मुझे Java के लिए Aspose.Slides का उपयोग करने के लिए अस्थायी लाइसेंस की आवश्यकता है?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
