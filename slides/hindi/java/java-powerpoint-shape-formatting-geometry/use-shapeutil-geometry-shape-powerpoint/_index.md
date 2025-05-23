---
"description": "Aspose.Slides for Java के साथ PowerPoint में कस्टम आकृतियाँ बनाएँ। अपनी प्रस्तुतियों को बेहतर बनाने के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"linktitle": "PowerPoint में ज्यामिति आकार के लिए ShapeUtil का उपयोग करें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "PowerPoint में ज्यामिति आकार के लिए ShapeUtil का उपयोग करें"
"url": "/hi/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint में ज्यामिति आकार के लिए ShapeUtil का उपयोग करें

## परिचय
दृश्य रूप से आकर्षक पावरपॉइंट प्रेजेंटेशन बनाने के लिए अक्सर सिर्फ़ मानक आकृतियों और टेक्स्ट का उपयोग करने से ज़्यादा की ज़रूरत होती है। कल्पना करें कि आप अपनी स्लाइड में सीधे कस्टमाइज़ किए गए आकार और टेक्स्ट पथ जोड़ पाएँ, जिससे आपकी प्रेजेंटेशन का दृश्य प्रभाव बढ़ जाए। जावा के लिए Aspose.Slides का उपयोग करके, आप इसे आसानी से प्राप्त कर सकते हैं। यह ट्यूटोरियल आपको उपयोग करने की प्रक्रिया के बारे में बताएगा `ShapeUtil` पावरपॉइंट प्रेजेंटेशन में ज्यामिति आकृतियाँ बनाने के लिए क्लास। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह चरण-दर-चरण मार्गदर्शिका आपको आश्चर्यजनक, कस्टम-आकार की सामग्री बनाने के लिए Aspose.Slides for Java की शक्ति का लाभ उठाने में मदद करेगी।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, आपको कुछ चीजों की आवश्यकता होगी:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपकी मशीन पर JDK 8 या उच्चतर संस्करण स्थापित है।
2. Aspose.Slides for Java: से नवीनतम संस्करण डाउनलोड करें [डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. विकास पर्यावरण: किसी भी जावा IDE जैसे IntelliJ IDEA, Eclipse, या NetBeans का उपयोग करें।
4. अस्थायी लाइसेंस: यहाँ से निःशुल्क अस्थायी लाइसेंस प्राप्त करें [Aspose का अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/) Aspose.Slides for Java की पूर्ण कार्यक्षमता को अनलॉक करने के लिए।
## पैकेज आयात करें
आरंभ करने के लिए, आपको Aspose.Slides और Java AWT (एब्सट्रैक्ट विंडो टूलकिट) के साथ काम करने के लिए आवश्यक पैकेज आयात करने होंगे:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## चरण 1: अपना प्रोजेक्ट सेट अप करना
सबसे पहले, अपना जावा प्रोजेक्ट सेट अप करें और अपने प्रोजेक्ट की निर्भरताओं में Aspose.Slides for Java जोड़ें। आप JAR फ़ाइलों को सीधे जोड़कर या Maven या Gradle जैसे बिल्ड टूल का उपयोग करके ऐसा कर सकते हैं।
## चरण 2: एक नई प्रस्तुति बनाएँ
एक नया पावरपॉइंट प्रेजेंटेशन ऑब्जेक्ट बनाकर शुरू करें। यह ऑब्जेक्ट वह कैनवास होगा जहाँ आप अपनी कस्टम आकृतियाँ जोड़ेंगे।
```java
Presentation pres = new Presentation();
```
## चरण 3: एक आयताकार आकार जोड़ें
इसके बाद, प्रस्तुति की पहली स्लाइड में एक बुनियादी आयताकार आकार जोड़ें। इस आकार को बाद में एक कस्टम ज्यामिति पथ शामिल करने के लिए संशोधित किया जाएगा।
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## चरण 4: ज्यामिति पथ को पुनः प्राप्त करें और संशोधित करें
आयत आकार के ज्यामिति पथ को पुनः प्राप्त करें और इसके भरण मोड को संशोधित करें `None`यह चरण महत्वपूर्ण है क्योंकि यह आपको इस पथ को किसी अन्य कस्टम ज्यामिति पथ के साथ संयोजित करने की अनुमति देता है।
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## चरण 5: टेक्स्ट से कस्टम ज्यामिति पथ बनाएँ
अब, टेक्स्ट के आधार पर एक कस्टम ज्यामिति पथ बनाएँ। इसमें एक टेक्स्ट स्ट्रिंग को ग्राफ़िकल पथ में बदलना और फिर उस पथ को ज्यामिति पथ में बदलना शामिल है।
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## चरण 6: ज्यामिति पथों को संयोजित करें
मूल ज्यामिति पथ को नए पाठ-आधारित ज्यामिति पथ के साथ संयोजित करें और इस संयोजन को आकृति पर सेट करें।
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## चरण 7: प्रस्तुति सहेजें
अंत में, संशोधित प्रस्तुति को एक फ़ाइल में सहेजें। यह आपके कस्टम आकृतियों के साथ एक PowerPoint फ़ाइल आउटपुट करेगा।
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## निष्कर्ष
बधाई हो! आपने अभी-अभी Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में एक कस्टम ज्यामिति आकृति बनाई है। इस ट्यूटोरियल ने आपको अपने प्रोजेक्ट को सेट करने से लेकर ज्यामिति पथ बनाने और संयोजित करने तक प्रत्येक चरण के बारे में बताया। इन तकनीकों में महारत हासिल करके, आप अपनी प्रस्तुतियों में अद्वितीय और आकर्षक तत्व जोड़ सकते हैं, जिससे वे अलग दिखें।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, जावा में PowerPoint फ़ाइलों के साथ काम करने के लिए एक शक्तिशाली API है। यह आपको प्रोग्रामेटिक रूप से प्रस्तुतियाँ बनाने, संशोधित करने और परिवर्तित करने की अनुमति देता है।
### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?
आप नवीनतम संस्करण को यहाँ से डाउनलोड कर सकते हैं [डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/) और JAR फ़ाइलों को अपने प्रोजेक्ट में जोड़ें.
### क्या मैं Aspose.Slides का निःशुल्क उपयोग कर सकता हूँ?
Aspose.Slides एक निःशुल्क परीक्षण संस्करण प्रदान करता है, जिसे आप यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/)पूर्ण कार्यक्षमता के लिए, आपको लाइसेंस खरीदना होगा।
### ShapeUtil क्लास का उपयोग क्या है?
The `ShapeUtil` Aspose.Slides में क्लास आकृतियों के साथ काम करने के लिए उपयोगिता विधियां प्रदान करता है, जैसे कि ग्राफिकल पथों को ज्यामिति पथों में परिवर्तित करना।
### मुझे Aspose.Slides के लिए समर्थन कहां मिल सकता है?
आप यहाँ से सहायता प्राप्त कर सकते हैं [Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}