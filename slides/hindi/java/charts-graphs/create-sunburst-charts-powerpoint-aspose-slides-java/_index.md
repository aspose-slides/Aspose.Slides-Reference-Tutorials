---
date: '2026-07-17'
description: Aspose Slides for Java का उपयोग करके PowerPoint में Sunburst Charts जोड़ना
  सीखें। चरण‑दर‑चरण गाइड में सेटअप, चार्ट निर्माण, कस्टमाइज़ेशन, और वास्तविक‑दुनिया
  के उपयोग मामलों को कवर किया गया है।
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Aspose Slides for Java का उपयोग करके PowerPoint में Sunburst Charts
  जोड़ने का तरीका। इस ट्यूटोरियल का पालन करके लाइब्रेरी सेट अप करें, चार्ट बनाएं,
  डेटा पॉइंट्स को कस्टमाइज़ करें, और इसे वास्तविक प्रोजेक्ट्स में लागू करें।
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Aspose (Java) के साथ PowerPoint में Sunburst Charts जोड़ने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Aspose (Java) के साथ PowerPoint में Sunburst Charts जोड़ने का तरीका
url: /hi/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose (Java) के साथ PowerPoint में Sunburst चार्ट कैसे जोड़ें

## परिचय

PowerPoint डेक में Sunburst चार्ट जोड़ने से एक सपाट डेटा तालिका तुरंत एक आकर्षक दृश्य पदानुक्रम में बदल सकती है। इस ट्यूटोरियल में आप Aspose.Slides for Java का उपयोग करके PowerPoint में **Sunburst जोड़ना** सीखेंगे, पर्यावरण सेटअप से लेकर रंगों और लेबलों को बारीकी से समायोजित करने तक। चाहे आप बिक्री डैशबोर्ड, प्रोजेक्ट‑टास्क ब्रेकडाउन, या शैक्षिक स्लाइड डेक बना रहे हों, नीचे दिए गए चरण आपको उत्पादन‑तैयार समाधान देंगे।

**आप क्या सीखेंगे**
- Maven या Gradle प्रोजेक्ट में Aspose.Slides को कॉन्फ़िगर करना  
- नया प्रस्तुति बनाना और Sunburst चार्ट सम्मिलित करना  
- डेटा पॉइंट्स, लेबल और फ़िल रंगों को अनुकूलित करना  
- वास्तविक दुनिया के परिदृश्य जहाँ Sunburst चार्ट चमकते हैं  

आइए शुरू करें और देखें कि कच्चे पदानुक्रम डेटा को एक परिष्कृत PowerPoint दृश्य में बदलना कितना आसान है।

## त्वरित उत्तर
- **मुख्य लाइब्रेरी?** Aspose.Slides for Java  
- **समर्थित चार्ट प्रकार?** Sunburst (त्रिज्यात्मक पदानुक्रमिक)  
- **न्यूनतम Java संस्करण?** JDK 16  
- **सामान्य कार्यान्वयन समय?** बुनियादी चार्ट के लिए 10‑15 मिनट  
- **उत्पादन के लिए लाइसेंस आवश्यक?** हाँ, एक वैध Aspose लाइसेंस  

## Sunburst चार्ट क्या है?
Sunburst चार्ट एक त्रिज्यात्मक आरेख है जो केंद्रीय बिंदु से बाहर की ओर रिंग्स को नेस्ट करके पदानुक्रमिक डेटा को दृश्य रूप देता है। यह संगठन संरचनाओं, उत्पाद श्रेणियों, या फ़ाइल‑सिस्टम ट्री जैसी बहु‑स्तरीय संबंधों को दिखाने के लिए उपयुक्त है। प्रत्येक समांतर रिंग पदानुक्रम के एक स्तर का प्रतिनिधित्व करती है, और प्रत्येक खंड का आकार उसकी मात्रात्मक मान को दर्शाता है, जिससे दर्शक संरचना और परिमाण दोनों को जल्दी समझ सकते हैं।

