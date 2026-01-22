---
date: '2026-01-22'
description: Aspose.Slides for Java का उपयोग करके पाई चार्ट के रंगों को कस्टमाइज़
  करना और चार्ट शीर्षक जोड़ना सीखें। इसमें Maven Aspose Slides सेटअप और प्रस्तुति pptx
  को कैसे सहेजें, शामिल है।
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 'जावा में Aspose.Slides के साथ पाई चार्ट के रंग कैसे कस्टमाइज़ करें: एक पूर्ण
  मार्गदर्शिका'
url: /hi/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java के साथ पाई चार्ट बनाना: **पाई चार्ट रंगों को कस्टमाइज़** कैसे करें – एक पूर्ण ट्यूटोरियल

## परिचय
प्रेजेंटेशन में डेटा‑ड्रिवेन कहानियों को प्रस्तुत करना आसान हो जाता है जब आप **पाई चार्ट रंगों को कस्टमाइज़** करके अपने ब्रांड से मेल खा सकते हैं या प्रमुख मानों को उजागर कर सकते हैं। इस ट्यूटोरियल में आप देखेंगे कि पाई चार्ट कैसे बनाते हैं, चार्ट टाइटल कैसे जोड़ते हैं, पाई चार्ट डेटा पॉइंट्स के साथ कैसे काम करते हैं, और Aspose.Slides for Java का उपयोग करके प्रत्येक स्लाइस के रंगों को कैसे फाइन‑ट्यून करते हैं। अंत तक, आप यह भी जानेंगे कि **प्रेजेंटेशन pptx को कैसे सेव करें** और लाइब्रेरी को Maven Aspose Slides के साथ कैसे इंटीग्रेट करें।

**आप क्या सीखेंगे**
- पाई चार्ट कैसे बनाते हैं (how to create pie) और एक Java प्रोजेक्ट सेट अप करना।
- चार्ट टाइटल जोड़ने और पाई चार्ट डेटा पॉइंट्स को मैनेज करने के चरण।
- अधिकतम विज़ुअल इम्पैक्ट के लिए **पाई चार्ट रंगों को कस्टमाइज़** करने की तकनीकें।
- Maven Aspose Slides डिपेंडेंसी कॉन्फ़िगरेशन।
- अंतिम फ़ाइल को PPTXकौन सा बिल्ड टूल सबसे अच्छा है?** Mavenाइस के रंग बदल सकता हूँ?** हाँ—`setColorVaried(true)` सेट करें और प्रत्येक `DataPoint` फ़िल को समायोजित करें।
ॉर्मेट में सेव होती है?** `presentation.save("MyChart.pptx", SaveFormat.Pptx)` का उपयोग करें।
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए स्थायी लाइसेंस आवश्यक है।

## पूर्वापेक्षाएँ
- **Aspose.Slides for Java** ≥ 25.4 (नवीनतम संस्करण की सलाह दी जाती है)।
- **JDK 16+** स्थापित और कॉन्फ़िगर किया हुआ।
- IntelliJ IDEA, Eclipse, या NetBeans जैसे IDE।
- बेसिक Java ज्ञान और Maven या Gradle की परिचितता।

## Aspose.Slides for Java सेटअप करना
Aspose.Slides का उपयोग शुरू करने के लिए लाइब्रेरी को अपने प्रोजेक्ट में जोड़ें।

**Maven** (maven aspose slides)  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
यदि आप बिल्ड टूल का उपयोग नहीं करना चाहते, तो नवीनतम रिलीज़ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंस प्राप्ति चरण
- **फ्री ट्रायल** – लाइसेंस के बिना प्रयोग शुरू करें।
- **टेम्पररी लाइसेंस** – ट्रायल उपयोग को विस्तारित करें।
- **पर्चेज** – प्रोडक्शन डिप्लॉयमेंट के लिए पूर्ण लाइसेंस प्राप्त करें।

### बेसिक इनिशियलाइज़ेशन
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## इम्प्लीमेंटेशन गाइड
नीचे एक चरण‑दर‑चरण walkthrough दिया गया है जो कोड को मूल लाइब्रेरी की अपेक्षा के अनुसार रखता है।

### चरण 1: प्रेजेंटेशन और स्लाइड को इनिशियलाइज़ करें
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
islide slides = presentation.getSlides().get_Item(0);
```

### चरण 2: स्लाइड में पाई चार्ट जोड़ें
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### चरण 3: चार्ट टाइटल जोड़ें
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### चरण 4: पहले सीरीज़ के लिए डेटा लेबल दिखाएँ
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### चरण 5: चार्ट डेटा वर्कशीट तैयार करें
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### चरण 6: कैटेगरीज (पाई चार्ट डेटा पॉइंट्स) जोड़ें
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### चरण 7: सीरीज़ जोड़ें और डेटा पॉइंट्स भरें
```java
import com.aspose.slides.*;

// Add a new series and set its name.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### चरण 8: **पाई चार्ट रंगों को कस्टमाइज़** – इस ट्यूटोरियल का मुख्य भाग
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### चरण 9: कस्टम डेटा लेबल कॉन्फ़िगर करें
```java
import com.aspose.slides.*;

// Configure custom labels.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### चरण 10: रोटेशन एंगल सेट करें और **प्रेजेंटेशन PPTX सेव करें**
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **एक्सपोर्ट के बाद रंग नहीं दिख रहे** – व्यक्तिगत डेटा पॉइंट्स को बदलने से पहले `setColorVaried(true)` कॉल करना सुनिश्चित करें।
- **डेटा पॉइंट्स नहीं दिख रहे** – नई एंट्रीज़ जोड़ने से पहले कैटेगरीज और सीरीज़ को क्लियर करना याद रखें (चरण 5 देखें)।
- **लाइसेंस लागू नहीं हुआ** – `Presentation` ऑब्जेक्ट बनाने से पहले अपना लाइसेंस फ़ाइल लोड करें ताकि ट्रायल वॉटरमार्क न आए।

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं इस कोड को पुराने JDK संस्करणों के साथ उपयोग कर सकता हूँ?**  
उ: लाइब्रेरी को JDK 16 या उससे ऊपर के बाद कैसे बदलूँ?**  
उ: `chartFrameForOverriding("New Title")` कॉल करें और आवश्यकतानुसार टेक्स्ट फ़ॉर्मेट समायोजित करें।

**प्र: क्या PPTX के अलावा अन्य फ़ॉर्मेट में एक्सपोर्ट कर सकता हूँ?**  
उ: हाँ—Aspose.Slides `SaveFormat` एन्नुम के माध्यम से PDF, ODP और कई इमेज फ़ॉर्मेट को सपोर्ट करतााई` API का उपयोग करके नहीं।

## निष्कर्ष
अब आपके पास एक पूर्ण, प्रोडक्शन‑रेडी उदाहरण है जो **पाई चार्ट रंगों को कस्टमाइज़** करने, चार्ट टाइटल जोड़ने, पाई चार्ट डेटा पॉइंट.Slides for Java का उपयोग करके **प्रेज के साथ प्रयोग करके अपने ब्रांड स्टाइल के अनुसार कस्टमाइज़ करें।

---

**Last Updated:** 2026-01-22  
**Tested With:** Aspose.Slides 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}