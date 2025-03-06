---
title: जावा का उपयोग करके पावरपॉइंट में स्मार्टआर्ट तक पहुंचें
linktitle: जावा का उपयोग करके पावरपॉइंट में स्मार्टआर्ट तक पहुंचें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ Java का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt तक पहुँचने और उसमें हेरफेर करने का तरीका जानें। डेवलपर्स के लिए चरण-दर-चरण मार्गदर्शिका।
weight: 12
url: /hi/java/java-powerpoint-smartart-manipulation/access-smartart-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
नमस्ते, जावा के शौकीनों! क्या आपको कभी PowerPoint प्रस्तुतियों में SmartArt के साथ प्रोग्रामेटिक रूप से काम करने की ज़रूरत महसूस हुई है? हो सकता है कि आप किसी रिपोर्ट को स्वचालित कर रहे हों, या शायद आप कोई ऐसा ऐप विकसित कर रहे हों जो तुरंत स्लाइड तैयार कर सके। आपकी ज़रूरत चाहे जो भी हो, SmartArt को संभालना एक मुश्किल काम लग सकता है। लेकिन डरें नहीं! आज, हम Java के लिए Aspose.Slides का उपयोग करके PowerPoint में SmartArt तक पहुँचने के तरीके के बारे में विस्तार से जानेंगे। यह चरण-दर-चरण मार्गदर्शिका आपको वह सब कुछ बताएगी जो आपको जानना ज़रूरी है, अपने परिवेश को सेट करने से लेकर SmartArt नोड्स को पार करने और उनमें हेरफेर करने तक। तो, एक कप कॉफ़ी लें, और चलिए शुरू करते हैं!
## आवश्यक शर्तें
इससे पहले कि हम बारीकियों में उतरें, आइए यह सुनिश्चित करें कि आपके पास सुचारू रूप से आगे बढ़ने के लिए आवश्यक सभी चीजें हैं:
- जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपकी मशीन पर JDK स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Slides: आपको Aspose.Slides लाइब्रेरी की आवश्यकता होगी। आप कर सकते हैं[यहाँ पर डाउनलोड करो](https://releases.aspose.com/slides/java/).
- आपकी पसंद का IDE: चाहे वह IntelliJ IDEA हो, Eclipse हो या कोई अन्य, सुनिश्चित करें कि वह सेटअप हो और उपयोग के लिए तैयार हो।
- एक नमूना पावरपॉइंट फ़ाइल: हमें काम करने के लिए एक पावरपॉइंट फ़ाइल की आवश्यकता होगी। आप एक बना सकते हैं या स्मार्टआर्ट तत्वों के साथ एक मौजूदा फ़ाइल का उपयोग कर सकते हैं।
## पैकेज आयात करें
सबसे पहले, आइए आवश्यक पैकेजों को आयात करें। ये आयात महत्वपूर्ण हैं क्योंकि वे हमें Aspose.Slides लाइब्रेरी द्वारा प्रदान की गई कक्षाओं और विधियों का उपयोग करने की अनुमति देते हैं।
```java
import com.aspose.slides.IShape;
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
```
यह एकल आयात हमें जावा में पावरपॉइंट प्रस्तुतियों को संभालने के लिए आवश्यक सभी क्लासों तक पहुंच प्रदान करेगा।
## चरण 1: अपना प्रोजेक्ट सेट अप करना
शुरू करने के लिए, हमें अपना प्रोजेक्ट सेट अप करना होगा। इसमें एक नया जावा प्रोजेक्ट बनाना और हमारे प्रोजेक्ट की निर्भरताओं में Aspose.Slides लाइब्रेरी जोड़ना शामिल है।
### चरण 1.1: एक नया जावा प्रोजेक्ट बनाएं
अपना IDE खोलें और एक नया Java प्रोजेक्ट बनाएँ। इसे कोई सार्थक नाम दें, जैसे “SmartArtInPowerPoint”।
### चरण 1.2: Aspose.Slides लाइब्रेरी जोड़ें
 Aspose.Slides for Java लाइब्रेरी को यहाँ से डाउनलोड करें[वेबसाइट](https://releases.aspose.com/slides/java/)और इसे अपने प्रोजेक्ट में जोड़ें। यदि आप Maven का उपयोग कर रहे हैं, तो आप अपने प्रोजेक्ट में निम्नलिखित निर्भरता जोड़ सकते हैं`pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>22.6</version>
    <classifier>jdk16</classifier>
</dependency>
```
## चरण 2: प्रस्तुति लोड करें
अब जबकि हमने अपना प्रोजेक्ट सेट कर लिया है, अब समय है पावरपॉइंट प्रेजेंटेशन को लोड करने का, जिसमें स्मार्टआर्ट तत्व शामिल हैं।
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AccessSmartArt.pptx");
```
 यहाँ,`dataDir` वह निर्देशिका का पथ है जहाँ आपकी PowerPoint फ़ाइल स्थित है।`"Your Document Directory"` वास्तविक पथ के साथ.
## चरण 3: पहली स्लाइड में आकृतियों को पार करें
इसके बाद, हमें स्मार्टआर्ट ऑब्जेक्ट्स को खोजने के लिए अपनी प्रस्तुति की पहली स्लाइड में आकृतियों के माध्यम से आगे बढ़ना होगा।
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        // हमें एक स्मार्टआर्ट आकृति मिली
    }
}
```
## चरण 4: स्मार्टआर्ट नोड्स तक पहुंचें
एक बार जब हम स्मार्टआर्ट आकृति की पहचान कर लेते हैं, तो अगला चरण उसके नोड्स पर जाना और उनके गुणों तक पहुंचना होता है।
```java
ISmartArt smartArt = (ISmartArt) shape;
for (int i = 0; i < smartArt.getAllNodes().size(); i++) {
    ISmartArtNode node = (ISmartArtNode) smartArt.getAllNodes().get_Item(i);
    String outString = String.format("i = %d, Text = %s, Level = %d, Position = %d",
                                      i, node.getTextFrame().getText(), node.getLevel(), node.getPosition());
    System.out.println(outString);
}
```
## चरण 5: प्रस्तुति का निपटान करें
अंत में, संसाधनों को मुक्त करने के लिए प्रस्तुति ऑब्जेक्ट का उचित तरीके से निपटान करना आवश्यक है।
```java
if (pres != null) pres.dispose();
```

## निष्कर्ष
और अब यह आपके लिए है! इन चरणों का पालन करके, आप आसानी से जावा का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt तत्वों तक पहुँच सकते हैं और उनमें हेरफेर कर सकते हैं। चाहे आप एक स्वचालित रिपोर्टिंग सिस्टम बना रहे हों या बस Aspose.Slides की क्षमताओं की खोज कर रहे हों, यह मार्गदर्शिका आपको वह आधार प्रदान करती है जिसकी आपको आवश्यकता है। याद रखें,[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) आपका मित्र है, जो गहन अन्वेषण के लिए भरपूर जानकारी प्रदान करता है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं नए स्मार्टआर्ट तत्व बनाने के लिए Aspose.Slides for Java का उपयोग कर सकता हूँ?
हां, Java के लिए Aspose.Slides मौजूदा स्मार्टआर्ट तत्वों तक पहुंचने और उन्हें संशोधित करने के अलावा नए स्मार्टआर्ट तत्वों को बनाने का समर्थन करता है।
### क्या Aspose.Slides for Java निःशुल्क है?
 Aspose.Slides for Java एक सशुल्क लाइब्रेरी है, लेकिन आप[निःशुल्क परीक्षण डाउनलोड करें](https://releases.aspose.com/) इसकी विशेषताओं का परीक्षण करने के लिए।
### मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
 आप अनुरोध कर सकते हैं[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) बिना किसी प्रतिबंध के पूर्ण उत्पाद का मूल्यांकन करने के लिए Aspose वेबसाइट से साइन इन करें।
### Aspose.Slides के साथ मैं किस प्रकार के स्मार्टआर्ट लेआउट तक पहुंच सकता हूं?
Aspose.Slides, PowerPoint में उपलब्ध सभी प्रकार के स्मार्टआर्ट लेआउट का समर्थन करता है, जिसमें संगठनात्मक चार्ट, सूचियाँ, चक्र आदि शामिल हैं।
### मैं Aspose.Slides for Java के लिए समर्थन कहां से प्राप्त कर सकता हूं?
 सहायता के लिए, यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11)जहां आप प्रश्न पूछ सकते हैं और समुदाय और Aspose डेवलपर्स से सहायता प्राप्त कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
