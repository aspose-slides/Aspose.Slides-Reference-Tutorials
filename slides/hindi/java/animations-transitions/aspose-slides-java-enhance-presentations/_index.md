---
date: '2026-06-23'
description: PowerPoint में तालिका बनाना, तालिका कोशिकाओं में टेक्स्ट जोड़ना, टेक्स्ट
  के चारों ओर फ़्रेम बनाना, और Aspose.Slides for Java का उपयोग करके प्रस्तुति को pptx
  के रूप में सहेजना सीखें।
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
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
title: PowerPoint में तालिका कैसे बनाएं और Aspose.Slides for Java के साथ फ़्रेम बनाएं
url: /hi/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint में तालिका बनाना और Aspose.Slides for Java के साथ फ्रेम बनाना कैसे करें

## परिचय

प्रोग्रामेटिक रूप से **create table in PowerPoint** बनाना आपके कई घंटे मैन्युअल फॉर्मेटिंग से बचा सकता है, विशेष रूप से जब आपको प्रमुख संख्याओं को हाइलाइट करने या व्याख्यात्मक नोट्स जोड़ने की आवश्यकता हो। इस ट्यूटोरियल में आप सीखेंगे कि तालिका कोशिकाओं में टेक्स्ट कैसे जोड़ें, विशिष्ट पैराग्राफ़ के चारों ओर फ्रेम कैसे बनाएं, सटीक टेक्स्ट अलाइनमेंट सेट करें, और अंत में **save presentation as pptx** – यह सब शक्तिशाली Aspose.Slides for Java API के साथ। अंत तक आपके पास एक स्लाइड होगी जो परिष्कृत दिखेगी, पढ़ने में आसान होगी, और तुरंत दर्शकों का ध्यान सबसे महत्वपूर्ण डेटा की ओर आकर्षित करेगी।

## त्वरित उत्तर
- **add text to table** का क्या अर्थ है? यह प्रोग्रामेटिक रूप से व्यक्तिगत तालिका कोशिकाओं की टेक्स्ट सामग्री को सम्मिलित या अपडेट करने को दर्शाता है।  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – यह **save presentation as pptx** चरण आपके बदलावों को अंतिम रूप देता है।  
- **How can I align text inside a shape?** `TextAlignment.Left` (या Center/Right) का उपयोग `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` के माध्यम से करें।  
- **Can I draw a rectangle around a paragraph?** हाँ – पैराग्राफ़ों पर इटरेट करें, उनका बाउंडिंग रेक्टेंगल प्राप्त करें, और बिना फ़िल और काली लाइन वाले `IAutoShape` को जोड़ें।  
- **Do I need a license?** एक टेम्पररी लाइसेंस मूल्यांकन के लिए काम करता है; उत्पादन उपयोग के लिए पूर्ण लाइसेंस आवश्यक है।  

## टेक्स्ट के चारों ओर फ्रेम क्यों बनाएं?

किसी पैराग्राफ़ या विशिष्ट भाग—जैसे वह टेक्स्ट जिसमें अक्षर **'0'** हो—के चारों ओर फ्रेम (या आयत) बनाना तुरंत दर्शकों का ध्यान उस सामग्री की ओर आकर्षित करता है। यह मूल टेक्स्ट को बदले बिना स्पष्ट दृश्य संकेत प्रदान करता है, जिससे प्रमुख आंकड़े, चेतावनियाँ, या स्लाइड के भीतर सेक्शन को अलग करना आसान हो जाता है।

## पूर्वापेक्षाएँ

कोड में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### आवश्यक लाइब्रेरीज़
आपको Aspose.Slides for Java की आवश्यकता होगी। यहाँ Maven या Gradle का उपयोग करके इसे शामिल करने का तरीका दिया गया है:

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
सुनिश्चित करें कि आपके पास Java Development Kit (JDK) स्थापित है, आदर्श रूप से JDK 16 या बाद का, क्योंकि इस उदाहरण में `jdk16` क्लासिफायर का उपयोग किया गया है।

### ज्ञान पूर्वापेक्षाएँ
- जावा प्रोग्रामिंग की बुनियादी समझ।  
- PowerPoint जैसे प्रस्तुति सॉफ़्टवेयर से परिचित होना।  
- IntelliJ IDEA या Eclipse जैसे एकीकृत विकास वातावरण (IDE) का उपयोग करने का अनुभव।

## Aspose.Slides for Java सेटअप करना

`Presentation` Aspose.Slides की कोर क्लास है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करती है और स्लाइड, शैप, तथा तालिकाओं तक पहुँच प्रदान करती है। Aspose.Slides का उपयोग शुरू करने के लिए नीचे दिए गए चरणों का पालन करें:

