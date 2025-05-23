---
"date": "2025-04-18"
"description": "Aspose.Slides for Java का उपयोग करके स्मार्टआर्ट बुलेट को छवियों के साथ अनुकूलित करके अपने प्रस्तुतीकरण को बेहतर बनाने का तरीका जानें। पेशेवर रूप के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"title": "जावा के लिए Aspose.Slides का उपयोग करके स्मार्टआर्ट बुलेट्स को छवियों के साथ कैसे अनुकूलित करें | चरण-दर-चरण मार्गदर्शिका"
"url": "/hi/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# जावा के लिए Aspose.Slides का उपयोग करके स्मार्टआर्ट बुलेट्स को छवियों के साथ अनुकूलित कैसे करें

## परिचय

अपने दर्शकों का ध्यान आकर्षित करने और अपने संदेश को प्रभावी ढंग से संप्रेषित करने के लिए दृश्य रूप से आकर्षक प्रस्तुतियाँ बनाना महत्वपूर्ण है। स्लाइड डिज़ाइन करने में एक आम चुनौती कस्टम छवियों का उपयोग करके स्मार्टआर्ट ग्राफ़िक्स के भीतर बुलेट पॉइंट को बढ़ाना है। यह ट्यूटोरियल आपको Aspose.Slides for Java के साथ स्मार्टआर्ट नोड्स में बुलेट फ़िल फ़ॉर्मेट के रूप में एक तस्वीर सेट करने के माध्यम से मार्गदर्शन करेगा, जिससे आप अपनी प्रस्तुतियों को पेशेवर रूप से बढ़ा पाएँगे।

**आप क्या सीखेंगे:**
- Java के लिए Aspose.Slides को सेट अप करना और उसका उपयोग करना
- स्मार्टआर्ट ग्राफ़िक्स में छवियों के साथ बुलेट पॉइंट्स को अनुकूलित करना
- इस अनुकूलन के व्यावहारिक अनुप्रयोग
- सामान्य समस्याओं का निवारण

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास सब कुछ तैयार है।

## आवश्यक शर्तें

इस ट्यूटोरियल का अनुसरण करने के लिए, सुनिश्चित करें कि आप निम्नलिखित पूर्वापेक्षाएँ पूरी करते हैं:

1. **पुस्तकालय और निर्भरताएँ**आपको Java लाइब्रेरी के लिए Aspose.Slides संस्करण 25.4 या बाद के संस्करण की आवश्यकता होगी।
2. **पर्यावरण सेटअप**:
   - IntelliJ IDEA या Eclipse जैसा संगत IDE
   - आपकी मशीन पर JDK 16 स्थापित है
3. **ज्ञान पूर्वापेक्षाएँ**जावा प्रोग्रामिंग और बुनियादी पावरपॉइंट प्रस्तुति संरचना से परिचित होना।

## Java के लिए Aspose.Slides सेट अप करना

आरंभ करने के लिए, निम्न विधियों में से किसी एक का उपयोग करके अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी शामिल करें:

### मावेन

इस निर्भरता को अपने में जोड़ें `pom.xml` फ़ाइल:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ग्रैडल

इसे अपने में शामिल करें `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### प्रत्यक्षत: डाउनलोड

वैकल्पिक रूप से, लाइब्रेरी को सीधे यहां से डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

**लाइसेंस प्राप्ति चरण**: Aspose अपनी सुविधाओं के परीक्षण के लिए एक निःशुल्क परीक्षण लाइसेंस प्रदान करता है। आप मूल्यांकन सीमाओं को हटाने के लिए एक अस्थायी लाइसेंस का अनुरोध कर सकते हैं या खरीद सकते हैं।

अपने परिवेश को आरंभ करने और सेट अप करने के लिए, इसका एक उदाहरण बनाएँ `Presentation` वर्ग जैसा दिखाया गया है:

```java
Presentation presentation = new Presentation();
```

## कार्यान्वयन मार्गदर्शिका

यह अनुभाग प्रक्रिया को प्रबंधनीय चरणों में विभाजित करेगा तथा बताएगा कि वांछित कार्यक्षमता कैसे प्राप्त की जाए।

### कस्टम बुलेट फिल के साथ स्मार्टआर्ट जोड़ना

#### अवलोकन

हम आपकी स्लाइड में एक स्मार्टआर्ट आकृति जोड़कर और एक छवि भरण का उपयोग करके इसके बुलेट बिंदुओं को अनुकूलित करके शुरुआत करेंगे।

#### चरण-दर-चरण निर्देश

**1. प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें**

```java
Presentation presentation = new Presentation();
```

*उद्देश्य*: एक नया प्रस्तुतिकरण इंस्टैंस आरंभ करता है, जहां आप स्मार्टआर्ट ग्राफिक्स जोड़ेंगे।

**2. स्मार्टआर्ट आकार जोड़ें**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*स्पष्टीकरण*: यह रेखा पहली स्लाइड में स्थिति (x=10, y=10) पर 500x400 पिक्सेल के आयामों के साथ एक नया स्मार्टआर्ट आकार जोड़ती है। `VerticalPictureList` लेआउट का उपयोग ऊर्ध्वाधर संरेखण के लिए किया जाता है।

**3. बुलेट फिल तक पहुंचें और उसे अनुकूलित करें**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*उद्देश्य*: जाँचता है कि नोड में कोई है या नहीं `BulletFillFormat` प्रॉपर्टी। यदि ऐसा है, तो यह एक छवि लोड करता है और इसे बुलेट के लिए भरण के रूप में सेट करता है।
*पैरामीटर*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: आपकी छवि फ़ाइल का पथ.
  - `PictureFillMode.Stretch`: यह सुनिश्चित करता है कि छवि बुलेट क्षेत्र को पूरी तरह से भर दे।

**4. अपनी प्रस्तुति सहेजें**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}