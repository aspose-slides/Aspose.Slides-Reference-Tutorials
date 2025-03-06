---
title: जावा में प्रस्तुति भाषा और आकार पाठ सेट करें
linktitle: जावा में प्रस्तुति भाषा और आकार पाठ सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों को स्वचालित करना सीखें। आसानी से प्रोग्रामेटिक रूप से स्लाइड बनाएँ, संशोधित करें और बढ़ाएँ।
weight: 19
url: /hi/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में प्रस्तुति भाषा और आकार पाठ सेट करें

## परिचय
जावा में प्रोग्रामेटिक रूप से पावरपॉइंट प्रेजेंटेशन बनाना और उसमें हेरफेर करना वर्कफ़्लो ऑटोमेशन को सुव्यवस्थित कर सकता है और उत्पादकता को बढ़ा सकता है। जावा के लिए Aspose.Slides इन कार्यों को कुशलतापूर्वक पूरा करने के लिए उपकरणों का एक मजबूत सेट प्रदान करता है। यह ट्यूटोरियल आपको जावा के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन भाषा सेट करने और टेक्स्ट को आकार देने के लिए आवश्यक चरणों के माध्यम से मार्गदर्शन करता है।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा डेवलपमेंट किट (JDK) स्थापित
-  Aspose.Slides for Java लाइब्रेरी, जिसे आप यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/)
- आपके सिस्टम पर IntelliJ IDEA या Eclipse जैसे एकीकृत विकास वातावरण (IDE) की स्थापना
- जावा प्रोग्रामिंग भाषा का बुनियादी ज्ञान
## पैकेज आयात करें
आरंभ करने के लिए, अपनी जावा फ़ाइल में आवश्यक Aspose.Slides पैकेज आयात करें:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## चरण 1: एक प्रेजेंटेशन ऑब्जेक्ट बनाएँ
 आरंभ करके प्रारंभ करें`Presentation` वस्तु:
```java
Presentation pres = new Presentation();
```
इससे एक नया पावरपॉइंट प्रेजेंटेशन तैयार हो जाता है।
## चरण 2: ऑटोशेप जोड़ें और कॉन्फ़िगर करें
इसके बाद, पहली स्लाइड में एक ऑटोशेप जोड़ें और उसके गुण कॉन्फ़िगर करें:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
यहां, हम निर्देशांक (50, 50) पर 200x50 पिक्सेल आयाम वाला एक आयत ऑटोशेप जोड़ते हैं।
## चरण 3: पाठ और भाषा सेट करें
पाठ सामग्री सेट करें और वर्तनी जाँच के लिए भाषा निर्दिष्ट करें:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
 प्रतिस्थापित करें`"Text to apply spellcheck language"` अपने इच्छित पाठ के साथ। भाषा आईडी`"en-EN"`अंग्रेजी (संयुक्त राज्य अमेरिका) निर्दिष्ट करता है।
## चरण 4: प्रस्तुति सहेजें
संशोधित प्रस्तुति को निर्दिष्ट आउटपुट निर्देशिका में सहेजें:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
 प्रतिस्थापन सुनिश्चित करें`"Your Output Directory"` अपने वास्तविक निर्देशिका पथ के साथ जहां आप फ़ाइल को सहेजना चाहते हैं।
## चरण 5: संसाधनों का निपटान करें
 उचित तरीके से निपटान करें`Presentation` संसाधन जारी करने पर आपत्ति:
```java
pres.dispose();
```
मेमोरी लीक से बचने के लिए यह कदम महत्वपूर्ण है।

## निष्कर्ष
निष्कर्ष में, Aspose.Slides for Java प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने और उनमें हेरफेर करने की प्रक्रिया को सरल बनाता है। इन चरणों का पालन करके, आप अपनी आवश्यकताओं के अनुसार प्रस्तुति भाषा को कुशलतापूर्वक सेट कर सकते हैं और टेक्स्ट गुणों को कॉन्फ़िगर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं PowerPoint प्रस्तुतियाँ बनाने के लिए Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, Aspose.Slides पूरी तरह से प्रोग्रामेटिक रूप से प्रस्तुतियाँ बनाने के लिए व्यापक API प्रदान करता है।
### मैं Java के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड्स में टेक्स्ट पर अलग-अलग फ़ॉन्ट कैसे लागू कर सकता हूं?
 आप फ़ॉन्ट गुणधर्म सेट कर सकते हैं`IPortionFormat` पाठ भागों से जुड़ी वस्तुएँ.
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 विस्तृत दस्तावेज उपलब्ध है[यहाँ](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java के लिए कौन से समर्थन विकल्प उपलब्ध हैं?
 आप Aspose.Slides फोरम पर जा सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
