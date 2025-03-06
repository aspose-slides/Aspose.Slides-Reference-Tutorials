---
title: PowerPoint में आकृतियों पर 3D रोटेशन प्रभाव लागू करें
linktitle: PowerPoint में आकृतियों पर 3D रोटेशन प्रभाव लागू करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: इस व्यापक, चरण-दर-चरण ट्यूटोरियल के साथ Java के लिए Aspose.Slides का उपयोग करके PowerPoint में आकृतियों पर 3D रोटेशन प्रभाव लागू करना सीखें।
weight: 12
url: /hi/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
क्या आप अपने पावरपॉइंट प्रेजेंटेशन को अगले स्तर पर ले जाने के लिए तैयार हैं? 3D रोटेशन इफ़ेक्ट जोड़ने से आपकी स्लाइड्स ज़्यादा गतिशील और आकर्षक बन सकती हैं। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह चरण-दर-चरण ट्यूटोरियल आपको दिखाएगा कि Aspose.Slides for Java का उपयोग करके PowerPoint में आकृतियों पर 3D रोटेशन इफ़ेक्ट कैसे लागू करें। चलिए शुरू करते हैं!
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित चीज़ें मौजूद हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं।[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java का नवीनतम संस्करण यहाँ से डाउनलोड करें[लिंक को डाउनलोड करें](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (आईडीई): कोडिंग के लिए इंटेलीज आईडीईए या एक्लिप्स जैसे आईडीई का उपयोग करें।
4.  वैध लाइसेंस: यदि आपके पास लाइसेंस नहीं है, तो आप[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) सुविधाओं को आज़माने के लिए.
## पैकेज आयात करें
सबसे पहले, आइए अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। ये आयात आपको Aspose.Slides के साथ प्रस्तुतियाँ और आकृतियों को संभालने में मदद करेंगे।
```java
import com.aspose.slides.*;

```
## चरण 1: अपना प्रोजेक्ट सेट करें
कोड में गोता लगाने से पहले, अपना प्रोजेक्ट वातावरण सेट करें। सुनिश्चित करें कि आपने अपने प्रोजेक्ट की निर्भरताओं में Aspose.Slides for Java को जोड़ा है।
अपने प्रोजेक्ट में Aspose.Slides जोड़ें:
1.  Aspose.Slides JAR फ़ाइलें यहाँ से डाउनलोड करें[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
2. इन JAR फ़ाइलों को अपने प्रोजेक्ट के बिल्ड पथ में जोड़ें।
## चरण 2: एक नया पावरपॉइंट प्रेजेंटेशन बनाएं
इस चरण में, हम एक नया पावरपॉइंट प्रेजेंटेशन बनाएंगे।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation pres = new Presentation();
```
यह कोड स्निपेट एक नया प्रेजेंटेशन ऑब्जेक्ट आरंभ करता है, जहां हम अपनी आकृतियां जोड़ेंगे।
## चरण 3: एक आयताकार आकार जोड़ें
अब, आइए पहली स्लाइड में एक आयताकार आकार जोड़ें।
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
यह कोड पहली स्लाइड पर निर्दिष्ट स्थान और आकार पर एक आयताकार आकृति जोड़ता है।
## चरण 4: आयत पर 3D रोटेशन लागू करें
अब, आइए आयताकार आकार पर 3D रोटेशन प्रभाव लागू करें।
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
यहां, हम अपने आयत को 3D लुक देने के लिए गहराई, कैमरा रोटेशन कोण, कैमरा प्रकार और प्रकाश प्रकार सेट करते हैं।
## चरण 5: एक रेखा आकार जोड़ें
आइए स्लाइड में एक और आकृति, इस बार एक रेखा, जोड़ें।
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
यह कोड स्लाइड पर एक रेखा आकार रखता है।
## चरण 6: रेखा पर 3D रोटेशन लागू करें
अंत में, हम रेखा आकार पर 3D रोटेशन प्रभाव लागू करेंगे।
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
आयत के समान, हम रेखा आकार के लिए 3D गुण सेट करते हैं।
## चरण 7: प्रेजेंटेशन सहेजें
अपनी आकृतियों को जोड़ने और कॉन्फ़िगर करने के बाद, प्रस्तुति को सहेजें।
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
यह कोड आपकी प्रस्तुति को निर्दिष्ट फ़ाइल नाम के साथ वांछित प्रारूप में सहेजता है।
## निष्कर्ष
 बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में आकृतियों पर 3D रोटेशन प्रभाव सफलतापूर्वक लागू किया है। इन चरणों का पालन करके, आप आकर्षक और गतिशील प्रस्तुतिकरण बना सकते हैं। आगे के अनुकूलन और अधिक उन्नत सुविधाओं के लिए, देखें[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/).
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, पावरपॉइंट प्रस्तुतियों को प्रोग्रामेटिक रूप से बनाने, संशोधित करने और उनमें हेरफेर करने के लिए एक शक्तिशाली API है।
### क्या मैं Java के लिए Aspose.Slides निःशुल्क आज़मा सकता हूँ?
 हाँ, आप प्राप्त कर सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) या एक[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) सुविधाओं का परीक्षण करने के लिए.
### मैं Aspose.Slides में किस प्रकार की आकृतियों में 3D प्रभाव जोड़ सकता हूँ?
आप विभिन्न आकृतियों जैसे आयत, रेखाएँ, दीर्घवृत्त और कस्टम आकृतियों में 3D प्रभाव जोड़ सकते हैं।
### मैं Java के लिए Aspose.Slides का समर्थन कैसे प्राप्त करूं?
 आप यहां जा सकते हैं[सहयता मंच](https://forum.aspose.com/c/slides/11) सहायता के लिए और किसी भी मुद्दे पर चर्चा करने के लिए।
### क्या मैं व्यावसायिक परियोजनाओं में Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
 हां, लेकिन आपको लाइसेंस खरीदना होगा। आप इसे यहां से खरीद सकते हैं।[खरीद पृष्ठ](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
