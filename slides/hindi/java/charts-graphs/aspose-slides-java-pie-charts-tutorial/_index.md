---
date: '2026-07-17'
description: Aspose.Slides for Java का उपयोग करके Pie Chart को घुमाना, Pie Chart Colors
  को कस्टमाइज़ करना, और Slide को PDF में एक्सपोर्ट करना सीखें – एक पूर्ण डेटा विज़ुअलाइज़ेशन
  गाइड।
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Aspose.Slides for Java का उपयोग करके Pie Chart को घुमाएँ और Pie Chart
  Colors को कस्टमाइज़ करें। Slide को PDF में एक्सपोर्ट करना और Chart Data Worksheet
  के साथ काम करना सीखें।
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Java में Pie Chart को घुमाएँ और Colors को कस्टमाइज़ करें – Aspose.Slides
  गाइड
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Java में Aspose.Slides के साथ Pie Chart को घुमाने और Colors को कस्टमाइज़ करने
  का तरीका
url: /hi/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java के साथ पाई चार्ट बनाना: एक पूर्ण ट्यूटोरियल

## परिचय
इस गाइड में आप सीखेंगे कि **पाई चार्ट** तत्वों को कैसे घुमाएँ, प्रत्येक स्लाइस का रंग कैसे अनुकूलित करें, और अंतिम स्लाइड को PDF में निर्यात करें—सभी Aspose.Slides for Java के साथ। चाहे आप एक बिक्री डैशबोर्ड, एक वित्तीय रिपोर्ट, या कोई भी डेटा‑आधारित प्रस्तुति बना रहे हों, इन तकनीकों में निपुणता आपको स्पष्ट, आकर्षक विज़ुअल प्रदान करने में मदद करेगी बिना Microsoft Office पर निर्भर हुए। चलिए उपकरण तैयार करते हैं और शुरू करते हैं।

## त्वरित उत्तर
- **नया प्रेजेंटेशन शुरू करने वाला क्लास कौन सा है?** `Presentation` from `com.aspose.slides`.
- **कौन सा API कॉल पाई चार्ट जोड़ता है?** `slide.addChart(ChartType.Pie, …)`.
- **आप प्रत्येक स्लाइस को अद्वितीय रंग कैसे दे सकते हैं?** `series.setColorVaried(true)` को कॉल करें और प्रत्येक डेटा पॉइंट के लिए सॉलिड फ़िल सेट करें।
- **चार्ट को घुमाने की विधि कौन सी है?** `chart.setRotationAngle(double)` – 0 से 360 डिग्री तक उपयोग करें।
- **क्या स्लाइड को PDF में निर्यात किया जा सकता है?** हाँ, `presentation.save("output.pdf", SaveFormat.Pdf)` को कॉल करें।

## “पाई चार्ट रंगों को अनुकूलित करना” क्या है?
पाई चार्ट के रंगों को अनुकूलित करने का अर्थ है पाई के प्रत्येक स्लाइस को अलग‑अलग फ़िल रंग देना, जिससे पठनीयता और दृश्य प्रभाव बेहतर होता है। Aspose.Slides में आप यह विविध रंगों को सक्षम करके और फिर प्रत्येक डेटा पॉइंट के लिए सॉलिड फ़िल रंग सेट करके प्राप्त करते हैं। यह तरीका सुनिश्चित करता है कि प्रस्तुति में प्रत्येक डेटा खंड स्पष्ट रूप से अलग दिखे।

## पाई चार्ट बनाने के लिए Aspose.Slides for Java का उपयोग क्यों करें?
Aspose.Slides **150+ चार्ट प्रकार** का समर्थन करता है और एक सामान्य सर्वर पर **5 सेकंड** से कम समय में 300‑पृष्ठ की प्रस्तुति रेंडर कर सकता है, वह भी Microsoft Office स्थापित किए बिना। यह लाइब्रेरी Windows, Linux, और macOS पर चलती है, जिससे आपको किसी भी Java‑आधारित डेटा‑विज़ुअलाइज़ेशन प्रोजेक्ट के लिए क्रॉस‑प्लेटफ़ॉर्म लचीलापन मिलता है।

