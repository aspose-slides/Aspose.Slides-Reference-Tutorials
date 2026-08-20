---
date: '2026-07-22'
description: Aspose Slides Maven Dependency को सीखें ताकि Java में stacked column
  chart बनाया जा सके, data labels जोड़ें, vertical axis number format बदलें, और परिणाम
  को PPTX फ़ाइल के रूप में निर्यात करें।
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency आपको Java में stacked column chart
  बनाने, data labels को कस्टमाइज़ करने, vertical axis format को समायोजित करने, और
  PPTX के रूप में सहेजने की सुविधा देता है – सभी संक्षिप्त, production‑ready कोड के
  साथ।
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Java में Stacked Column Chart'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Java में Stacked Column Chart'
url: /hi/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven निर्भरता: जावा में स्टैक्ड कॉलम चार्ट

## परिचय

अपने प्रस्तुतियों को **Aspose.Slides for Java** की शक्ति के साथ सूचनात्मक डेटा विज़ुअलाइज़ेशन शामिल करके उन्नत बनाएं। इस गाइड में आप एक **स्टैक्ड कॉलम चार्ट** बनाएँगे जो पेशेवर दिखेगा, चाहे आप व्यापार रिपोर्ट तैयार कर रहे हों या प्रोजेक्ट आँकड़े प्रदर्शित कर रहे हों। इस ट्यूटोरियल के अंत तक आप सक्षम होंगे:

- **Aspose Slides Maven निर्भरता** के साथ अपना वातावरण सेट करें
- शुरू से एक प्रस्तुति बनाएं
- **परसेंटेज‑स्टैक्ड चार्ट** जोड़ें और उसकी उपस्थिति को अनुकूलित करें
- **चार्ट डेटा लेबल्स को फ़ॉर्मेट** करें और **वर्टिकल एक्सिस नंबर फ़ॉर्मेट बदलें**
- एक ही कोड लाइन से **प्रेजेंटेशन को PPTX के रूप में सेव** करें

## त्वरित उत्तर
- **मुझे कौनसी लाइब्रेरी चाहिए?** `aspose-slides` Maven/Gradle निर्भरता जोड़ें (नीचे “Aspose Slides Maven Dependency” देखें)।  
- **कौनसा चार्ट प्रकार स्टैक्ड व्यू बनाता है?** प्रतिशत‑स्टैक्ड कॉलम चार्ट के लिए `ChartType.PercentsStackedColumn` का उपयोग करें।  
- **मैं एक्सिस नंबर फ़ॉर्मेट कैसे बदलूँ?** `IAxis.setNumberFormat()` कॉल करें और `setNumberFormatLinkedToSource(false)` सेट करें।  
- **क्या मैं डेटा लेबल्स को कस्टमाइज़ कर सकता हूँ?** हाँ – प्रत्येक `IChartDataPoint` पर इटररेट करके एक कस्टम `ITextFrame` असाइन करें।  
- **फ़ाइल को कैसे सेव करूँ?** `presentation.save("output.pptx", SaveFormat.Pptx)` को कॉल करें।

## स्टैक्ड कॉलम चार्ट क्या है?
एक स्टैक्ड कॉलम चार्ट कई डेटा सीरीज़ को प्रत्येक श्रेणी कॉलम में लंबवत रूप से स्टैक करके दर्शाता है, जहाँ **परसेंटेज‑स्टैक्ड** वैरिएंट प्रत्येक कॉलम को 100 % तक सामान्यीकृत करता है ताकि अनुपात तुलना आसान हो। यह फॉर्मेट दर्शकों को जल्दी से समझने में मदद करता है कि प्रत्येक घटक विभिन्न श्रेणियों में संपूर्ण में कितना योगदान देता है, जिससे ट्रेंड और सापेक्ष आकार तुरंत स्पष्ट हो जाते हैं।

## क्यों उपयोग करें Aspose.Slides for Java?
Aspose.Slides for Java आपको Microsoft Office की आवश्यकता के बिना PowerPoint फ़ाइलें **जेनरेट, एडिट और कनवर्ट** करने की सुविधा देता है और **50+ आउटपुट फ़ॉर्मेट** को Windows, Linux और macOS पर सपोर्ट करता है। लाइब्रेरी पूरी तरह से JRE पर चलती है, जिससे सर्वर‑साइड ऑटोमेशन और हाई‑थ्रूपुट रिपोर्टिंग संभव होती है। यह चार्ट ऑब्जेक्ट्स, स्लाइड लेआउट्स और डॉक्यूमेंट प्रॉपर्टीज़ पर सूक्ष्म नियंत्रण प्रदान करती है, जो एंटरप्राइज़‑लेवल प्रेजेंटेशन जेनरेशन के लिए आदर्श है।

