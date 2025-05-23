---
"description": "हमारे चरण-दर-चरण गाइड के साथ Aspose.Slides for Java का उपयोग करके PowerPoint में आकृतियों पर बेवल प्रभाव लागू करना सीखें। अपनी प्रस्तुतियों को बेहतर बनाएँ।"
"linktitle": "पावरपॉइंट में आकृतियों पर बेवल प्रभाव लागू करें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "पावरपॉइंट में आकृतियों पर बेवल प्रभाव लागू करें"
"url": "/hi/java/java-powerpoint-animation-shape-manipulation/apply-bevel-effects-shapes-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# पावरपॉइंट में आकृतियों पर बेवल प्रभाव लागू करें

## परिचय
अपने दर्शकों का ध्यान आकर्षित करने और उसे बनाए रखने के लिए आकर्षक प्रस्तुतिकरण बनाना बहुत ज़रूरी है। आकृतियों में बेवल इफ़ेक्ट जोड़ने से आपकी स्लाइड्स की समग्र सुंदरता बढ़ सकती है, जिससे आपकी प्रस्तुति अलग नज़र आएगी। इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint में आकृतियों पर बेवल इफ़ेक्ट लगाने की प्रक्रिया के बारे में बताएँगे। चाहे आप डेवलपर हों जो प्रस्तुति निर्माण को स्वचालित करना चाहते हों या कोई ऐसा व्यक्ति जो डिज़ाइन के साथ छेड़छाड़ करना पसंद करता हो, यह गाइड आपके लिए है।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके पास JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं [ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Slides for Java लाइब्रेरी: लाइब्रेरी को यहां से डाउनलोड करें [जावा के लिए Aspose.Slides](https://releases.aspose.com/slides/java/).
- IDE (एकीकृत विकास वातावरण): अपनी पसंद का कोई भी IDE उपयोग करें, जैसे IntelliJ IDEA, Eclipse, या NetBeans.
- Aspose लाइसेंस: Aspose.Slides को बिना किसी सीमा के उपयोग करने के लिए, लाइसेंस प्राप्त करें [Aspose खरीद](https://purchase.aspose.com/buy) या प्राप्त करें [अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) मूल्यांकन हेतु.
## पैकेज आयात करें
सबसे पहले, आपको अपने जावा प्रोजेक्ट में Aspose.Slides के साथ काम करने के लिए आवश्यक पैकेज आयात करने होंगे। आप इसे इस प्रकार कर सकते हैं:
```java
import com.aspose.slides.*;

import java.awt.*;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
कोडिंग शुरू करने से पहले, सुनिश्चित करें कि आपका प्रोजेक्ट सही तरीके से सेट अप किया गया है। अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides लाइब्रेरी शामिल करें। यदि आप Maven का उपयोग कर रहे हैं, तो अपने प्रोजेक्ट में निम्न निर्भरता जोड़ें `pom.xml` फ़ाइल:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>23.6</version>
</dependency>
```
## चरण 2: एक प्रस्तुति बनाएं
Aspose.Slides के साथ काम करना शुरू करने के लिए, आपको इसका एक उदाहरण बनाना होगा `Presentation` क्लास. यह क्लास एक PowerPoint फ़ाइल का प्रतिनिधित्व करता है.
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation pres = new Presentation();
```
## चरण 3: पहली स्लाइड तक पहुंचें
प्रस्तुति बनाने के बाद, पहली स्लाइड पर पहुँचें जहाँ आप आकृतियाँ जोड़ेंगे और उनमें परिवर्तन करेंगे।
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## चरण 4: स्लाइड में आकृति जोड़ें
अब, स्लाइड में एक आकृति जोड़ें। इस उदाहरण में, हम एक दीर्घवृत्त जोड़ेंगे।
```java
// स्लाइड पर आकृति जोड़ें
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.getFillFormat().setFillType(FillType.Solid);
shape.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
ILineFillFormat format = shape.getLineFormat().getFillFormat();
format.setFillType(FillType.Solid);
format.getSolidFillColor().setColor(Color.ORANGE);
shape.getLineFormat().setWidth(2.0);
```
## चरण 5: आकृति पर बेवल प्रभाव लागू करें
इसके बाद, आकृति को त्रि-आयामी स्वरूप देने के लिए उस पर बेवल प्रभाव लागू करें।
```java
// आकृति के ThreeDFormat गुण सेट करें
shape.getThreeDFormat().setDepth((short) 4);
shape.getThreeDFormat().getBevelTop().setBevelType(BevelPresetType.Circle);
shape.getThreeDFormat().getBevelTop().setHeight(6);
shape.getThreeDFormat().getBevelTop().setWidth(6);
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.ThreePt);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
```
## चरण 6: प्रस्तुति सहेजें
अंत में, प्रस्तुति को PPTX फ़ाइल के रूप में अपनी निर्दिष्ट निर्देशिका में सहेजें।
```java
// प्रस्तुति को PPTX फ़ाइल के रूप में लिखें
pres.save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
## चरण 7: प्रेजेंटेशन ऑब्जेक्ट को हटाएँ
संसाधनों को मुक्त करने के लिए, हमेशा सुनिश्चित करें कि `Presentation` वस्तु का उचित तरीके से निपटान किया जाता है।
```java
if (pres != null) pres.dispose();
```
## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में आकृतियों पर बेवल प्रभाव लागू करना एक सरल प्रक्रिया है जो आपकी स्लाइड्स की दृश्य अपील को काफी हद तक बढ़ा सकती है। इस गाइड में बताए गए चरणों का पालन करके, आप आसानी से पेशेवर और आकर्षक प्रस्तुतियाँ बना सकते हैं। [Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) अधिक विस्तृत जानकारी और उन्नत सुविधाओं के लिए.
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली API है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने, संशोधित करने और प्रबंधित करने की अनुमति देता है।
### क्या मैं Java के लिए Aspose.Slides का निःशुल्क उपयोग कर सकता हूँ?
Aspose.Slides एक निःशुल्क परीक्षण प्रदान करता है जिसे आप यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/)पूर्ण सुविधाओं के लिए, आपको लाइसेंस खरीदना होगा।
### मैं अपनी स्लाइडों में किस प्रकार की आकृतियाँ जोड़ सकता हूँ?
आप Java के लिए Aspose.Slides का उपयोग करके विभिन्न आकार जैसे आयत, दीर्घवृत्त, रेखाएँ और कस्टम आकार जोड़ सकते हैं।
### क्या बेवेल के अलावा अन्य 3D प्रभाव लागू करना संभव है?
हां, Aspose.Slides for Java आपको गहराई, प्रकाश और कैमरा प्रभाव सहित विभिन्न 3D प्रभाव लागू करने की अनुमति देता है।
### मैं Aspose.Slides for Java के लिए समर्थन कहां से प्राप्त कर सकता हूं?
आप Aspose समुदाय और सहायता टीम से सहायता प्राप्त कर सकते हैं [सहयता मंच](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}