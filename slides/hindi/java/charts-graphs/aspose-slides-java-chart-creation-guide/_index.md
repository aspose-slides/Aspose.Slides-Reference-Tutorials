---
date: '2026-06-03'
description: Aspose.Slides का उपयोग करके Java में clustered column chart बनाना सीखें।
  यह गाइड Maven dependency, chart creation steps, और data handling को कवर करता है।
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Java में Aspose.Slides के साथ Clustered Column Chart बनाएं
url: /hi/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java में Aspose.Slides के साथ क्लस्टर्ड कॉलम चार्ट बनाएं

## Java में चार्ट कैसे बनाएं: परिचय
डायनामिक प्रस्तुतियों को बनाते समय अक्सर डेटा को चार्ट के माध्यम से विज़ुअलाइज़ किया जाता है। **Aspose.Slides for Java** के साथ, आप आसानी से **क्लस्टर्ड कॉलम चार्ट** ऑब्जेक्ट बना सकते हैं, स्पष्टता बढ़ा सकते हैं, और अपने दर्शकों पर अधिक प्रभाव डाल सकते हैं। यह ट्यूटोरियल आपको लाइब्रेरी सेटअप करने, क्लस्टर्ड कॉलम चार्ट जोड़ने, सीरीज़ प्रबंधित करने, और नकारात्मक डेटा पॉइंट्स को शर्तीय रूप से उलटने की प्रक्रिया दिखाता है।

**आप क्या सीखेंगे**
- Aspose.Slides for Java को कैसे सेटअप करें।
- अपने प्रेजेंटेशन में **क्लस्टर्ड कॉलम चार्ट** बनाने के चरण।
- चार्ट सीरीज़ और डेटा पॉइंट्स को प्रबंधित करने की तकनीकें।
- बेहतर विज़ुअलाइज़ेशन के लिए नकारात्मक डेटा पॉइंट्स को शर्तीय रूप से उलटने के तरीके।
- प्रेजेंटेशन को सुरक्षित रूप से सहेजने का तरीका।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी उपयोग की गई है?** Aspose.Slides for Java.  
- **कौनसा चार्ट प्रकार प्रदर्शित किया गया है?** Clustered column chart.  
- **क्या मैं नकारात्मक मानों को उलट सकता हूँ?** Yes, using `invertIfNegative`.  
- **कौनसा Java संस्करण आवश्यक है?** JDK 16 or later.  
- **क्या उत्पादन के लिए लाइसेंस आवश्यक है?** Yes, a valid Aspose license.  

## क्लस्टर्ड कॉलम चार्ट क्या है?
क्लस्टर्ड कॉलम चार्ट एक दृश्य प्रतिनिधित्व है जो प्रत्येक श्रेणी के लिए कई डेटा सीरीज़ को एक-दूसरे के बगल में रखता है, जिससे समूहों के बीच तेज़ तुलना संभव होती है। यह वित्तीय रिपोर्ट, बिक्री डैशबोर्ड, और किसी भी स्थिति में जहाँ आपको एक साथ कई मीट्रिक की तुलना करनी हो, के लिए उपयुक्त है।

## चार्ट निर्माण के लिए Aspose.Slides का उपयोग क्यों करें?
Aspose.Slides आपको प्रोग्रामेटिक रूप से चार्ट बनाने और पूरी तरह कस्टमाइज़ करने देता है, जिससे मैन्युअल PowerPoint संपादन की आवश्यकता नहीं रहती। यह **70+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करता है और **10,000 स्लाइड्स तक** के प्रेजेंटेशन को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, जिससे बड़े‑स्तर की रिपोर्टिंग के लिए उच्च प्रदर्शन सुनिश्चित होता है।

## पूर्वापेक्षाएँ
1. **आवश्यक लाइब्रेरीज़**  
   - Aspose.Slides for Java (version 25.4 or later).  

2. **पर्यावरण**  
   - JDK 16 or newer.  
   - Maven or Gradle for dependency management.  

3. **ज्ञान**  
   - Basic Java programming.  
   - Familiarity with build tools (Maven/Gradle).  

## Aspose.Slides for Java की सेटअप
### Maven इंस्टॉलेशन
अपने `pom.xml` फ़ाइल में निम्नलिखित डिपेंडेंसी जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle इंस्टॉलेशन
अपने `build.gradle` फ़ाइल में निम्नलिखित पंक्ति जोड़ें:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### सीधे डाउनलोड
वैकल्पिक रूप से, नवीनतम संस्करण यहाँ से डाउनलोड करें: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### लाइसेंस प्राप्ति
- **Free Trial:** लाइसेंस के बिना फीचर्स का अन्वेषण करें।  
- **Temporary License:** मूल्यांकन के दौरान उपयोग करें।  
- **Full License:** उत्पादन परिनियोजन के लिए खरीदें।  