## आवश्यकताएँ
- **Java Development Kit (JDK):** 8 या उससे ऊपर  
- **IDE:** IntelliJ IDEA, Eclipse, या कोई भी Java‑compatible एडिटर  
- **Build Tool:** Maven या Gradle (वैकल्पिक लेकिन अनुशंसित)  
- **बेसिक Java ज्ञान** – आपको क्लासेस और मेथड्स के साथ सहज होना चाहिए  

## Aspose.Slides for Java सेटअप
शुरू करने के लिए, अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी जोड़ें।

### Aspose Slides Maven निर्भरता
अपने `pom.xml` में निम्नलिखित जोड़ें (यह वह **aspose slides maven dependency** है जिसकी आपको आवश्यकता होगी):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle विकल्प
यदि आप Gradle पसंद करते हैं, तो `build.gradle` में यह लाइन शामिल करें:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### सीधे डाउनलोड
वैकल्पिक रूप से, नवीनतम JAR को [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंस प्राप्ति
आप Aspose.Slides फीचर्स को एक्सप्लोर करने के लिए एक फ्री ट्रायल से शुरू कर सकते हैं। इवैल्यूएशन सीमाओं को हटाने के लिए, एक टेम्पररी या पर्चेज्ड लाइसेंस प्राप्त करने पर विचार करें।

- **Free Trial:** तुरंत लागत के बिना सीमित फीचर्स तक पहुँच।  
- **Temporary License:** [Aspose’s site](https://purchase.aspose.com/temporary-license/) से अनुरोध करें।  
- **Purchase:** पूर्ण एक्सेस के लिए पर्चेज पेज पर जाएँ।

### बेसिक इनिशियलाइज़ेशन
`Presentation` Aspose.Slides की कोर क्लास है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करती है। नीचे दिया गया न्यूनतम स्निपेट दिखाता है कि कैसे एक `Presentation` ऑब्जेक्ट बनाया जाता है:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## कार्यान्वयन गाइड

### प्रस्तुति बनाना और स्लाइड जोड़ना
**Overview:**  
पहले, हम एक खाली प्रस्तुति बनाएँगे और यह सत्यापित करेंगे कि एक स्लाइड मौजूद है।

#### चरण 1: Presentation ऑब्जेक्ट इनिशियलाइज़ करें
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### चरण 2: प्रस्तुति को सेव करें
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### स्लाइड में परसेंटेज स्टैक्ड कॉलम चार्ट जोड़ना
**Overview:**  
अब हम पहले स्लाइड पर एक **percentage stacked chart** रखेंगे।

`ChartType.PercentsStackedColumn` एक percentage‑stacked कॉलम चार्ट टाइप को निर्दिष्ट करता है।

#### चरण 1: स्लाइड को इनिशियलाइज़ और एक्सेस करें
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### चरण 2: स्लाइड में चार्ट जोड़ें
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### चार्ट एक्सिस नंबर फ़ॉर्मेट कस्टमाइज़ करना
**Overview:**  
बेहतर पठनीयता के लिए हम **वर्टिकल एक्सिस फ़ॉर्मेट** को प्रतिशत दिखाने के लिए बदलेंगे।

`IAxis` एक इंटरफ़ेस है जो चार्ट एक्सिस का प्रतिनिधित्व करता है, जिससे फ़ॉर्मेट और स्केलिंग समायोजन संभव होते हैं।

#### चरण 1: चार्ट जोड़ें और एक्सेस करें
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### चरण 2: कस्टम नंबर फ़ॉर्मेट सेट करें
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### चार्ट में सीरीज़ और डेटा पॉइंट्स जोड़ना
**Overview:**  
हम चार्ट को सैंपल डेटा सीरीज़ से भरेंगे।

#### चरण 1: प्रस्तुति और चार्ट इनिशियलाइज़ करें
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### चरण 2: डेटा सीरीज़ जोड़ें
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### सीरीज़ फ़िल कलर फ़ॉर्मेट करना
**Overview:**  
प्रत्येक सीरीज़ को अलग रंग दें ताकि चार्ट पढ़ने में आसान हो।

#### चरण 1: चार्ट इनिशियलाइज़ और एक्सेस करें
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### चरण 2: फ़िल कलर्स सेट करें
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### डेटा लेबल्स फ़ॉर्मेट करना
**Overview:**  
अब हम **चार्ट डेटा लेबल्स** को फ़ॉर्मेट करेंगे ताकि वे कस्टम टेक्स्ट दिखाएँ।

`IChartDataPoint` चार्ट सीरीज़ के भीतर एक व्यक्तिगत डेटा पॉइंट का प्रतिनिधित्व करता है, और `ITextFrame` लेबल टेक्स्ट रखता है।

#### चरण 1: चार्ट सीरीज़ और डेटा पॉइंट्स एक्सेस करें
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### चरण 2: डेटा लेबल्स कस्टमाइज़ करें
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## सामान्य समस्याएँ और समाधान
- **चार्ट खाली दिख रहा है:** सेव करने से पहले सुनिश्चित करें कि आपने कम से कम एक डेटा सीरीज़ और डेटा पॉइंट जोड़ा है।  
- **एक्सिस नंबर प्रतिशत नहीं दिखा रहे:** याद रखें `verticalAxis.setNumberFormatLinkedToSource(false)` सेट करें; अन्यथा कस्टम फ़ॉर्मेट अनदेखा हो जाएगा।  
- **लाइसेंस इवैल्यूएशन संदेश:** `Presentation` ऑब्जेक्ट बनाने से पहले वैध लाइसेंस फ़ाइल लागू करें ताकि इवैल्यूएशन बैनर दबाया जा सके।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं इस कोड को Java 11 या उससे नए संस्करण के साथ उपयोग कर सकता हूँ?**  
A: हाँ। लाइब्रेरी JDK 8+ को सपोर्ट करती है; बस उपयुक्त क्लासिफ़ायर (जैसे, `jdk16` JDK 16 या बाद के लिए) उपयोग करें।

**Q: मैं चार्ट को PPTX के बजाय इमेज के रूप में कैसे एक्सपोर्ट करूँ?**  
A: स्लाइड में चार्ट जोड़ने के बाद `chart.getImage().save("chart.png", ImageFormat.Png);` का उपयोग करें।

**Q: क्या स्टैक्ड कॉलम चार्ट में लेजेंड जोड़ना संभव है?**  
A: बिल्कुल। `chart.getChartTitle().addTextFrameForOverriding("My Chart");` को कॉल करें और आवश्यकतानुसार `chart.getLegend()` को कॉन्फ़िगर करें।

**Q: यदि प्रस्तुति जेनरेट होने के बाद डेटा अपडेट करना हो तो क्या करूँ?**  
A: आप `ChartDataWorkbook` की सेल्स को मॉडिफ़ाई कर सकते हैं और फिर `chart.refresh();` कॉल करके बदलाव दर्शा सकते हैं।

**Q: क्या Aspose.Slides Linux सर्वरों पर काम करता है?**  
A: हाँ। लाइब्रेरी शुद्ध Java है और किसी भी OS पर चलती है जहाँ संगत JRE उपलब्ध हो।

## निष्कर्ष
इस गाइड को फॉलो करके आपने **Aspose Slides Maven निर्भरता** का उपयोग करके जावा में **स्टैक्ड कॉलम चार्ट** बनाना सीखा, पर्यावरण सेटअप से लेकर फाइन‑ट्यून विज़ुअल स्टाइलिंग तक। विभिन्न डेटा सेट, रंग और लेबल फ़ॉर्मेट के साथ प्रयोग करें ताकि आपके रिपोर्ट वास्तव में standout हों।

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [जावा में Aspose.Slides के साथ क्लस्टर्ड कॉलम चार्ट कैसे बनाएं](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Aspose.Slides for Java का उपयोग करके चार्ट डेटा पॉइंट्स में नंबर फ़ॉर्मेट कैसे सेट करें](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Aspose.Slides for Java का उपयोग करके प्रस्तुतियों में चार्ट कैसे जोड़ें और कॉन्फ़िगर करें](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}