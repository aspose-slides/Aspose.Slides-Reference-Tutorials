---
"date": "2025-04-18"
"description": "Aspose.Slides for Java के साथ प्रस्तुतियों में टिप्पणियाँ जोड़ना और प्रबंधित करना सीखें। सीधे अपनी स्लाइड में फ़ीडबैक एकीकृत करके सहयोग बढ़ाएँ।"
"title": "Aspose.Slides Java का उपयोग करके प्रस्तुतियों में टिप्पणियाँ कैसे जोड़ें (ट्यूटोरियल)"
"url": "/hi/java/comments-reviewing/aspose-slides-java-add-comments/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java का उपयोग करके प्रस्तुतियों में टिप्पणियाँ कैसे जोड़ें

## परिचय

क्या आपको अपनी प्रस्तुतियों में फीडबैक को सहजता से एकीकृत करने की आवश्यकता है? चाहे वह सहयोगी संपादन के लिए हो, विस्तृत समीक्षा प्रदान करने के लिए हो, या भविष्य के संदर्भ के लिए नोट्स छोड़ने के लिए हो, टिप्पणियाँ जोड़ना महत्वपूर्ण है। **जावा के लिए Aspose.Slides**, प्रेजेंटेशन टिप्पणियों का प्रबंधन आसान और कुशल हो जाता है। यह ट्यूटोरियल आपको टिप्पणियों को शामिल करके अपने प्रेजेंटेशन वर्कफ़्लो को बढ़ाने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा।

**आप क्या सीखेंगे:**
- Aspose.Slides के साथ एक प्रेजेंटेशन इंस्टैंस आरंभ करें
- नई सामग्री के लिए टेम्पलेट के रूप में एक खाली स्लाइड जोड़ें
- टिप्पणी लेखक बनाएं और स्लाइड में टिप्पणियाँ जोड़ें
- विशिष्ट स्लाइडों से टिप्पणियाँ प्राप्त करें
- सभी संशोधनों के साथ उन्नत प्रस्तुति को सहेजें

आइये, शुरू करने से पहले सुनिश्चित करें कि आपका वातावरण तैयार है!

## आवश्यक शर्तें

इससे पहले कि आप Aspose.Slides Java का उपयोग करके टिप्पणियाँ जोड़ना शुरू करें, सुनिश्चित करें कि आपके सेटअप में निम्नलिखित शामिल हैं:
- **जावा के लिए Aspose.Slides** लाइब्रेरी संस्करण 25.4 या बाद का
- एक संगत JDK (क्लासिफायर के अनुसार संस्करण 16)
- निर्भरता प्रबंधन के लिए Maven या Gradle (या प्रत्यक्ष डाउनलोड)

### पर्यावरण सेटअप

सुनिश्चित करें कि आपके पास निम्नलिखित उपकरण और निर्भरताएँ तैयार हैं:

#### मावेन निर्भरता

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### ग्रेडेल निर्भरता

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### प्रत्यक्षत: डाउनलोड

