---
date: '2026-01-14'
description: जानिए कैसे .NET प्रेजेंटेशन में Aspose.Slides for Java का उपयोग करके
  क्लस्टर्ड कॉलम चार्ट जोड़ें और स्लाइड में चार्ट सम्मिलित करें। इस चरण‑दर‑चरण गाइड
  को पूर्ण कोड उदाहरणों के साथ अनुसरण करें।
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: .NET स्लाइड्स में क्लस्टर्ड कॉलम चार्ट जोड़ें Aspose.Slides Java
url: /hi/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creating Charts in .NET Presentations Using Aspose.Slides for Java
## Introduction
आकर्षक प्रस्तुतियों को अक्सर चार्ट जैसे दृश्य डेटा प्रतिनिधित्वों को एकीकृत करके दर्शकों की समझ और सहभागिता को बढ़ाया जाता है। यदि आप एक डेवलपर हैं जो Aspose.Slides for Java का उपयोग करके अपने .NET प्रस्तुतियों में गतिशील, अनुकूलन योग्य चार्ट जोड़ना चाहते हैं, तो यह ट्यूटोरियल आपके लिए ही तैयार किया गया है। हम यह देखेंगे कि आप प्रस्तुतियों को कैसे इनिशियलाइज़ कर सकते हैं, विभिन्न प्रकार के चार्ट कैसे जोड़ सकते हैं, चार्ट डेटा को कैसे प्रबंधित कर सकते हैं, और सीरीज़ डेटा को प्रभावी रूप से कैसे फॉर्मेट कर सकते हैं।

**What You'll Learn:**
- अपने .NET वातावरण में Aspose.Slides for Java को सेट अप और उपयोग करने का तरीका।
- Aspose.Slides का उपयोग करके नई प्रस्तुति को इनिशियलाइज़ करना।
- स्लाइड्स में चार्ट जोड़ना और कस्टमाइज़ करना।
- चार्ट डेटा वर्कबुक को प्रबंधित करना।
- विशेष रूप से नकारात्मक मानों को संभालते हुए सीरीज़ डेटा को फॉर्मेट करना।

Prerequisites सेक्शन में जाने से पहले आप सुनिश्चित कर लेंगे कि आप आसानी से आगे बढ़ सकते हैं।

## Quick Answers
- **What is the primary goal?** Add a clustered column chart to a .NET slide.  
- **Which library is required?** Aspose.Slides for Java (v25.4+).  
- **Can I use it in a .NET project?** Yes – the Java library works via the Java‑to‑.NET bridge.  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **How long does the implementation take?** About 10‑15 minutes for a basic chart.

## What is a clustered column chart?
एक क्लस्टर्ड कॉलम चार्ट प्रत्येक श्रेणी के लिए कई डेटा सीरीज़ को साइड‑बाय‑साइड दिखाता है, जिससे समूहों के बीच मानों की तुलना आसान हो जाती है। यह विज़ुअल बिज़नेस डैशबोर्ड, परफ़ॉर्मेंस रिपोर्ट, और किसी भी स्थिति में जहाँ आपको कई मीट्रिक को कंट्रास्ट करना हो, के लिए उपयुक्त है।

## Why add chart to slide with Aspose.Slides for Java?
Aspose.Slides का उपयोग करके आप Microsoft PowerPoint स्थापित किए बिना प्रस्तुतियों को जेनरेट, मॉडिफ़ाई और सेव कर सकते हैं। यह चार्ट प्रकार, डेटा और स्टाइलिंग पर पूर्ण नियंत्रण प्रदान करता है, जिससे आप अपने .NET एप्लिकेशन से सीधे रिपोर्ट जेनरेशन को ऑटोमेट कर सकते हैं।

## Prerequisites
Aspose.Slides for Java के साथ चार्ट बनाने से पहले, आइए देखें कि आपको क्या चाहिए:

### Required Libraries and Versions
- **Aspose.Slides for Java**: संस्करण 25.4 या बाद का।

### Environment Setup Requirements
- .NET एप्लिकेशन को सपोर्ट करने वाला विकास वातावरण।
- Java प्रोग्रामिंग कॉन्सेप्ट्स की बुनियादी समझ।

### Knowledge Prerequisites
- .NET एप्लिकेशन कॉन्टेक्स्ट में प्रस्तुतियों को बनाने की परिचितता।
- Java डिपेंडेंसीज़ और उनके मैनेजमेंट (Maven/Gradle) की समझ।

## Setting Up Aspose.Slides for Java
Aspose.Slides का उपयोग शुरू करने के लिए आपको इसे अपने प्रोजेक्ट में डिपेंडेंसी के रूप में शामिल करना होगा। इसे करने का तरीका नीचे दिया गया है:

