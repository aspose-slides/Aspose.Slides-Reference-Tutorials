---
date: '2025-12-10'
description: Aspose.Slides for Java का उपयोग करके PowerPoint में तालिका में टेक्स्ट
  जोड़ना और टेक्स्ट के चारों ओर फ्रेम बनाना सीखें। यह गाइड तालिकाएँ बनाना, टेक्स्ट
  संरेखण सेट करना, और सामग्री को फ्रेम करने को कवर करता है।
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides for Java – तालिका में टेक्स्ट जोड़ना और फ्रेम का संचालन
url: /hi/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# प्रेजेंटेशन में टेबल और फ्रेम मैनिपुलेशन में महारत हासिल करना Aspose.Slides for Java के साथ

## परिचय

PowerPoint में डेटा को प्रभावी ढंग से प्रस्तुत करना चुनौतीपूर्ण हो सकता है। चाहे आप एक सॉफ़्टवेयर डेवलपर हों या प्रेजेंटेशन डिज़ाइनर, **add text to table** सेल्स में टेक्स्ट जोड़ें और प्रमुख पैराग्राफ़ के चारों ओर फ्रेम ड्रॉ करें ताकि आपकी स्लाइड्स आकर्षक बनें। इस ट्यूटोरियल में आप देखेंगे कि कैसे **add text to table** जोड़ें, उसे संरेखित करें, और टेक्स्ट के चारों ओर फ्रेम ड्रॉ करें — सभी Aspose.Slides for Java के साथ। अंत तक, आप ऐसी पॉलिश्ड डेक बना सकेंगे जो सही समय पर सही जानकारी को उजागर करे।

क्या आप अपनी प्रेजेंटेशन को बदलने के लिए तैयार हैं? चलिए शुरू करते हैं!

## त्वरित उत्तर
- **add text to table** का क्या अर्थ है? यह प्रोग्रामेटिक रूप से व्यक्तिगत टेबल सेल्स की टेक्स्ट सामग्री को सम्मिलित या अपडेट करने को दर्शाता है।  
- **फ़ाइल को सहेजने की विधि कौन सी है?** `pres.save("output.pptx", SaveFormat.Pptx)` – यह **save presentation as pptx** चरण आपके बदलावों को अंतिम रूप देता है।  
- **शेप के अंदर टेक्स्ट को कैसे संरेखित करूँ?** `TextAlignment.Left` (या Center/Right) का उपयोग करें `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` के माध्यम से।  
- **क्या मैं पैराग्राफ़ के चारों ओर एक आयत बना सकता हूँ?** हाँ – पैराग्राफ़ पर इटररेट करें, उनका बाउंडिंग रेक्टेंगल प्राप्त करें, और बिना फ़िल और काली लाइन वाले `IAutoShape` को जोड़ें।  
- **क्या मुझे लाइसेंस चाहिए?** एक टेम्पररी लाइसेंस मूल्यांकन के लिए काम करता है; उत्पादन उपयोग के लिए पूर्ण लाइसेंस आवश्यक है।

## पूर्वापेक्षाएँ

कोड में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### आवश्यक लाइब्रेरीज़
आपको Aspose.Slides for Java की आवश्यकता होगी। इसे Maven या Gradle का उपयोग करके शामिल करने का तरीका नीचे दिया गया है:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### पर्यावरण सेटअप
एक Java Development Kit (JDK) स्थापित होना चाहिए, आदर्श रूप से JDK 16 या बाद का, क्योंकि इस उदाहरण में `jdk16` क्लासिफ़ायर का उपयोग किया गया है।

### ज्ञान पूर्वापेक्षाएँ
- जावा प्रोग्रामिंग की बुनियादी समझ।  
- PowerPoint जैसे प्रेजेंटेशन सॉफ़्टवेयर से परिचित।  
- IntelliJ IDEA या Eclipse जैसे एकीकृत विकास वातावरण (IDE) का उपयोग करने का अनुभव।

## Aspose.Slides for Java सेटअप

Aspose.Slides का उपयोग शुरू करने के लिए निम्न चरणों का पालन करें:

