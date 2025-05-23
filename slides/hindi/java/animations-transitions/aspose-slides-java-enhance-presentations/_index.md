---
"date": "2025-04-18"
"description": "Aspose.Slides for Java के साथ टेबल और फ़्रेम मैनिपुलेशन में महारत हासिल करके अपने प्रेजेंटेशन को बेहतर बनाने का तरीका जानें। यह गाइड टेबल बनाना, टेक्स्ट फ़्रेम जोड़ना और विशिष्ट सामग्री के चारों ओर फ़्रेम बनाना सिखाती है।"
"title": "Aspose.Slides for Java&#58; प्रस्तुतियों में टेबल और फ्रेम हेरफेर में महारत हासिल करना"
"url": "/hi/java/animations-transitions/aspose-slides-java-enhance-presentations/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java के साथ प्रस्तुतियों में तालिका और फ़्रेम हेरफेर में महारत हासिल करना

## परिचय

PowerPoint में डेटा को प्रभावी ढंग से प्रस्तुत करना चुनौतीपूर्ण हो सकता है। चाहे आप सॉफ़्टवेयर डेवलपर हों या प्रेजेंटेशन डिज़ाइनर, दिखने में आकर्षक टेबल का उपयोग करना और टेक्स्ट फ़्रेम जोड़ना आपकी स्लाइड को और अधिक आकर्षक बना सकता है। यह ट्यूटोरियल बताता है कि टेबल सेल में टेक्स्ट जोड़ने और पैराग्राफ़ और '0' जैसे विशिष्ट वर्णों वाले भागों के चारों ओर फ़्रेम बनाने के लिए Aspose.Slides for Java का उपयोग कैसे करें। इन तकनीकों में महारत हासिल करके, आप अपनी प्रेजेंटेशन को सटीकता और शैली के साथ बेहतर बना पाएँगे।

### आप क्या सीखेंगे:
- स्लाइडों में तालिकाएँ बनाना और उनमें पाठ भरना।
- बेहतर प्रस्तुति के लिए स्वचालित आकृतियों के भीतर पाठ संरेखित करना।
- विषय-वस्तु पर जोर देने के लिए पैराग्राफों और भागों के चारों ओर फ्रेम बनाना।
- वास्तविक दुनिया के परिदृश्यों में इन विशेषताओं के व्यावहारिक अनुप्रयोग।

क्या आप अपनी प्रस्तुतियों को बदलने के लिए तैयार हैं? चलिए शुरू करते हैं!

## आवश्यक शर्तें

कोड में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### आवश्यक पुस्तकालय
आपको Java के लिए Aspose.Slides की आवश्यकता होगी। Maven या Gradle का उपयोग करके इसे शामिल करने का तरीका यहां बताया गया है:

**मावेन:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**ग्रेडेल:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### पर्यावरण सेटअप
सुनिश्चित करें कि आपके पास जावा डेवलपमेंट किट (JDK) स्थापित है, अधिमानतः JDK 16 या बाद का, क्योंकि यह उदाहरण इसका उपयोग करता है `jdk16` वर्गीकारक.

### ज्ञान पूर्वापेक्षाएँ
- जावा प्रोग्रामिंग की बुनियादी समझ.
- पावरपॉइंट जैसे प्रेजेंटेशन सॉफ्टवेयर से परिचित होना।
- इंटेलीज आईडिया या एक्लिप्स जैसे एकीकृत विकास वातावरण (आईडीई) का उपयोग करने का अनुभव।

## Java के लिए Aspose.Slides सेट अप करना

Aspose.Slides का उपयोग शुरू करने के लिए, इन चरणों का पालन करें:

1. **लाइब्रेरी स्थापित करें**: निर्भरताओं को प्रबंधित करने के लिए Maven या Gradle का उपयोग करें, या इसे सीधे डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

