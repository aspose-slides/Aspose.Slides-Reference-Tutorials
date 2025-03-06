---
title: जावा का उपयोग करके पावरपॉइंट में वर्डआर्ट बनाएं
linktitle: जावा का उपयोग करके पावरपॉइंट में वर्डआर्ट बनाएं
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ Java का उपयोग करके PowerPoint प्रस्तुतियों में आकर्षक वर्डआर्ट बनाना सीखें। डेवलपर्स के लिए चरण-दर-चरण ट्यूटोरियल।
weight: 26
url: /hi/java/java-powerpoint-text-font-customization/create-wordart-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके पावरपॉइंट में वर्डआर्ट बनाएं

## परिचय
आज के डिजिटल संचार परिदृश्य में गतिशील और आकर्षक प्रस्तुतियाँ बनाना महत्वपूर्ण है। Aspose.Slides for Java, PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए शक्तिशाली उपकरण प्रदान करता है, जो डेवलपर्स को निर्माण प्रक्रिया को बढ़ाने और स्वचालित करने के लिए व्यापक क्षमताएँ प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Slides के साथ Java का उपयोग करके PowerPoint प्रस्तुतियों में WordArt बनाने का तरीका जानेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. जावा डेवलपमेंट किट (JDK): JDK संस्करण 8 या उच्चतर स्थापित करें।
2.  Aspose.Slides for Java: Aspose.Slides for Java लाइब्रेरी डाउनलोड करें और सेट अप करें। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): किसी भी जावा समर्थित IDE का उपयोग करें जैसे कि IntelliJ IDEA, Eclipse, या NetBeans.
## पैकेज आयात करें
सबसे पहले, आवश्यक Aspose.Slides क्लासेस को अपने जावा प्रोजेक्ट में आयात करें:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.IOException;
```
## चरण 1: एक नई प्रस्तुति बनाएँ
Aspose.Slides का उपयोग करके एक नया पावरपॉइंट प्रेजेंटेशन बनाकर आरंभ करें:
```java
String resultPath = "Your_Output_Directory/WordArt_out.pptx";
Presentation pres = new Presentation();
```
## चरण 2: वर्डआर्ट आकार जोड़ें
इसके बाद, प्रस्तुति की पहली स्लाइड में वर्डआर्ट आकृति जोड़ें:
```java
// वर्डआर्ट के लिए एक स्वचालित आकार (आयताकार) बनाएँ
IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 314, 122, 400, 215.433f);
// आकृति के टेक्स्ट फ़्रेम तक पहुँचें
ITextFrame textFrame = shape.getTextFrame();
```
## चरण 3: टेक्स्ट और फ़ॉर्मेटिंग सेट करें
वर्डआर्ट के लिए पाठ सामग्री और स्वरूपण विकल्प सेट करें:
```java
// पाठ सामग्री सेट करें
Portion portion = (Portion)textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
portion.setText("Aspose.Slides");
// फ़ॉन्ट और आकार सेट करें
FontData fontData = new FontData("Arial Black");
portion.getPortionFormat().setLatinFont(fontData);
portion.getPortionFormat().setFontHeight(36);
// भरण और रूपरेखा रंग सेट करें
portion.getPortionFormat().getFillFormat().setFillType(FillType.Pattern);
portion.getPortionFormat().getFillFormat().getPatternFormat().getForeColor().setColor(Color.getColor("16762880"));
portion.getPortionFormat().getFillFormat().getPatternFormat().getBackColor().setColor(Color.WHITE);
portion.getPortionFormat().getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.SmallGrid);
portion.getPortionFormat().getLineFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## चरण 4: प्रभाव लागू करें
वर्डआर्ट पर छाया, प्रतिबिंब, चमक और 3D प्रभाव लागू करें:
```java
// छाया प्रभाव जोड़ें
portion.getPortionFormat().getEffectFormat().enableOuterShadowEffect();
portion.getPortionFormat().getEffectFormat().getOuterShadowEffect().getShadowColor().setColor(Color.BLACK);
// प्रतिबिंब प्रभाव जोड़ें
portion.getPortionFormat().getEffectFormat().enableReflectionEffect();
// चमक प्रभाव जोड़ें
portion.getPortionFormat().getEffectFormat().enableGlowEffect();
// 3D प्रभाव जोड़ें
textFrame.getTextFrameFormat().setThreeDFormat(new ThreeDFormat());
```
## चरण 5: प्रस्तुति सहेजें
अंत में, प्रस्तुति को निर्दिष्ट आउटपुट निर्देशिका में सहेजें:
```java
pres.save(resultPath, SaveFormat.Pptx);
```
## निष्कर्ष
इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि PowerPoint प्रस्तुतियों में प्रोग्रामेटिक रूप से आकर्षक वर्डआर्ट बनाने के लिए Aspose.Slides for Java का लाभ कैसे उठाया जाए। यह क्षमता डेवलपर्स को प्रस्तुति अनुकूलन को स्वचालित करने, व्यावसायिक संचार में उत्पादकता और रचनात्मकता को बढ़ाने में सक्षम बनाती है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Slides for Java जटिल एनिमेशन को संभाल सकता है?
हां, Aspose.Slides पावरपॉइंट प्रस्तुतियों में एनिमेशन और संक्रमण के लिए व्यापक समर्थन प्रदान करता है।
### मैं Aspose.Slides for Java के लिए और अधिक उदाहरण और दस्तावेज़ कहां पा सकता हूं?
 आप विस्तृत दस्तावेज़ और उदाहरण देख सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
### क्या Aspose.Slides एंटरप्राइज़-स्तरीय अनुप्रयोगों के लिए उपयुक्त है?
बिल्कुल, Aspose.Slides को मापनीयता और प्रदर्शन के लिए डिज़ाइन किया गया है, जो इसे उद्यम उपयोग के लिए आदर्श बनाता है।
### क्या मैं खरीदने से पहले Aspose.Slides for Java आज़मा सकता हूँ?
 हां, आप निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए तकनीकी सहायता कैसे प्राप्त कर सकता हूं?
 आप Aspose मंचों पर समुदाय और विशेषज्ञों से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
