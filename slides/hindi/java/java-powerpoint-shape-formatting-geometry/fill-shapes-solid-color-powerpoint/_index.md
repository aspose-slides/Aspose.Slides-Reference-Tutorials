---
title: पावरपॉइंट में ठोस रंग से आकृतियाँ भरें
linktitle: पावरपॉइंट में ठोस रंग से आकृतियाँ भरें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint में ठोस रंगों से आकृतियों को भरना सीखें। डेवलपर्स के लिए चरण-दर-चरण मार्गदर्शिका।
weight: 13
url: /hi/java/java-powerpoint-shape-formatting-geometry/fill-shapes-solid-color-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
यदि आपने कभी PowerPoint प्रस्तुतियों के साथ काम किया है, तो आप जानते हैं कि आकृतियाँ जोड़ना और उनके रंगों को अनुकूलित करना आपकी स्लाइड्स को देखने में आकर्षक और जानकारीपूर्ण बनाने का एक महत्वपूर्ण पहलू हो सकता है। Aspose.Slides for Java के साथ, यह प्रक्रिया बहुत आसान हो जाती है। चाहे आप एक डेवलपर हों जो PowerPoint प्रस्तुतियों के निर्माण को स्वचालित करना चाहते हैं या कोई ऐसा व्यक्ति जो अपनी स्लाइड्स में रंग भरना चाहता हो, यह ट्यूटोरियल आपको Aspose.Slides for Java का उपयोग करके ठोस रंगों के साथ आकृतियाँ भरने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
इससे पहले कि हम कोड में उतरें, कुछ पूर्व-आवश्यकताएं हैं जो आपके पास होनी चाहिए:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं।[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java लाइब्रेरी को यहाँ से डाउनलोड करें[Aspose वेबसाइट](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (आईडीई): इंटेलीज आईडीईए या एक्लिप्स जैसा आईडीई आपकी विकास प्रक्रिया को अधिक सुचारू बना देगा।
4. जावा का बुनियादी ज्ञान: जावा प्रोग्रामिंग से परिचित होने से आपको कोड को प्रभावी ढंग से समझने और कार्यान्वित करने में मदद मिलेगी।

## पैकेज आयात करें
Aspose.Slides for Java का उपयोग शुरू करने के लिए, आपको आवश्यक पैकेज आयात करने होंगे। आप यह कैसे कर सकते हैं, यहाँ बताया गया है:
```java
import com.aspose.slides.*;

import java.awt.*;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
 सबसे पहले, आपको अपना जावा प्रोजेक्ट सेट अप करना होगा और अपनी प्रोजेक्ट निर्भरताओं में Aspose.Slides for Java को शामिल करना होगा। यदि आप Maven का उपयोग कर रहे हैं, तो अपनी निर्भरता में निम्न जोड़ें`pom.xml` फ़ाइल:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace XX.X with the latest version -->
</dependency>
```
 यदि आप Maven का उपयोग नहीं कर रहे हैं, तो JAR फ़ाइल को यहाँ से डाउनलोड करें.[Aspose वेबसाइट](https://releases.aspose.com/slides/java/) और इसे अपने प्रोजेक्ट के निर्माण पथ में जोड़ें.
## चरण 2: प्रस्तुति आरंभ करें
 इसका एक उदाहरण बनाएं`Presentation` क्लास. यह क्लास उस पावरपॉइंट प्रेजेंटेशन को दर्शाता है जिस पर आप काम करेंगे.
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
```
## चरण 3: पहली स्लाइड तक पहुंचें
इसके बाद, आपको प्रस्तुति की पहली स्लाइड प्राप्त करनी होगी जहां आप अपनी आकृतियाँ जोड़ेंगे।
```java
// पहली स्लाइड प्राप्त करें
ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 4: स्लाइड में आकृति जोड़ें
अब, स्लाइड में एक आयताकार आकृति जोड़ें। आप पैरामीटर समायोजित करके आकृति की स्थिति और आकार को अनुकूलित कर सकते हैं।
```java
// आयत प्रकार का स्वतः आकार जोड़ें
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
## चरण 5: भरण प्रकार को ठोस पर सेट करें
 आकृति को ठोस रंग से भरने के लिए, भरण प्रकार को इस पर सेट करें`Solid`.
```java
// भरण प्रकार को ठोस पर सेट करें
shape.getFillFormat().setFillType(FillType.Solid);
```
## चरण 6: रंग चुनें और लागू करें
आकृति के लिए कोई रंग चुनें: यहाँ हम पीले रंग का उपयोग कर रहे हैं, लेकिन आप अपनी पसंद का कोई भी रंग चुन सकते हैं।
```java
//आयत का रंग सेट करें
shape.getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
```
## चरण 7: प्रेजेंटेशन सहेजें
अंत में, संशोधित प्रस्तुति को फ़ाइल में सहेजें।
```java
// PPTX फ़ाइल को डिस्क पर लिखें
presentation.save(dataDir + "RectShpSolid_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
और अब यह हो गया! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में एक आकृति को ठोस रंग से सफलतापूर्वक भर दिया है। यह लाइब्रेरी सुविधाओं का एक मजबूत सेट प्रदान करती है जो आपको आसानी से अपनी प्रस्तुतियों को स्वचालित और अनुकूलित करने में मदद कर सकती है। चाहे आप रिपोर्ट तैयार कर रहे हों, शैक्षिक सामग्री बना रहे हों या व्यावसायिक स्लाइड डिज़ाइन कर रहे हों, Aspose.Slides for Java एक अमूल्य उपकरण हो सकता है।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, जावा में पावरपॉइंट प्रेजेंटेशन के साथ काम करने के लिए एक शक्तिशाली लाइब्रेरी है। यह आपको प्रोग्रामेटिक रूप से प्रेजेंटेशन बनाने, संशोधित करने और परिवर्तित करने की अनुमति देता है।
### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?
 आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose वेबसाइट](https://releases.aspose.com/slides/java/) और JAR फ़ाइल को अपने प्रोजेक्ट में जोड़ें, या इसे शामिल करने के लिए Maven जैसे निर्भरता प्रबंधक का उपयोग करें।
### क्या मैं मौजूदा प्रस्तुतियों को संपादित करने के लिए Aspose.Slides for Java का उपयोग कर सकता हूँ?
हां, Java के लिए Aspose.Slides आपको मौजूदा पावरपॉइंट प्रस्तुतियों को खोलने, संपादित करने और सहेजने की अनुमति देता है।
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं।[Aspose वेबसाइट](https://releases.aspose.com/).
### मुझे अधिक दस्तावेज और सहायता कहां मिल सकती है?
 विस्तृत दस्तावेज यहां उपलब्ध है[Aspose वेबसाइट](https://reference.aspose.com/slides/java/) और आप सहायता मांग सकते हैं[Aspose फ़ोरम](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
