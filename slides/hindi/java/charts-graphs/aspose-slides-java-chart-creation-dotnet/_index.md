---
date: '2026-02-06'
description: Aspose Slides को इनिशियलाइज़ करना और .NET में Aspose.Slides for Java
  का उपयोग करके क्लस्टर्ड कॉलम चार्ट को कस्टमाइज़ करना सीखें। डेटा विज़ुअलाइज़ेशन
  को बेहतर बनाने के लिए इस चरण-दर-चरण गाइड का पालन करें।
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Aspose Slides के साथ प्रस्तुति प्रारंभ करें: .NET चार्ट'
url: /hi/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# .NET प्रस्तुतियों में Aspose.Slides for Java का उपयोग करके चार्ट बनाना

## परिचय
इस ट्यूटोरियल में आप **presentation Aspose Slides** को **initialize** करेंगे और यह सीखेंगे कि कैसे गतिशील, अनुकूलन योग्य चार्ट को अपने .NET स्लाइड्स में एम्बेड किया जाए। विज़ुअल डेटा—जैसे क्लस्टर्ड कॉलम चार्ट—आपके दर्शकों को रुझानों को तुरंत समझने में मदद करता है, और Aspose.Slides for Java आपको पूर्ण प्रोग्रामेटिक नियंत्रण देता है, भले ही आप .NET वातावरण को लक्षित कर रहे हों। हम लाइब्रेरी सेटअप, नई प्रस्तुति बनाना, चार्ट जोड़ना, डेटा भरना, और नकारात्मक मानों को रंगने जैसे फ़ॉर्मेटिंग ट्रिक्स को लागू करने की प्रक्रिया को चरण‑दर‑चरण देखेंगे।

**आप क्या सीखेंगे**
- .NET प्रोजेक्ट में Aspose.Slides for Java को कैसे सेटअप करें।  
- **presentation Aspose Slides** को **initialize** करना और चार्ट जोड़ना।  
- **क्लस्टर्ड कॉलम चार्ट** की सीरीज़ और कैटेगरीज को कैसे **customize** करें।  
- चार्ट के डेटा वर्कबुक को मैनेज करना और कंडीशनल फ़ॉर्मेटिंग लागू करना।  

### त्वरित उत्तर
- **पहला कदम क्या है?** `Presentation` ऑब्जेक्ट को **initialize** करें।  
- **उदाहरण में कौन सा चार्ट प्रकार उपयोग किया गया है?** `ClusteredColumn`।  
- **क्या मैं नकारात्मक मानों को अलग ढंग से फ़ॉर्मेट कर सकता हूँ?** हाँ, कंडीशनल फ़िल कलर्स का उपयोग करके।  
- **परीक्षण के लिए लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल लाइसेंस काम करता है।  
- **कौन सा Maven आर्टिफैक्ट आवश्यक है?** `com.aspose:aspose-slides:25.4` साथ में `jdk16` क्लासिफ़ायर।

## “presentation Aspose Slides को initialize” क्या है?
एक प्रस्तुति को initialize करने से एक इन‑मेमोरी PPTX फ़ाइल बनती है, जिसे आप सहेजने से पहले संशोधित कर सकते हैं। Aspose.Slides फ़ाइल फ़ॉर्मेट को एब्स्ट्रैक्ट करता है, जिससे आप स्लाइड्स, शैप्स और चार्ट्स को बिना लो‑लेवल OPC स्ट्रक्चर को समझे जोड़ सकते हैं।

## क्लस्टर्ड कॉलम चार्ट को कस्टमाइज़ क्यों करें?
क्लस्टर्ड कॉलम चार्ट कई डेटा सीरीज़ को विभिन्न कैटेगरीज में तुलना करने के लिए आदर्श होते हैं। रंग, डेटा पॉइंट्स और लेबल्स को कस्टमाइज़ करने से आप प्रमुख अंतर्दृष्टियों को उजागर कर सकते हैं—जैसे नकारात्मक मानों को लाल और सकारात्मक मानों को हरे रंग में दिखाना—जिससे आपकी स्लाइड्स अधिक प्रभावशाली बनती हैं।