1. **लाइब्रेरी स्थापित करें**: Maven या Gradle का उपयोग करके निर्भरताओं को प्रबंधित करें, या इसे सीधे [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

2. **लाइसेंस प्राप्त करना**:
   - एक मुफ्त ट्रायल के साथ शुरू करें और टेम्पररी लाइसेंस को [Temporary License](https://purchase.aspose.com/temporary-license/) से डाउनलोड करें।
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

## Aspose.Slides for Java में तालिका में टेक्स्ट कैसे जोड़ें?

एक नया `Presentation` लोड करें, इच्छित निर्देशांक पर एक तालिका बनाएं, कोशिकाओं को `TextFrame` ऑब्जेक्ट्स से भरें, और अंत में `pres.save("output.pptx", SaveFormat.Pptx)` को कॉल करें। यह क्रम **create table in PowerPoint** बनाता है, प्रत्येक कोशिका में कस्टम टेक्स्ट डालता है, और परिणाम को एक ही प्रभावी वर्कफ़्लो में PPTX फ़ाइल में लिखता है।

### फ़ीचर 1: तालिका बनाएं और कोशिकाओं में टेक्स्ट जोड़ें

#### सारांश
यह फ़ीचर दिखाता है कि **create table** कैसे बनाएं, फिर **add text to table** कोशिकाओं में टेक्स्ट जोड़ें और अंत में **save presentation as pptx** करें।

#### चरण

**1. Create a Table**  
पहले अपने प्रेजेंटेशन को इनिशियलाइज़ करें और (50, 50) स्थिति पर निर्दिष्ट कॉलम चौड़ाई और पंक्ति ऊँचाई के साथ एक तालिका जोड़ें।  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Text to Cells**  
पैराग्राफ़ बनाएं जिनमें टेक्स्ट के भाग हों और उन्हें किसी विशिष्ट कोशिका में जोड़ें।  
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
**set text alignment java** का एक उदाहरण—कैसे एक ऑटोशेप में विशिष्ट अलाइनमेंट के साथ टेक्स्ट फ्रेम जोड़ें।

#### चरण

AutoShape एक ऐसा शैप है जो टेक्स्ट और ग्राफ़िक्स रख सकता है।

**1. Add an AutoShape**  
(400, 100) स्थिति पर निर्दिष्ट आयामों के साथ एक आयत को AutoShape के रूप में जोड़ें।  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum शैप के भीतर टेक्स्ट के क्षैतिज अलाइनमेंट विकल्पों को परिभाषित करता है।

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

### फ़ीचर 3: तालिका कोशिकाओं में पैराग्राफ़ और भागों के चारों ओर फ्रेम बनाएं

#### सारांश
यह फ़ीचर **draw frames around text** और **draw rectangle around paragraph** को दर्शाता है, विशेष रूप से उन भागों के लिए जिनमें अक्षर ‘0’ हो।

#### चरण

`IAutoShape` एक शैप ऑब्जेक्ट है जिसे स्लाइड पर ड्रॉ किया जा सकता है, जैसे फ्रेम के लिए आयतें।

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
पैराग्राफ़ों और भागों पर इटरेट करें और उनके चारों ओर फ्रेम बनाएं।  
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

## सामान्य कठिनाइयाँ और टिप्स

- **Null checks** – हमेशा अपने `Presentation` उपयोग को `try‑finally` ब्लॉक में रखें ताकि `pres.dispose()` चलकर नेटिव रिसोर्सेज़ मुक्त हो सकें।  
- **Bounding rectangle accuracy** – `para.getRect()` द्वारा लौटाया गया आयत वर्तमान लेआउट को दर्शाता है; यदि आप फ़ॉन्ट आकार या मार्जिन बदलते हैं, तो फ्रेम ड्रॉ करने से पहले आयत को पुनः गणना करें।  
- **Performance** – बहुत बड़ी तालिकाओं के साथ काम करते समय, शैप जोड़ने को बैच में करने या एक ही `IAutoShape` इंस्टेंस को अपडेटेड ज्योमेट्री के साथ पुन: उपयोग करने पर विचार करें ताकि मेमोरी ओवरहेड कम हो।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं इन APIs को पुराने JDK संस्करणों के साथ उपयोग कर सकता हूँ?**  
A: लाइब्रेरी JDK 8 से आगे का समर्थन करती है, लेकिन `jdk16` क्लासिफायर नए रनटाइम पर बेहतर प्रदर्शन देता है।

**Q: मैं फ्रेम का रंग कैसे बदलूँ?**  
A: लाइन फ़ॉर्मेट फ़िल रंग को संशोधित करें, उदाहरण के लिए `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`।

**Q: क्या अंतिम स्लाइड को इमेज के रूप में एक्सपोर्ट करना संभव है?**  
A: हाँ—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` का उपयोग करें और फिर बाइट ऐरे को सहेजें।

**Q: यदि मुझे केवल कोशिका के भीतर शब्द “Total” को हाइलाइट करना हो तो क्या करूँ?**  
A: `cell.getTextFrame().getParagraphs()` पर इटरेट करें, “Total” वाले भाग को खोजें, और उस भाग के बाउंडिंग बॉक्स के चारों ओर आयत बनाएं।

**Q: क्या Aspose.Slides बड़े प्रेजेंटेशन को कुशलता से संभालता है?**  
A: API डेटा को स्ट्रीम करता है और `pres.dispose()` कॉल होने पर रिसोर्सेज़ रिलीज़ करता है, जिससे बड़े फ़ाइलों के लिए मेमोरी मैनेजमेंट आसान हो जाता है।

---

**अंतिम अपडेट:** 2026-06-23  
**टेस्टेड विथ:** Aspose.Slides for Java 25.4 (jdk16)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Slides for Java: PowerPoint प्रस्तुतियों में PPTX तालिका और टेक्स्ट हेरफेर में महारत](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Aspose.Slides for Java का उपयोग करके PowerPoint में डायनामिक टेक्स्ट फ्रेम कैसे बनाएं](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Aspose.Slides for Java का उपयोग करके टेक्स्ट फ्रेम में कॉलम जोड़ें](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}