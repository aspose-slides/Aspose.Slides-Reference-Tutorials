---
title: जावा पावरपॉइंट प्रेजेंटेशन में इनर शैडो लागू करें
linktitle: जावा पावरपॉइंट प्रेजेंटेशन में इनर शैडो लागू करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में आकृतियों पर आंतरिक छाया प्रभाव लागू करना सीखें। इस चरण-दर-चरण मार्गदर्शिका के साथ अपनी स्लाइड्स को बेहतर बनाएँ।
weight: 12
url: /hi/java/java-powerpoint-animation-effects/apply-inner-shadow-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
अपने विचारों को प्रभावी ढंग से संप्रेषित करने के लिए दृश्य रूप से आकर्षक प्रस्तुतियाँ बनाना महत्वपूर्ण है। आपके प्रस्तुतियों को महत्वपूर्ण रूप से बेहतर बनाने वाले उपकरणों में से एक आंतरिक छाया का उपयोग है। यह ट्यूटोरियल आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में आकृतियों पर आंतरिक छाया लागू करने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा। इस ट्यूटोरियल के अंत तक, आपको आश्चर्यजनक प्रभाव बनाने के लिए स्लाइड तत्वों में हेरफेर करने के तरीके के बारे में व्यापक समझ होगी।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके मशीन पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं।[जावा वेबसाइट](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: से नवीनतम संस्करण डाउनलोड करें[Aspose.Slides डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (आईडीई): इंटेलीज आईडीईए या एक्लिप्स जैसा आईडीई आपकी परियोजना को अधिक कुशलतापूर्वक प्रबंधित करने में आपकी सहायता करेगा।
4.  Aspose.Slides लाइसेंस: अस्थायी लाइसेंस के लिए, यहां जाएं[Aspose अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) . खरीद विकल्पों के लिए, जाँच करें[Aspose खरीद पृष्ठ](https://purchase.aspose.com/buy).
## पैकेज आयात करें
सबसे पहले, आपको आवश्यक पैकेज आयात करने होंगे। ये आपको Aspose.Slides द्वारा प्रदान की गई कक्षाओं और विधियों का उपयोग करने में सक्षम करेंगे।
```java
import com.aspose.slides.*;
import java.io.File;
```
## चरण 1: अपनी प्रोजेक्ट निर्देशिका सेट करें
सबसे पहले, अपनी प्रोजेक्ट डायरेक्टरी सेट करें। यह वह जगह होगी जहाँ आपकी पावरपॉइंट फ़ाइलें और जावा क्लासेस होंगी।
```java
String dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
इस चरण में, हम सुनिश्चित करते हैं कि आपकी प्रोजेक्ट फ़ाइलों के लिए निर्देशिका मौजूद है। अगर ऐसा नहीं है, तो हम इसे बनाते हैं।
## चरण 2: प्रस्तुति आरंभ करें
 इसके बाद, आपको इसका एक उदाहरण बनाना होगा`Presentation` क्लास। यह ऑब्जेक्ट पावरपॉइंट प्रेजेंटेशन में हेरफेर करने के लिए आपका प्राथमिक इंटरफ़ेस होगा।
```java
Presentation pres = new Presentation();
```
## चरण 3: पहली स्लाइड तक पहुंचें
अब, अपनी प्रस्तुति की पहली स्लाइड तक पहुँचें। स्लाइड्स एक संग्रह में संग्रहीत की जाती हैं, और आप इसके इंडेक्स का उपयोग करके पहली स्लाइड को पुनः प्राप्त कर सकते हैं।
```java
ISlide sld = pres.getSlides().get_Item(0);
```
## चरण 4: स्लाइड में आकृति जोड़ें
हम स्लाइड में एक आयताकार आकार जोड़ेंगे। इस आकार में बाद में टेक्स्ट और एक आंतरिक छाया लागू की जाएगी।
```java
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## चरण 5: आकृति में पाठ जोड़ें
### टेक्स्टफ्रेम बनाएं और उस तक पहुंचें
 आकृति में पाठ जोड़ने के लिए, आपको बनाना और उस तक पहुँचना होगा`TextFrame`.
```java
ashp.addTextFrame(" ");
ITextFrame txtFrame = ashp.getTextFrame();
```
### पाठ सेट करें
आयत आकार में पहुँच कर पाठ जोड़ें`Paragraph` और`Portion` वस्तुएं.
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## चरण 6: आंतरिक छाया लागू करें
इस चरण में आंतरिक छाया प्रभाव बनाना और उसे आकृति पर लागू करना शामिल है।
```java
IEffectFormat effectFormat = ashp.getEffectFormat();
effectFormat.enableInnerShadowEffect();
IInnerShadowEffect innerShadow = effectFormat.getInnerShadowEffect();
innerShadow.setBlurRadius(5.0);
innerShadow.setDirection(45.0);
innerShadow.setDistance(4.0);
innerShadow.getShadowColor().setColor(java.awt.Color.BLACK);
```
## चरण 7: प्रेजेंटेशन सहेजें
अंत में, प्रेजेंटेशन को निर्दिष्ट निर्देशिका में सेव करें। यह चरण सुनिश्चित करता है कि आपके परिवर्तन किसी फ़ाइल में लिखे गए हैं।
```java
pres.save(dataDir + "ApplyInnerShadow_out.pptx", SaveFormat.Pptx);
```
## चरण 8: संसाधनों को साफ़ करें
 मेमोरी लीक से बचने के लिए, हमेशा इसका निपटान करें`Presentation` जब आप किसी वस्तु के साथ काम कर लें, तो उसे हटा दें।
```java
if (pres != null) pres.dispose();
```
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में आकृति पर सफलतापूर्वक आंतरिक छाया लागू की है। इस ट्यूटोरियल में आपके प्रोजेक्ट को सेट करने से लेकर अंतिम प्रेजेंटेशन को सहेजने तक के आवश्यक चरणों को शामिल किया गया है। इन कौशलों के साथ, अब आप अपनी प्रस्तुतियों को विभिन्न प्रभावों के साथ बेहतर बना सकते हैं ताकि उन्हें अधिक आकर्षक और दृश्यमान रूप से आकर्षक बनाया जा सके।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से बनाने और उनमें हेरफेर करने के लिए एक शक्तिशाली API है। यह डेवलपर्स को Microsoft PowerPoint की आवश्यकता के बिना प्रस्तुतियों के साथ काम करने की अनुमति देता है।
### क्या मैं लाइसेंस के बिना Aspose.Slides का उपयोग कर सकता हूँ?
 Aspose.Slides एक निःशुल्क परीक्षण प्रदान करता है जिसे आप यहाँ से डाउनलोड कर सकते हैं।[Aspose निःशुल्क परीक्षण पृष्ठ](https://releases.aspose.com/)हालाँकि, पूर्ण कार्यक्षमता के लिए लाइसेंस की आवश्यकता होती है।
### मैं स्लाइड में विभिन्न आकृतियाँ कैसे जोड़ूँ?
 आप इसका उपयोग करके विभिन्न आकृतियाँ जोड़ सकते हैं`addAutoShape` विधि और आकार प्रकार निर्दिष्ट करना, जैसे`ShapeType.Rectangle`, `ShapeType.Ellipse`, वगैरह।
### क्या मैं छाया प्रभाव को और अधिक अनुकूलित कर सकता हूँ?
हां, आप छाया प्रभाव के विभिन्न मापदंडों को, जैसे धुंधलापन त्रिज्या, दिशा, दूरी और रंग, अपनी आवश्यकताओं के अनुरूप अनुकूलित कर सकते हैं।
### मैं अधिक विस्तृत दस्तावेज कहां पा सकता हूं?
 आप इसका संदर्भ ले सकते हैं[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) विस्तृत जानकारी और उदाहरण के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
