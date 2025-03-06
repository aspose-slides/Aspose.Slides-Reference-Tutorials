---
title: पावरपॉइंट में छवियों पर डुओटोन प्रभाव लागू करें
linktitle: पावरपॉइंट में छवियों पर डुओटोन प्रभाव लागू करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: हमारे चरण-दर-चरण गाइड के साथ Aspose.Slides for Java का उपयोग करके PowerPoint में छवियों पर Duotone प्रभाव लागू करना सीखें। अपनी प्रस्तुतियों को बेहतर बनाएँ।
weight: 20
url: /hi/java/java-powerpoint-animation-shape-manipulation/apply-duotone-effects-images-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# पावरपॉइंट में छवियों पर डुओटोन प्रभाव लागू करें

## परिचय
अपने पावरपॉइंट प्रेजेंटेशन में विज़ुअल इफ़ेक्ट जोड़ने से उनकी अपील और प्रभावशीलता में काफ़ी वृद्धि हो सकती है। ऐसा ही एक आकर्षक इफ़ेक्ट है डुओटोन इफ़ेक्ट, जो एक इमेज पर दो विपरीत रंग लागू करता है, जिससे उसे एक आधुनिक और पेशेवर रूप मिलता है। इस व्यापक गाइड में, हम आपको Aspose.Slides for Java का उपयोग करके पावरपॉइंट में इमेज पर डुओटोन इफ़ेक्ट लागू करने की प्रक्रिया के बारे में बताएँगे।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपकी मशीन पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Oracle JDK वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java लाइब्रेरी: आप लाइब्रेरी को यहां से डाउनलोड कर सकते हैं[Aspose.Slides डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (आईडीई): जावा कोड लिखने और निष्पादित करने के लिए इंटेलीज आईडीईए या एक्लिप्स जैसा एक आईडीई।
4.  छवि फ़ाइल: एक छवि फ़ाइल (जैसे,`aspose-logo.jpg`) डुओटोन प्रभाव लागू करने के लिए.
## पैकेज आयात करें
सबसे पहले, आपको अपने जावा प्रोग्राम में ज़रूरी पैकेज आयात करने होंगे। यह आप इस प्रकार कर सकते हैं:
```java
import com.aspose.slides.*;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## चरण 1: एक नई प्रस्तुति बनाएँ
एक नया प्रेजेंटेशन ऑब्जेक्ट बनाकर शुरू करें। यह वह कैनवास होगा जहाँ आप अपनी छवि जोड़ेंगे और डुओटोन प्रभाव लागू करेंगे।
```java
Presentation presentation = new Presentation();
```
## चरण 2: छवि फ़ाइल पढ़ें
इसके बाद, अपनी डायरेक्टरी से इमेज फ़ाइल पढ़ें। यह इमेज प्रेजेंटेशन में जोड़ दी जाएगी और इस पर डुओटोन इफ़ेक्ट लागू किया जाएगा।
```java
try {
    byte[] imageBytes = Files.readAllBytes(Paths.get("Your Document Directory/aspose-logo.jpg"));
```
## चरण 3: प्रस्तुति में छवि जोड़ें
छवि को प्रस्तुति के छवि संग्रह में जोड़ें। यह चरण छवि को प्रस्तुति के भीतर उपयोग के लिए उपलब्ध कराता है।
```java
    IPPImage backgroundImage = presentation.getImages().addImage(imageBytes);
```
## चरण 4: छवि को स्लाइड पृष्ठभूमि के रूप में सेट करें
अब, छवि को पहली स्लाइड के लिए पृष्ठभूमि के रूप में सेट करें। इसमें पृष्ठभूमि प्रकार और भरण प्रारूप को कॉन्फ़िगर करना शामिल है।
```java
    presentation.getSlides().get_Item(0).getBackground().setType(BackgroundType.OwnBackground);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().setFillType(FillType.Picture);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().setImage(backgroundImage);
```
## चरण 5: डुओटोन प्रभाव जोड़ें
पृष्ठभूमि छवि में Duotone प्रभाव जोड़ें। इस चरण में Duotone ऑब्जेक्ट बनाना और उसके गुण सेट करना शामिल है।
```java
    IDuotone duotone = presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().getImageTransform().addDuotoneEffect();
```
## चरण 6: डुओटोन गुण सेट करें
रंग सेट करके डुओटोन प्रभाव को कॉन्फ़िगर करें। यहाँ, हम डुओटोन प्रभाव के लिए स्कीम रंगों का उपयोग कर रहे हैं।
```java
    duotone.getColor1().setColorType(ColorType.Scheme);
    duotone.getColor1().setSchemeColor(SchemeColor.Accent1);
    duotone.getColor2().setColorType(ColorType.Scheme);
    duotone.getColor2().setSchemeColor(SchemeColor.Dark2);
```
## चरण 7: प्रभावी डुओटोन मान प्राप्त करें और प्रदर्शित करें
प्रभाव को सत्यापित करने के लिए, डुओटोन प्रभाव के प्रभावी मानों को पुनः प्राप्त करें और उन्हें कंसोल पर प्रिंट करें।
```java
    IDuotoneEffectiveData duotoneEffective = duotone.getEffective();
    System.out.println("Duotone effective color1: " + duotoneEffective.getColor1());
    System.out.println("Duotone effective color2: " + duotoneEffective.getColor2());
} catch(IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष
पावरपॉइंट में छवियों पर डुओटोन प्रभाव लागू करने से आपकी प्रस्तुतियों को एक स्टाइलिश और पेशेवर रूप मिल सकता है। Aspose.Slides for Java के साथ, यह प्रक्रिया सरल और अत्यधिक अनुकूलन योग्य है। अपनी छवियों पर डुओटोन प्रभाव जोड़ने और अपनी प्रस्तुतियों को अलग दिखाने के लिए इस ट्यूटोरियल में बताए गए चरणों का पालन करें।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और हेरफेर करने की अनुमति देती है।
### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?
 आप Java के लिए Aspose.Slides को यहाँ से डाउनलोड कर सकते हैं[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/)दस्तावेज़ में दिए गए स्थापना निर्देशों का पालन करें।
### क्या मैं किसी भी IDE के साथ Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, Java के लिए Aspose.Slides सभी प्रमुख IDEs के साथ संगत है, जिसमें IntelliJ IDEA, Eclipse और NetBeans शामिल हैं।
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण प्राप्त कर सकते हैं[Aspose.Slides निःशुल्क परीक्षण पृष्ठ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए और अधिक उदाहरण और दस्तावेज़ कहां पा सकता हूं?
 आप यहाँ पर विस्तृत दस्तावेज और उदाहरण पा सकते हैं।[Aspose.Slides दस्तावेज़ीकरण पृष्ठ](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