जो लोग सीधे डाउनलोड करना पसंद करते हैं, वे यहां जाएं [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

### लाइसेंस अधिग्रहण

बिना किसी सीमा के Aspose.Slides सुविधाओं का पूर्ण उपयोग करने के लिए:
- **मुफ्त परीक्षण**: सीमित कार्यक्षमता के साथ लाइब्रेरी का परीक्षण करें।
- **अस्थायी लाइसेंस**मूल्यांकन के दौरान पूर्ण पहुँच के लिए अस्थायी लाइसेंस प्राप्त करें।
- **खरीदना**: दीर्घकालिक उपयोग के लिए वाणिज्यिक लाइसेंस खरीदें।

### बुनियादी आरंभीकरण और सेटअप

अपने प्रेजेंटेशन इंस्टैंस को आरंभ करके प्रारंभ करें:

```java
import com.aspose.slides.Presentation;

Presentation presentation = new Presentation();
try {
    // आपका कोड यहाँ
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Java के लिए Aspose.Slides सेट अप करना

Aspose.Slides को अपने प्रोजेक्ट में एकीकृत करना सरल है। चाहे आप Maven, Gradle या सीधे डाउनलोड का उपयोग करें, सेटअप सुनिश्चित करता है कि आप आसानी से अपनी प्रस्तुतियों में सुविधाएँ जोड़ना शुरू कर सकते हैं।

### स्थापना जानकारी

के लिए **मावेन** उपयोगकर्ता:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

के लिए **ग्रैडल** उत्साही:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### प्रत्यक्षत: डाउनलोड

नवीनतम लाइब्रेरी यहाँ से डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

## कार्यान्वयन मार्गदर्शिका

आइए Aspose.Slides का उपयोग करके प्रत्येक सुविधा को लागू करने का गहन अध्ययन करें।

### सुविधा 1: प्रस्तुति आरंभ करें

**अवलोकन**: एक नया उदाहरण बनाकर शुरू करें `Presentation` क्लास। यह आपके प्रेजेंटेशन फ्रेमवर्क को सेट करता है, जिससे आप स्लाइड और अन्य सामग्री जोड़ सकते हैं।

```java
import com.aspose.slides.Presentation;

// प्रस्तुतिकरण क्लास को तत्कालित करें
Presentation presentation = new Presentation();
try {
    // आपका कोड यहाँ
} finally {
    if (presentation != null) presentation.dispose();
}
```

**क्यों**उचित संसाधन प्रबंधन सुनिश्चित करता है कि आपका एप्लिकेशन कुशल बना रहे। `finally` प्रस्तुति को नष्ट करने से मेमोरी लीक को रोकने में मदद मिलती है।

### फ़ीचर 2: खाली स्लाइड जोड़ें

**अवलोकन**एक संरचित प्रस्तुति बनाने में स्लाइड जोड़ना मौलिक है।

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlideCollection;
import com.aspose.slides.ILayoutSlide;

// प्रस्तुतिकरण क्लास को तत्कालित करें
Presentation presentation = new Presentation();
try {
    // स्लाइड संग्रह तक पहुंचें और एक खाली स्लाइड जोड़ें
    ISlideCollection slides = presentation.getSlides();
    ILayoutSlide layoutSlide = presentation.getLayoutSlides().get_Item(0);
    slides.addEmptySlide(layoutSlide);
} finally {
    if (presentation != null) presentation.dispose();
}
```

**क्यों**: पहली लेआउट स्लाइड को टेम्पलेट के रूप में उपयोग करने से आपकी सभी स्लाइडों में एकरूपता सुनिश्चित होती है।

### फ़ीचर 3: टिप्पणी लेखक जोड़ें

**अवलोकन**: टिप्पणियाँ जोड़ने से पहले, आपको एक लेखक इकाई बनानी होगी.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ICommentAuthorCollection;

// प्रस्तुतिकरण क्लास को तत्कालित करें
Presentation presentation = new Presentation();
try {
    // नाम और आद्याक्षर के साथ लेखक को जोड़ना
    ICommentAuthorCollection authors = presentation.getCommentAuthors();
    ICommentAuthor author = authors.addAuthor("Jawad", "MF");
} finally {
    if (presentation != null) presentation.dispose();
}
```

**क्यों**प्रस्तुति में टिप्पणियों को सही ढंग से प्रस्तुत करने के लिए टिप्पणी लेखकों की पहचान करना महत्वपूर्ण है।

### फ़ीचर 4: स्लाइड में टिप्पणियाँ जोड़ें

**अवलोकन**अब, आइए विशिष्ट स्लाइडों पर टिप्पणियाँ जोड़ें। इससे सहयोग और प्रतिक्रिया तंत्र में सुधार होता है।

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ICommentAuthorCollection;
import com.aspose.slides.ISlide;
import java.awt.geom.Point2D;
import java.util.Date;

// प्रस्तुतिकरण क्लास को तत्कालित करें
Presentation presentation = new Presentation();
try {
    // प्रस्तुति में लेखक को जोड़ना
    ICommentAuthorCollection authors = presentation.getCommentAuthors();
    ICommentAuthor author = authors.addAuthor("Jawad", "MF");
    
    // टिप्पणी की स्थिति निर्धारित करें और टिप्पणी जोड़ें
    Point2D.Float point = new Point2D.Float(0.2f, 0.2f);
    ISlide slide1 = presentation.getSlides().get_Item(0);
    author.getComments().addComment("Hello Jawad, this is slide comment", slide1, point, new Date());
} finally {
    if (presentation != null) presentation.dispose();
}
```

**क्यों**टिप्पणियों को स्थान देने से स्लाइड के विशिष्ट क्षेत्रों पर सटीक फ़ीडबैक मिलता है। टाइमस्टैम्प शामिल करने से यह पता लगाने में मदद मिलती है कि फ़ीडबैक कब दिया गया था।

### फ़ीचर 5: स्लाइड से टिप्पणियाँ प्राप्त करें

**अवलोकन**: मौजूदा टिप्पणियों की समीक्षा करने या उन्हें कुशलतापूर्वक प्रबंधित करने के लिए उन तक पहुंचें।

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ICommentAuthorCollection;
import com.aspose.slides.ISlide;
import com.aspose.slides.IComment[];

// प्रस्तुतिकरण क्लास को तत्कालित करें
Presentation presentation = new Presentation();
try {
    // प्रस्तुति में लेखक को जोड़ना
    ICommentAuthorCollection authors = presentation.getCommentAuthors();
    ICommentAuthor author = authors.addAuthor("Jawad", "MF");
    
    // किसी विशिष्ट स्लाइड और लेखक के लिए टिप्पणियाँ प्राप्त करें
    ISlide slide = presentation.getSlides().get_Item(0);
    IComment[] comments = slide.getSlideComments(author);
} finally {
    if (presentation != null) presentation.dispose();
}
```

**क्यों**: टिप्पणियां प्राप्त करने से समीक्षा और प्रबंधन संभव होता है, तथा यह सुनिश्चित होता है कि आवश्यकतानुसार फीडबैक को संबोधित या संग्रहीत किया जाए।

### फ़ीचर 6: टिप्पणियों के साथ प्रस्तुति सहेजें

**अवलोकन**अंत में, किए गए सभी परिवर्तनों और परिवर्धनों को संरक्षित करने के लिए अपनी प्रस्तुति को सेव करें।

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

// प्रस्तुतिकरण क्लास को तत्कालित करें
Presentation presentation = new Presentation();
try {
    // सहेजी गई फ़ाइल के लिए आउटपुट पथ निर्धारित करें
    String outPptxFile = "YOUR_DOCUMENT_DIRECTORY" + "Comments_out.pptx";
    
    // टिप्पणियों के साथ प्रस्तुति सहेजें
    presentation.save(outPptxFile, SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

**क्यों**आपके कार्य को सहेजने से यह सुनिश्चित होता है कि सभी संशोधन सहेज लिए गए हैं और बाद में आगे के संपादन या वितरण के लिए उन तक पहुँचा जा सकता है।

## निष्कर्ष

Aspose.Slides Java के साथ प्रस्तुतियों में टिप्पणियाँ जोड़ना सहयोग और प्रतिक्रिया तंत्र को बढ़ाने का एक शक्तिशाली तरीका है। इस गाइड का पालन करके, अब आपके पास प्रस्तुति टिप्पणियों को कुशलतापूर्वक प्रबंधित करने के लिए आवश्यक उपकरण हैं। अपने प्रस्तुति वर्कफ़्लो को और बेहतर बनाने के लिए Aspose.Slides सुविधाओं का अन्वेषण करना जारी रखें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}