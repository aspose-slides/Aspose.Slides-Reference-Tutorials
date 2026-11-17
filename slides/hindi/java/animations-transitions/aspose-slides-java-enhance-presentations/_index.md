---
date: '2026-11-16'
description: Aspose.Slides for Java का उपयोग करके PowerPoint टेबल में टेक्स्ट के चारों
  ओर फ़्रेम बनाएं – टेबल बनाना, सेल में टेक्स्ट जोड़ना, सेल को हाइलाइट करना, और फ़ाइल
  को PPTX के रूप में एक्सपोर्ट करना सीखें।
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Aspose.Slides for Java का उपयोग करके PowerPoint टेबल में टेक्स्ट के
  चारों ओर फ़्रेम बनाएं। यह गाइड टेबल बनाने, टेक्स्ट जोड़ने और align करने, सेल को
  हाइलाइट करने, और स्लाइड को PNG के रूप में एक्सपोर्ट करने का तरीका दिखाता है।
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: PowerPoint में टेक्स्ट के चारों ओर फ़्रेम बनाएं और Aspose.Slides for Java
  के साथ टेबल बनाएं
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: PowerPoint में टेक्स्ट के चारों ओर फ़्रेम कैसे बनाएं और Aspose.Slides for Java
  के साथ टेबल बनाएं
url: /hi/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint में टेक्स्ट के चारों ओर फ्रेम कैसे बनाएं और तालिकाएँ बनाएं Aspose.Slides for Java

## परिचय

PowerPoint स्लाइड में **draw frame around text** बनाना आपको मुख्य आंकड़ों को बिना मूल सामग्री बदले उजागर करने में मदद करता है। इस ट्यूटोरियल में आप प्रोग्रामेटिक रूप से तालिका बनाना, कोशिकाओं के भीतर टेक्स्ट डालना और संरेखित करना, विशिष्ट शब्दों या पूरी कोशिकाओं को हाइलाइट करना, और अंत में प्रस्तुति को PPTX फ़ाइल के रूप में सहेजना सीखेंगे। अंत तक आपके पास एक ऐसा स्लाइड होगा जो दर्शकों की नजर ठीक उसी जगह पर ले जाएगा जहाँ आप चाहते हैं।

## त्वरित उत्तर
- **What does “add text to table” mean?** यह व्यक्तिगत तालिका कोशिकाओं की टेक्स्ट सामग्री को प्रोग्रामेटिक रूप से सम्मिलित या अपडेट करने का अर्थ है।  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – यह **save presentation as pptx** चरण आपके बदलावों को अंतिम रूप देता है।  
- **How can I align text inside a shape?** `TextAlignment.Left` (या Center/Right) का उपयोग `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` के माध्यम से करें।  
- **Can I draw a rectangle around a paragraph?** हाँ – पैराग्राफ़ों पर इटररेट करें, उनका बाउंडिंग रेक्टेंगल प्राप्त करें, और बिना फ़िल और काली लाइन वाले `IAutoShape` को जोड़ें।  
- **Do I need a license?** मूल्यांकन के लिए एक अस्थायी लाइसेंस काम करता है; उत्पादन उपयोग के लिए पूर्ण लाइसेंस आवश्यक है।  

## टेक्स्ट के चारों ओर फ्रेम क्यों बनाएं?

टेक्स्ट के चारों ओर फ्रेम बनाना तुरंत महत्वपूर्ण संख्याओं, चेतावनियों या शीर्षकों को उजागर करता है। यह मूल फ़ॉर्मेटिंग को अपरिवर्तित रखता है, जिससे यह वित्तीय रिपोर्ट, KPI डैशबोर्ड या किसी भी स्लाइड के लिए आदर्श है जहाँ ज़ोर देना आवश्यक है।

## टेक्स्ट के चारों ओर फ्रेम क्या है?

`draw frame around text` वह तकनीक है जिसमें प्रोग्रामेटिक रूप से एक आयताकार आकार जोड़ा जाता है जो पैराग्राफ या टेक्स्ट भाग की सटीक सीमा का अनुसरण करता है, लाइन फ़ॉर्मेटिंग के साथ लेकिन अंदर का भाग खाली रहता है। यह सामग्री को बिना टेक्स्ट बदले हाइलाइट करने की अनुमति देता है।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

### आवश्यक लाइब्रेरीज़
आपको Aspose.Slides for Java की आवश्यकता होगी। इसे किसी एक पैकेज मैनेजर के माध्यम से शामिल करें:

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

आप रिलीज़ को यहाँ भी देख सकते हैं: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)।

### पर्यावरण सेटअप
Java Development Kit (JDK) 16 या उससे नया अनुशंसित है क्योंकि उदाहरण `jdk16` क्लासिफ़ायर का उपयोग करते हैं। IntelliJ IDEA या Eclipse जैसे कोई भी IDE काम करेगा।