## पूर्वापेक्षाएँ
- **Aspose.Slides for Java** ≥ 25.4  
- .NET विकास वातावरण (Visual Studio, .NET 6+ अनुशंसित)  
- बेसिक Java ज्ञान (आप Java कोड लिखेंगे जो JVM पर चलता है और .NET से JNI या ब्रिजिंग लेयर के माध्यम से कॉल किया जाता है)  

### आवश्यक लाइब्रेरी और संस्करण
- **Aspose.Slides for Java**: संस्करण 25.4 या बाद का।

### पर्यावरण सेटअप आवश्यकताएँ
- एक .NET‑संगत Java रनटाइम (जैसे AdoptOpenJDK 16)।  
- डिपेंडेंसी मैनेजमेंट के लिए Maven या Gradle।

### ज्ञान‑पूर्वापेक्षाएँ
- .NET संदर्भ में प्रस्तुतियों को बनाने की परिचितता।  
- Java प्रोजेक्ट कॉन्फ़िगरेशन (Maven/Gradle) की समझ।

## Aspose.Slides for Java सेटअप करना
अपनी पसंदीदा बिल्ड टूल का उपयोग करके लाइब्रेरी को प्रोजेक्ट में जोड़ें।

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

### डायरेक्ट डाउनलोड
आप आधिकारिक रिलीज़ पेज से नवीनतम JAR भी डाउनलोड कर सकते हैं: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)।

#### लाइसेंस प्राप्त करने के चरण
- **फ्री ट्रायल** – विकास के लिए एक अस्थायी लाइसेंस फ़ाइल जेनरेट करें।  
- **खरीदें** – प्रोडक्शन डिप्लॉयमेंट के लिए पूर्ण लाइसेंस प्राप्त करें।

#### बेसिक Initialization और सेटअप
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
`try/finally` ब्लॉक यह सुनिश्चित करता है कि नेटिव रिसोर्सेज़ रिलीज़ हो जाएँ, जिससे मेमोरी लीक्स नहीं होते।

## presentation Aspose Slides को कैसे initialize करें
नीचे हम एक नई प्रस्तुति बनाने और चार्ट इन्सर्शन के लिए तैयार करने के ठोस चरणों में उतरते हैं।

### Presentation को Initialize करना
**सारांश:**  
एक प्रस्तुति इंस्टेंस बनाना सभी आगे की ऑपरेशन्स के लिए मंच तैयार करता है।

#### चरण 1: आवश्यक पैकेज इम्पोर्ट करें
```java
import com.aspose.slides.Presentation;
```

#### चरण 2: नई Presentation ऑब्जेक्ट बनाएं
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*यह सुनिश्चित करता है कि उपयोग के बाद प्रस्तुति ऑब्जेक्ट सही ढंग से डिस्पोज़ हो, जिससे मेमोरी लीक्स नहीं होते।*

## क्लस्टर्ड कॉलम चार्ट को कैसे कस्टमाइज़ करें
अब जब प्रस्तुति तैयार है, चलिए एक क्लस्टर्ड कॉलम चार्ट जोड़ते और उसे अनुकूलित करते हैं।

### स्लाइड में चार्ट जोड़ना
**सारांश:**  
चार्ट जोड़ने से डेटा स्लाइड पर जीवंत हो जाता है।

#### चरण 1: आवश्यक पैकेज इम्पोर्ट करें
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### चरण 2: Presentation को Initialize करें और चार्ट जोड़ें
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
*यहाँ हम पहले स्लाइड में निर्दिष्ट कोऑर्डिनेट्स और डाइमेंशन के साथ एक क्लस्टर्ड कॉलम चार्ट जोड़ते हैं।*