## आवश्यकताएँ
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 या नया
- IntelliJ IDEA, Eclipse, या NetBeans जैसे IDE
- बुनियादी Java ज्ञान और Maven या Gradle की परिचितता

## Aspose.Slides for Java सेटअप करना
अपने बिल्ड कॉन्फ़िगरेशन में लाइब्रेरी जोड़ें।

**Maven**  
अपने `pom.xml` फ़ाइल में यह स्निपेट जोड़ें:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
अपने `build.gradle` फ़ाइल में निम्नलिखित शामिल करें:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
यदि आप मैन्युअल तरीका पसंद करते हैं, तो नवीनतम JAR को [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंस प्राप्ति चरण
- **Free Trial** – बिना लागत के सभी फीचर देखें।
- **Temporary License** – सीमित समय के लिए ट्रायल सीमा बढ़ाएँ।
- **Purchase** – प्रोडक्शन उपयोग के लिए स्थायी लाइसेंस प्राप्त करें।

**बेसिक इनिशियलाइज़ेशन और सेटअप**  
`Presentation` क्लास मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करती है और स्लाइड्स को बदलने के लिए मेथड्स प्रदान करती है।  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## कार्यान्वयन गाइड
नीचे एक चरण‑दर‑चरण walkthrough दिया गया है जो स्लाइड बनाने से लेकर अंतिम पाई चार्ट को घुमाने तक सब कुछ कवर करता है।

### प्रेजेंटेशन और स्लाइड इनिशियलाइज़ करें
`Presentation` का नया instance बनाएं और पहले स्लाइड को प्राप्त करें जो चार्ट कैनवास के रूप में काम करेगा।  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### स्लाइड में पाई चार्ट जोड़ें
`addChart` निर्दिष्ट प्रकार का चार्ट शेप स्लाइड पर दिए गए निर्देशांक पर जोड़ता है।  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### चार्ट शीर्षक सेट करें
`setTitle` चार्ट को एक टेक्स्ट शीर्षक देता है और उसे केंद्र में स्थित करता है।  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### सीरीज़ के लिए डेटा लेबल कॉन्फ़िगर करें
`setShowValue(true)` सीरीज़ के प्रत्येक डेटा पॉइंट पर संख्यात्मक मान लेबल सक्षम करता है।  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### चार्ट डेटा वर्कशीट तैयार करें
`ChartDataWorkbook` वह अंतर्निहित डेटा टेबल संग्रहीत करता है जो चार्ट सीरीज़ और कैटेगरीज को डेटा प्रदान करता है।  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### चार्ट में कैटेगरीज जोड़ें
`addCategory` चार्ट की डेटा सीरीज़ के लिए नया कैटेगरी लेबल बनाता है।  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### सीरीज़ जोड़ें और डेटा पॉइंट्स भरें
`addSeries` एक डेटा सीरीज़ बनाता है, और `addDataPointForBarSeries` प्रत्येक कैटेगरी के लिए संख्यात्मक मान डालता है।  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### सीरीज़ रंग और बॉर्डर कस्टमाइज़ करें
`setColorVaried(true)` प्रति‑स्लाइस रंग सक्षम करता है, और `setFillFormat` प्रत्येक डेटा पॉइंट को सॉलिड फ़िल असाइन करता है।  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### कस्टम डेटा लेबल कॉन्फ़िगर करें
`setDataLabelFormat` लेबल की उपस्थिति, स्थिति, और फ़ॉन्ट को कस्टमाइज़ करता है ताकि चार्ट एनोटेशन स्पष्ट हों।  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### रोटेशन एंगल सेट करें और प्रेजेंटेशन सेव करें
`setRotationAngle` पूरे पाई चार्ट को घुमाता है, और `save` प्रेजेंटेशन को फ़ाइल में लिखता है।  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## पाई चार्ट को कैसे घुमाएँ?
चार्ट ऑब्जेक्ट लोड करें, `chart.setRotationAngle(45.0)` (या कोई भी डिग्री मान) को कॉल करें, और फिर प्रेजेंटेशन सेव करें। पाई चार्ट को घुमाने से स्टार्ट एंगल बदलता है, जिससे आप डेटा को बदले बिना किसी विशेष सेगमेंट पर ज़ोर दे सकते हैं। यह एकल मेथड कॉल Aspose.Slides में किसी भी `Chart` इंस्टेंस के लिए काम करता है। आप घुमाव को विविध स्लाइस रंगों के साथ भी जोड़ सकते हैं ताकि सबसे महत्वपूर्ण डेटा पॉइंट पर ध्यान आकर्षित हो।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| **सभी स्लाइस एक ही रंग में दिख रहे हैं** | `setColorVaried(true)` नहीं कॉल किया गया | सुनिश्चित करें कि आप सीरीज़ ग्रुप पर विविध रंग सक्षम करें। |
| **डेटा लेबल नहीं दिख रहे हैं** | `showValue` फ़्लैग डिसेबल है | लेबल फ़ॉर्मेट पर `setShowValue(true)` कॉल करें। |
| **घुमाव का कोई प्रभाव नहीं है** | पुराना Aspose.Slides संस्करण उपयोग कर रहे हैं | संस्करण 25.4 या बाद के में अपग्रेड करें। |
| **रनटाइम पर लाइसेंस एक्सेप्शन** | लाइसेंस फ़ाइल गायब या अमान्य है | `Presentation` बनाने से पहले `License license = new License(); license.setLicense("Aspose.Slides.lic");` के साथ अपना लाइसेंस लोड करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: मैं Java के लिए Aspose.Slides लाइसेंस कैसे प्राप्त करूँ?**  
A: Aspose वेबसाइट से एक फ्री ट्रायल अनुरोध करें, फिर स्थायी लाइसेंस खरीदें। इसे रनटाइम पर Common Issues तालिका में दिखाए अनुसार लोड करें।

**Q: क्या मैं इस कोड को पुराने JDK संस्करणों के साथ उपयोग कर सकता हूँ?**  
A: API को JDK 16 या उससे ऊपर की आवश्यकता है; पुराने संस्करण समर्थित नहीं हैं।

**Q: क्या चार्ट को PPTX के बजाय इमेज के रूप में निर्यात करना संभव है?**  
A: हाँ—रेंडरिंग के बाद, `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` को कॉल करें।

**Q: यदि मुझे पाई चार्ट में एक से अधिक सीरीज़ चाहिए तो?**  
A: पाई चार्ट एकल डेटा सीरीज़ के लिए डिज़ाइन किया गया है; कई सीरीज़ के लिए डोनट चार्ट उपयोग करने पर विचार करें।

**Q: क्या Aspose.Slides Linux सर्वरों पर चलता है?**  
A: बिल्कुल—Aspose.Slides for Java प्लेटफ़ॉर्म‑स्वतंत्र है और किसी भी OS पर काम करता है जहाँ संगत JDK उपलब्ध हो।

---

**अंतिम अपडेट:** 2026-07-17  
**परीक्षण किया गया:** Aspose.Slides for Java 25.4 (JDK 16)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Java प्रस्तुतियों में Aspose.Slides का उपयोग करके पाई चार्ट कैसे बनाएं: एक व्यापक गाइड](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Aspose.Slides का उपयोग करके Java में पाई चार्ट में महारत: एक व्यापक गाइड](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Aspose.Slides के साथ Java में चार्ट टेक्स्ट को घुमाएँ: एक व्यापक गाइड](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}