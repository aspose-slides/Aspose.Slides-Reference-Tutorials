---
date: '2026-05-23'
description: Aspose.Slides for Java के साथ PowerPoint में Chart जोड़ना, Chart के axis
  labels को समायोजित करना, और Java में pie chart जोड़ना सीखें – पूर्ण setup, code
  walk‑through, और performance tips।
keywords:
- add chart to powerpoint
- adjust chart axis labels
- add pie chart java
schemas:
- author: Aspose
  dateModified: '2026-05-23'
  description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  headline: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  type: TechArticle
- description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  name: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  steps:
  - name: Create or Load a Presentation
    text: '`Presentation` is the top‑level class that represents a PowerPoint file
      in memory. > **Pro tip:** Always call `presentation.dispose()` after you finish
      to free native resources.'
  - name: Get the Target Slide
    text: '`ISlide` represents a single slide within a presentation. The first slide
      can be accessed via the `getSlides().get_Item(0)` method. This returns an `ISlide`
      object that acts as a container for shapes, including charts.'
  - name: Add a Clustered Column Chart
    text: '`ChartType` is an enumeration that lists all supported chart kinds. `ChartType.ClusteredColumn`
      creates a classic column chart. You can replace it with any other enum value,
      such as `ChartType.Pie` to add a pie chart.'
  - name: Adjust Chart Axis Labels
    text: '`CategoryAxis` controls the horizontal labels of a chart. The **category
      axis** controls horizontal labels. Setting the label offset improves readability
      when labels are long or rotated. > **Why adjust axis labels?** Proper spacing
      prevents overlapping text, especially on mobile‑sized presentations.'
  - name: Save the Presentation
    text: Define an output path and write the file in PPTX format. Aspose.Slides also
      supports saving to PDF, ODP, and HTML if needed.
  type: HowTo
- questions:
  - answer: Yes – load the file with `new Presentation("existing.pptx")`, modify the
      slides, and save it back.
    question: Can I add charts to an existing PowerPoint file?
  - answer: Access the `Chart` object and set `chart.getChartData().setChartType(ChartType.Pie)`
      to switch types instantly.
    question: How do I change a chart’s type after it’s been added?
  - answer: Absolutely – it works with IntelliJ IDEA, Eclipse, NetBeans, and even
      command‑line builds.
    question: Is Aspose.Slides compatible with all major Java IDEs?
  - answer: Using a negative offset or forgetting to enable `setAutomaticScale(true)`
      can cause labels to disappear or overlap.
    question: What are typical pitfalls when configuring axis labels?
  - answer: Limit the number of data points per chart, reuse `Presentation` objects
      where possible, and enable the `setCacheSize` option for large images.
    question: How can I improve rendering speed for massive slide decks?
  type: FAQPage
title: 'Aspose.Slides for Java का उपयोग करके PowerPoint में Chart कैसे जोड़ें: एक
  चरण‑दर‑चरण गाइड'
url: /hi/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java का उपयोग करके PowerPoint में चार्ट जोड़ने की चरण‑दर‑चरण गाइड

## परिचय
यदि आपको प्रोग्रामेटिक रूप से **PowerPoint में चार्ट जोड़ना** है, तो Aspose.Slides for Java आपको एक साफ़, लाइसेंस‑मुक्त तरीका प्रदान करता है जिससे आप बार, लाइन, पाई, या 150+ चार्ट प्रकारों को सीधे PPTX फ़ाइलों में एम्बेड कर सकते हैं। इस ट्यूटोरियल में आप देखेंगे कि प्रस्तुति कैसे बनाएं, चार्ट कैसे डालें, अक्ष लेबल को कैसे समायोजित करें, और परिणाम को कैसे सहेजें—सभी संक्षिप्त Java कोड के साथ जिसे आप कॉपी‑पेस्ट कर सकते हैं।  

**आप क्या सीखेंगे**
- कैसे `Presentation` बनाएं और इनिशियलाइज़ करें।
- कैसे विभिन्न चार्ट प्रकार जोड़ें, जिसमें Java में पाई चार्ट भी शामिल है।
- परिपूर्ण पठनीयता के लिए **चार्ट अक्ष लेबल समायोजित** करने का तरीका।
- अंतिम फ़ाइल को डिस्क पर कैसे सहेजें।