## Aspose.Slides for Java का उपयोग क्यों करें?
Aspose.Slides **50+ चार्ट प्रकार** का समर्थन करता है और **10,000 स्लाइड्स** तक की प्रस्तुतियों को पूरी फ़ाइल को मेमोरी में लोड किए बिना संभाल सकता है, जिससे एंटरप्राइज़‑स्तर की रिपोर्टिंग के लिए उच्च प्रदर्शन मिलता है। यह क्रॉस‑प्लेटफ़ॉर्म काम करता है, व्यापक API कवरेज प्रदान करता है, और मजबूत लाइसेंसिंग विकल्प शामिल करता है जो मूल्यांकन सीमाओं को हटाते हैं, जिससे यह उत्पादन वातावरण के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK)** 16 या नया  
- **IDE** – IntelliJ IDEA, Eclipse, या कोई भी Java‑संगत संपादक  
- Java सिंटैक्स और Maven/Gradle बिल्ड टूल्स की बुनियादी परिचितता  

## Aspose.Slides for Java सेटअप करना

### Maven निर्भरता
अपने `pom.xml` में Aspose.Slides Maven आर्टिफैक्ट जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle निर्भरता
यदि आप Gradle पसंद करते हैं, तो `build.gradle` में निम्न पंक्ति शामिल करें:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### सीधे डाउनलोड
आप आधिकारिक रिलीज़ पेज से नवीनतम JAR सीधे डाउनलोड भी कर सकते हैं: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)।

