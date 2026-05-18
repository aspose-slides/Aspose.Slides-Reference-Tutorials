---
date: '2026-02-22'
description: जावा में Aspose.Slides का उपयोग करके स्टैक्ड कॉलम चार्ट बनाना सीखें।
  इस ट्यूटोरियल में Aspose Slides Maven डिपेंडेंसी, प्रतिशत स्टैक्ड चार्ट जोड़ना,
  चार्ट डेटा लेबल्स को फॉर्मेट करना, और प्रस्तुति को PPTX के रूप में सहेजना शामिल
  है।
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: जावा में Aspose.Slides के साथ स्टैक्ड कॉलम चार्ट कैसे बनाएं – एक व्यापक गाइड
url: /hi/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java में Aspose.Slides के साथ stacked column chart कैसे बनाएं – एक व्यापक गाइड

## परिचय

Aspose.Slides for Java की शक्ति के साथ सूचनात्मक डेटा विज़ुअलाइज़ेशन को शामिल करके अपनी प्रस्तुतियों को उन्नत बनाएं। इस गाइड में आप **stacked column chart** स्लाइड्स बनाएँगे जो पेशेवर दिखेंगी, चाहे आप व्यापार रिपोर्ट तैयार कर रहे हों या प्रोजेक्ट सांख्यिकी प्रदर्शित कर रहे हों। इस ट्यूटोरियल के अंत तक आप सक्षम होंगे:

- Aspose Slides Maven dependency के साथ अपना वातावरण सेट अप करें
- शून्य से एक प्रस्तुति बनाएं
- **percentage stacked chart** जोड़ें और उसकी उपस्थिति को अनुकूलित करें
- **chart data labels** का फ़ॉर्मेट करें और **vertical axis format** बदलें
- **presentation को PPTX** के रूप में सहेजें एक लाइन कोड से

आइए प्रत्येक चरण को देखें ताकि आप तुरंत प्रभावशाली प्रस्तुतियाँ बनाना शुरू कर सकें।

## त्वरित उत्तर
- **मुझे कौनसी लाइब्रेरी चाहिए?** `aspose-slides` Maven/Gradle dependency (see “aspose slides maven dependency” below)  
- **कौनसा चार्ट प्रकार उपयोग किया जाता है?** `ChartType.PercentsStackedColumn` for a percentage‑stacked column chart  
- **मैं axis number format कैसे बदलूँ?** Use `IAxis.setNumberFormat()` and disable linking to source  
- **क्या मैं data labels को कस्टमाइज़ कर सकता हूँ?** Yes – iterate through `IChartDataPoint` objects and set a custom `ITextFrame`  
- **फ़ाइल को कैसे सहेजूँ?** Call `presentation.save("output.pptx", SaveFormat.Pptx)`

## stacked column chart क्या है?
एक stacked column chart कई डेटा श्रृंखलाओं को ऊर्ध्वाधर कॉलम में एक के ऊपर एक स्टैक करके दर्शाता है। जब आप **percentage‑stacked** वैरिएंट का उपयोग करते हैं, तो प्रत्येक कॉलम हमेशा 100 % तक कुल होता है, जिससे श्रेणियों के बीच अनुपातिक योगदान की तुलना आसान हो जाती है।

## Java के लिए Aspose.Slides क्यों उपयोग करें?
Aspose.Slides एक शुद्ध‑Java API प्रदान करता है जो किसी भी प्लेटफ़ॉर्म पर Microsoft Office स्थापित किए बिना काम करता है। यह चार्ट ऑब्जेक्ट्स पर सूक्ष्म नियंत्रण देता है, विभिन्न फ़ॉर्मैट्स को सपोर्ट करता है, और आपको प्रोग्रामेटिक रूप से प्रस्तुतियाँ उत्पन्न करने देता है—स्वचालित रिपोर्टिंग या सर्वर‑साइड दस्तावेज़ जनरेशन के लिए आदर्श।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK):** 8 या उससे ऊपर  
- **IDE:** IntelliJ IDEA, Eclipse, या कोई भी Java‑compatible editor  
- **Build Tool:** Maven या Gradle (वैकल्पिक लेकिन अनुशंसित)  
- **Basic Java knowledge** – आपको क्लासेस और मेथड्स में सहज होना चाहिए  

## Java के लिए Aspose.Slides सेट अप करना
शुरू करने के लिए, अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी जोड़ें।