### चार्ट डेटा वर्कबुक को मैनेज करना
**सारांश:**  
चार्ट के डेटा वर्कबुक को प्रभावी ढंग से मैनेज करने से आप सीरीज़ और कैटेगरीज को सहजता से हेर‑फेर कर सकते हैं।

#### चरण 1: आवश्यक पैकेज इम्पोर्ट करें
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### चरण 2: डेटा वर्कबुक तक पहुँचें और उसे क्लियर करें
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
*वर्कबुक को क्लियर करना नया सीरीज़ और कैटेगरीज जोड़ते समय साफ़ स्लेट से शुरू करने के लिए आवश्यक है।*

### चार्ट में सीरीज़ और कैटेगरीज जोड़ना
**सारांश:**  
यह चरण दर्शाता है कि आप सीरीज़ और कैटेगरीज को मैनेज करके सार्थक डेटा पॉइंट्स कैसे जोड़ सकते हैं।

#### चरण 1: सीरीज़ और कैटेगरीज जोड़ें
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

### सीरीज़ डेटा भरना और फ़ॉर्मेटिंग
**सारांश:**  
अपने चार्ट को डेटा पॉइंट्स से भरें और नकारात्मक मानों को विशेष रूप से हाइलाइट करने के लिए फ़ॉर्मेटिंग लागू करें।

#### चरण 1: सीरीज़ डेटा भरें
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
*यह भाग दिखाता है कि डेटा कैसे भरें और बेहतर विज़ुअलाइज़ेशन के लिए रंग फ़ॉर्मेटिंग कैसे लागू करें।*

## सामान्य समस्याएँ और समाधान
- **मेमोरी लीक्स** – हमेशा `Presentation` ऑब्जेक्ट को `try/finally` ब्लॉक में रैप करें जैसा ऊपर दिखाया गया है, ताकि डिस्पोज़ सुनिश्चित हो सके।  
- **गलत सेल कोऑर्डिनेट्स** – याद रखें कि रो और कॉलम शून्य‑आधारित होते हैं; गलत इंडेक्स `NullPointerException` का कारण बनते हैं।  
- **लाइसेंस नहीं मिला** – लाइसेंस फ़ाइल को एप्लिकेशन की वर्किंग डायरेक्टरी में रखें या स्पष्ट रूप से `License.setLicense("Aspose.Slides.Java.lic")` के माध्यम से पाथ सेट करें।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं इस दृष्टिकोण को .NET Core के साथ उपयोग कर सकता हूँ?**  
उत्तर: हाँ। Aspose.Slides for Java किसी भी JVM पर चलता है, और आप Java कोड को .NET Core से IKVM या JNI जैसे ब्रिज का उपयोग करके कॉल कर सकते हैं।

**प्रश्न: विकास के लिए क्या मुझे पेड लाइसेंस चाहिए?**  
उत्तर: विकास और टेस्टिंग के लिए फ्री ट्रायल लाइसेंस पर्याप्त है। प्रोडक्शन डिप्लॉयमेंट के लिए खरीदा हुआ लाइसेंस आवश्यक है।

**प्रश्न: निर्माण के बाद चार्ट प्रकार कैसे बदलूँ?**  
उत्तर: आप `chart.getChartData().setChartType(ChartType.Pie)` कॉल करके किसी अन्य चार्ट प्रकार में स्विच कर सकते हैं।

**प्रश्न: क्या डेटा लेबल्स को प्रोग्रामेटिकली जोड़ना संभव है?**  
उत्तर: हाँ। `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` का उपयोग करके चार्ट पर वैल्यू दिखा सकते हैं।

**प्रश्न: मैं प्रस्तुति को किन फॉर्मेट्स में सहेज सकता हूँ?**  
उत्तर: Aspose.Slides PPTX, PPT, PDF, XPS, और PNG, JPEG जैसे कई इमेज फॉर्मेट्स को सपोर्ट करता है।

---

**अंतिम अपडेट:** 2026-02-06  
**टेस्टेड वर्ज़न:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}