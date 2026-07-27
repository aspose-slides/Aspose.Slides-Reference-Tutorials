---
date: '2026-07-27'
description: Aspose.Slides for Java का उपयोग करके चार्ट को कस्टमाइज़ करने का तरीका।
  PowerPoint चार्ट बनाना सीखें, scatter series को स्टाइल करें, और presentations को
  कुशलतापूर्वक सहेजें।
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Aspose.Slides for Java के साथ चार्ट को कस्टमाइज़ करने का तरीका। यह
  गाइड दिखाता है कि PowerPoint चार्ट कैसे बनाएं, scatter points को स्टाइल करें, और
  presentations को export करें।
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'चार्ट को कस्टमाइज़ करने का तरीका: Scatter Chart Aspose in Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'चार्ट को कस्टमाइज़ करने का तरीका: Scatter Chart Aspose in Java'
url: /hi/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java में Aspose के Scatter Chart को अनुकूलित करें

इस ट्यूटोरियल में आप **चार्ट को कैसे अनुकूलित करें** — विशेष रूप से एक scatter chart — को Aspose.Slides for Java लाइब्रेरी की शक्ति का उपयोग करके जानेंगे। हम प्रोजेक्ट सेटअप, scatter chart बनाने, series प्रकार और markers को समायोजित करने, और अंत में प्रस्तुति को सहेजने की प्रक्रिया से गुजरेंगे। अंत तक, आप प्रोग्रामेटिक रूप से पेशेवर‑दिखावट वाले scatter charts जेनरेट कर सकेंगे और हर दृश्य विवरण को अपने ब्रांड या रिपोर्टिंग आवश्यकताओं के अनुसार अनुकूलित कर सकेंगे।

## त्वरित उत्तर
- **मुझे कौन सी लाइब्रेरी चाहिए?** Aspose.Slides for Java (v25.4+).  
- **कौन सा Java संस्करण समर्थित है?** JDK 8 या उससे ऊपर।  
- **क्या मैं marker के आकार बदल सकता हूँ?** हाँ – `MarkerStyleType` का उपयोग करके सितारे, वृत्त आदि चुनें।  
- **फ़ाइल को कैसे सहेजें?** `pres.save("output.pptx", SaveFormat.Pptx)` को कॉल करें।  
- **क्या लाइसेंस आवश्यक है?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।

## Aspose.Slides के साथ Java में चार्ट को कैसे अनुकूलित करें?
`Presentation` Aspose.Slides की वह क्लास है जो मेमोरी में पूरी PowerPoint फ़ाइल का प्रतिनिधित्व करती है। एक नया `Presentation` लोड करें, पहले स्लाइड पर एक scatter chart जोड़ें, series और marker शैलियों को कॉन्फ़िगर करें, फिर `save` को कॉल करें। यह एकल वर्कफ़्लो कुछ ही Java कोड लाइनों में पूरी तरह से स्टाइल किया हुआ चार्ट बनाता है, जिसे किसी भी PowerPoint डेक में शामिल किया जा सकता है।

## “customize scatter chart aspose” क्या है?
Aspose के साथ scatter chart को अनुकूलित करना मतलब है कि चार्ट के डेटा, रूप-रंग और व्यवहार को प्रोग्रामेटिक रूप से परिभाषित करना — बिंदु निर्देशांक से लेकर marker प्रतीकों तक — बिना PowerPoint को मैन्युअल रूप से खोले। यह तरीका स्वचालित रिपोर्टिंग, डेटा‑आधारित प्रस्तुतियों, या किसी भी स्थिति के लिए आदर्श है जहाँ आपको दोहराने योग्य, उच्च‑गुणवत्ता वाले विज़ुअलाइज़ेशन चाहिए।

## Aspose.Slides के साथ scatter charts को क्यों अनुकूलित करें?
Aspose.Slides डेवलपर्स को चार्ट के रूप-रंग पर पूर्ण प्रोग्रामेटिक नियंत्रण देता है, जिससे उच्च‑गुणवत्ता वाले विज़ुअलाइज़ेशन का स्वचालित निर्माण, रिपोर्टिंग पाइपलाइन में सहज एकीकरण, और PowerPoint को मैन्युअल रूप से खोले बिना हर दृश्य तत्व को अनुकूलित करने की क्षमता मिलती है, जो समय बचाता है और प्रस्तुतियों में स्थिरता सुनिश्चित करता है।

- **पूर्ण नियंत्रण** – Java कोड के माध्यम से series प्रकार, marker शैलियाँ, रंग, और अधिक संशोधित करें।  
- **स्वचालन** – डैशबोर्ड या बैच रिपोर्टों के लिए तुरंत दर्जनों चार्ट उत्पन्न करें।  
- **क्रॉस‑प्लेटफ़ॉर्म** – किसी भी OS पर काम करता है जो Java का समर्थन करता है, Office इंस्टॉल करने की आवश्यकता नहीं।  
- **प्रदर्शन** – हल्का API जो **150+ चार्ट प्रकार** को प्रोसेस करता है और पूरी फ़ाइल को मेमोरी में लोड किए बिना सैकड़ों‑पृष्ठ वाली प्रस्तुतियों को संभालता है।

## पूर्वापेक्षाएँ
अनुक्रमणिका के लिए, सुनिश्चित करें कि आपके पास है:

- **Aspose.Slides for Java** (v25.4 या बाद का)।  
- **Java Development Kit (JDK)** 8 + स्थापित हो।  
- निर्भरता प्रबंधन के लिए Maven या Gradle (या आप JAR मैन्युअल रूप से डाउनलोड कर सकते हैं)।  
- बुनियादी Java ज्ञान और आपके चुने हुए बिल्ड टूल की परिचितता।

