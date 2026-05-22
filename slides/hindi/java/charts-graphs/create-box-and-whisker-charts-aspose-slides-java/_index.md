---
date: '2026-03-02'
description: Aspose.Slides for Java का उपयोग करके बॉक्स प्लॉट जावा कैसे बनाएं, स्लाइड
  में चार्ट जोड़ें, और PowerPoint में बॉक्स व्हिस्कर चार्ट जनरेट करें, यह सीखें।
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Aspose.Slides for PowerPoint का उपयोग करके जावा में बॉक्स प्लॉट बनाएं
url: /hi/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint में Aspose.Slides for Java का उपयोग करके बॉक्स‑एंड‑व्हिस्कर चार्ट कैसे बनाएं

इस गाइड में आप Aspose.Slides के साथ **box plot java** बनाएँगे, और फिर चार्ट को सीधे PowerPoint स्लाइड में एम्बेड करेंगे। आज के डेटा‑ड्रिवेन विश्व में दृश्य रूप से आकर्षक डेटा प्रस्तुतियाँ बनाना अत्यंत महत्वपूर्ण है, और चार्ट इस उद्देश्य के लिए आवश्यक उपकरण हैं। यदि आप Java का उपयोग करके PowerPoint में बॉक्स‑एंड‑व्हिस्कर चार्ट बनाना चाहते हैं, तो Aspose.Slides लाइब्रेरी एक मजबूत समाधान प्रदान करती है। यह ट्यूटोरियल आपको Aspose.Slides for Java के साथ इन चार्ट्स को सहजता से बनाने और कॉन्फ़िगर करने की प्रक्रिया दिखाएगा।

## आप क्या सीखेंगे

- Aspose.Slides for Java के लिए अपना पर्यावरण सेट अप करना
- PowerPoint में Java का उपयोग करके **add chart to slide** करने और बॉक्स‑व्हिस्कर चार्ट जनरेट करने के चरण
- Aspose.Slides के साथ काम करते समय प्रदर्शन को अनुकूलित करने के लिए सर्वोत्तम प्रथाएँ
- बॉक्स‑एंड‑व्हिस्कर चार्ट्स के वास्तविक‑विश्व अनुप्रयोग

## त्वरित उत्तर

- **Java में बॉक्स प्लॉट बनाने वाली लाइब्रेरी कौन सी है?** Aspose.Slides for Java.  
- **कौन सा चार्ट प्रकार उपयोग किया जाता है?** `ChartType.BoxAndWhisker`.  
- **क्या मुझे लाइसेंस चाहिए?** मूल्यांकन के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक वाणिज्यिक लाइसेंस आवश्यक है।  
- **क्या मैं कई सीरीज़ जोड़ सकता हूँ?** हाँ – प्रत्येक डेटा सेट के लिए सीरीज़‑क्रिएशन ब्लॉक दोहराएँ।  
- **अंतिम फ़ाइल का फ़ॉर्मेट क्या है?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## पूर्वापेक्षाएँ

इस ट्यूटोरियल को फॉलो करने के लिए, सुनिश्चित करें कि आपके पास है:

- **Java Development Kit (JDK)**: JDK 8 या उससे ऊपर स्थापित होना चाहिए।  
- **Aspose.Slides for Java Library**: Java में PowerPoint प्रस्तुतियों को संभालने के लिए आवश्यक।  
- **IDE**: IntelliJ IDEA या Eclipse जैसे एकीकृत विकास वातावरण, जिसमें आप अपना कोड लिख और चलाएँ।  

## Aspose.Slides for Java सेट अप करना

Aspose.Slides का उपयोग करने के लिए, इसे एक डिपेंडेंसी के रूप में जोड़ें। आप इसे Maven, Gradle, या सीधे डाउनलोड के माध्यम से प्रबंधित कर सकते हैं।

### Maven

`pom.xml` में निम्नलिखित डिपेंडेंसी जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

`build.gradle` में शामिल करें:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### सीधे डाउनलोड

वैकल्पिक रूप से, नवीनतम संस्करण यहाँ से डाउनलोड करें: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)  

#### लाइसेंस प्राप्ति

- **Free Trial**: फीचर्स का पता लगाने के लिए फ्री ट्रायल से शुरू करें।  
- **Temporary License**: मूल्यांकन के लिए एक टेम्पररी लाइसेंस प्राप्त करें।  
- **Purchase**: पूर्ण कार्यक्षमता के लिए लाइसेंस खरीदने पर विचार करें।  

Aspose.Slides को इनिशियलाइज़ करने के लिए, सुनिश्चित करें कि लाइब्रेरी आपके क्लासपाथ में है और आवश्यकतानुसार लाइसेंसिंग सेटअप किया गया है।