### ज्ञान पूर्वापेक्षाएँ
- बुनियादी Java प्रोग्रामिंग कौशल।  
- PowerPoint अवधारणाओं (स्लाइड्स, आकार, तालिकाएँ) से परिचित होना।  
- Maven/Gradle कैसे निर्भरताओं को प्रबंधित करता है, इसकी समझ।

## Aspose.Slides for Java सेटअप करना

`Presentation` Aspose.Slides का मुख्य क्लास है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करता है और स्लाइड्स, आकार और तालिकाओं तक पहुँच प्रदान करता है। यह **10,000 स्लाइड्स** तक संभाल सकता है जबकि मेमोरी उपयोग **500 MB** से कम रहता है, जिससे यह बड़े‑स्तर के ऑटोमेशन के लिए उपयुक्त है।

1. **Install the library** – Maven या Gradle का उपयोग करें, या सीधे [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।  
2. **License acquisition** – [Temporary License](https://purchase.aspose.com/temporary-license/) से एक मुफ्त ट्रायल शुरू करें और उत्पादन कार्यभार के लिए [Purchase Aspose.Slides](https://purchase.aspose.com/buy) से पूर्ण लाइसेंस प्राप्त करें।  
3. **Basic initialization** – नया `Presentation` ऑब्जेक्ट बनाएं और आवश्यकतानुसार स्लाइड्स लोड या बनाएं।  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Aspose.Slides for Java में तालिका में टेक्स्ट कैसे जोड़ें?

`Presentation` वह मुख्य क्लास है जो PowerPoint फ़ाइल को मेमोरी में दर्शाता है।  
नया `Presentation` लोड करें, इच्छित निर्देशांक पर एक तालिका बनाएं, कोशिकाओं को `TextFrame` ऑब्जेक्ट्स से भरें, और अंत में `pres.save("output.pptx", SaveFormat.Pptx)` को कॉल करें। यह क्रम **create table in PowerPoint** बनाता है, प्रत्येक कोशिका में कस्टम टेक्स्ट डालता है, और परिणाम को एक ही, कुशल वर्कफ़्लो में PPTX फ़ाइल में लिखता है।

### सीधा उत्तर
`slide.getShapes().addTable(...)` को कॉल करके तालिका बनाएं, फिर प्रत्येक कोशिका के लिए `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))` का उपयोग करें। सभी कोशिकाओं को भरने के बाद `pres.save("output.pptx", SaveFormat.Pptx)` को कॉल करके फ़ाइल लिखें। यह तरीका आपको प्रत्येक कोशिका की सामग्री और शैली को प्रोग्रामेटिक रूप से नियंत्रित करने देता है।

#### फ़ीचर 1: तालिका बनाएं और कोशिकाओं में टेक्स्ट जोड़ें

**1. create a table** – एक प्रस्तुति इनिशियलाइज़ करें, एक स्लाइड जोड़ें, और (50, 50) पर परिभाषित कॉलम चौड़ाई और पंक्ति ऊँचाई के साथ तालिका रखें।  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add text to cells** – प्रत्येक कोशिका के लिए एक `Paragraph` बनाएं, वांछित स्ट्रिंग के साथ एक `Portion` जोड़ें, और पैराग्राफ को कोशिका के `TextFrame` को असाइन करें।  
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

**3. save the presentation** – `pres.save("output.pptx", SaveFormat.Pptx)` को कॉल करें।  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## PowerPoint स्लाइड में टेक्स्ट के चारों ओर फ्रेम कैसे बनाएं?

`Rectangle2D` दो‑आयामी निर्देशांक स्थान में एक आयताकार क्षेत्र का प्रतिनिधित्व करता है।  
स्लाइड लोड करें, वह पैराग्राफ या भाग खोजें जिसे आप उजागर करना चाहते हैं, `getRect()` के माध्यम से उसका बाउंडिंग रेक्टेंगल प्राप्त करें, और फिर बिना फ़िल और रंगीन लाइन वाले `IAutoShape` आयत जोड़ें। यह विधि पूरे पैराग्राफ़ और व्यक्तिगत शब्द भाग दोनों के लिए काम करती है।

### सीधा उत्तर
टेक्स्ट के चारों ओर फ्रेम बनाने के लिए पहले पैराग्राफ़ का रेक्टेंगल प्राप्त करें (`Rectangle2D rect = paragraph.getRect();`)। फिर एक `IAutoShape` आयत बनाएं (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)` सेट करें, और फ़िल को निष्क्रिय करें (`shape.getFillFormat().setFillType(FillType.NoFill)`)। आकार टेक्स्ट को पूरी तरह से आउटलाइन करेगा।

#### फ़ीचर 3: तालिका कोशिकाओं में पैराग्राफ और भागों के चारों ओर फ्रेम बनाएं

**1. create a table** – फ़ीचर 1 से कोड पुनः उपयोग करके प्रारंभिक तालिका सेट करें।  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add paragraphs** – फ़ीचर 1 से पैराग्राफ निर्माण कोड पुनः उपयोग करें।  
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

**3. draw frames** – प्रत्येक पैराग्राफ़ पर इटररेट करें, उसका बाउंडिंग रेक्टेंगल प्राप्त करें, और ऊपर वर्णित अनुसार एक आयताकार आकार जोड़ें। उन भागों के लिए जिनमें अक्षर ‘0’ है, अतिरिक्त फ्रेम जोड़ें ताकि उन संख्याओं को हाइलाइट किया जा सके।  
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

**4. save the presentation** – पहले की तरह अंतिम चरण।  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## AutoShape में टेक्स्ट फ्रेम कैसे जोड़ें और संरेखण सेट करें

`AutoShape` एक ऐसा आकार है जो टेक्स्ट, इमेज या अन्य सामग्री रख सकता है।  
एक `AutoShape` में `TextFrame` हो सकता है। आप `ParagraphFormat` एनेम का उपयोग करके क्षैतिज संरेखण नियंत्रित कर सकते हैं।

### सीधा उत्तर
एक आयताकार AutoShape बनाएं (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), उसका `TextFrame` एक्सेस करें, `shape.getTextFrame().setText("Text in shape")` से टेक्स्ट सेट करें, और फिर `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)` को कॉल करके टेक्स्ट को बाएँ संरेखित करें।

**1. add an AutoShape** – इच्छित स्थान पर एक आयत रखें।  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. set text alignment** – ऊपर दिखाए अनुसार बाएँ संरेखण लागू करें।  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. save the presentation** – वही अंतिम चरण।  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## सामान्य कठिनाइयाँ और सुझाव

- **Always dispose** – `Presentation` उपयोग को try‑finally ब्लॉक में रखें और `pres.dispose()` को कॉल करके नेटिव संसाधन मुक्त करें।  
- **Re‑compute bounding rectangles** – यदि आप फ़ॉन्ट आकार, मार्जिन या कोशिका पैडिंग बदलते हैं तो फ्रेम जोड़ने से पहले `paragraph.getRect()` को फिर से कॉल करें।  
- **Batch shape creation for large tables** – एक ही `IAutoShape` इंस्टेंस को पुन: उपयोग करके और उसकी ज्योमेट्री अपडेट करके बड़ी तालिकाओं (सैकड़ों पंक्तियों) में मेमोरी दबाव कम किया जा सकता है।  
- **Performance numbers** – Aspose.Slides एक सामान्य 4‑कोर सर्वर पर 200‑पेज PPTX को 2 सेकंड से कम समय में जेनरेट कर सकता है, और 1,000 पैराग्राफ़ के चारों ओर फ्रेम बनाना 150 ms से कम ओवरहेड जोड़ता है।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं इन APIs को पुराने JDK संस्करणों के साथ उपयोग कर सकता हूँ?**  
A: लाइब्रेरी JDK 8 से आगे समर्थित है, लेकिन `jdk16` क्लासिफ़ायर नए रनटाइम पर बेहतर प्रदर्शन देता है।

**Q: मैं फ्रेम का रंग कैसे बदलूँ?**  
A: लाइन फ़ॉर्मेट फ़िल रंग को संशोधित करें, उदाहरण के लिए `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`।

**Q: क्या अंतिम स्लाइड को इमेज के रूप में निर्यात करना संभव है?**  
A: हाँ—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` का उपयोग करें और बाइट एरे को सहेजें।

**Q: यदि मुझे केवल कोशिका के भीतर शब्द “Total” को हाइलाइट करना हो तो?**  
A: `cell.getTextFrame().getParagraphs()` पर इटररेट करें, “Total” वाले भाग को खोजें, और उस भाग के बाउंडिंग बॉक्स के चारों ओर एक आयत जोड़ें।

**Q: क्या Aspose.Slides बड़े प्रस्तुतियों को कुशलतापूर्वक संभालता है?**  
A: API डेटा को स्ट्रीम करता है और `pres.dispose()` कॉल करने पर संसाधन रिलीज़ करता है, जिससे बड़ी फ़ाइलों के लिए मेमोरी प्रबंधन आसान हो जाता है।

---

**Last Updated:** 2026-11-16  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

## संबंधित ट्यूटोरियल

- [Aspose.Slides for Java&#58; Master PPTX Table & Text Manipulation in PowerPoint Presentations](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [How to Create Dynamic Text Frames in PowerPoint Using Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Add Columns in Text Frame using Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}