1. **लाइब्रेरी इंस्टॉल करें**: Maven या Gradle का उपयोग करके डिपेंडेंसीज़ प्रबंधित करें, या सीधे [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

2. **लाइसेंस प्राप्ति**:
   - एक मुफ्त ट्रायल के साथ शुरू करें, टेम्पररी लाइसेंस को [Temporary License](https://purchase.aspose.com/temporary-license/) से डाउनलोड करके।
   - पूर्ण एक्सेस के लिए, लाइसेंस खरीदने पर विचार करें: [Purchase Aspose.Slides](https://purchase.aspose.com/buy)।

3. **बेसिक इनिशियलाइज़ेशन**:
   निम्न कोड स्निपेट के साथ अपने प्रेजेंटेशन वातावरण को इनिशियलाइज़ करें:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## टेबल में टेक्स्ट जोड़ने और फ्रेम ड्रॉ करने का कारण क्या है?

टेबल में टेक्स्ट जोड़ने से आप संरचित डेटा को स्पष्ट रूप से प्रस्तुत कर सकते हैं, जबकि पैराग्राफ़ या विशिष्ट हिस्सों (जैसे **'0'** अक्षर वाले) के चारों ओर फ्रेम ड्रॉ करने से दर्शकों का ध्यान महत्वपूर्ण मानों की ओर आकर्षित होता है। यह संयोजन वित्तीय रिपोर्ट, डैशबोर्ड, या किसी भी स्लाइड के लिए आदर्श है जहाँ आपको प्रमुख संख्याओं को बिना अव्यवस्था के उजागर करना होता है।

## Aspose.Slides for Java में टेबल में टेक्स्ट कैसे जोड़ें

### फीचर 1: टेबल बनाएं और सेल्स में टेक्स्ट जोड़ें

#### सारांश
यह फीचर दर्शाता है कि **how to create table** कैसे बनाएं, फिर **add text to table** सेल्स में जोड़ें और बाद में **save presentation as pptx** करें।

#### कदम

**1. टेबल बनाएं**  
पहले, अपनी प्रेजेंटेशन को इनिशियलाइज़ करें और (50, 50) स्थिति पर निर्दिष्ट कॉलम चौड़ाई और रो ऊँचाई के साथ एक टेबल जोड़ें।  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. सेल्स में टेक्स्ट जोड़ें**  
पैराग्राफ़ बनाएं जिसमें टेक्स्ट के हिस्से हों और उन्हें एक विशिष्ट सेल में जोड़ें।  
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

**3. प्रेजेंटेशन सहेजें**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### फीचर 2: AutoShape में TextFrame जोड़ें और संरेखण सेट करें

#### सारांश
एक ऑटोशेप में विशिष्ट संरेखण के साथ टेक्स्ट फ्रेम जोड़ना सीखें—यह **set text alignment java** का एक उदाहरण है।

#### कदम

**1. AutoShape जोड़ें**  
(400, 100) स्थिति पर निर्दिष्ट आयामों के साथ एक आयत को AutoShape के रूप में जोड़ें।  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. टेक्स्ट संरेखण सेट करें**  
टेक्स्ट को “Text in shape” सेट करें और उसे बाएँ संरेखित करें।  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. प्रेजेंटेशन सहेजें**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### फीचर 3: टेबल सेल्स में पैराग्राफ़ और हिस्सों के चारों ओर फ्रेम ड्रॉ करें

#### सारांश
यह फीचर **draw frames around text** और यहाँ तक कि **draw rectangle around paragraph** को भी कवर करता है, विशेष रूप से उन हिस्सों के लिए जिनमें अक्षर ‘0’ है।

#### कदम

**1. टेबल बनाएं**  
प्रारंभिक सेटअप के लिए “Create Table and Add Text to Cells” कोड को पुनः उपयोग करें।  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. पैराग्राफ़ जोड़ें**  
पिछले फीचर से पैराग्राफ़ निर्माण कोड को पुनः उपयोग करें।  
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

**3. फ्रेम ड्रॉ करें**  
पैराग्राफ़ और हिस्सों पर इटररेट करके उनके चारों ओर फ्रेम ड्रॉ करें।  
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

**4. प्रेजेंटेशन सहेजें**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## निष्कर्ष
इस गाइड का पालन करके आप **add text to table** कर सकते हैं, शैप्स के अंदर टेक्स्ट संरेखित कर सकते हैं, और महत्वपूर्ण जानकारी को उजागर करने के लिए **draw frames around text** बना सकते हैं। इन तकनीकों में महारत हासिल करने से आप Aspose.Slides for Java के साथ अत्यधिक पॉलिश्ड, डेटा‑ड्रिवन प्रेजेंटेशन बना सकते हैं। आगे की खोज के लिए, इन फीचर्स को चार्ट, एनीमेशन, या PDF एक्सपोर्ट के साथ संयोजित करने का प्रयास करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं इन APIs को पुराने JDK संस्करणों के साथ उपयोग कर सकता हूँ?**  
A: लाइब्रेरी JDK 8 से आगे का समर्थन करती है, लेकिन `jdk16` क्लासिफ़ायर नए रनटाइम्स पर बेहतर प्रदर्शन देता है।

**Q: फ्रेम का रंग कैसे बदलूँ?**  
A: लाइन फ़ॉर्मेट फ़िल रंग को संशोधित करें, उदाहरण के लिए `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`।

**Q: क्या अंतिम स्लाइड को इमेज के रूप में एक्सपोर्ट करना संभव है?**  
A: हाँ—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` का उपयोग करें और फिर बाइट एरे को सहेजें।

**Q: यदि मुझे केवल सेल के भीतर शब्द “Total” को हाइलाइट करना हो तो क्या करूँ?**  
A: `cell.getTextFrame().getParagraphs()` पर इटररेट करें, “Total” वाले हिस्से को खोजें, और उस हिस्से के बाउंडिंग बॉक्स के चारों ओर आयत बनाएं।

**Q: क्या Aspose.Slides बड़े प्रेजेंटेशन को कुशलता से संभालता है?**  
A: API डेटा को स्ट्रीम करता है और `pres.dispose()` कॉल होने पर संसाधनों को रिलीज़ करता है, जिससे बड़े फ़ाइलों के लिए मेमोरी मैनेजमेंट में मदद मिलती है।

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}