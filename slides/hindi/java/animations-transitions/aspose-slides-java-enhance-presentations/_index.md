---
date: '2026-02-09'
description: जानेँ कि Aspose.Slides for Java का उपयोग करके PowerPoint में टेक्स्ट
  के चारों ओर फ्रेम कैसे बनाएं और टेबल सेल्स में टेक्स्ट कैसे जोड़ें। यह ट्यूटोरियल
  टेबल बनाने, टेक्स्ट अलाइनमेंट सेट करने और प्रस्तुति को pptx के रूप में सहेजने को
  कवर करता है।
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides for Java के साथ फ्रेम बनाना और तालिका में टेक्स्ट जोड़ना
url: /hi/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java के साथ प्रस्तुतियों में फ्रेम कैसे बनाएं और तालिका में टेक्स्ट जोड़ें

## परिचय

PowerPoint में डेटा को स्पष्ट रूप से प्रस्तुत करना वास्तव में एक बड़ी चुनौती हो सकती है, विशेष रूप से जब आपको **add text to table** कोशिकाओं में टेक्स्ट जोड़ना हो और महत्वपूर्ण मानों को दृश्य संकेतों से हाइलाइट करना हो। इस गाइड में आप सीखेंगे **how to draw frames** विशिष्ट पैराग्राफ़ के चारों ओर, आकारों के भीतर टेक्स्ट अलाइनमेंट सेट करना, और अंत में **save presentation as pptx**—सभी Aspose.Slides for Java का उपयोग करके। अंत में आपके पास एक परिष्कृत स्लाइड डेक होगा जो दर्शकों की नजर ठीक उसी जगह आकर्षित करेगा जहाँ आप चाहते हैं।

क्या आप अपनी स्लाइड्स को अलग बनाना चाहते हैं? चलिए प्रक्रिया को चरण दर चरण देखते हैं।

## त्वरित उत्तर
- **What does “add text to table” mean?** इसका अर्थ है प्रोग्रामेटिक रूप से व्यक्तिगत तालिका कोशिकाओं की टेक्स्ट सामग्री को सम्मिलित या अपडेट करना।  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – यह **save presentation as pptx** चरण आपके बदलावों को अंतिम रूप देता है।  
- **How can I align text inside a shape?** `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` के माध्यम से `TextAlignment.Left` (या Center/Right) का उपयोग करें।  
- **Can I draw a rectangle around a paragraph?** हाँ – पैराग्राफ़ों पर इटरेट करें, उनका बाउंडिंग रेक्टैंगल प्राप्त करें, और बिना फ़िल और काली लाइन वाले `IAutoShape` को जोड़ें।  
- **Do I need a license?** मूल्यांकन के लिए एक अस्थायी लाइसेंस काम करता है; उत्पादन उपयोग के लिए पूर्ण लाइसेंस आवश्यक है।  

## टेक्स्ट के चारों ओर फ्रेम क्यों बनाएं?

पैराग्राफ़ या किसी विशिष्ट भाग (उदाहरण के लिए, वह टेक्स्ट जिसमें **'0'** अक्षर हो) के चारों ओर फ्रेम (या आयत) बनाना तुरंत ध्यान आकर्षित करता है। यह तकनीक निम्नलिखित के लिए आदर्श है:

- तालिका में प्रमुख वित्तीय आंकड़ों को हाइलाइट करना।  
- स्लाइड में चेतावनियों या महत्वपूर्ण नोट्स को ज़ोर देना।  
- अतिरिक्त आकारों को मैन्युअली जोड़ने के बिना दृश्य विभाजक बनाना।

## पूर्वापेक्षाएँ

कोड में डुबने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### Required Libraries
आपको Aspose.Slides for Java की आवश्यकता होगी। इसे Maven या Gradle का उपयोग करके शामिल करने का तरीका इस प्रकार है:

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
सुनिश्चित करें कि आपके पास Java Development Kit (JDK) स्थापित है, आदर्श रूप से JDK 16 या बाद का, क्योंकि इस उदाहरण में `jdk16` क्लासिफ़ायर का उपयोग किया गया है।

### ज्ञान पूर्वापेक्षाएँ
- Java प्रोग्रामिंग की बुनियादी समझ।  
- PowerPoint जैसे प्रस्तुति सॉफ़्टवेयर से परिचित होना।  
- IntelliJ IDEA या Eclipse जैसे Integrated Development Environment (IDE) का उपयोग करने का अनुभव।

## Aspose.Slides for Java की सेटअप

Aspose.Slides का उपयोग शुरू करने के लिए, निम्न चरणों का पालन करें:

1. **Install the Library**: निर्भरताओं को प्रबंधित करने के लिए Maven या Gradle का उपयोग करें, या इसे सीधे [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

2. **License Acquisition**:
   - एक मुफ्त ट्रायल से शुरू करें, [Temporary License](https://purchase.aspose.com/temporary-license/) से अस्थायी लाइसेंस डाउनलोड करके।
   - पूर्ण एक्सेस के लिए, [Purchase Aspose.Slides](https://purchase.aspose.com/buy) पर लाइसेंस खरीदने पर विचार करें।

3. **Basic Initialization**:
   निम्न कोड स्निपेट के साथ अपने प्रस्तुति वातावरण को इनिशियलाइज़ करें:
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Aspose.Slides for Java में तालिका में टेक्स्ट कैसे जोड़ें

### फ़ीचर 1: तालिका बनाएं और कोशिकाओं में टेक्स्ट जोड़ें

#### सारांश
यह फ़ीचर दिखाता है कि कैसे **create table** किया जाए, फिर **add text to table** कोशिकाओं में टेक्स्ट जोड़ा जाए और बाद में **save presentation as pptx** किया जाए।

#### कदम

**1. Create a Table**  
सबसे पहले, अपनी प्रस्तुति को इनिशियलाइज़ करें और (50, 50) स्थिति पर निर्दिष्ट कॉलम चौड़ाई और पंक्ति ऊँचाई के साथ एक तालिका जोड़ें।  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
पैराग्राफ़ बनाएं जिसमें टेक्स्ट के हिस्से हों और उन्हें एक विशिष्ट कोशिका में जोड़ें।  
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

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### फ़ीचर 2: AutoShape में TextFrame जोड़ें और अलाइनमेंट सेट करें

#### सारांश
एक AutoShape में विशिष्ट अलाइनमेंट के साथ टेक्स्ट फ्रेम जोड़ना सीखें—यह **set text alignment java** का एक उदाहरण है।

#### कदम

**1. Add an AutoShape**  
स्थिति (400, 100) पर निर्दिष्ट आयामों के साथ एक आयत को AutoShape के रूप में जोड़ें।  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
टेक्स्ट को “Text in shape” सेट करें और उसे बाएँ अलाइन करें।  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### फ़ीचर 3: तालिका कोशिकाओं में पैराग्राफ़ और हिस्सों के चारों ओर फ्रेम बनाएं

#### सारांश
यह फ़ीचर **draw frames around text** और यहाँ तक कि ‘0’ अक्षर वाले हिस्सों के लिए **draw rectangle around paragraph** पर केंद्रित है।

#### कदम

**1. Create a Table**  
प्रारंभिक सेटअप के लिए “Create Table and Add Text to Cells” कोड को पुनः उपयोग करें।  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
पिछले फ़ीचर से पैराग्राफ़ निर्माण कोड को पुनः उपयोग करें।  
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

**3. Draw Frames**  
पैराग्राफ़ और हिस्सों पर इटरेट करके उनके चारों ओर फ्रेम बनाएं।  
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

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## सामान्य कठिनाइयाँ और सुझाव

- **Null checks** – हमेशा अपने `Presentation` उपयोग को एक try‑finally ब्लॉक में लपेटें ताकि `pres.dispose()` चल सके और मूल संसाधनों को मुक्त कर सके।  
- **Bounding rectangle accuracy** – `para.getRect()` द्वारा लौटाया गया आयत वर्तमान लेआउट को दर्शाता है; यदि आप फ़ॉन्ट आकार या मार्जिन बदलते हैं, तो फ्रेम ड्रॉ करने से पहले आयत को पुनः गणना करें।  
- **Performance** – बहुत बड़ी तालिकाओं के साथ काम करते समय, आकार जोड़ने को बैच करने या अपडेटेड ज्योमेट्री के साथ एक ही `IAutoShape` इंस्टेंस को पुन: उपयोग करने पर विचार करें ताकि मेमोरी ओवरहेड कम हो।

## अक्सर पूछे जाने वाले प्रश्न

**Q: Can I use these APIs with older JDK versions?**  
A: लाइब्रेरी JDK 8 से आगे का समर्थन करती है, लेकिन `jdk16` क्लासिफ़ायर नए रनटाइम पर सबसे अच्छा प्रदर्शन देता है।

**Q: How do I change the frame color?**  
A: लाइन फ़ॉर्मेट फ़िल रंग को बदलें, उदाहरण के लिए, `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`।

**Q: Is it possible to export the final slide as an image?**  
A: हाँ—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` का उपयोग करें और फिर बाइट एरे को सहेजें।

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: `cell.getTextFrame().getParagraphs()` पर इटरेट करें, “Total” शब्द वाले हिस्से को खोजें, और उस हिस्से के बाउंडिंग बॉक्स के चारों ओर एक आयत बनाएं।

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API डेटा को स्ट्रीम करता है और `pres.dispose()` कॉल होने पर संसाधनों को मुक्त करता है, जिससे बड़े फ़ाइलों के लिए मेमोरी प्रबंधन में मदद मिलती है।

---

**अंतिम अपडेट:** 2026-02-09  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (jdk16)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