## कार्यान्वयन गाइड

अब हम चरण‑दर‑चरण कोड में डुबकी लगाते हैं। प्रत्येक ब्लॉक को स्निपेट से पहले समझाया गया है ताकि आप ठीक‑ठीक जान सकें कि यह क्या करता है।

### बॉक्स प्लॉट क्या है और इसे Java में क्यों उपयोग करें?

एक बॉक्स‑एंड‑व्हिस्कर चार्ट (अक्सर *बॉक्स प्लॉट* कहा जाता है) डेटा वितरण—मीडियन, क्वार्टाइल्स, और आउट्लायर्स—को एक संक्षिप्त रूप में दर्शाता है। Java में इस चार्ट को प्रोग्रामेटिकली जनरेट करने से आप सांख्यिकीय अंतर्दृष्टि को सीधे PowerPoint डेक्स में एम्बेड कर सकते हैं, जिससे मैन्युअल चार्ट निर्माण समाप्त हो जाता है।

### Aspose.Slides के साथ स्लाइड में चार्ट क्यों जोड़ें?

Aspose.Slides लो‑लेवल OpenXML विवरणों को एब्स्ट्रैक्ट करता है, जिससे आपको चार्ट बनाने, स्टाइल करने और एक्सपोर्ट करने के लिए एक सहज API मिलता है। इसका मतलब है कि आप रिपोर्ट जनरेशन को ऑटोमेट कर सकते हैं, सुसंगत ब्रांडिंग बना सकते हैं, और चार्ट को बड़े Java वर्कफ़्लो में इंटीग्रेट कर सकते हैं।

### चरण 1: प्रस्तुति बनाएं या खोलें

पहले, मौजूदा PPTX खोलें या नया बनाएं:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro tip:** यदि फ़ाइल मौजूद नहीं है, तो Aspose.Slides आपके लिए एक नई खाली प्रस्तुति बनाएगा।

### चरण 2: स्लाइड में बॉक्स‑एंड‑व्हिस्कर चार्ट जोड़ें

स्थिति और आकार (पॉइंट्स में) निर्दिष्ट करके चार्ट को जहाँ चाहिए वहाँ रखें:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### चरण 3: मौजूदा डेटा साफ़ करें

नया डेटा फीड करने से पहले, किसी भी प्लेसहोल्डर कैटेगरी या सीरीज़ को हटाएँ:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### चरण 4: कैटेगरीज कॉन्फ़िगर करें

ऐसी कैटेगरीज (X‑axis लेबल) जोड़ें जो प्रत्येक बॉक्स के नीचे दिखेंगी:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Note:** लेबल टेक्स्ट को अपने डेटा डोमेन से मिलाने के लिए समायोजित करें (जैसे, “Q1”, “Product A”).

### चरण 5: सीरीज़ बनाएं और कस्टमाइज़ करें

अब एक सीरीज़ बनाएं, विज़ुअल विकल्प सेट करें, और संख्यात्मक डेटा पॉइंट्स फीड करें:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

आप `int[] data` एरे को डेटाबेस, CSV फ़ाइल, या किसी अन्य स्रोत से पढ़े गए मानों से बदल सकते हैं।

### चरण 6: प्रस्तुति सहेजें

परिवर्तनों को नई PPTX फ़ाइल में सहेजें:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### चरण 7: संसाधनों को साफ़ करें

`Presentation` ऑब्जेक्ट को हमेशा डिस्पोज़ करें ताकि नेटिव रिसोर्सेज़ मुक्त हो सकें:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## व्यावहारिक अनुप्रयोग

बॉक्स‑एंड‑व्हिस्कर चार्ट्स सांख्यिकीय विश्लेषण और डेटा प्रस्तुति में अनमोल होते हैं। यहाँ कुछ परिदृश्य हैं जहाँ वे उत्कृष्ट होते हैं:

1. **Financial Analysis** – क्षेत्रों के बीच राजस्व वितरण को विज़ुअलाइज़ करें।  
2. **Quality Control** – निर्माण माप में आउट्लायर्स को पहचानें।  
3. **Academic Research** – प्रयोगात्मक परिणामों की विविधता दिखाएँ।  
4. **Market Research** – जनसांख्यिकी के अनुसार उत्पाद प्रदर्शन की तुलना करें।  

इन चार्ट्स को PowerPoint डेक्स में इंटीग्रेट करने से स्टेकहोल्डर्स को एक नज़र में जटिल डेटा समझ में आता है।

## प्रदर्शन संबंधी विचार

Java में Aspose.Slides के साथ काम करते समय, इन टिप्स को ध्यान में रखें:

- **Memory Management** – `Presentation` ऑब्जेक्ट्स को तुरंत डिस्पोज़ करें।  
- **Data Handling** – केवल आवश्यक डेटा लोड करें; बड़े डेटा सेट को सीधे चार्ट वर्कबुक में फीड करने से बचें।  
- **Lazy Loading** – यदि आप कई स्लाइड्स जनरेट करते हैं, तो केवल उन स्लाइड्स के लिए चार्ट बनाना विचार करें जो प्रदर्शित होंगी।  

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|-------|----------|
| **चार्ट खाली दिख रहा है** | डेटा सेल्स सही तरीके से पॉप्युलेट नहीं हुए | Verify that `wb.getCell` references the correct row/column and that the value is not `null`. |
| **आउटलायर्स नहीं दिख रहे** | `setShowOutlierPoints` को `false` पर सेट किया गया है | Ensure `series.setShowOutlierPoints(true)` is called. |
| **मेमोरी लीक** | प्रस्तुति डिस्पोज़ नहीं हुई | Always wrap usage in try/finally and call `dispose()`. |
| **गलत क्वार्टाइल्स** | डिफ़ॉल्ट `Inclusive` मेथड का उपयोग | Switch to `Exclusive` via `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## अक्सर पूछे जाने वाले प्रश्न

**Q1: बॉक्स‑एंड‑व्हिस्कर चार्ट क्या है?**  
एक बॉक्स‑एंड‑व्हिस्कर चार्ट, जिसे बॉक्स प्लॉट भी कहा जाता है, डेटा का वितरण पाँच सारांश सांख्यिकियों—न्यूनतम, पहला क्वार्टाइल, मीडियन, तीसरा क्वार्टाइल, और अधिकतम—के साथ तथा किसी भी आउट्लायर के साथ प्रदर्शित करता है।

**Q2: क्या मैं बॉक्स‑एंड‑व्हिस्कर चार्ट की उपस्थिति को कस्टमाइज़ कर सकता हूँ?**  
हाँ। Aspose.Slides आपको रंग, लाइन स्टाइल, मार्कर शेप बदलने और चार्ट के फ़ॉर्मेटिंग API के माध्यम से डेटा लेबल जोड़ने की अनुमति देता है।

**Q3: क्या एक ही चार्ट में कई सीरीज़ को संभालना संभव है?**  
बिल्कुल। आप प्रत्येक डेटा सेट के लिए सीरीज़‑क्रिएशन ब्लॉक दोहरा सकते हैं जिसे आप विज़ुअलाइज़ करना चाहते हैं।

**Q4: डेटा सही ढंग से नहीं दिखने की समस्या को कैसे हल करें?**  
सुनिश्चित करें कि डेटा वर्कबुक सेल्स में सही ढंग से लिखा गया है और `setShowMeanLine` जैसी विज़िबिलिटी प्रॉपर्टीज़ सक्षम हैं।

**Q5: यदि मुझे समस्याएँ आती हैं तो मैं समर्थन कहाँ से प्राप्त कर सकता हूँ?**  
समुदाय सहायता के लिए [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) पर जाएँ, या आधिकारिक दस्तावेज़ देखें।

**Q6: क्या Aspose.Slides अन्य चार्ट प्रकारों का समर्थन करता है?**  
हाँ, यह लाइन, बार, पाई, स्कैटर, रडार और कई अन्य चार्ट प्रकारों का समर्थन करता है।

**Q7: क्या मैं हेडलेस सर्वर वातावरण में चार्ट जनरेट कर सकता हूँ?**  
यह लाइब्रेरी सर्वर‑साइड परिदृश्यों में पूरी तरह काम करती है; कोई UI आवश्यक नहीं है।

## संसाधन

- **Documentation**: विस्तृत API रेफ़रेंसेज़ यहाँ देखें: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Aspose.Slides रिलीज़ यहाँ प्राप्त करें: [here](https://releases.aspose.com/slides/java/)  
- **Purchase**: पूर्ण फीचर्स अनलॉक करने के लिए लाइसेंस खरीदें: [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Free Trial & Temporary License**: फ्री ट्रायल से शुरू करें या टेम्पररी लाइसेंस का अनुरोध करें [here](https://releases.aspose.com/slides/java/)  

इस गाइड को फॉलो करके, आप अब अपने Java एप्लिकेशन में प्रोग्रामेटिकली इनसाइटफुल बॉक्स‑एंड‑व्हिस्कर चार्ट्स जनरेट करने और उन्हें सीधे PowerPoint प्रस्तुतियों में एम्बेड करने में सक्षम हैं। कोडिंग का आनंद लें!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अद्यतन:** 2026-03-02  
**परीक्षित संस्करण:** Aspose.Slides 25.4 (JDK 16 classifier)  
**लेखक:** Aspose