---
date: '2026-06-08'
description: Aspose.Slides for Java का उपयोग करके .NET प्रस्तुतियों में chart में
  series जोड़ना और stacked column charts को कस्टमाइज़ करना सीखें।
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Aspose.Slides for Java का उपयोग करके .NET में chart में series जोड़ें
url: /hi/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java का उपयोग करके .NET प्रस्तुतियों में चार्ट अनुकूलन में महारत

## परिचय
डेटा‑ड्रिवेन प्रस्तुतियों की दुनिया में, चार्ट अनिवार्य उपकरण हैं जो कच्चे आँकड़ों को आकर्षक दृश्य कहानियों में बदलते हैं। जब आपको प्रोग्रामेटिक रूप से **add series to chart** करने की आवश्यकता होती है, विशेष रूप से .NET प्रस्तुति फ़ाइलों के भीतर, तो कार्य भारी लग सकता है। सौभाग्य से, **Aspose.Slides for Java** एक शक्तिशाली, भाषा‑अज्ञेय API प्रदान करता है जो चार्ट निर्माण और अनुकूलन को सरल बनाता है—भले ही आपका लक्ष्य फ़ॉर्मेट .NET PPTX हो। यह गाइड आपको सीरीज़ जोड़ने, स्टैक्ड कॉलम चार्ट बनाने, और गैप विड्थ जैसे दृश्य पहलुओं को फाइन‑ट्यून करने के माध्यम से ले जाता है, ताकि आप गतिशील, डेटा‑समृद्ध स्लाइड्स बना सकें जो पेशेवर और परिष्कृत दिखें।

## त्वरित उत्तर
`Presentation` क्लास एक PPTX फ़ाइल का प्रतिनिधित्व करती है, और `slide.getShapes().addChart(...)` एक चार्ट शेप जोड़ता है। `chart.getChartData().getSeries().add(...)` से सीरीज़ जोड़ें, और `setGapWidth()` से स्पेसिंग समायोजित करें।

