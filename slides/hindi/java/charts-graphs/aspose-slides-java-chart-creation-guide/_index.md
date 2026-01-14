---
date: '2026-01-14'
description: Aspose.Slides का उपयोग करके जावा में क्लस्टर्ड कॉलम चार्ट बनाना सीखें।
  चरण‑दर‑चरण गाइड जिसमें खाली प्रस्तुति, प्रस्तुति में चार्ट जोड़ना, और सीरीज़ का
  प्रबंधन शामिल है।
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Aspose.Slides के साथ जावा में क्लस्टर्ड कॉलम चार्ट कैसे बनाएं
url: /hi/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java में Aspose.Slides के साथ चार्ट निर्माण में महारत हासिल करें

## Aspose.Slides for Java का उपयोग करके चार्ट कैसे बनाएं और प्रबंधित करें

### परिचय
डायनामिक प्रेजेंटेशन बनाते समय अक्सर डेटा को चार्ट के माध्यम से विज़ुअलाइज़ करना पड़ता है। **Aspose.Slides for Java** के साथ आप आसानी से **क्लस्टर्ड कॉलम चार्ट** बना सकते हैं और विभिन्न चार्ट प्रकारों को प्रबंधित कर सकते हैं, जिससे स्पष्टता और प्रभाव दोनों बढ़ते हैं। यह ट्यूटोरियल आपको एक खाली प्रेजेंटेशन बनाने, क्लस्टर्ड कॉलम चार्ट जोड़ने, सीरीज़ को मैनेज करने और डेटा पॉइंट इनवर्ज़न को कस्टमाइज़ करने के चरणों से परिचित कराएगा—सब कुछ Aspose.Slides for Java का उपयोग करके।

**आप क्या सीखेंगे:**
- Aspose.Slides for Java को कैसे सेटअप करें।
- **खाली प्रेजेंटेशन बनाना** और प्रेजेंटेशन में चार्ट जोड़ने के चरण।
- चार्ट सीरीज़ और डेटा पॉइंट्स को प्रभावी ढंग से मैनेज करने की तकनीकें।
- बेहतर विज़ुअलाइज़ेशन के लिए नकारात्मक डेटा पॉइंट्स को शर्तीय रूप से इनवर्ट करने के तरीके।
- प्रेजेंटेशन को सुरक्षित रूप से कैसे सेव करें।

चलने से पहले आवश्यक शर्तों को देखें।

## त्वरित उत्तर
- **शुरू करने के लिए मुख्य क्लास कौन सी है?** `Presentation` from `com.aspose.slides`।
- **कौन सा चार्ट प्रकार क्लस्टर्ड कॉलम चार्ट बनाता है?** `ChartType.ClusteredColumn`।
- **स्लाइड में चार्ट कैसे जोड़ें?** स्लाइड की shape कलेक्शन पर `addChart()` का उपयोग करें।
- **क्या आप नकारात्मक मानों को इनवर्ट कर सकते हैं?** हाँ, डेटा पॉइंट पर `invertIfNegative(true)` के साथ।
- **कौन सा संस्करण आवश्यक है?** Aspose.Slides for Java 25.4 या बाद का।

## क्लस्टर्ड कॉलम चार्ट क्या है?
क्लस्टर्ड कॉलम चार्ट प्रत्येक श्रेणी के लिए कई डेटा सीरीज़ को साइड‑बाय‑साइड दिखाता है, जिससे समूहों के बीच मानों की तुलना करना आसान हो जाता है। Aspose.Slides इस चार्ट को प्रोग्रामेटिकली जनरेट करता है बिना PowerPoint खोले।

## प्रेजेंटेशन में चार्ट जोड़ने के लिए Aspose.Slides for Java क्यों उपयोग करें?
- **डेटा, लुक और लेआउट पर पूर्ण नियंत्रण**।
- **सर्वर पर कोई Office इंस्टॉलेशन आवश्यक नहीं**।
- **सभी प्रमुख चार्ट प्रकारों का समर्थन**, जिसमें क्लस्टर्ड कॉलम चार्ट भी शामिल है।
- **Maven/Gradle बिल्ड्स के साथ आसान इंटीग्रेशन**।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **आवश्यक लाइब्रेरीज़:**
   - Aspose.Slides for Java (संस्करण 25.4 या बाद का)।

2. **पर्यावरण सेटअप आवश्यकताएँ:**
   - संगत JDK संस्करण (जैसे, JDK 16)।
   - यदि आप डिपेंडेंसी मैनेजमेंट पसंद करते हैं तो Maven या Gradle स्थापित हों।

3. **ज्ञान पूर्वापेक्षाएँ:**
   - Java प्रोग्रामिंग की बुनियादी समझ।
   - अपने विकास पर्यावरण में डिपेंडेंसीज़ को हैंडल करने की परिचितता।

## Aspose.Slides for Java सेटअप करना
Aspose.Slides का उपयोग शुरू करने के लिए इन चरणों का पालन करें:

