---
"description": "जानें कि Aspose.Slides के साथ जावा का उपयोग करके PowerPoint में स्मार्टआर्ट नोड टेक्स्ट को कैसे अपडेट किया जाए, जिससे प्रस्तुति अनुकूलन में वृद्धि हो।"
"linktitle": "जावा का उपयोग करके स्मार्टआर्ट नोड पर टेक्स्ट बदलें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा का उपयोग करके स्मार्टआर्ट नोड पर टेक्स्ट बदलें"
"url": "/hi/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके स्मार्टआर्ट नोड पर टेक्स्ट बदलें

## परिचय
PowerPoint में SmartArt, आकर्षक आरेख बनाने के लिए एक शक्तिशाली सुविधा है। Java के लिए Aspose.Slides, SmartArt तत्वों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए व्यापक सहायता प्रदान करता है। इस ट्यूटोरियल में, हम आपको Java का उपयोग करके SmartArt नोड पर टेक्स्ट बदलने की प्रक्रिया के बारे में बताएँगे।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
- Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई है और आपके Java प्रोजेक्ट में संदर्भित है।
- जावा प्रोग्रामिंग की बुनियादी समझ.

## पैकेज आयात करें
सबसे पहले, अपने जावा कोड के भीतर Aspose.Slides कार्यक्षमता तक पहुंचने के लिए आवश्यक पैकेज आयात करें।
```java
import com.aspose.slides.*;
```
आइये इस उदाहरण को कई चरणों में विभाजित करें:
## चरण 1: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
```java
Presentation presentation = new Presentation();
```
एक नया उदाहरण बनाएँ `Presentation` एक पावरपॉइंट प्रेजेंटेशन के साथ काम करने के लिए कक्षा।
## चरण 2: स्लाइड में स्मार्टआर्ट जोड़ें
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
पहली स्लाइड में स्मार्टआर्ट जोड़ें। इस उदाहरण में, हम इसका उपयोग कर रहे हैं `BasicCycle` लेआउट।
## चरण 3: स्मार्टआर्ट नोड तक पहुंचें
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
स्मार्टआर्ट के दूसरे मूल नोड का संदर्भ प्राप्त करें।
## चरण 4: नोड पर टेक्स्ट सेट करें
```java
node.getTextFrame().setText("Second root node");
```
चयनित स्मार्टआर्ट नोड के लिए पाठ सेट करें.
## चरण 5: प्रस्तुति सहेजें
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
संशोधित प्रस्तुति को निर्दिष्ट स्थान पर सहेजें.

## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा और Aspose.Slides का उपयोग करके स्मार्टआर्ट नोड पर टेक्स्ट बदलने का तरीका दिखाया है। इस ज्ञान के साथ, आप अपने पावरपॉइंट प्रेजेंटेशन में स्मार्टआर्ट तत्वों को गतिशील रूप से हेरफेर कर सकते हैं, जिससे उनकी दृश्य अपील और स्पष्टता बढ़ जाती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं स्लाइड में जोड़ने के बाद स्मार्टआर्ट का लेआउट बदल सकता हूँ?
हां, आप तक पहुंचकर लेआउट बदल सकते हैं `SmartArt.setAllNodes(LayoutType)` तरीका।
### क्या Aspose.Slides Java 11 के साथ संगत है?
हां, Aspose.Slides for Java, Java 11 और नए संस्करणों के साथ संगत है।
### क्या मैं स्मार्टआर्ट नोड्स के स्वरूप को प्रोग्रामेटिक रूप से अनुकूलित कर सकता हूँ?
निश्चित रूप से, आप Aspose.Slides API का उपयोग करके रंग, आकार और आकृति जैसे विभिन्न गुणों को संशोधित कर सकते हैं।
### क्या Aspose.Slides अन्य प्रकार के स्मार्टआर्ट लेआउट का समर्थन करता है?
हां, Aspose.Slides स्मार्टआर्ट लेआउट की एक विस्तृत श्रृंखला का समर्थन करता है, जिससे आप अपनी प्रस्तुति आवश्यकताओं के लिए सबसे उपयुक्त लेआउट चुन सकते हैं।
### मैं Aspose.Slides के लिए अधिक संसाधन और समर्थन कहां पा सकता हूं?
आप यहां जा सकते हैं [Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) विस्तृत API संदर्भ और ट्यूटोरियल के लिए। इसके अतिरिक्त, आप सहायता भी ले सकते हैं [Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) या खरीदने पर विचार करें [अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) व्यावसायिक सहायता के लिए.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}