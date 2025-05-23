---
"description": "Aspose.Slides for Java के साथ Java का उपयोग करके PowerPoint प्रस्तुतियों में फ़ॉन्ट गुणों में हेरफेर करना सीखें। इस चरण-दर-चरण मार्गदर्शिका के साथ आसानी से फ़ॉन्ट कस्टमाइज़ करें।"
"linktitle": "जावा के साथ पावरपॉइंट में फ़ॉन्ट गुण"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा के साथ पावरपॉइंट में फ़ॉन्ट गुण"
"url": "/hi/java/java-powerpoint-font-management/font-properties-powerpoint-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा के साथ पावरपॉइंट में फ़ॉन्ट गुण

## परिचय
इस ट्यूटोरियल में, हम जावा का उपयोग करके पावरपॉइंट प्रेजेंटेशन में फ़ॉन्ट गुणों में हेरफेर करने का तरीका जानेंगे, विशेष रूप से Aspose.Slides for Java के साथ। हम आपको आवश्यक पैकेज आयात करने से लेकर आपके संशोधित प्रेजेंटेशन को सहेजने तक प्रत्येक चरण में मार्गदर्शन करेंगे। आइए शुरू करते हैं!
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java JAR: Aspose.Slides for Java लाइब्रेरी को यहाँ से डाउनलोड करें [यहाँ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): आप अपनी पसंद के किसी भी Java IDE का उपयोग कर सकते हैं, जैसे IntelliJ IDEA, Eclipse, या NetBeans.

## पैकेज आयात करें
सबसे पहले, आइए Aspose.Slides for Java के साथ काम करने के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंशिएट करें
एक बनाकर शुरू करें `Presentation` वह ऑब्जेक्ट जो आपकी PowerPoint फ़ाइल का प्रतिनिधित्व करता है:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "FontProperties.pptx");
```
## चरण 2: स्लाइड और प्लेसहोल्डर्स तक पहुंचें
अब, आइए आपकी प्रस्तुति में स्लाइडों और प्लेसहोल्डर्स तक पहुंचें:
```java
ISlide slide = pres.getSlides().get_Item(0);
ITextFrame tf1 = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
ITextFrame tf2 = ((IAutoShape) slide.getShapes().get_Item(1)).getTextFrame();
```
## चरण 3: पैराग्राफ़ और अंशों तक पहुँचें
इसके बाद, हम पैराग्राफ़ और टेक्स्ट फ़्रेम के भीतर के भागों तक पहुंचेंगे:
```java
IParagraph para1 = tf1.getParagraphs().get_Item(0);
IParagraph para2 = tf2.getParagraphs().get_Item(0);
IPortion port1 = para1.getPortions().get_Item(0);
IPortion port2 = para2.getPortions().get_Item(0);
```
## चरण 4: नए फ़ॉन्ट निर्धारित करें
उन भागों के लिए आप जो फ़ॉन्ट उपयोग करना चाहते हैं उसे परिभाषित करें:
```java
FontData fd1 = new FontData("Elephant");
FontData fd2 = new FontData("Castellar");
```
## चरण 5: फ़ॉन्ट गुण सेट करें
विभिन्न फ़ॉन्ट गुण जैसे बोल्ड, इटैलिक और रंग सेट करें:
```java
port1.getPortionFormat().setLatinFont(fd1);
port2.getPortionFormat().setLatinFont(fd2);
port1.getPortionFormat().setFontBold(NullableBool.True);
port2.getPortionFormat().setFontBold(NullableBool.True);
port1.getPortionFormat().setFontItalic(NullableBool.True);
port2.getPortionFormat().setFontItalic(NullableBool.True);
port1.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port1.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
port2.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port2.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Peru));
```
## चरण 6: संशोधित प्रस्तुति को सहेजें
अंत में, अपनी संशोधित प्रस्तुति को डिस्क पर सहेजें:
```java
pres.save(dataDir + "WelcomeFont_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
जावा का उपयोग करके पावरपॉइंट प्रेजेंटेशन में फ़ॉन्ट गुणों में हेरफेर करना Aspose.Slides for Java के साथ आसान बना दिया गया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपनी स्लाइड्स की दृश्य अपील को बढ़ाने के लिए फ़ॉन्ट को कस्टमाइज़ कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides for Java के साथ कस्टम फ़ॉन्ट का उपयोग कर सकता हूँ?
हां, आप फ़ॉन्ट को परिभाषित करते समय फ़ॉन्ट नाम निर्दिष्ट करके कस्टम फ़ॉन्ट का उपयोग कर सकते हैं। `FontData`.
### मैं पावरपॉइंट स्लाइड में टेक्स्ट का फ़ॉन्ट आकार कैसे बदल सकता हूँ?
आप फ़ॉन्ट आकार को सेट करके समायोजित कर सकते हैं `FontHeight` की संपत्ति `PortionFormat`.
### क्या Aspose.Slides for Java पाठ प्रभाव जोड़ने का समर्थन करता है?
हां, Aspose.Slides for Java आपकी प्रस्तुतियों को बेहतर बनाने के लिए विभिन्न टेक्स्ट प्रभाव विकल्प प्रदान करता है।
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए और अधिक समर्थन और संसाधन कहां पा सकता हूं?
आप Aspose.Slides फ़ोरम पर जा सकते हैं [यहाँ](https://forum.aspose.com/c/slides/11) सहायता और दस्तावेज़ीकरण के लिए [यहाँ](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}