**Maven इंस्टॉलेशन:**  
अपने `pom.xml` फ़ाइल में निम्न डिपेंडेंसी जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle इंस्टॉलेशन:**  
अपने `build.gradle` में निम्न पंक्ति जोड़ें:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**सीधे डाउनलोड:**  
वैकल्पिक रूप से, नवीनतम संस्करण [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंस प्राप्त करना
- **फ्री ट्रायल:** फीचर एक्सप्लोर करने के लिए फ्री ट्रायल से शुरू करें।  
- **टेम्पररी लाइसेंस:** मूल्यांकन अवधि के दौरान पूर्ण एक्सेस के लिए टेम्पररी लाइसेंस प्राप्त करें।  
- **खरीदें:** यदि यह आपकी दीर्घकालिक जरूरतों के अनुरूप है तो खरीदने पर विचार करें।

### बेसिक इनिशियलाइज़ेशन
नया प्रेजेंटेशन इंस्टेंस बनाने के लिए न्यूनतम कोड नीचे दिया गया है:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## इम्प्लीमेंटेशन गाइड
अब प्रत्येक फीचर को प्रबंधनीय चरणों में विभाजित करते हैं।

### क्लस्टर्ड कॉलम चार्ट के साथ प्रेजेंटेशन बनाना
#### अवलोकन
यह सेक्शन दिखाता है कि **खाली प्रेजेंटेशन** कैसे बनाएं, **क्लस्टर्ड कॉलम चार्ट** जोड़ें, और इसे पहली स्लाइड पर पोजिशन करें।

**चरण:**
1. **Presentation ऑब्जेक्ट इनिशियलाइज़ करें** – नया `Presentation` बनाएं।
2. **क्लस्टर्ड कॉलम चार्ट जोड़ें** – उचित प्रकार और डाइमेंशन के साथ `addChart()` कॉल करें।

**कोड उदाहरण:**
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

### चार्ट सीरीज़ का प्रबंधन
#### अवलोकन
डिफ़ॉल्ट सीरीज़ को साफ़ करना, नई सीरीज़ जोड़ना, और उसे पॉज़िटिव व नेगेटिव दोनों मानों से भरना सीखें।

**चरण:**
1. **मौजूदा सीरीज़ साफ़ करें** – प्री‑पॉप्युलेटेड डेटा हटाएँ।
2. **नई सीरीज़ जोड़ें** – वर्कबुक सेल को सीरीज़ नाम के रूप में उपयोग करें।
3. **डेटा पॉइंट्स इन्सर्ट करें** – मान जोड़ें, जिसमें नकारात्मक मान भी हों, ताकि बाद में इनवर्ज़न दिखाया जा सके।

**कोड उदाहरण:**
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

### शर्तीय रूप से सीरीज़ डेटा पॉइंट्स को इनवर्ट करना
#### अवलोकन
डिफ़ॉल्ट रूप से Aspose.Slides नकारात्मक मानों को इनवर्ट कर सकता है। आप इस व्यवहार को ग्लोबली और प्रत्येक डेटा पॉइंट स्तर पर नियंत्रित कर सकते हैं।

**चरण:**
1. **ग्लोबल इनवर्ज़न सेट करें** – पूरी सीरीज़ के लिए ऑटोमैटिक इनवर्ज़न को डिसेबल करें।
2. **शर्तीय इनवर्ज़न लागू करें** – केवल विशिष्ट नकारात्मक पॉइंट्स के लिए इनवर्ज़न एनेबल करें।

**कोड उदाहरण:**
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

### सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| चार्ट खाली दिख रहा है | सुनिश्चित करें कि स्लाइड इंडेक्स (`0`) मौजूद है और चार्ट डाइमेंशन स्लाइड की सीमा के भीतर हैं। |
| नकारात्मक मान इनवर्ट नहीं हो रहे | जांचें कि `invertIfNegative(false)` सीरीज़ पर सेट है और विशिष्ट डेटा पॉइंट पर `invertIfNegative(true)` है। |
| लाइसेंस एक्सेप्शन | `Presentation` ऑब्जेक्ट बनाने से पहले वैध Aspose लाइसेंस लागू करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं क्लस्टर्ड कॉलम के अलावा अन्य चार्ट प्रकार जोड़ सकता हूँ?**  
उ: हाँ, Aspose.Slides लाइन, पाई, बार, एरिया और कई अन्य चार्ट प्रकारों का समर्थन करता है।

**प्र: विकास के लिए लाइसेंस आवश्यक है क्या?**  
उ: फ्री ट्रायल मूल्यांकन के लिए काम करता है, लेकिन प्रोडक्शन उपयोग के लिए कमर्शियल लाइसेंस आवश्यक है।

**प्र: चार्ट को इमेज के रूप में कैसे एक्सपोर्ट करूँ?**  
उ: रेंडरिंग के बाद `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` उपयोग करें।

**प्र: क्या चार्ट को स्टाइल (रंग, फ़ॉन्ट) किया जा सकता है?**  
उ: बिल्कुल। प्रत्येक `IChartSeries` और `IChartDataPoint` स्टाइलिंग प्रॉपर्टीज़ प्रदान करता है।

**प्र: यदि मैं मौजूदा PPTX फ़ाइल में चार्ट जोड़ना चाहूँ तो?**  
उ: `new Presentation("existing.pptx")` से फ़ाइल लोड करें, फिर इच्छित स्लाइड पर चार्ट जोड़ें।

## निष्कर्ष
इस ट्यूटोरियल में आपने Java में **क्लस्टर्ड कॉलम चार्ट** बनाना, सीरीज़ मैनेज करना, और नकारात्मक डेटा पॉइंट्स को शर्तीय रूप से इनवर्ट करना सीखा। इन तकनीकों के साथ आप प्रोग्रामेटिकली आकर्षक, डेटा‑ड्रिवेन प्रेजेंटेशन बना सकते हैं।

**अगले कदम:**
- Aspose.Slides for Java द्वारा प्रदान किए गए अन्य चार्ट प्रकारों के साथ प्रयोग करें।  
- कस्टम रंग, डेटा लेबल और एक्सिस फ़ॉर्मेटिंग जैसी एडवांस्ड स्टाइलिंग विकल्पों में डुबकी लगाएँ।  
- अपने रिपोर्टिंग या एनालिटिक्स पाइपलाइन में चार्ट जेनरेशन को इंटीग्रेट करें।

---

**अंतिम अपडेट:** 2026-01-14  
**टेस्टेड विद:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}