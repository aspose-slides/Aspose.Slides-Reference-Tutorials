---
title: जावा पावरपॉइंट में स्मार्टआर्ट नोड से टेक्स्ट प्राप्त करें
linktitle: जावा पावरपॉइंट में स्मार्टआर्ट नोड से टेक्स्ट प्राप्त करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में SmartArt नोड्स से टेक्स्ट निकालने का तरीका जानें। डेवलपर्स के लिए आसान, चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 14
url: /hi/java/java-powerpoint-text-alignment-formatting/get-text-from-smartart-node-java-powerpoint/
---
## परिचय
इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में SmartArt नोड्स से टेक्स्ट निकालने का तरीका जानेंगे। Aspose.Slides एक शक्तिशाली Java लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। SmartArt नोड्स से टेक्स्ट निकालना विभिन्न अनुप्रयोगों जैसे डेटा निष्कर्षण, सामग्री विश्लेषण और बहुत कुछ के लिए उपयोगी हो सकता है। इस गाइड के अंत तक, आपको Java में Aspose.Slides का उपयोग करके SmartArt नोड्स से कुशलतापूर्वक टेक्स्ट प्राप्त करने के तरीके के बारे में स्पष्ट समझ हो जाएगी।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. जावा डेवलपमेंट किट (JDK): Java के लिए Aspose.Slides को JDK 8 या उच्चतर की आवश्यकता होती है।
2.  Aspose.Slides for Java लाइब्रेरी: आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): IntelliJ IDEA, Eclipse, या जावा समर्थन के साथ अपनी पसंद के किसी भी IDE का उपयोग करें।
4. प्रस्तुति फ़ाइल: आपके पास स्मार्टआर्ट के साथ एक पावरपॉइंट फ़ाइल (.pptx) है जिससे आप पाठ निकालना चाहते हैं।
## पैकेज आयात करें
आरंभ करने के लिए, अपनी जावा फ़ाइल में आवश्यक Aspose.Slides क्लासेस आयात करें:
```java
import com.aspose.slides.*;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने जावा प्रोजेक्ट को सेट अप करके और अपने प्रोजेक्ट की निर्भरताओं में Aspose.Slides for Java को शामिल करके शुरू करें। सुनिश्चित करें कि आपने अपने बिल्ड पथ या Maven/Gradle निर्भरताओं में Aspose.Slides JAR फ़ाइल को जोड़ा है।
## चरण 2: प्रस्तुति लोड करें
Aspose.Slides का उपयोग करके PowerPoint प्रस्तुति फ़ाइल लोड करें।
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Presentation.pptx");
```
## चरण 3: स्लाइड पर स्मार्टआर्ट तक पहुंचें
प्रस्तुति से पहली स्लाइड प्राप्त करें और स्मार्टआर्ट ऑब्जेक्ट तक पहुँचें।
```java
ISlide slide = presentation.getSlides().get_Item(0);
ISmartArt smartArt = (ISmartArt) slide.getShapes().get_Item(0);
```
## चरण 4: स्मार्टआर्ट नोड्स पुनः प्राप्त करें
प्रत्येक नोड के आकार के माध्यम से पुनरावृति करने के लिए स्मार्टआर्ट के भीतर सभी नोड्स तक पहुंचें।
```java
ISmartArtNodeCollection smartArtNodes = smartArt.getAllNodes();
for (ISmartArtNode smartArtNode : (Iterable<ISmartArtNode>) smartArtNodes) {
    for (ISmartArtShape nodeShape : smartArtNode.getShapes()) {
        if (nodeShape.getTextFrame() != null)
            System.out.println(nodeShape.getTextFrame().getText());
    }
}
```
## चरण 5: प्रेजेंटेशन ऑब्जेक्ट को हटाएँ
एक बार जब आप प्रेजेंटेशन ऑब्जेक्ट का उपयोग कर लें तो उसे नष्ट कर देना अच्छा अभ्यास है।
```java
finally {
    if (presentation != null) presentation.dispose();
}
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने बताया है कि Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में SmartArt नोड्स से टेक्स्ट कैसे निकाला जाता है। इन चरणों का पालन करके, आप प्रोग्रामेटिक रूप से SmartArt ऑब्जेक्ट से टेक्स्ट सामग्री को प्रभावी ढंग से प्राप्त कर सकते हैं, जिससे आपके Java अनुप्रयोगों में विभिन्न दस्तावेज़ प्रसंस्करण कार्यों को सुविधाजनक बनाया जा सकता है।

## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक मजबूत API है जो डेवलपर्स को Java का उपयोग करके प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने में सक्षम बनाता है।
### मैं Java के लिए Aspose.Slides कैसे डाउनलोड कर सकता हूँ?
 आप Java के लिए Aspose.Slides को यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
### क्या Aspose.Slides for Java व्यावसायिक उपयोग के लिए उपयुक्त है?
 हां, Aspose.Slides for Java का व्यावसायिक उपयोग किया जा सकता है। आप लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या Aspose.Slides for Java निःशुल्क परीक्षण प्रदान करता है?
 हां, आप Java के लिए Aspose.Slides का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए समर्थन कहां पा सकता हूं?
 तकनीकी सहायता और सामुदायिक समर्थन के लिए, यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).