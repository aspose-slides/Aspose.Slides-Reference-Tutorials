---
date: '2026-02-19'
description: Aspose.Slides के साथ जावा में पाई चार्ट बनाना सीखें, पाई चार्ट के रंगों
  को अनुकूलित करें, चार्ट सीरीज़ जोड़ें, चार्ट डेटा वर्कशीट के साथ काम करें, और रोटेशन
  एंगल सेट करें।
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Java में Aspose.Slides के साथ पाई चार्ट के रंगों को कस्टमाइज़ करने का तरीका
  – एक पूर्ण गाइड
url: /hi/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java के साथ पाई चार्ट बनाना: एक पूर्ण ट्यूटोरियल

## परिचय
डायनामिक और दृश्यात्मक रूप से आकर्षक प्रस्तुतियों का निर्माण प्रभावशाली जानकारी प्रदान करने के लिए अत्यंत महत्वपूर्ण है। Aspose.Slides for Java के साथ आप अपने स्लाइड्स में पाई चार्ट जैसे जटिल चार्ट को सहजता से एकीकृत कर सकते हैं, **पाई चार्ट के रंगों को कस्टमाइज़** कर सकते हैं, और डेटा विज़ुअलाइज़ेशन को आसानी से बेहतर बना सकते हैं। यह व्यापक गाइड आपको Aspose.Slides Java का उपयोग करके पाई चार्ट बनाने और कस्टमाइज़ करने की पूरी प्रक्रिया से परिचित कराएगा, जिससे सामान्य प्रस्तुति चुनौतियों का समाधान सरल हो जाएगा।

**आप क्या सीखेंगे:**
- एक प्रेजेंटेशन को इनिशियलाइज़ करना और स्लाइड्स जोड़ना।
- अपनी स्लाइड पर पाई चार्ट बनाना और कॉन्फ़िगर करना।
- चार्ट टाइटल, डेटा लेबल सेट करना, और **पाई चार्ट के रंगों को कस्टमाइज़** करना।
- प्रदर्शन को ऑप्टिमाइज़ करना और संसाधनों का प्रभावी प्रबंधन करना।
- Maven या Gradle का उपयोग करके Java प्रोजेक्ट्स में Aspose.Slides को इंटीग्रेट करना।

आइए शुरू करते हैं, यह सुनिश्चित करते हुए कि आपके पास सभी आवश्यक टूल्स और ज्ञान है जिससे आप इस ट्यूटोरियल को फॉलो कर सकें!

## त्वरित उत्तर
- **प्रेजेंटेशन शुरू करने के लिए मुख्य क्लास कौन सी है?** `Presentation` from `com.aspose.slides`।
- **कौन सा मेथड स्लाइड में पाई चार्ट जोड़ता है?** `addChart(ChartType.Pie, …)`।
- **प्रत्येक स्लाइस के लिए विभिन्न रंग कैसे सक्षम करें?** सीरीज़ ग्रुप पर `setColorVaried(true)` सेट करें।
- **क्या आप पाई चार्ट को घुमा सकते हैं?** हाँ, चार्ट ऑब्जेक्ट पर `setRotationAngle(double)` का उपयोग करें।
- **प्रोडक्शन उपयोग के लिए लाइसेंस चाहिए?** व्यावसायिक डिप्लॉयमेंट के लिए Aspose.Slides लाइसेंस आवश्यक है।

## “पाई चार्ट के रंगों को कस्टमाइज़” क्या है?
पाई चार्ट के रंगों को कस्टमाइज़ करने का अर्थ है प्रत्येक स्लाइस को अलग-अलग फ़िल रंग असाइन करना, जिससे पठनीयता और दृश्य प्रभाव बढ़ता है। Aspose.Slides में आप यह वैरिएड कलर्स को सक्षम करके और फिर व्यक्तिगत डेटा पॉइंट्स के लिए सॉलिड फ़िल कलर्स सेट करके प्राप्त करते हैं।

## Java के लिए Aspose.Slides का उपयोग करके पाई चार्ट क्यों बनाएं?
- **पूर्ण नियंत्रण** चार्ट की उपस्थिति पर, बिना Microsoft Office की आवश्यकता के।
- **क्रॉस‑प्लेटफ़ॉर्म** संगतता – Windows, Linux, और macOS पर काम करता है।
- **समृद्ध API** डेटा बाइंडिंग, स्टाइलिंग, और PPTX, PDF, या इमेज में एक्सपोर्ट करने के लिए।
- **लाइसेंस लचीलापन** – फ्री ट्रायल से शुरू करें और जब पूरी फीचर सेट की जरूरत हो तो अपग्रेड करें।

## पूर्वापेक्षाएँ
इस ट्यूटोरियल को शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित सेटअप तैयार है:

### आवश्यक लाइब्रेरी, संस्करण, और डिपेंडेंसियाँ
- **Aspose.Slides for Java**: संस्करण 25.4 या बाद का।
- **Java Development Kit (JDK)**: संस्करण 16 या उससे ऊपर।

### पर्यावरण सेटअप आवश्यकताएँ
- Java स्थापित और कॉन्फ़िगर किया हुआ विकास पर्यावरण।
- IntelliJ IDEA, Eclipse, या NetBeans जैसे एकीकृत विकास पर्यावरण (IDE)।

### ज्ञान पूर्वापेक्षाएँ
- Java प्रोग्रामिंग की बुनियादी समझ।
- डिपेंडेंसी मैनेजमेंट के लिए Maven या Gradle की परिचितता।

## Aspose.Slides for Java सेटअप करना
अपने Java प्रोजेक्ट्स में Aspose.Slides का उपयोग शुरू करने के लिए, लाइब्रेरी को डिपेंडेंसी के रूप में जोड़ें। विभिन्न बिल्ड टूल्स का उपयोग करके इसे कैसे करें, नीचे दिया गया है:

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

