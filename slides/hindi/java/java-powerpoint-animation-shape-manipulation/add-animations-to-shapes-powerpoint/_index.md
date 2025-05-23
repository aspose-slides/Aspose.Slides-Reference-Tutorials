---
"description": "इस विस्तृत ट्यूटोरियल के साथ Aspose.Slides for Java का उपयोग करके PowerPoint में आकृतियों में एनिमेशन जोड़ना सीखें। आकर्षक प्रस्तुतियाँ बनाने के लिए बिल्कुल सही।"
"linktitle": "PowerPoint में आकृतियों में एनिमेशन जोड़ें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "PowerPoint में आकृतियों में एनिमेशन जोड़ें"
"url": "/hi/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint में आकृतियों में एनिमेशन जोड़ें

## परिचय
आकर्षक प्रस्तुतियाँ बनाने के लिए अक्सर आकृतियों और पाठ में एनिमेशन जोड़ने की आवश्यकता होती है। एनिमेशन आपकी स्लाइड्स को अधिक गतिशील और आकर्षक बना सकते हैं, जिससे आपके दर्शकों की दिलचस्पी बनी रहेगी। इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में आकृतियों में एनिमेशन जोड़ने की प्रक्रिया के बारे में बताएँगे। इस लेख के अंत तक, आप आसानी से पेशेवर एनिमेशन बनाने में सक्षम हो जाएँगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, आइए सुनिश्चित करें कि आपके पास वह सब कुछ है जो आपको चाहिए:
1. Aspose.Slides for Java लाइब्रेरी: आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित होनी चाहिए। आप ऐसा कर सकते हैं [यहाँ पर डाउनलोड करो](https://releases.aspose.com/slides/java/).
2. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपकी मशीन पर JDK स्थापित है।
3. एकीकृत विकास वातावरण (IDE): किसी भी Java IDE जैसे IntelliJ IDEA, Eclipse, या NetBeans का उपयोग करें।
4. जावा का बुनियादी ज्ञान: यह ट्यूटोरियल मानता है कि आपको जावा प्रोग्रामिंग की बुनियादी समझ है।
## पैकेज आयात करें
आरंभ करने के लिए, आपको Aspose.Slides और अन्य आवश्यक Java क्लासेस के लिए आवश्यक पैकेज आयात करने होंगे।
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## चरण 1: अपनी प्रोजेक्ट निर्देशिका सेट करें
सबसे पहले, अपनी प्रोजेक्ट फ़ाइलों के लिए एक निर्देशिका बनाएं।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
इसके बाद, उदाहरण बनाएं `Presentation` क्लास का उपयोग करके अपनी पावरपॉइंट फ़ाइल का प्रतिनिधित्व करें।
```java
// PPTX का प्रतिनिधित्व करने वाला इन्स्टेन्शियेट प्रेजेंटेशन क्लास
Presentation pres = new Presentation();
```
## चरण 3: पहली स्लाइड तक पहुंचें
अब, प्रस्तुति में पहली स्लाइड पर पहुँचें जहाँ आप एनिमेशन जोड़ेंगे।
```java
// पहली स्लाइड पर पहुँचें
ISlide sld = pres.getSlides().get_Item(0);
```
## चरण 4: स्लाइड में आकृति जोड़ें
स्लाइड में एक आयताकार आकार जोड़ें और उसमें कुछ पाठ डालें।
```java
// स्लाइड में आयताकार आकार जोड़ें
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## चरण 5: एनिमेशन प्रभाव लागू करें
आकृति पर "पथफुटबॉल" एनीमेशन प्रभाव लागू करें।
```java
// PathFootBall एनीमेशन प्रभाव जोड़ें
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## चरण 6: एक इंटरैक्टिव ट्रिगर बनाएँ
एक बटन आकार बनाएं जो क्लिक करने पर एनीमेशन को ट्रिगर करेगा।
```java
// एनीमेशन को ट्रिगर करने के लिए एक "बटन" आकार बनाएं
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## चरण 7: इंटरैक्टिव अनुक्रम को परिभाषित करें
बटन के लिए प्रभावों का अनुक्रम निर्धारित करें.
```java
// बटन के लिए प्रभावों का एक क्रम बनाएँ
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## चरण 8: कस्टम उपयोगकर्ता पथ जोड़ें
आकृति में एक कस्टम उपयोगकर्ता पथ एनीमेशन जोड़ें.
```java
// कस्टम उपयोगकर्ता पथ एनीमेशन प्रभाव जोड़ें
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// गति प्रभाव बनाएँ
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// पथ बिंदु परिभाषित करें
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## चरण 9: प्रस्तुति सहेजें
अंत में, प्रस्तुति को अपने इच्छित स्थान पर सेव करें।
```java
// प्रस्तुति को PPTX फ़ाइल के रूप में सहेजें
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// प्रस्तुति ऑब्जेक्ट का निपटान करें
if (pres != null) pres.dispose();
```
## निष्कर्ष
और अब यह हो गया! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में आकृतियों में सफलतापूर्वक एनिमेशन जोड़ दिए हैं। यह शक्तिशाली लाइब्रेरी गतिशील प्रभावों के साथ आपकी प्रस्तुतियों को बेहतर बनाना आसान बनाती है, जिससे यह सुनिश्चित होता है कि आपके दर्शक जुड़े रहें। याद रखें, अभ्यास से निपुणता आती है, इसलिए अलग-अलग प्रभावों और ट्रिगर्स के साथ प्रयोग करते रहें ताकि पता चल सके कि आपकी ज़रूरतों के लिए सबसे अच्छा क्या काम करता है।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, पावरपॉइंट प्रस्तुतियों को प्रोग्रामेटिक रूप से बनाने, संशोधित करने और उनमें हेरफेर करने के लिए एक शक्तिशाली API है।
### क्या मैं Aspose.Slides का निःशुल्क उपयोग कर सकता हूँ?
आप Aspose.Slides को निःशुल्क आज़मा सकते हैं [अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/)निरंतर उपयोग के लिए, सशुल्क लाइसेंस की आवश्यकता है।
### कौन से Java संस्करण Aspose.Slides के साथ संगत हैं?
Aspose.Slides Java SE 6 और इसके बाद के संस्करण का समर्थन करता है।
### मैं एकाधिक आकृतियों में अलग-अलग एनिमेशन कैसे जोड़ूं?
आप प्रत्येक आकृति के लिए चरणों को दोहराकर और आवश्यकतानुसार विभिन्न प्रभाव निर्दिष्ट करके एकाधिक आकृतियों में भिन्न एनिमेशन जोड़ सकते हैं।
### मैं और अधिक उदाहरण और दस्तावेज कहां पा सकता हूं?
इसकी जाँच पड़ताल करो [प्रलेखन](https://reference.aspose.com/slides/java/) और [सहयता मंच](https://forum.aspose.com/c/slides/11) अधिक उदाहरण और सहायता के लिए.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}