शुरू करने से पहले, सुनिश्चित करें कि आपका वातावरण नीचे सूचीबद्ध आवश्यकताओं को पूरा करता है।

## त्वरित उत्तर
- **क्या मैं मौजूदा PPTX में चार्ट जोड़ सकता हूँ?** हाँ – फ़ाइल को `new Presentation("path.pptx")` से लोड करके उसे संशोधित करें।  
- **कौन से चार्ट प्रकार समर्थित हैं?** 150 से अधिक प्रकार, क्लस्टर्ड कॉलम से लेकर 3‑D पाई तक।  
- **क्या विकास के लिए लाइसेंस चाहिए?** एक मुफ्त ट्रायल सभी फीचर के लिए काम करता है; एक स्थायी लाइसेंस मूल्यांकन सीमाओं को हटाता है।  
- **अक्ष लेबल की दूरी कैसे बदलें?** `chart.getAxes().getCategoryAxis().setLabelOffset(value)` सेट करें।  
- **क्या Aspose.Slides Java Maven और Gradle के साथ संगत है?** बिल्कुल – दोनों बिल्ड टूल समर्थित हैं।

## “PowerPoint में चार्ट जोड़ना” क्या है?
*“PowerPoint में चार्ट जोड़ना”* का अर्थ है API का उपयोग करके स्लाइड में दृश्य डेटा श्रृंखला को प्रोग्रामेटिक रूप से डालना, न कि UI में मैन्युअल डिज़ाइन। यह तकनीक स्वचालित रिपोर्ट निर्माण, गतिशील डेटा अपडेट, और प्रस्तुतियों की बैच प्रोसेसिंग को सक्षम करती है, बिना सर्वर पर Microsoft Office की आवश्यकता के, जिससे यह एंटरप्राइज़‑स्तर के वर्कफ़्लो के लिए आदर्श बनती है।

## Aspose.Slides for Java का उपयोग क्यों करें?
Aspose.Slides प्रस्तुतियों को प्रोसेस कर सकता है जिनमें **10,000 तक स्लाइड्स** और **सैकड़ों मेगाबाइट** डेटा हो, बिना पूरी फ़ाइल को मेमोरी में लोड किए, और कई प्रतिस्पर्धियों की तुलना में **40 % तक तेज़ रेंडरिंग** प्रदान करता है। यह **150+ चार्ट प्रकार**, **50+ इमेज फ़ॉर्मेट**, और **पूर्ण PPTX/ODP संगतता** को भी सपोर्ट करता है, जिससे यह स्वचालित स्लाइड जनरेशन के लिए सबसे बहुमुखी लाइब्रेरी बनती है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK)** 8 या उससे नया।  
- **Aspose.Slides for Java** – Maven, Gradle, या सीधे डाउनलोड के माध्यम से जोड़ें।  
- बुनियादी Java ज्ञान और IntelliJ IDEA या Eclipse जैसे IDE।

### Aspose.Slides for Java सेटअप