**डायरेक्ट डाउनलोड**  
यदि आप बिल्ड टूल का उपयोग नहीं करना चाहते, तो नवीनतम रिलीज़ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंस प्राप्त करने के चरण
- **फ्री ट्रायल**: Aspose.Slides की सुविधाओं को एक्सप्लोर करने के लिए फ्री ट्रायल से शुरू करें।  
- **टेम्पररी लाइसेंस**: बिना सीमाओं के विस्तारित उपयोग के लिए टेम्पररी लाइसेंस प्राप्त करें।  
- **खरीदें**: यदि आपको दीर्घकालिक एक्सेस चाहिए तो खरीदने पर विचार करें।

**बेसिक इनिशियलाइज़ेशन और सेटअप**  
Aspose.Slides का उपयोग शुरू करने के लिए, एक नया प्रेजेंटेशन ऑब्जेक्ट बनाकर अपने प्रोजेक्ट को इनिशियलाइज़ करें:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## इम्प्लीमेंटेशन गाइड
अब हम पाई चार्ट जोड़ने और कस्टमाइज़ करने की प्रक्रिया को प्रबंधनीय चरणों में विभाजित करेंगे।

### प्रेजेंटेशन और स्लाइड इनिशियलाइज़ करें
एक नया प्रेजेंटेशन सेट अप करें और पहली स्लाइड तक पहुँचें। यह आपके चार्ट बनाने के लिए कैनवास है:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### स्लाइड में पाई चार्ट जोड़ें
डिफ़ॉल्ट डेटा सेट के साथ निर्दिष्ट पोजीशन पर पाई चार्ट इन्सर्ट करें:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### चार्ट टाइटल सेट करें
टाइटल सेट करके और सेंटर करके अपने चार्ट को कस्टमाइज़ करें:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### सीरीज़ के लिए डेटा लेबल कॉन्फ़िगर करें
स्पष्टता के लिए डेटा लेबल्स को वैल्यू दिखाने के लिए सुनिश्चित करें:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### चार्ट डेटा वर्कशीट तैयार करें
मौजूदा सीरीज़ और कैटेगरीज को क्लियर करके अपने चार्ट की डेटा वर्कशीट सेट अप करें:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### चार्ट में कैटेगरीज जोड़ें
अपने पाई चार्ट के लिए कैटेगरीज परिभाषित करें:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### सीरीज़ जोड़ें और डेटा पॉइंट्स भरें
एक सीरीज़ बनाएं और डेटा पॉइंट्स से भरें – यही वह जगह है जहाँ हम **चार्ट सीरीज़ जोड़ते** हैं:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### सीरीज़ के रंग और बॉर्डर कस्टमाइज़ करें
रंग सेट करके और बॉर्डर कस्टमाइज़ करके दृश्य आकर्षण बढ़ाएँ – यह सीधे **पाई चार्ट के रंगों को कस्टमाइज़** करता है:
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

### कस्टम डेटा लेबल्स कॉन्फ़िगर करें
प्रत्येक डेटा पॉइंट के लिए लेबल्स को फाइन‑ट्यून करें:
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
**रोटेशन एंगल सेट** करके और फ़ाइल को सेव करके अपने पाई चार्ट को अंतिम रूप दें:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| **स्लाइस सभी एक ही रंग में दिखते हैं** | `setColorVaried(true)` नहीं बुलाया गया | सुनिश्चित करें कि आप सीरीज़ ग्रुप पर वैरिएड कलर्स को सक्षम करें। |
| **डेटा लेबल नहीं दिख रहे** | `showValue` फ़्लैग डिसेबल है | उपयुक्त लेबल फ़ॉर्मेट पर `setShowValue(true)` कॉल करें। |
| **रोटेशन का कोई प्रभाव नहीं** | पुराना Aspose.Slides संस्करण उपयोग में है | संस्करण 25.4 या बाद में अपग्रेड करें। |
| **रनटाइम पर लाइसेंस एक्सेप्शन** | लाइसेंस फ़ाइल गायब या अमान्य है | `License license = new License(); license.setLicense("Aspose.Slides.lic");` को `Presentation` बनाने से पहले लोड करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: Java के लिए Aspose.Slides लाइसेंस कैसे प्राप्त करें?**  
उ: आप Aspose वेबसाइट से फ्री ट्रायल का अनुरोध कर सकते हैं, फिर स्थायी लाइसेंस खरीदें। सामान्य समस्याओं की तालिका में दिखाए अनुसार रनटाइम पर इसे लोड करें।

**प्र: क्या मैं इस कोड को पुराने JDK संस्करणों के साथ उपयोग कर सकता हूँ?**  
उ: API को JDK 16 या उससे ऊपर की आवश्यकता है; पुराने संस्करण समर्थित नहीं हैं।

**प्र: क्या PPTX के बजाय चार्ट को इमेज के रूप में एक्सपोर्ट करना संभव है?**  
उ: हाँ, रेंडरिंग के बाद `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` कॉल करें।

**प्र: यदि मुझे पाई चार्ट में एक से अधिक सीरीज़ जोड़नी हों तो क्या करें?**  
उ: पाई चार्ट आमतौर पर एक ही सीरीज़ दिखाते हैं; कई सीरीज़ के लिए डोनट चार्ट पर विचार करें।

**प्र: क्या लाइब्रेरी Linux सर्वरों पर काम करती है?**  
उ: बिल्कुल – Aspose.Slides for Java प्लेटफ़ॉर्म‑इंडिपेंडेंट है और किसी भी OS पर चलती है जहाँ संगत JDK उपलब्ध हो।

---

**Last Updated:** 2026-02-19  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}