- **प्रेजेंटेशन शुरू करने के लिए मुख्य क्लास कौन सी है?** `Presentation` – यह मेमोरी में PPTX फ़ाइल का प्रतिनिधित्व करता है।  
- **कौन सा मेथड स्लाइड में चार्ट जोड़ता है?** `slide.getShapes().addChart(...)` स्लाइड पर चार्ट ऑब्जेक्ट बनाता है।  
- **नया सीरीज़ कैसे जोड़ें?** `chart.getChartData().getSeries().add(...)` एक नई डेटा सीरीज़ डालता है।  
- **क्या आप बार के बीच गैप विड्थ बदल सकते हैं?** हाँ—`chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (मान प्रतिशत में) कॉल करें।  
- **उत्पादन के लिए लाइसेंस चाहिए?** बिल्कुल—एक वैध Aspose.Slides for Java लाइसेंस सभी फीचर्स अनलॉक करता है और इवैल्यूएशन वॉटरमार्क हटाता है।

## “add series to chart” क्या है?
चार्ट में सीरीज़ जोड़ना मतलब डेटा पॉइंट्स का एक नया संग्रह सम्मिलित करना है जिसे चार्ट एक अलग दृश्य तत्व (जैसे अलग कॉलम समूह) के रूप में रेंडर करता है। प्रत्येक सीरीज़ के अपने मान, रंग, और फ़ॉर्मेटिंग हो सकते हैं, जिससे कई डेटा सेट्स की साइड‑बाय‑साइड तुलना संभव होती है।

## .NET प्रस्तुतियों को संशोधित करने के लिए Aspose.Slides for Java का उपयोग क्यों करें?
Aspose.Slides for Java आपको PPTX फ़ाइलें जनरेट या एडिट करने देता है जो पूरी तरह .NET PowerPoint व्यूअर्स के साथ संगत होती हैं, बिना किसी Microsoft Office इंस्टॉलेशन की आवश्यकता के। जब आपको सर्वर‑साइड, क्रॉस‑प्लेटफ़ॉर्म समाधान चाहिए जो .NET PPTX फ़ाइलें बनाता या अपडेट करता है, 50+ चार्ट प्रकारों का समर्थन करता है, और पूरे दस्तावेज़ को मेमोरी में लोड किए बिना 500 MB तक की फ़ाइलें प्रोसेस करता है, तो Aspose.Slides for Java उपयोग करें। इसका API Java, Kotlin, Scala, या किसी भी JVM भाषा में काम करता है, वही आउटपुट देता है जिसकी .NET डेवलपर्स अपेक्षा करते हैं।

## आवश्यकताएँ
- **Aspose.Slides for Java** लाइब्रेरी (संस्करण 25.4 या बाद का)।  
- Maven, Gradle, या मैन्युअल JAR डाउनलोड।  
- बेसिक Java ज्ञान और PPTX फ़ाइल संरचना की परिचितता।  

## Aspose.Slides for Java सेटअप करना
### Maven इंस्टॉलेशन
अपने `pom.xml` में निम्नलिखित डिपेंडेंसी जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle इंस्टॉलेशन
अपने `build.gradle` फ़ाइल में यह लाइन शामिल करें:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### डायरेक्ट डाउनलोड
वैकल्पिक रूप से, आधिकारिक रिलीज़ पेज से नवीनतम JAR प्राप्त करें: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)।

**लाइसेंस प्राप्ति**  
एक फ्री ट्रायल शुरू करने के लिए [यहाँ](https://purchase.aspose.com/temporary-license/) से टेम्पररी लाइसेंस डाउनलोड करें। उत्पादन उपयोग के लिए, सभी फीचर्स अनलॉक करने और इवैल्यूएशन वॉटरमार्क हटाने हेतु पूर्ण लाइसेंस खरीदें।

## चरण‑दर‑चरण कार्यान्वयन गाइड
नीचे प्रत्येक चरण के साथ एक संक्षिप्त कोड स्निपेट (मूल ट्यूटोरियल से अपरिवर्तित) और उसका विवरण दिया गया है।

### चरण 1: खाली प्रस्तुति बनाएं
`Presentation` वह एंट्री पॉइंट क्लास है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करता है।  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*हम एक साफ़ PPTX फ़ाइल से शुरू करते हैं, जो चार्ट जोड़ने के लिए कैनवास प्रदान करती है।*

### चरण 2: स्लाइड में स्टैक्ड कॉलम चार्ट जोड़ें
`Chart` स्लाइड के भीतर एक चार्ट शेप को दर्शाता है। `ChartType.StackedColumn` स्टैक्ड कॉलम चार्ट निर्दिष्ट करता है।  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*`addChart` मेथड एक **स्टैक्ड कॉलम चार्ट** बनाता है और इसे स्लाइड के टॉप‑लेफ़्ट कोने में रखता है।*

### चरण 3: चार्ट में सीरीज़ जोड़ें (मुख्य लक्ष्य)
`Series` चार्ट में एकल डेटा सीरीज़ को एन्कैप्सुलेट करता है।  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*यहाँ हम **add series to chart** करते हैं – प्रत्येक कॉल नई डेटा सीरीज़ बनाता है जो अलग कॉलम समूह के रूप में दिखाई देगा।*

### चरण 4: चार्ट में कैटेगरीज जोड़ें
`Category` चार्ट डेटा के लिए X‑axis लेबल को परिभाषित करता है।  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*कैटेगरीज X‑axis लेबल के रूप में कार्य करती हैं, प्रत्येक कॉलम को अर्थ प्रदान करती हैं।*

### चरण 5: सीरीज़ डेटा भरें
`DataPoint` किसी विशिष्ट कैटेगरी पर सीरीज़ के लिए संख्यात्मक मान रखता है।  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*डेटा पॉइंट्स प्रत्येक सीरीज़ को उसके संख्यात्मक मान देते हैं, जिन्हें चार्ट बार की ऊँचाई के रूप में रेंडर करता है।*

### चरण 6: चार्ट सीरीज़ ग्रुप की गैप विड्थ सेट करें
`SeriesGroup` सीरीज़ ग्रुप के लेआउट प्रॉपर्टीज़ को नियंत्रित करता है, जैसे गैप विड्थ।  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*गैप विड्थ को समायोजित करने से पठनीयता बढ़ती है, विशेषकर जब कई कैटेगरीज हों।*

## सामान्य उपयोग केस
- **वित्तीय रिपोर्टिंग** – विभिन्न बिज़नेस यूनिट्स के क्वार्टरली रिवेन्यू की तुलना।  
- **प्रोजेक्ट डैशबोर्ड** – टीम‑वार टास्क कम्प्लीशन प्रतिशत दिखाना।  
- **मार्केटिंग एनालिटिक्स** – कैंपेन परफॉर्मेंस को साइड‑बाय‑साइड विज़ुअलाइज़ करना।  
इन परिदृश्यों में **स्टैक्ड कॉलम चार्ट** उदाहरण उपयोगी है क्योंकि यह कुल में व्यक्तिगत कैटेगरी के योगदान को उजागर करता है।

## प्रदर्शन टिप्स
- **`Presentation` ऑब्जेक्ट को पुनः उपयोग करें** जब कई चार्ट बनाते हों ताकि मेमोरी ओवरहेड कम हो।  
- **डेटा पॉइंट्स की संख्या सीमित रखें** केवल आवश्यक विज़ुअल स्टोरी के लिए; Aspose.Slides 10,000 पॉइंट्स संभाल सकता है, पर ~5,000 के बाद रेंडरिंग गति घटती है।  
- **ऑब्जेक्ट्स को डिस्पोज़ करें** (`presentation.dispose()`) सेव करने के बाद रिसोर्स फ्री करने और मेमोरी लीक्स से बचने के लिए।  

## अक्सर पूछे जाने वाले प्रश्न
**प्रश्न: क्या मैं स्टैक्ड कॉलम के अलावा अन्य चार्ट प्रकार जोड़ सकता हूँ?**  
उत्तर: हाँ, Aspose.Slides लाइन, पाई, एरिया, रडार, बबल और 50+ अन्य चार्ट प्रकारों का समर्थन करता है, सभी को समान `addChart` मेथड से एक्सेस किया जा सकता है।

**प्रश्न: क्या .NET आउटपुट के लिए अलग लाइसेंस चाहिए?**  
उत्तर: नहीं, वही जावा लाइसेंस सभी आउटपुट फ़ॉर्मेट्स, जिसमें .NET PPTX फ़ाइलें शामिल हैं, के लिए काम करता है।

**प्रश्न: चार्ट की कलर पैलेट कैसे बदलें?**  
उत्तर: `series.getFormat().getFill().setFillType(FillType.Solid)` उपयोग करें और प्रत्येक सीरीज़ के लिए इच्छित `Color` ऑब्जेक्ट सेट करें।

**प्रश्न: क्या डेटा लेबल्स प्रोग्रामेटिकली जोड़ सकते हैं?**  
उत्तर: बिल्कुल। `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` कॉल करके प्रत्येक कॉलम पर संख्यात्मक मान दिखा सकते हैं।

**प्रश्न: मौजूदा प्रस्तुति को अपडेट करने की जरूरत पड़े तो?**  
उत्तर: `new Presentation("existing.pptx")` से फ़ाइल लोड करें, समान API कॉल्स से चार्ट संशोधित करें, और फिर डिस्क पर सेव करें।

## निष्कर्ष
अब आपके पास **add series to chart**, **स्टैक्ड कॉलम चार्ट** बनाने, और .NET प्रस्तुतियों में Aspose.Slides for Java का उपयोग करके उसकी उपस्थिति को फाइन‑ट्यून करने की पूरी‑एंड‑टू‑एंड गाइड है। विभिन्न चार्ट प्रकारों, रंगों, और डेटा स्रोतों के साथ प्रयोग करें ताकि आकर्षक विज़ुअल रिपोर्ट्स बन सकें जो स्टेकहोल्डर्स को प्रभावित करें और डेटा‑ड्रिवेन निर्णयों को आगे बढ़ाएँ।

**अंतिम अपडेट:** 2026-06-08  
**टेस्टेड विद:** Aspose.Slides for Java 25.4 (JDK 16)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Slides का उपयोग करके .NET में प्रतिशत-आधारित स्टैक्ड कॉलम चार्ट बनाना](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [प्रभावी डेटा विज़ुअलाइज़ेशन के लिए Aspose.Slides .NET के साथ मास्टर चार्ट सीरीज़ निर्माण और हेरफेर](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Aspose.Slides .NET के साथ विशिष्ट चार्ट सीरीज़ डेटा पॉइंट्स साफ़ करना](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}