#### Maven निर्भरता
अपने `pom.xml` में निम्नलिखित जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle निर्भरता
अपने `build.gradle` फ़ाइल में यह जोड़ें:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### सीधे डाउनलोड
वैकल्पिक रूप से, नवीनतम संस्करण [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

Aspose.Slides का उपयोग शुरू करने के लिए, एक लाइसेंस प्राप्त करें:
- **Free Trial** – पूर्ण फीचर सेट, कोई समय सीमा नहीं।  
- **Temporary License** – [Aspose के टेम्पररी लाइसेंस पेज](https://purchase.aspose.com/temporary-license/) से अनुरोध करें।  
- **Purchase** – [Aspose के खरीद पेज](https://purchase.aspose.com/buy) से स्थायी लाइसेंस प्राप्त करें।

लाइब्रेरी को इनिशियलाइज़ करने के लिए `Presentation` का एक इंस्टेंस बनाएं।

## Aspose.Slides for Java का उपयोग करके PowerPoint में चार्ट कैसे जोड़ें?
`Presentation` ऑब्जेक्ट को लोड या बनाएं, एक स्लाइड प्राप्त करें, इच्छित `ChartType` के साथ `addChart` कॉल करें, डेटा फीड करें, और अंत में `save` कॉल करें। यह पूरी प्रक्रिया केवल कुछ ही Java लाइनों में पूरी हो जाती है और JRE चलाने वाले किसी भी प्लेटफ़ॉर्म पर काम करती है।

### चरण 1: प्रस्तुति बनाएं या लोड करें
`Presentation` वह टॉप‑लेवल क्लास है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करती है।

```java
import com.aspose.slides.Presentation;

// Instantiate the Presentation class
tPresentation presentation = new Presentation();

// Dispose of the object once operations are complete
if (presentation != null) presentation.dispose();
```

> **Pro tip:** समाप्त होने पर हमेशा `presentation.dispose()` कॉल करें ताकि नेटिव संसाधन मुक्त हो सकें।

### चरण 2: लक्ष्य स्लाइड प्राप्त करें
`ISlide` प्रस्तुति के भीतर एकल स्लाइड का प्रतिनिधित्व करता है।  
पहली स्लाइड `getSlides().get_Item(0)` मेथड से एक्सेस की जा सकती है। यह एक `ISlide` ऑब्जेक्ट लौटाता है जो शैप्स, जिसमें चार्ट भी शामिल हैं, के कंटेनर के रूप में कार्य करता है।

```java
import com.aspose.slides.ISlide;

ISlide sld = presentation.getSlides().get_Item(0);
```

### चरण 3: क्लस्टर्ड कॉलम चार्ट जोड़ें
`ChartType` एक एनेमरेशन है जो सभी समर्थित चार्ट प्रकारों को सूचीबद्ध करता है।  
`ChartType.ClusteredColumn` एक क्लासिक कॉलम चार्ट बनाता है। आप इसे किसी अन्य एनेम वैल्यू, जैसे `ChartType.Pie` के साथ बदलकर पाई चार्ट जोड़ सकते हैं।

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = sld.getShapes().addChart(
    ChartType.ClusteredColumn, 20, 20, 500, 300);
```

### चरण 4: चार्ट अक्ष लेबल समायोजित करें
`CategoryAxis` चार्ट के क्षैतिज लेबल को नियंत्रित करता है।  
**कैटेगरी एक्सिस** क्षैतिज लेबल को नियंत्रित करता है। लेबल ऑफसेट सेट करने से लेबल लंबा या घुमा हुआ होने पर पढ़ने में आसानी होती है।

```java
chart.getAxes().getHorizontalAxis().setLabelOffset(500);
```

> **अक्ष लेबल क्यों समायोजित करें?** उचित स्पेसिंग टेक्स्ट के ओवरलैप को रोकती है, विशेष रूप से मोबाइल‑साइज़्ड प्रस्तुतियों में।

### चरण 5: प्रस्तुति सहेजें
एक आउटपुट पाथ निर्धारित करें और फ़ाइल को PPTX फ़ॉर्मेट में लिखें। यदि आवश्यक हो तो Aspose.Slides PDF, ODP, और HTML में सहेजने का भी समर्थन करता है।

```java
import com.aspose.slides.SaveFormat;

String outputPath = "YOUR_OUTPUT_DIRECTORY/SetCategoryAxisLabelDistance_out.pptx";
```

```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Aspose.Slides के साथ Java में पाई चार्ट कैसे जोड़ें?
`ChartType.Pie` के साथ एक नया चार्ट बनाएं, एक सिंगल सीरीज़ को वैल्यूज़ से भरें, और वैकल्पिक रूप से ज़ोर देने के लिए एक्सप्लोडेड स्लाइस सक्षम करें। पाई चार्ट स्वचालित रूप से स्लाइड के थीम को अपनाता है, लेकिन आप रंग, लेजेंड, और डेटा लेबल को पूरी तरह कस्टमाइज़ कर सकते हैं। आप विशिष्ट स्लाइस को हाइलाइट करने के लिए स्टार्ट एंगल और एक्सप्लोड ऑफसेट भी सेट कर सकते हैं।

> **सीधा उत्तर (40‑70 शब्द):**  
`Presentation` को इंस्टैंशिएट करें, एक स्लाइड प्राप्त करें, `slide.getShapes().addChart(ChartType.Pie, x, y, width, height)` कॉल करें, फिर `chart.getChartData().getSeries().add(...)` से संख्यात्मक वैल्यूज़ फीड करें। अंत में `presentation.save("pieChart.pptx", SaveFormat.Pptx)` कॉल करें। यह दस लाइनों से कम कोड में एक पूर्ण कार्यात्मक पाई चार्ट बनाता है।

## व्यावहारिक अनुप्रयोग
- **व्यावसायिक रिपोर्ट** – त्वरित रूप से त्रैमासिक वित्तीय चार्ट जनरेट करें।  
- **शैक्षणिक प्रस्तुतियाँ** – CSV शोध डेटा को परिष्कृत ग्राफ़ में बदलें।  
- **मार्केटिंग डेक** – बिक्री फ़नल विज़ुअल्स को दैनिक रूप से रिफ्रेश करें, बिना मैन्युअल एडिट के।

## प्रदर्शन संबंधी विचार
जब बड़े डेक्स को संभालते हैं:
- चार्ट डेटा एरे को 10 000 पॉइंट्स से कम रखें ताकि मेमोरी स्पाइक न हो।  
- `presentation.dispose()` तुरंत कॉल करें।  
- बैच प्रोसेसिंग (`Presentation` ऑब्जेक्ट्स को लूप में) का उपयोग करें ताकि JVM गैर्बेज कलेक्शन को प्रभावी ढंग से उपयोग किया जा सके।

## सामान्य समस्याएँ और समाधान
- **Memory Leak** – `dispose()` भूलने से नेटिव मेमोरी जमा हो जाती है।  
- **Incorrect Axis Scaling** – सुनिश्चित करें कि आप `chart.getAxes().getValueAxis().setAutomaticScale(true)` सेट करें।  
- **License Not Found** – लाइसेंस फ़ाइल को क्लासपाथ में रखें या प्रोग्रामेटिक रूप से `License license = new License(); license.setLicense("Aspose.Slides.Java.lic");` सेट करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं मौजूदा PowerPoint फ़ाइल में चार्ट जोड़ सकता हूँ?**  
A: हाँ – फ़ाइल को `new Presentation("existing.pptx")` से लोड करें, स्लाइड्स को संशोधित करें, और फिर वापस सहेजें।

**Q: एक बार चार्ट जोड़ने के बाद उसका प्रकार कैसे बदलूँ?**  
A: `Chart` ऑब्जेक्ट को एक्सेस करें और `chart.getChartData().setChartType(ChartType.Pie)` सेट करके तुरंत प्रकार बदलें।

**Q: क्या Aspose.Slides सभी प्रमुख Java IDEs के साथ संगत है?**  
A: बिल्कुल – यह IntelliJ IDEA, Eclipse, NetBeans, और यहाँ तक कि कमांड‑लाइन बिल्ड्स के साथ काम करता है।

**Q: अक्ष लेबल कॉन्फ़िगर करते समय सामान्य समस्याएँ क्या हैं?**  
A: नकारात्मक ऑफसेट उपयोग करना या `setAutomaticScale(true)` को सक्षम करना भूल जाना लेबल गायब या ओवरलैप हो सकते हैं।

**Q: बड़े स्लाइड डेक्स की रेंडरिंग गति कैसे बढ़ाएँ?**  
A: प्रति चार्ट डेटा पॉइंट्स की संख्या सीमित रखें, जहाँ संभव हो `Presentation` ऑब्जेक्ट्स को पुनः उपयोग करें, और बड़े इमेजेज़ के लिए `setCacheSize` विकल्प सक्षम करें।

## संसाधन
- [Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/)
- [Aspose.Slides for Java डाउनलोड करें](https://releases.aspose.com/slides/java/)
- [लाइसेंस खरीदें](https://purchase.aspose.com/buy)
- [मुफ़्त ट्रायल संस्करण](https://releases.aspose.com/slides/java/)
- [टेम्पररी लाइसेंस अनुरोध](https://purchase.aspose.com/temporary-license/)
- [Aspose सपोर्ट फ़ोरम](https://forum.aspose.com/c/slides/11)

---

**अंतिम अपडेट:** 2026-05-23  
**परीक्षण किया गया:** Aspose.Slides for Java 24.11  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [PowerPoint में चार्ट अक्ष शीर्षक घुमाने की गाइड (Aspose.Slides for Java)](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)
- [Aspose.Slides for Java के साथ PowerPoint में चार्ट एनीमेट करें – चरण‑दर‑चरण गाइड](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Aspose.Slides के साथ Java में पाई चार्ट रंग कस्टमाइज़ करने की पूरी गाइड](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}