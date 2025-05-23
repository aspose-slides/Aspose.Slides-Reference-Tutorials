---
"description": "हमारे विस्तृत चरण-दर-चरण मार्गदर्शिका के साथ Java के लिए Aspose.Slides का उपयोग करके PowerPoint में एक स्वरूपित दीर्घवृत्त बनाना सीखें।"
"linktitle": "PowerPoint में स्वरूपित दीर्घवृत्त बनाएँ"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "PowerPoint में स्वरूपित दीर्घवृत्त बनाएँ"
"url": "/hi/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint में स्वरूपित दीर्घवृत्त बनाएँ

## परिचय
जावा के लिए Aspose.Slides का उपयोग करके PowerPoint में एक स्वरूपित दीर्घवृत्त बनाने पर इस व्यापक ट्यूटोरियल में आपका स्वागत है। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint फ़ाइलों में हेरफेर करने की अनुमति देती है। चाहे आप स्लाइड जनरेशन को स्वचालित कर रहे हों या कस्टम आकृतियों के साथ प्रस्तुतियों को बेहतर बना रहे हों, यह मार्गदर्शिका आपको हर चरण में मार्गदर्शन करेगी, यह सुनिश्चित करते हुए कि आप आसानी से अपनी स्लाइड में एक पूरी तरह से स्वरूपित दीर्घवृत्त जोड़ सकते हैं। आइए इसमें गोता लगाएँ और देखें कि हम इसे कैसे प्राप्त कर सकते हैं!
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके पास JDK 1.6 या उच्चतर संस्करण स्थापित है।
2. Aspose.Slides for Java: यहां से नवीनतम संस्करण डाउनलोड करें [जावा के लिए Aspose.Slides](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): IntelliJ IDEA या Eclipse जैसे IDE का उपयोग करें।
4. जावा का बुनियादी ज्ञान: जावा प्रोग्रामिंग से परिचित होना आवश्यक है।
## पैकेज आयात करें
Aspose.Slides का उपयोग शुरू करने के लिए, आपको आवश्यक पैकेज आयात करने होंगे। आप यह कैसे कर सकते हैं, यहाँ बताया गया है:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## चरण 1: अपनी प्रोजेक्ट निर्देशिका सेट करें
सबसे पहले, आपको अपनी पावरपॉइंट फ़ाइलों को संग्रहीत करने के लिए एक निर्देशिका की आवश्यकता होगी।
### निर्देशिका बनाओ
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
सुनिश्चित करें कि आप प्रतिस्थापित करें `"Your Document Directory"` उस वास्तविक पथ के साथ जहां आप अपनी फ़ाइलें संग्रहीत करना चाहते हैं.
## चरण 2: प्रस्तुति आरंभ करें
अब, प्रेजेंटेशन क्लास को इन्स्टेन्सिएट करें, जो पावरपॉइंट फ़ाइल का प्रतिनिधित्व करता है।
```java
// PPTX का प्रतिनिधित्व करने वाला इन्स्टेन्शियेट प्रेजेंटेशन क्लास
Presentation pres = new Presentation();
```
## चरण 3: पहली स्लाइड प्राप्त करें
इसके बाद, प्रस्तुति से पहली स्लाइड लें जहां आप दीर्घवृत्त जोड़ेंगे।
```java
// पहली स्लाइड प्राप्त करें
ISlide sld = pres.getSlides().get_Item(0);
```
## चरण 4: एक दीर्घवृत्त आकार जोड़ें
स्लाइड में दीर्घवृत्त प्रकार का एक स्वचालित आकार जोड़ें.
```java
// दीर्घवृत्त प्रकार का स्वतः आकार जोड़ें
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
यहाँ, `50, 150, 150, 50` दीर्घवृत्त के निर्देशांक और आकार (x स्थिति, y स्थिति, चौड़ाई, ऊँचाई) हैं।
## चरण 5: दीर्घवृत्त पर स्वरूपण लागू करें
अब, दीर्घवृत्त पर कुछ फ़ॉर्मेटिंग लागू करें। हम एक ठोस भरण रंग और एक रेखा रंग सेट करेंगे।
### भरण रंग सेट करें
```java
// दीर्घवृत्त आकार पर कुछ स्वरूपण लागू करें
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### रेखा का रंग और चौड़ाई सेट करें
```java
// दीर्घवृत्त की रेखा पर कुछ स्वरूपण लागू करें
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## चरण 6: प्रस्तुति सहेजें
अंत में, प्रस्तुति को अपनी निर्दिष्ट निर्देशिका में सहेजें।
```java
// PPTX फ़ाइल को डिस्क पर लिखें
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## चरण 7: प्रेजेंटेशन ऑब्जेक्ट को हटाएँ
संसाधनों को मुक्त करने के लिए प्रस्तुति ऑब्जेक्ट को हटा दें।
```java
finally {
    if (pres != null) pres.dispose();
}
```
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में सफलतापूर्वक एक फ़ॉर्मेट किया हुआ दीर्घवृत्त बनाया है। इस ट्यूटोरियल में आपको अपना प्रोजेक्ट सेट अप करने, दीर्घवृत्त जोड़ने, फ़ॉर्मेटिंग लागू करने और अपनी प्रेजेंटेशन को सहेजने के बारे में बताया गया है। इन कौशलों के साथ, अब आप अपने PowerPoint स्लाइड को प्रोग्रामेटिक रूप से बेहतर बना सकते हैं, जिससे आपकी प्रेजेंटेशन अधिक गतिशील और आकर्षक बन सकती हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और प्रबंधित करने की अनुमति देती है।
### क्या मैं किसी भी IDE के साथ Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, आप किसी भी Java IDE जैसे IntelliJ IDEA, Eclipse, या NetBeans के साथ Aspose.Slides for Java का उपयोग कर सकते हैं।
### क्या मुझे Aspose.Slides के लिए लाइसेंस की आवश्यकता है?
हां, Aspose.Slides एक व्यावसायिक उत्पाद है, और आपको पूर्ण कार्यक्षमता के लिए लाइसेंस की आवश्यकता है। आप एक अस्थायी लाइसेंस प्राप्त कर सकते हैं [यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides for Java पर अधिक दस्तावेज़ कहां पा सकता हूं?
आप Aspose.Slides for Java पर विस्तृत दस्तावेज़ पा सकते हैं [दस्तावेज़ पृष्ठ](https://reference.aspose.com/slides/java/).
### क्या Aspose.Slides के लिए समर्थन उपलब्ध है?
हाँ, Aspose उनके माध्यम से समर्थन प्रदान करता है [मंच](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}