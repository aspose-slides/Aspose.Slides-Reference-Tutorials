---
title: पावरपॉइंट में छवि भरने के लिए स्ट्रेच ऑफसेट जोड़ें
linktitle: पावरपॉइंट में छवि भरने के लिए स्ट्रेच ऑफसेट जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में छवि भरण के लिए स्ट्रेच ऑफ़सेट जोड़ना सीखें। चरण-दर-चरण ट्यूटोरियल शामिल है।
weight: 16
url: /hi/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि PowerPoint प्रस्तुतियों में छवि भरने के लिए स्ट्रेच ऑफ़सेट जोड़ने के लिए Aspose.Slides for Java का उपयोग कैसे करें। यह सुविधा आपको अपनी स्लाइड्स के भीतर छवियों में हेरफेर करने की अनुमति देती है, जिससे आपको उनकी उपस्थिति पर अधिक नियंत्रण मिलता है।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2. Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके Java प्रोजेक्ट में सेट अप की गई।
## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
वह निर्देशिका निर्धारित करें जहां आपका PowerPoint दस्तावेज़ स्थित है:
```java
String dataDir = "Your Document Directory";
```
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट बनाएँ
PowerPoint फ़ाइल को प्रदर्शित करने के लिए Presentation क्लास को इन्स्टेन्शियेट करें:
```java
Presentation pres = new Presentation();
```
## चरण 3: स्लाइड में छवि जोड़ें
पहली स्लाइड प्राप्त करें और उसमें एक छवि जोड़ें:
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## चरण 4: चित्र फ़्रेम जोड़ें
चित्र के समतुल्य आयामों वाला एक चित्र फ़्रेम बनाएँ:
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## चरण 5: प्रस्तुति सहेजें
संशोधित PowerPoint फ़ाइल सहेजें:
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint में छवि भरने के लिए स्ट्रेच ऑफ़सेट जोड़ना सफलतापूर्वक सीख लिया है। यह सुविधा कस्टम छवियों के साथ आपकी प्रस्तुतियों को बेहतर बनाने के लिए संभावनाओं की दुनिया खोलती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं किसी प्रस्तुति में विशिष्ट स्लाइडों में छवियाँ जोड़ने के लिए इस विधि का उपयोग कर सकता हूँ?
हां, आप किसी विशिष्ट स्लाइड को लक्षित करने के लिए स्लाइड ऑब्जेक्ट को पुनर्प्राप्त करते समय स्लाइड इंडेक्स निर्दिष्ट कर सकते हैं।
### क्या Java के लिए Aspose.Slides JPEG के अलावा अन्य छवि प्रारूपों का समर्थन करता है?
हां, Aspose.Slides for Java विभिन्न छवि प्रारूपों का समर्थन करता है, जिनमें PNG, GIF और BMP आदि शामिल हैं।
### क्या इस पद्धति का उपयोग करके जोड़े जा सकने वाले चित्रों के आकार की कोई सीमा है?
Java के लिए Aspose.Slides विभिन्न आकारों की छवियों को संभाल सकता है, लेकिन प्रस्तुतियों में बेहतर प्रदर्शन के लिए छवियों को अनुकूलित करने की अनुशंसा की जाती है।
### क्या मैं स्लाइड में चित्र जोड़ने के बाद उन पर अतिरिक्त प्रभाव या परिवर्तन लागू कर सकता हूँ?
हां, आप Aspose.Slides for Java के व्यापक API का उपयोग करके छवियों पर प्रभावों और परिवर्तनों की एक विस्तृत श्रृंखला लागू कर सकते हैं।
### मैं Aspose.Slides for Java के लिए और अधिक संसाधन और समर्थन कहां पा सकता हूं?
 आप यहां जा सकते हैं[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/) विस्तृत गाइड के लिए और अन्वेषण करें[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन के लिए.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