### बेसिक इनिशियलाइज़ेशन
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## मैं स्लाइड में क्लस्टर्ड कॉलम चार्ट कैसे जोड़ूं?
`Presentation` PowerPoint फ़ाइल का मुख्य क्लास है। नया `Presentation` लोड करें, एक स्लाइड जोड़ें, और `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)` कॉल करें। यह एकल कॉल निर्दिष्ट निर्देशांक पर एक पूर्ण कार्यात्मक क्लस्टर्ड कॉलम चार्ट बनाता है। आप फिर चार्ट ऑब्जेक्ट तक पहुंच कर सीरीज़, डेटा पॉइंट्स, और विज़ुअल स्टाइल्स को संशोधित कर सकते हैं।

## स्टेप‑बाय‑स्टेप गाइड

### स्टेप 1: एक प्रेजेंटेशन बनाएं और क्लस्टर्ड कॉलम चार्ट जोड़ें
`Presentation` क्लास PowerPoint दस्तावेज़ का प्रतिनिधित्व करती है और स्लाइड बनाने की अनुमति देती है।  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### स्टेप 2: चार्ट सीरीज़ प्रबंधित करें
अब हम किसी भी डिफ़ॉल्ट सीरीज़ को साफ़ करेंगे, एक नई जोड़ेंगे, और इसे सकारात्मक और नकारात्मक दोनों मानों से भरेंगे।  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### स्टेप 3: नकारात्मक डेटा पॉइंट्स को शर्तीय रूप से उलटें
`invertIfNegative` मेथड चार्ट सीरीज़ में नकारात्मक मानों को उलटने की सुविधा देता है।  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## सामान्य समस्याएँ और टिप्स
- **क्या आप `Presentation` ऑब्जेक्ट को डिस्पोज करना भूल गए?** हमेशा `finally` ब्लॉक में `dispose()` कॉल करें ताकि नेटिव रिसोर्सेज़ मुक्त हो सकें।  
- **नकारात्मक मान उलटे नहीं दिख रहे हैं?** सुनिश्चित करें कि आप डेटा पॉइंट जोड़ने के **बाद** `invertIfNegative(true)` कॉल करें।  
- **चार्ट आकार समस्याएँ:** कोऑर्डिनेट्स (X, Y) और डाइमेंशन (width, height) पॉइंट्स में होते हैं; इन्हें अपने स्लाइड लेआउट के अनुसार समायोजित करें।  

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न:** क्या मैं उसी दृष्टिकोण से अन्य चार्ट प्रकार बना सकता हूँ?  
**उत्तर:** हाँ, बस `ChartType.ClusteredColumn` को किसी अन्य `ChartType` enum मान (जैसे `Line`, `Pie`) से बदल दें।  

**प्रश्न:** क्या मुझे विकास बिल्ड्स के लिए लाइसेंस चाहिए?  
**उत्तर:** पूर्ण फीचर एक्सेस के लिए एक टेम्पररी या इवैल्यूएशन लाइसेंस आवश्यक है; अन्यथा, लाइब्रेरी ट्रायल मोड में वॉटरमार्क सीमाओं के साथ काम करती है।  

**प्रश्न:** चार्ट जोड़ने के बाद प्रेजेंटेशन को PDF में कैसे एक्सपोर्ट करें?  
**उत्तर:** `SaveFormat.Pdf` प्रेजेंटेशन को सहेजने के लिए PDF को आउटपुट फ़ॉर्मेट के रूप में निर्दिष्ट करता है। चार्ट मैनिपुलेशन समाप्त करने के बाद `pres.save("output.pdf", SaveFormat.Pdf);` का उपयोग करें।  

**प्रश्न:** क्या व्यक्तिगत कॉलम (रंग, बॉर्डर) को स्टाइल करना संभव है?  
**उत्तर:** `IChartDataPoint` चार्ट में एक एकल डेटा पॉइंट का प्रतिनिधित्व करता है और फ़ॉर्मेटिंग की अनुमति देता है। प्रत्येक `IChartDataPoint` विकल्प प्रदान करता है जैसे `getFillFormat().setFillType(FillType.Solid)` और `getLineFormat()`।  

**प्रश्न:** यदि प्रेजेंटेशन सहेजने के बाद मुझे चार्ट डेटा अपडेट करना हो तो क्या करें?  
**उत्तर:** `new Presentation("file.pptx")` के साथ प्रेजेंटेशन को फिर से लोड करें, चार्ट डेटा को संशोधित करें, और पुनः सहेजें।  

---

**अंतिम अपडेट:** 2026-06-03  
**परीक्षण किया गया:** Aspose.Slides for Java 25.4 (JDK 16)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Java में Aspose.Slides के साथ स्टैक्ड कॉलम चार्ट कैसे बनाएं – एक व्यापक गाइड](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Java में Aspose.Slides के साथ चार्ट कैसे बनाएं – चार्ट निर्माण और वैलिडेशन में महारत](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Aspose.Slides का उपयोग करके Java में चार्ट बनाएं और फ़ॉर्मेट करें: एक व्यापक गाइड](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}