### Aspose Slides Maven Dependency
`pom.xml` में निम्नलिखित जोड़ें (यह वह **aspose slides maven dependency** है जिसकी आपको आवश्यकता होगी):

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
वैकल्पिक रूप से, नवीनतम JAR [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंस प्राप्त करना
आप Aspose.Slides की सुविधाओं को आज़माने के लिए मुफ्त ट्रायल से शुरू कर सकते हैं। मूल्यांकन सीमाओं को हटाने के लिए, एक अस्थायी या खरीदा हुआ लाइसेंस प्राप्त करने पर विचार करें।

- **Free Trial:** बिना तुरंत लागत के सीमित सुविधाओं तक पहुँचें।  
- **Temporary License:** [Aspose’s site](https://purchase.aspose.com/temporary-license/) के माध्यम से अनुरोध करें।  
- **Purchase:** पूर्ण एक्सेस के लिए खरीद पृष्ठ पर जाएँ।

### बेसिक इनिशियलाइज़ेशन
यहाँ एक न्यूनतम स्निपेट है जो दिखाता है कि `Presentation` ऑब्जेक्ट कैसे बनाएं:

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

## इम्प्लीमेंटेशन गाइड

### प्रस्तुति बनाना और स्लाइड जोड़ना
**Overview:**  
पहले, हम एक खाली प्रस्तुति बनाएँगे और सत्यापित करेंगे कि एक स्लाइड मौजूद है।

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

#### चरण 2: प्रस्तुति सहेजें
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### स्लाइड में Percentage Stacked Column Chart जोड़ना
**Overview:**  
अब हम पहले स्लाइड पर एक **percentage stacked chart** रखेंगे।

#### चरण 1: स्लाइड इनिशियलाइज़ और एक्सेस करें
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

### चार्ट एक्सिस नंबर फ़ॉर्मेट को कस्टमाइज़ करना
**Overview:**  
बेहतर पठनीयता के लिए हम **vertical axis format** को प्रतिशत दिखाने के लिए बदलेंगे।

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
हम चार्ट को नमूना डेटा सीरीज़ से भरेंगे।

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
प्रत्येक सीरीज़ को एक विशिष्ट रंग दें ताकि चार्ट पढ़ने में आसान हो।

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
अब हम **chart data labels** को फ़ॉर्मेट करेंगे ताकि वे कस्टम टेक्स्ट दिखाएँ।

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
- **Chart appears empty:** सुनिश्चित करें कि आपने सहेजने से पहले कम से कम एक डेटा सीरीज़ और डेटा पॉइंट जोड़ा है।  
- **Axis numbers not showing percentages:** याद रखें `verticalAxis.setNumberFormatLinkedToSource(false)` सेट करें; अन्यथा कस्टम फ़ॉर्मेट अनदेखा हो जाएगा।  
- **License evaluation message:** `Presentation` ऑब्जेक्ट बनाने से पहले एक वैध लाइसेंस फ़ाइल लागू करें ताकि मूल्यांकन बैनर दबाया जा सके।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं इस कोड को Java 11 या उससे नए संस्करण के साथ उपयोग कर सकता हूँ?**  
A: हाँ। लाइब्रेरी JDK 8+ को सपोर्ट करती है; बस उपयुक्त classifier उपयोग करें (उदाहरण के लिए, JDK 16 या बाद के लिए `jdk16`)।

**Q: मैं चार्ट को PPTX के बजाय इमेज के रूप में कैसे एक्सपोर्ट करूँ?**  
A: स्लाइड में चार्ट जोड़ने के बाद `chart.getImage().save("chart.png", ImageFormat.Png);` उपयोग करें।

**Q: क्या stacked column chart में लेजेंड जोड़ना संभव है?**  
A: बिल्कुल। `chart.getChartTitle().addTextFrameForOverriding("My Chart");` कॉल करें और आवश्यकतानुसार `chart.getLegend()` को कॉन्फ़िगर करें।

**Q: यदि प्रस्तुति जनरेट होने के बाद डेटा अपडेट करना हो तो क्या करें?**  
A: आप `ChartDataWorkbook` की सेल्स को संशोधित कर सकते हैं और फिर `chart.refresh();` कॉल करके बदलाव लागू कर सकते हैं।

**Q: क्या Aspose.Slides Linux सर्वर पर काम करता है?**  
A: हाँ। लाइब्रेरी शुद्ध Java है और किसी भी OS पर चलती है जिसमें संगत JRE हो।

## निष्कर्ष
इस गाइड का पालन करके आपने Aspose.Slides for Java के साथ **stacked column chart** प्रस्तुतियों को बनाना सीखा, पर्यावरण सेटअप से लेकर सूक्ष्म दृश्य शैली तक। विभिन्न डेटा सेट, रंग, और लेबल फ़ॉर्मेट के साथ प्रयोग करें ताकि आपकी रिपोर्ट वास्तव में अलग दिखे।

---

**अंतिम अपडेट:** 2026-02-22  
**परीक्षण किया गया:** Aspose.Slides 25.4 (jdk16 classifier)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}