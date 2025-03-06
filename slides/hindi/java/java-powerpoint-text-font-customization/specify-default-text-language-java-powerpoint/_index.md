---
title: जावा पावरपॉइंट में डिफ़ॉल्ट टेक्स्ट भाषा निर्दिष्ट करें
linktitle: जावा पावरपॉइंट में डिफ़ॉल्ट टेक्स्ट भाषा निर्दिष्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java PowerPoint में डिफ़ॉल्ट टेक्स्ट भाषा निर्दिष्ट करना सीखें। प्रोग्रामेटिक रूप से टेक्स्ट स्थानीयकरण की तलाश करने वाले डेवलपर्स के लिए बिल्कुल सही।
weight: 21
url: /hi/java/java-powerpoint-text-font-customization/specify-default-text-language-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पावरपॉइंट में डिफ़ॉल्ट टेक्स्ट भाषा निर्दिष्ट करें

## परिचय
जावा एप्लिकेशन डेवलपमेंट के क्षेत्र में, PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से प्रबंधित और हेरफेर करना एक सामान्य आवश्यकता है। जावा के लिए Aspose.Slides कार्यात्मकताओं का एक मजबूत सेट प्रदान करता है जो डेवलपर्स को जावा कोड के माध्यम से PowerPoint प्रस्तुतियों को सहजता से बनाने, संशोधित करने और बढ़ाने में सक्षम बनाता है। इस ट्यूटोरियल का उद्देश्य आपको Aspose.Slides का उपयोग करके जावा पावरपॉइंट प्रेजेंटेशन में डिफ़ॉल्ट टेक्स्ट भाषा निर्दिष्ट करने के आवश्यक चरणों के माध्यम से मार्गदर्शन करना है।
## आवश्यक शर्तें
इस ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
- एकीकृत विकास वातावरण (आईडीई) जैसे कि इंटेलीज आईडिया या एक्लिप्स की स्थापना।
-  Aspose.Slides for Java लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
-  Aspose.Slides for Java दस्तावेज़ तक पहुंच, जो यहां पाया जा सकता है[यहाँ](https://reference.aspose.com/slides/java/).

## पैकेज आयात करें
कोडिंग शुरू करने से पहले, अपनी जावा फ़ाइल में आवश्यक Aspose.Slides क्लासेस को आयात करना सुनिश्चित करें:
```java
import com.aspose.slides.*;
```
## चरण 1: लोड विकल्प सेट करें
सबसे पहले, प्रस्तुति के लिए लोड विकल्प कॉन्फ़िगर करें, डिफ़ॉल्ट पाठ भाषा निर्दिष्ट करें (`en-US` इस मामले में)।
```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setDefaultTextLanguage("en-US");
```
## चरण 2: प्रस्तुति लोड करें
 एक उदाहरण बनाना`Presentation` किसी मौजूदा पावरपॉइंट प्रेजेंटेशन को लोड करने या नया प्रेजेंटेशन बनाने के लिए कॉन्फ़िगर किए गए लोड विकल्पों का उपयोग करके ऑब्जेक्ट पर राइट-क्लिक करें।
```java
Presentation pres = new Presentation(loadOptions);
```
## चरण 3: टेक्स्ट के साथ आकृति जोड़ें
प्रस्तुति की पहली स्लाइड में एक आयताकार आकृति जोड़ें और इसकी पाठ सामग्री सेट करें।
```java
IAutoShape shp = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 150, 50);
shp.getTextFrame().setText("New Text");
```
## चरण 4: पाठ भागों की भाषा जांचें
जोड़े गए आकार के भीतर पाठ भागों की भाषा सेटिंग्स को पुनः प्राप्त करें और सत्यापित करें।
```java
PortionFormat portionFormat = shp.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat();
System.out.println(portionFormat.getLanguageId());
```
## चरण 5: प्रेजेंटेशन ऑब्जेक्ट को हटाएँ
 उचित निपटान सुनिश्चित करें`Presentation` उपयोग के बाद संसाधनों को छोड़ने पर आपत्ति।
```java
finally {
    if (pres != null) pres.dispose();
}
```

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा है कि PowerPoint प्रेजेंटेशन में प्रोग्रामेटिक रूप से डिफ़ॉल्ट टेक्स्ट भाषा निर्दिष्ट करने के लिए Aspose.Slides for Java का लाभ कैसे उठाया जाए। यह क्षमता आपके प्रेजेंटेशन में टेक्स्ट तत्वों में सुसंगत भाषा सेटिंग सुनिश्चित करने, पठनीयता और स्थानीयकरण प्रयासों को बढ़ाने के लिए महत्वपूर्ण है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं डिफ़ॉल्ट टेक्स्ट भाषा को किसी अन्य भाषा, जैसे फ्रेंच या स्पेनिश, में बदल सकता हूँ?
हां, आप Aspose.Slides for Java का उपयोग करते हुए डिफ़ॉल्ट पाठ भाषा सेट करते समय कोई भी समर्थित भाषा कोड निर्दिष्ट कर सकते हैं।
### क्या Aspose.Slides for Java एंटरप्राइज़-स्तरीय अनुप्रयोगों के लिए उपयुक्त है?
बिल्कुल। Aspose.Slides for Java को स्केलेबिलिटी और प्रदर्शन के लिए डिज़ाइन किया गया है, जो इसे एंटरप्राइज़ वातावरण के लिए आदर्श बनाता है।
### मैं Aspose.Slides for Java के लिए और अधिक उदाहरण और संसाधन कहां पा सकता हूं?
 आप यहां पर विस्तृत दस्तावेज और अतिरिक्त उदाहरण देख सकते हैं[Aspose.Slides for Java दस्तावेज़न पृष्ठ](https://reference.aspose.com/slides/java/).
### क्या Aspose.Slides for Java क्लाउड सेवाओं के साथ एकीकरण का समर्थन करता है?
हां, Aspose.Slides for Java ऐसे API प्रदान करता है जो लोकप्रिय क्लाउड प्लेटफॉर्म के साथ एकीकरण का समर्थन करते हैं।
### क्या मैं खरीदने से पहले Aspose.Slides for Java का मूल्यांकन कर सकता हूँ?
 हां, आप Aspose.Slides for Java का निःशुल्क परीक्षण यहां से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