## Aspose.Slides for Java को सेटअप करना
नीचे दिए गए तरीकों में से एक का उपयोग करके लाइब्रेरी को अपने प्रोजेक्ट में एकीकृत करें।

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

या नवीनतम रिलीज़ [Aspose Releases](https://releases.aspose.com/slides/java/) से प्राप्त करें।

#### लाइसेंस प्राप्ति
- **Free Trial** – 30‑दिन मूल्यांकन।  
- **Temporary License** – विस्तारित परीक्षण अवधि।  
- **Full License** – प्रोडक्शन उपयोग के साथ प्रीमियम समर्थन।

## Scatter Chart Aspose को अनुकूलित करने के चरण‑दर‑चरण गाइड
### 1️⃣ अपनी प्रस्तुति फ़ाइलों के लिए एक फ़ोल्डर तैयार करें
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*क्यों महत्वपूर्ण है:* आउटपुट फ़ोल्डर मौजूद होने से बाद में PPTX सहेजते समय `FileNotFoundException` से बचा जा सकता है।

### 2️⃣ एक नई प्रस्तुति बनाएं और पहला स्लाइड प्राप्त करें
`Presentation` एक PowerPoint दस्तावेज़ का प्रतिनिधित्व करता है और स्लाइड्स व शैप्स तक पहुँच प्रदान करता है। `Presentation` क्लास मेमोरी में पूरी PowerPoint फ़ाइल का प्रतिनिधित्व करती है।  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ स्मूथ लाइनों के साथ एक scatter chart जोड़ें
`ChartType.ScatterWithSmoothLines` एक scatter chart बनाता है जहाँ बिंदु स्मूथ लाइनों से जुड़े होते हैं।  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ किसी भी डिफ़ॉल्ट series को साफ़ करें और अपनी जोड़ें
`IChartSeries` चार्ट के भीतर एक डेटा series का प्रतिनिधित्व करता है।  
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

### 5️⃣ पहली series को डेटा बिंदुओं से भरें
`addDataPointForScatterSeries` एक scatter series में एकल X‑Y बिंदु जोड़ता है।  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ series प्रकार और marker रूप‑रंग को अनुकूलित करें
`Marker` चार्ट series में प्रत्येक डेटा बिंदु के लिए उपयोग किए जाने वाले दृश्य प्रतीक को नियंत्रित करता है।  
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

### 7️⃣ प्रस्तुति सहेजें
`save` प्रस्तुति को निर्दिष्ट फ़ॉर्मेट में फ़ाइल में लिखता है।  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## अनुकूलित Scatter Charts के सामान्य उपयोग केस
- **Financial dashboards** – स्टॉक कीमत बनाम वॉल्यूम को प्लॉट करें।  
- **Scientific research** – त्रुटि markers के साथ प्रयोगात्मक माप दिखाएँ।  
- **Project management** – कार्यों में नियोजित बनाम वास्तविक प्रयास की तुलना करें।  

## प्रदर्शन सुझाव
- सहेजने के बाद `pres.dispose()` को कॉल करके नेटिव मेमोरी रिलीज़ करें।  
- बड़े डेटा सेट के लिए, पहले वर्कबुक को भरें और फिर series को बाइंड करें ताकि बार‑बार UI रिफ्रेश से बचा जा सके।  
- कई series जोड़ते समय मेमोरी उपयोग कम रखने के लिए एक ही `IChartDataWorkbook` इंस्टेंस को पुनः उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न
**प्र: मैं markers का रंग कैसे बदलूँ?**  
उ: `series.getMarker().getFillFormat().setFillColor(Color)` उपयोग करें जहाँ `Color` एक `java.awt.Color` इंस्टेंस है जैसे `Color.RED`।

**प्र: क्या मैं scatter chart में दो से अधिक series जोड़ सकता हूँ?**  
उ: हाँ। प्रत्येक अतिरिक्त series के लिए `chart.getChartData().getSeries().add(...)` कॉल करें और उसके बिंदुओं को उसी अनुसार भरें।

**प्र: क्या प्रत्येक series के लिए कस्टम लेजेंड सेट करना संभव है?**  
उ: बिल्कुल। एक series बनाने के बाद, डिफ़ॉल्ट नाम को ओवरराइड करने के लिए `series.getLegend().setText("Your Legend Text")` को बुलाएँ।

**प्र: मैं chart को PPTX के बजाय इमेज के रूप में कैसे एक्सपोर्ट करूँ?**  
उ: chart को कॉन्फ़िगर करने के बाद `chart.getImage().save("chart.png", ImageFormat.Png)` को कॉल करें। यह एक स्वतंत्र PNG फ़ाइल बनाता है।

**प्र: अगर मुझे scatter points को एनीमेट करना हो तो क्या करें?**  
उ: Aspose.Slides एनीमेशन इफ़ेक्ट्स को सपोर्ट करता है। chart या व्यक्तिगत series में प्रवेश या ज़ोर देने वाले एनीमेशन जोड़ने के लिए `chart.getTimeline().getMainSequence().addEffect(...)` उपयोग करें।

---

**अंतिम अपडेट:** 2026-07-27  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Java में Aspose.Slides का उपयोग करके PowerPoint Charts बनाएं और अनुकूलित करें](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Java के लिए Aspose.Slides का उपयोग करके PowerPoint में बबल चार्ट कैसे बनाएं (ट्यूटोरियल)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Aspose.Slides for Java में ट्रेंड लाइनों के साथ चार्ट बनाएं और अनुकूलित करें](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}