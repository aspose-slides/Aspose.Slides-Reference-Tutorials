---
title: पावरपॉइंट में चित्र से आकृतियाँ भरें
linktitle: पावरपॉइंट में चित्र से आकृतियाँ भरें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में चित्रों के साथ आकृतियाँ भरना सीखें। दृश्य अपील को सहजता से बढ़ाएँ।
type: docs
weight: 12
url: /hi/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---
## परिचय
पावरपॉइंट प्रेजेंटेशन में अक्सर छवियों से भरी आकृतियों जैसे विज़ुअल तत्वों की आवश्यकता होती है ताकि उनकी अपील बढ़े और जानकारी को प्रभावी ढंग से व्यक्त किया जा सके। Aspose.Slides for Java इस कार्य को सहजता से पूरा करने के लिए उपकरणों का एक शक्तिशाली सेट प्रदान करता है। इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके आकृतियों को चित्रों से कैसे भरा जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2.  Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई। आप इसे यहाँ से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
3. जावा प्रोग्रामिंग का बुनियादी ज्ञान.
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## चरण 1: प्रोजेक्ट निर्देशिका सेट करें
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
 प्रतिस्थापन सुनिश्चित करें`"Your Document Directory"` अपने प्रोजेक्ट निर्देशिका के पथ के साथ.
## चरण 2: एक प्रस्तुति बनाएं
```java
Presentation pres = new Presentation();
```
 उदाहरण प्रस्तुत करें`Presentation` एक नया पावरपॉइंट प्रेजेंटेशन बनाने के लिए क्लास का उपयोग करें।
## चरण 3: स्लाइड और आकार जोड़ें
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
प्रस्तुति में एक स्लाइड जोड़ें और उस पर एक आयताकार आकार बनाएं।
## चरण 4: भरण प्रकार को चित्र पर सेट करें
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
आकृति का भरण प्रकार चित्र पर सेट करें.
## चरण 5: चित्र भरण मोड सेट करें
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
आकृति का चित्र भरण मोड सेट करें.
## चरण 6: चित्र सेट करें
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
छवि को लोड करें और इसे आकृति के लिए भरण के रूप में सेट करें।
## चरण 7: प्रस्तुति सहेजें
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
संशोधित प्रस्तुति को फ़ाइल में सहेजें.

## निष्कर्ष
Aspose.Slides for Java के साथ, PowerPoint प्रस्तुतियों में चित्रों के साथ आकृतियों को भरना एक सीधी प्रक्रिया बन जाती है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप आसानी से अपनी प्रस्तुतियों को आकर्षक तत्वों के साथ बेहतर बना सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides for Java का उपयोग करके चित्रों के साथ विभिन्न आकृतियाँ भर सकता हूँ?
हां, Aspose.Slides for Java चित्रों के साथ विभिन्न आकृतियों को भरने का समर्थन करता है, जिससे डिजाइन में लचीलापन मिलता है।
### क्या Aspose.Slides for Java PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides for Java, PowerPoint 97 और इसके बाद के संस्करणों के साथ संगत प्रस्तुतियाँ तैयार करता है, जिससे व्यापक अनुकूलता सुनिश्चित होती है।
### मैं आकृति के भीतर छवि का आकार कैसे बदल सकता हूँ?
आप आकृति के आयामों को समायोजित करके या छवि को भरण के रूप में सेट करने से पहले उसके अनुसार स्केलिंग करके आकृति के भीतर छवि का आकार बदल सकते हैं।
### क्या आकृतियों को भरने के लिए समर्थित छवि प्रारूपों पर कोई सीमाएं हैं?
Aspose.Slides for Java कई प्रकार के छवि प्रारूपों का समर्थन करता है, जिनमें JPEG, PNG, GIF, BMP, और TIFF आदि शामिल हैं।
### क्या मैं भरी हुई आकृतियों पर प्रभाव लागू कर सकता हूँ?
हां, Java के लिए Aspose.Slides भरे हुए आकृतियों पर छाया, प्रतिबिंब और 3D घुमाव जैसे विभिन्न प्रभाव लागू करने के लिए व्यापक API प्रदान करता है।