2. **लाइसेंस अधिग्रहण**:
   - से एक अस्थायी लाइसेंस डाउनलोड करके निःशुल्क परीक्षण शुरू करें [अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/).
   - पूर्ण पहुँच के लिए, लाइसेंस खरीदने पर विचार करें [Aspose.Slides खरीदें](https://purchase.aspose.com/buy).

3. **मूल आरंभीकरण**:
निम्नलिखित कोड स्निपेट के साथ अपने प्रस्तुतिकरण वातावरण को आरंभ करें:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // आपका कोड यहाँ
} finally {
    if (pres != null) pres.dispose();
}
```

## कार्यान्वयन मार्गदर्शिका

यह अनुभाग विभिन्न सुविधाओं को कवर करता है जिन्हें आप Java के लिए Aspose.Slides का उपयोग करके कार्यान्वित कर सकते हैं।

### फ़ीचर 1: टेबल बनाएँ और सेल में टेक्स्ट जोड़ें

#### अवलोकन
यह सुविधा दर्शाती है कि पहली स्लाइड पर तालिका कैसे बनाई जाए और विशिष्ट कक्षों में पाठ कैसे भरा जाए। 

##### चरण:
**1. एक तालिका बनाएं**
सबसे पहले, अपनी प्रस्तुति आरंभ करें और निर्दिष्ट स्तंभ चौड़ाई और पंक्ति ऊंचाई के साथ स्थिति (50, 50) पर एक तालिका जोड़ें।
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. कक्षों में पाठ जोड़ें**
पाठ के कुछ भागों से पैराग्राफ बनाएं और उन्हें किसी विशिष्ट सेल में जोड़ें।
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```
**3. प्रेजेंटेशन को सेव करें**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### फ़ीचर 2: ऑटोशेप में टेक्स्टफ़्रेम जोड़ें और संरेखण सेट करें

#### अवलोकन
जानें कि किसी स्वचालित आकृति में विशिष्ट संरेखण के साथ टेक्स्ट फ़्रेम कैसे जोड़ें।

##### चरण:
**1. एक ऑटोशेप जोड़ें**
निर्दिष्ट आयामों के साथ स्थिति (400, 100) पर एक ऑटोशेप के रूप में एक आयत जोड़ें।
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```
**2. टेक्स्ट संरेखण सेट करें**
पाठ को "आकार में पाठ" पर सेट करें और इसे बाईं ओर संरेखित करें।
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
**3. प्रेजेंटेशन को सेव करें**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### फ़ीचर 3: टेबल सेल में पैराग्राफ़ और भागों के चारों ओर फ़्रेम बनाएँ

#### अवलोकन
यह सुविधा पैराग्राफ़ों और तालिका कक्षों में '0' वाले भागों के चारों ओर फ़्रेम बनाने पर केंद्रित है।

##### चरण:
**1. एक तालिका बनाएं**
प्रारंभिक सेटअप के लिए "तालिका बनाएं और कक्षों में पाठ जोड़ें" से कोड का पुनः उपयोग करें।
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. पैराग्राफ़ जोड़ें**
पिछली सुविधा से पैराग्राफ निर्माण कोड का पुनः उपयोग करें।
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```
**3. फ़्रेम बनाएं**
पैराग्राफों और भागों पर पुनरावृत्ति करके उनके चारों ओर फ्रेम बनाएं।
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```
**4. प्रेजेंटेशन को सेव करें**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## निष्कर्ष
इस गाइड का पालन करके, आप Aspose.Slides for Java का उपयोग करके अपनी प्रस्तुतियों को प्रभावी ढंग से बेहतर बना सकते हैं। टेबल और फ़्रेम में हेरफेर करने में महारत हासिल करने से आप अधिक आकर्षक और दिखने में आकर्षक स्लाइड बना सकते हैं। आगे की खोज के लिए, Aspose.Slides की अतिरिक्त सुविधाओं में गोता लगाने या इसे अन्य Java अनुप्रयोगों के साथ एकीकृत करने पर विचार करें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}