### Maven
अपने `pom.xml` फ़ाइल में निम्नलिखित डिपेंडेंसी जोड़ें:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
अपने `build.gradle` फ़ाइल में यह शामिल करें:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
वैकल्पिक रूप से, आप नवीनतम संस्करण [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड कर सकते हैं।

#### License Acquisition Steps
- **Free Trial**: फीचर एक्सप्लोर करने के लिए एक टेम्पररी लाइसेंस से शुरू करें।  
- **Purchase**: व्यापक उपयोग के लिए लाइसेंस खरीदने पर विचार करें।

#### Basic Initialization and Setup
कोड में Aspose.Slides को इनिशियलाइज़ करने का तरीका नीचे दिया गया है:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
यह सेटअप सुनिश्चित करता है कि रिसोर्स मैनेजमेंट प्रभावी रूप से संभाला जाए।

## Implementation Guide
हम आपको फीचर‑बाय‑फ़ीचर इम्प्लीमेंटेशन के माध्यम से ले चलेंगे।

### Initializing Presentation
**Overview:**  
एक प्रस्तुति इंस्टेंस बनाना सभी बाद के ऑपरेशन्स के लिए मंच तैयार करता है। यह फीचर दिखाता है कि आप Aspose.Slides का उपयोग करके शून्य से कैसे शुरू कर सकते हैं।

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
```

#### Step 2: Create a New Presentation Object
इसे इस प्रकार करें:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*यह सुनिश्चित करता है कि उपयोग के बाद प्रस्तुति ऑब्जेक्ट सही तरीके से डिस्पोज़ हो, जिससे मेमोरी लीक नहीं होगी।*

### Adding Chart to Slide
**Overview:**  
स्लाइड में चार्ट जोड़ने से डेटा विज़ुअलाइज़ेशन अधिक प्रभावी और आकर्षक बन जाता है।

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Step 2: Initialize Presentation and Add Chart
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*यहाँ, हम पहले स्लाइड में निर्दिष्ट कोऑर्डिनेट्स और डाइमेंशन्स के साथ एक क्लस्टर्ड कॉलम चार्ट जोड़ते हैं।*

### Managing Chart Data Workbook
**Overview:**  
अपने चार्ट के डेटा वर्कबुक को कुशलतापूर्वक मैनेज करने से आप सीरीज़ और कैटेगरीज को सहजता से हेरफेर कर सकते हैं।

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Step 2: Access and Clear Data Workbook
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*वर्कबुक को क्लियर करना नई सीरीज़ और कैटेगरीज जोड़ते समय एक साफ़ शुरुआत के लिए आवश्यक है।*

### Adding Series and Categories to Chart
**Overview:**  
यह फीचर दिखाता है कि आप सीरीज़ और कैटेगरीज को कैसे जोड़कर अर्थपूर्ण डेटा पॉइंट्स बना सकते हैं।

#### Step 1: Add Series and Categories
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*सीरीज़ और कैटेगरीज जोड़ने से डेटा प्रस्तुति अधिक व्यवस्थित हो जाती है।*

### Populating Series Data and Formatting
**Overview:**  
अपने चार्ट को डेटा पॉइंट्स से भरें और नकारात्मक मानों को विशेष रूप से हाइलाइट करने के लिए फॉर्मेटिंग लागू करें।

#### Step 1: Populate Series Data
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*यह सेक्शन डेटा को पॉपुलेट करने और बेहतर विज़ुअलाइज़ेशन के लिए कलर फॉर्मेटिंग लागू करने का प्रदर्शन करता है।*

## Common Issues and Solutions
- **Memory leaks:** हमेशा `Presentation` ऑब्जेक्ट पर `finally` ब्लॉक में `dispose()` कॉल करें।  
- **Incorrect chart type:** जब आप क्लस्टर्ड कॉलम चार्ट चाहते हैं तो `ChartType.ClusteredColumn` का उपयोग सुनिश्चित करें; अन्य प्रकार अलग विज़ुअल परिणाम देंगे।  
- **Negative value colors not applied:** `IDataPoint` वैल्यू को `Number` में सही तरीके से कास्ट किया गया है या नहीं, यह जांचें।

## Frequently Asked Questions

**Q: Can I use Aspose.Slides for Java in a pure .NET project without Java?**  
A: Yes. The library works via the Java‑to‑.NET bridge, allowing you to call Java APIs from .NET languages.

**Q: Does the free trial support chart creation?**  
A: The trial version includes full chart functionality, but generated files contain a small evaluation watermark.

**Q: Which .NET versions are compatible?**  
A: Any .NET version that can interoperate with Java 16+, including .NET Framework 4.6+, .NET Core 3.1+, and .NET 5/6/7.

**Q: How do I handle large presentations with many charts?**  
A: Reuse the same `IChartDataWorkbook` instance where possible and dispose of each `Presentation` promptly to free memory.

**Q: Is it possible to export the chart as an image?**  
A: Yes. Use `chart.getImage()` or `chart.exportChartImage()` methods to obtain PNG/JPEG representations.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

---