### लाइसेंस प्राप्ति
मूल्यांकन सीमाओं के बिना चलाने के लिए, एक लाइसेंस प्राप्त करें:
- **Free trial** – त्वरित मूल्यांकन के लिए अस्थायी लाइसेंस।  
- **Temporary license** – [Aspose वेबसाइट](https://purchase.aspose.com/temporary-license) से अनुरोध करें।  
- **Full purchase** – अनलिमिटेड उत्पादन उपयोग के लिए सब्सक्रिप्शन खरीदें।

### बुनियादी प्रारंभिककरण
`Presentation` क्लास PowerPoint फ़ाइलें बनाने या खोलने के लिए प्रवेश बिंदु है।

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## कार्यान्वयन गाइड

### Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में Sunburst चार्ट कैसे जोड़ें?
एक नया `Presentation` लोड करें, एक स्लाइड जोड़ें, `ChartType.Sunburst` प्रकार का `IChart` सम्मिलित करें, और `save` को कॉल करें। यह संक्षिप्त तीन‑चरणीय पैटर्न एक पूर्ण कार्यात्मक Sunburst चार्ट बनाता है जो आगे के अनुकूलन के लिए तैयार है।

#### चरण 1: प्रस्तुति को प्रारंभ करें
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### चरण 2: Sunburst चार्ट जोड़ें
`IChart` इंटरफ़ेस एक चार्ट ऑब्जेक्ट को परिभाषित करता है जिसे किसी भी स्लाइड पर रखा जा सकता है। यहाँ हम (100, 100) निर्देशांक पर 450 × 400 पॉइंट्स आकार का Sunburst चार्ट जोड़ते हैं।

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### चरण 3: प्रस्तुति सहेजें
हमेशा `save` को कॉल करके अपने परिवर्तन सहेजें। आप PPTX, PDF, या 50+ समर्थित आउटपुट फॉर्मेट्स में से कोई भी चुन सकते हैं।

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### चार्ट में डेटा पॉइंट्स संशोधित करें

#### अवलोकन
आप चार्ट के डेटा पॉइंट संग्रह के माध्यम से Sunburst के प्रत्येक स्लाइस—लेबल, रंग, और दृश्यता—को अनुकूलित कर सकते हैं।

#### चरण 1: डेटा पॉइंट्स संग्रह तक पहुंचें
चार्ट की पहली सीरीज़ में `IChartDataPoint` ऑब्जेक्ट्स का संग्रह होता है जो प्रत्येक स्लाइस का प्रतिनिधित्व करता है।

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### चरण 2: विशिष्ट डेटा पॉइंट के लिए मान दिखाएँ
इच्छित डेटा पॉइंट पर `IsValueShown` को `true` सेट करें ताकि उसका संख्यात्मक मान सीधे स्लाइस पर दिखे।

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### चरण 3: लेबल फ़ॉर्मेट संशोधित करें
लेबल की दृश्यता, फ़ॉन्ट रंग, और पृष्ठभूमि को समायोजित करें ताकि पठनीयता बढ़े।

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### चरण 4: डेटा पॉइंट्स के लिए फ़िल रंग सेट करें
व्यक्तिगत स्लाइस के फ़िल रंग को अपने ब्रांड पैलेट के अनुसार या प्रमुख खंडों को उजागर करने के लिए अनुकूलित करें।

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### चरण 5: संशोधित प्रस्तुति सहेजें
प्रस्तुति को फिर से सहेजकर अनुकूलित चार्ट को सहेजें।

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## व्यावहारिक अनुप्रयोग

1. **व्यवसाय विश्लेषण** – एकल त्रिज्यात्मक दृश्य में क्षेत्र → उत्पाद लाइन → SKU द्वारा बिक्री को दृश्य बनाएं।  
2. **प्रोजेक्ट प्रबंधन** – कार्य विभाजन संरचनाओं को दिखाएं, चरणों से कार्यों और उप‑कार्य तक ड्रिल करें।  
3. **शिक्षा** – पाठ्यक्रम पदानुक्रम को मैप करें, जैसे विभाग → पाठ्यक्रम → मॉड्यूल।  

## प्रदर्शन संबंधी विचार

- **Memory Efficiency:** Aspose.Slides डेटा को स्ट्रीम करता है, इसलिए कई चार्ट वाले 500‑पृष्ठ डेक भी 200 MB RAM से कम रहता है।  
- **Garbage Collection:** जब स्लाइड ऑब्जेक्ट्स की आवश्यकता न हो तो (`slide.dispose()`) उन्हें रिलीज़ करें ताकि मेमोरी लीक न हो।  

## अक्सर पूछे जाने वाले प्रश्न

**प्र.: Sunburst चार्ट क्या है?**  
उ: Sunburst चार्ट पदानुक्रमिक डेटा को समांतर रिंग्स में दृश्य बनाता है, जहाँ प्रत्येक रिंग पदानुक्रम के एक स्तर का प्रतिनिधित्व करती है।

**प्र.: Maven का उपयोग करके Aspose.Slides for Java कैसे स्थापित करें?**  
उ: “Maven Dependency” सेक्शन में दिखाए गए Maven निर्भरता को अपने `pom.xml` में जोड़ें और `mvn clean install` चलाएँ।

**प्र.: क्या मैं Aspose.Slides के साथ अन्य चार्ट प्रकार अनुकूलित कर सकता हूँ?**  
उ: हाँ, लाइब्रेरी 50 से अधिक चार्ट प्रकारों का समर्थन करती है, जिसमें कॉलम, लाइन, पाई, और रडार चार्ट शामिल हैं।

**प्र.: मेरी प्रस्तुति सहेज नहीं रही है—मैं क्या जांचूँ?**  
उ: फ़ाइल पथ सही है, डायरेक्टरी मौजूद है, और आपके पास लिखने की अनुमति है, यह सत्यापित करें। साथ ही, सुनिश्चित करें कि `Presentation.save()` मेथड कॉल किया गया है।

**प्र.: अधिक मदद या उदाहरण कहाँ प्राप्त कर सकते हैं?**  
उ: [Aspose फोरम](https://forum.aspose.com/c/slides/11) पर जाएँ या आधिकारिक [Aspose.Slides रेफ़रेंस](https://reference.aspose.com/slides/java/) देखें।

## संसाधन
- **डॉक्यूमेंटेशन:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **संदर्भ (छोटे अक्षर):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **कम्युनिटी फ़ोरम:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **डाउनलोड्स:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**अंतिम अपडेट:** 2026-07-17  
**परीक्षित संस्करण:** Aspose.Slides for Java 24.12  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Slides for Java का उपयोग करके PowerPoint में चार्ट कैसे जोड़ें: चरण‑दर‑चरण गाइड](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java का उपयोग करके PowerPoint में चार्ट एनीमेट करें – चरण‑दर‑चरण गाइड](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Java में Aspose.Slides के साथ चार्ट बनाएं – जोड़ें और वैधता जांचें](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}