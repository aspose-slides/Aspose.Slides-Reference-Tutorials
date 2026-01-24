---
date: '2026-01-24'
description: Aspose.Slides का उपयोग करके जावा में स्कैटर चार्ट बनाने के लिए चरण‑दर‑चरण
  मार्गदर्शिका, स्कैटर डेटा पॉइंट्स जोड़ें और कई श्रृंखलाओं वाले स्कैटर चार्ट के साथ
  काम करें।
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Aspose.Slides के साथ जावा में स्कैटर चार्ट बनाएं – अनुकूलित करें और सहेजें
url: /hi/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides के साथ Java में स्कैटर चार्ट बनाएं

इस ट्यूटोरियल में आप **स्कैटर चार्ट जावा** प्रोजेक्ट्स को शून्य से बनाएँगे, डेटा पॉइंट्स स्कैटर जोड़ेंगे, और मल्टीपल सीरीज़ स्कैटर चार्ट के साथ काम करना सीखेंगे—सभी Aspose.Slides for Java का उपयोग करके। हम डायरेक्टरी सेटअप, प्रेजेंटेशन इनिशियलाइज़ेशन, चार्ट निर्माण, डेटा प्रबंधन, मार्कर कस्टमाइज़ेशन, और अंत में प्रेजेंटेशन को सेव करने की प्रक्रिया को चरण-दर-चरण देखेंगे।

**What You'll Learn**
- प्रेजेंटेशन फ़ाइलों को स्टोर करने के लिए डायरेक्टरी सेटअप करना  
- Aspose.Slides का उपयोग करके प्रेजेंटेशन को इनिशियलाइज़ और मैनीपुलेट करना  
- स्लाइड पर स्कैटर चार्ट बनाना  
- प्रत्येक सीरीज़ के लिए डेटा पॉइंट्स जोड़ना और मैनेज करना  
- सीरीज़ टाइप्स, मार्कर्स को कस्टमाइज़ करना, और मल्टीपल सीरीज़ स्कैटर चार्ट को हैंडल करना  
- पूरा हुआ प्रेजेंटेशन सेव करना  

आइए प्रीरेक्विज़िट्स के साथ शुरू करते हैं।

## Quick Answers
- **What is the primary library?** Aspose.Slides for Java  
- **Which Java version is required?** JDK 8 or higher (JDK 16 recommended)  
- **Can I add more than two series?** Yes – you can add any number of series to a scatter chart  
- **How do I change marker colors?** Use `series.getMarker().getFillFormat().setFillColor(Color)`  
- **Is a license needed for production?** Yes, a commercial license removes evaluation limits  

## Prerequisites

- **Aspose.Slides for Java** – संस्करण 25.4 या बाद का।  
- **Java Development Kit (JDK)** – JDK 8 या नया।  
- बेसिक Java ज्ञान और Maven या Gradle की परिचितता।  

## Setting Up Aspose.Slides for Java

अपने प्रोजेक्ट में Aspose.Slides को एक निम्नलिखित विधियों में से किसी एक के साथ इंटीग्रेट करें।

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

या नवीनतम पैकेज को [Aspose Releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

#### License Acquisition
- **Free Trial** – 30‑दिन की इवैल्यूएशन।  
- **Temporary License** – विस्तारित परीक्षण।  
- **Commercial License** – पूर्ण प्रोडक्शन उपयोग।  

अब चलिए कोड में डाइव करते हैं।

## Implementation Guide

### Step 1: Directory Setup
सबसे पहले, सुनिश्चित करें कि आउटपुट फ़ोल्डर मौजूद है ताकि प्रेजेंटेशन बिना त्रुटियों के सेव हो सके।

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Step 2: Presentation Initialization
एक नया प्रेजेंटेशन बनाएं और पहली स्लाइड प्राप्त करें।

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Step 3: Add a Scatter Chart
स्लाइड पर स्मूद लाइन्स के साथ एक स्कैटर चार्ट इन्सर्ट करें।

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Step 4: Manage Chart Data (Clear & Add Series)
डिफ़ॉल्ट सीरीज़ को क्लियर करें और हमारे अपने सीरीज़ को **multiple series scatter chart** के लिए जोड़ें।

```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### Step 5: Add Data Points Scatter
प्रत्येक सीरीज़ को X‑Y वैल्यूज़ से **add data points scatter** का उपयोग करके भरें।

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Step 6: Customize Series Types & Markers
विज़ुअल स्टाइल को एडजस्ट करें—मार्कर्स के साथ स्ट्रेट लाइन्स पर स्विच करें और अलग-अलग मार्कर सिम्बॉल सेट करें।

```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### Step 7: Save the Presentation
फ़ाइल को डिस्क पर सेव करें।

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Practical Applications
- **Financial Analysis** – मल्टीपल सीरीज़ स्कैटर चार्ट के साथ स्टॉक प्राइस मूवमेंट्स को प्लॉट करें।  
- **Scientific Research** – सटीक डेटा प्रतिनिधित्व के लिए add data points scatter का उपयोग करके प्रयोगात्मक माप को विज़ुअलाइज़ करें।  
- **Project Management** – एक ही स्कैटर चार्ट पर कई प्रोजेक्ट्स में रिसोर्स एलोकेशन ट्रेंड्स दिखाएँ।  

## Performance Considerations
- `Presentation` ऑब्जेक्ट को सेव करने के बाद डिस्पोज़ करें ताकि मेमोरी फ्री हो सके।  
- बड़े डेटा सेट्स के लिए, वर्कबुक को एक‑एक करके नहीं बल्कि बैच में पॉप्युलेट करें।  
- टाइट लूप्स के अंदर अत्यधिक स्टाइलिंग से बचें; डेटा इन्सर्शन के बाद स्टाइल्स लागू करें।  

## Common Issues & Solutions

| समस्या | समाधान |
|-------|----------|
| **Chart appears empty** | Verify that data points are added to the correct series and that the workbook indices match. |
| **Markers not visible** | Ensure `series.getMarker().setSize()` is set to a value greater than 0 and that the marker symbol is defined. |
| **OutOfMemoryError on large charts** | Use `pres.dispose()` after saving and consider increasing JVM heap size (`-Xmx`). |

## Frequently Asked Questions

### How do I change the color of the markers?
मार्कर का रंग बदलने के लिए `series.getMarker().getFillFormat().setFillColor(Color)` का उपयोग करें जहाँ `Color` `java.awt.Color` का एक इंस्टेंस है।

### Can I add more than two series to a scatter chart?
बिल्कुल। प्रत्येक अतिरिक्त सीरीज़ के लिए (Step 4) की सीरीज़‑क्रिएशन ब्लॉक को दोहराएँ।

### Is it possible to export the chart as an image?
हाँ। सभी डेटा जोड़ने के बाद `chart.exportChartImage("chart.png", ImageFormat.Png)` कॉल करें।

### Does Aspose.Slides support interactive tooltips on scatter points?
हालाँकि PowerPoint स्वयं रनटाइम टूलटिप्स प्रदान नहीं करता, आप `series.getDataPoints().get_Item(i).getLabel().setText("Your text")` का उपयोग करके डेटा लेबल एम्बेड कर सकते हैं।

### How can I animate the scatter series?
सरल appear एनीमेशन जोड़ने के लिए `chart.getChartData().getSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)` का उपयोग करें।

**Last Updated:** 2026-01-24  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}