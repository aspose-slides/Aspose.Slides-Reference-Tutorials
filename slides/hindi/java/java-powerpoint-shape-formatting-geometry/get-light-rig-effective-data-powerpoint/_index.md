---
"description": "इस विस्तृत, चरण-दर-चरण मार्गदर्शिका में जानें कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों से लाइट रिग प्रभावी डेटा कैसे प्राप्त करें।"
"linktitle": "पावरपॉइंट में लाइट रिग प्रभावी डेटा प्राप्त करें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "पावरपॉइंट में लाइट रिग प्रभावी डेटा प्राप्त करें"
"url": "/hi/java/java-powerpoint-shape-formatting-geometry/get-light-rig-effective-data-powerpoint/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# पावरपॉइंट में लाइट रिग प्रभावी डेटा प्राप्त करें

## परिचय
क्या आप Java का उपयोग करके अपने PowerPoint प्रेजेंटेशन कार्यों को स्वचालित करना चाहते हैं? आगे न देखें! Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft PowerPoint इंस्टॉल किए बिना PowerPoint फ़ाइलों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। इस व्यापक गाइड में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन से लाइट रिग प्रभावी डेटा प्राप्त करने के चरणों के माध्यम से मार्गदर्शन करेंगे। चाहे आप एक अनुभवी Java डेवलपर हों या अभी शुरुआत कर रहे हों, यह ट्यूटोरियल आपको अपनी परियोजनाओं में Aspose.Slides की पूरी क्षमता का दोहन करने में मदद करेगा।
## आवश्यक शर्तें
कोड में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK 8 या उच्चतर संस्करण स्थापित है।
2. Aspose.Slides for Java: लाइब्रेरी को यहां से डाउनलोड करें [यहाँ](https://releases.aspose.com/slides/java/).
3. IDE: कोडिंग के लिए IntelliJ IDEA या Eclipse जैसे एकीकृत विकास वातावरण (IDE) का उपयोग करें।
4. प्रस्तुति फ़ाइल: एक नमूना पावरपॉइंट फ़ाइल (`Presentation1.pptx`) कोड का परीक्षण करने के लिए.
## पैकेज आयात करें
सबसे पहले, आइए अपना प्रोजेक्ट सेट अप करें और आवश्यक पैकेज आयात करें। अपने IDE में एक नया Java प्रोजेक्ट बनाएँ और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides for Java लाइब्रेरी जोड़ें।
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;

```
## चरण 1: प्रोजेक्ट निर्देशिका सेट करें
अपनी प्रोजेक्ट डायरेक्टरी सेट अप करके शुरू करें। एक फ़ोल्डर बनाएँ जहाँ आप अपनी जावा फ़ाइलें और पावरपॉइंट प्रेजेंटेशन स्टोर करेंगे (`Presentation1.pptx`).
```java
String dataDir = "Your Document Directory";  // अपने दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करें
```
## चरण 2: प्रस्तुति लोड करें
इसके बाद, आप PowerPoint प्रस्तुति को लोड करेंगे `Presentation` Aspose.Slides से क्लास.
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## चरण 3: पहली स्लाइड तक पहुंचें
एक बार प्रस्तुति लोड हो जाने पर, प्रस्तुति की पहली स्लाइड तक पहुंचें।
```java
try {
    IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
}
```
## चरण 4: प्रभावी लाइट रिग डेटा प्राप्त करें
पहली स्लाइड और आकृति का चयन करके, प्रभावी प्रकाश रिग गुण प्राप्त करें।
```java
System.out.println("= Effective light rig properties =");
System.out.println("Type: " + threeDEffectiveData.getLightRig().getLightType());
System.out.println("Direction: " + threeDEffectiveData.getLightRig().getDirection());
```
## चरण 5: प्रेजेंटेशन ऑब्जेक्ट को हटाएँ
अंत में, संसाधनों को मुक्त करने के लिए प्रस्तुति ऑब्जेक्ट को हटाना सुनिश्चित करें।
```java
} finally {
    if (pres != null) pres.dispose();
}
```
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन से प्रभावी लाइट रिग डेटा को सफलतापूर्वक प्राप्त कर लिया है। इस ट्यूटोरियल में आपके प्रोजेक्ट को सेट अप करने से लेकर लाइट रिग प्रॉपर्टी तक पहुँचने और प्रदर्शित करने तक के आवश्यक चरणों को शामिल किया गया है। Aspose.Slides में कई सुविधाएँ हैं जो आपको PowerPoint फ़ाइलों को प्रोग्रामेटिक रूप से मैनिपुलेट करने में मदद कर सकती हैं, जिससे यह डेवलपर्स के लिए एक अमूल्य टूल बन जाता है।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, Java का उपयोग करके PowerPoint फ़ाइलें बनाने, उनमें हेरफेर करने और उन्हें परिवर्तित करने के लिए एक शक्तिशाली लाइब्रेरी है।
### क्या मैं Microsoft PowerPoint इंस्टॉल किए बिना Aspose.Slides का उपयोग कर सकता हूँ?
हां, आप Microsoft PowerPoint इंस्टॉल किए बिना Aspose.Slides का उपयोग कर सकते हैं।
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं [यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
दस्तावेज़ यहां उपलब्ध है [इस लिंक](https://reference.aspose.com/slides/java/).
### मैं Aspose.Slides के लिए समर्थन कैसे प्राप्त करूं?
आप Aspose.Slides सहायता मंच से सहायता प्राप्त कर सकते हैं [यहाँ](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}