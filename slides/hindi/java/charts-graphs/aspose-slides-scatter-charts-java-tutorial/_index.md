---
date: '2026-02-24'
description: Aspose.Slides for Java का उपयोग करके स्कैटर चार्ट को कस्टमाइज़ करना सीखें।
  यह गाइड आपको आपके प्रेजेंटेशन में डायनेमिक स्कैटर चार्ट बनाने, स्टाइल करने और सेव
  करने की प्रक्रिया से परिचित कराता है।
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: जावा में Aspose के साथ स्कैटर चार्ट को अनुकूलित करें
url: /hi/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# जावा में Aspose के साथ स्कैटर चार्ट को कस्टमाइज़ करें

इस ट्यूटोरियल में आप **कस्टमाइज़ स्कैटर चार्ट Aspose** को शक्तिशाली Aspose.Slides for Java लाइब्रेरी की मदद से सीखेंगे। हम प्रोजेक्ट सेटअप, स्कैटर चार्ट बनाना, सीरीज़ प्रकार और मार्कर को ट्यून करना, और अंत में प्रेजेंटेशन को सेव करना दिखाएंगे। अंत तक आप प्रोग्रामेटिकली प्रोफेशनल‑लुकिंग स्कैटर चार्ट जेनरेट कर सकेंगे और हर विज़ुअल डिटेल को अपने ब्रांड या रिपोर्टिंग जरूरतों के अनुसार कस्टमाइज़ कर सकेंगे।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी चाहिए?** Aspose.Slides for Java (v25.4+).  
- **कौन सा जावा संस्करण समर्थित है?** JDK 8 या उससे ऊपर।  
- **क्या मैं मार्कर के आकार बदल सकता हूँ?** हाँ – `MarkerStyleType` का उपयोग करके स्टार, सर्कल आदि चुनें।  
- **फ़ाइल कैसे सेव करें?** `pres.save("output.pptx", SaveFormat.Pptx)` कॉल करें।  
- **क्या लाइसेंस आवश्यक है?** विकास के लिए फ्री ट्रायल चलती है; प्रोडक्शन के लिए कॉमर्शियल लाइसेंस चाहिए।

## “कस्टमाइज़ स्कैटर चार्ट Aspose” क्या है?
Aspose के साथ स्कैटर चार्ट को कस्टमाइज़ करना मतलब प्रोग्रामेटिकली चार्ट का डेटा, लुक और बिहेवियर परिभाषित करना—पॉइंट कोऑर्डिनेट्स से लेकर मार्कर सिंबल तक—बिना PowerPoint को मैन्युअली खोले। यह ऑटोमेटेड रिपोर्टिंग, डेटा‑ड्रिवन प्रेजेंटेशन या किसी भी ऐसी स्थिति में आदर्श है जहाँ आपको दोहराने योग्य, हाई‑क्वालिटी विज़ुअलाइज़ेशन चाहिए।

## Aspose.Slides के साथ स्कैटर चार्ट कस्टमाइज़ क्यों करें?
- **पूर्ण नियंत्रण** – सीरीज़ प्रकार, मार्कर स्टाइल, रंग आदि को जावा कोड से बदलें।  
- **ऑटोमेशन** – डैशबोर्ड या बैच रिपोर्ट के लिए तुरंत कई चार्ट जेनरेट करें।  
- **क्रॉस‑प्लेटफ़ॉर्म** – कोई Office इंस्टॉलेशन नहीं, जावा सपोर्ट करने वाले किसी भी OS पर काम करता है।  
- **परफॉर्मेंस** – हल्का API जो बड़े डेटा सेट को कुशलता से संभालता है।

## पूर्वापेक्षाएँ

शुरू करने के लिए सुनिश्चित करें कि आपके पास है:

- **Aspose.Slides for Java** (v25.4 या बाद का)।  
- **Java Development Kit (JDK)** 8 + स्थापित।  
- डिपेंडेंसी मैनेजमेंट के लिए Maven या Gradle (या आप JAR मैन्युअली डाउनलोड कर सकते हैं)।  
- बेसिक जावा ज्ञान और अपने बिल्ड टूल की परिचितता।

## Aspose.Slides for Java सेटअप करना

नीचे दिए गए किसी एक तरीके से लाइब्रेरी को प्रोजेक्ट में इंटीग्रेट करें।

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

या नवीनतम रिलीज़ यहाँ से डाउनलोड करें: [Aspose Releases](https://releases.aspose.com/slides/java/)।

#### लाइसेंस प्राप्त करना
- **फ्री ट्रायल** – 30‑दिन की इवैल्युएशन।  
- **टेम्पररी लाइसेंस** – विस्तारित टेस्टिंग अवधि।  
- **फुल लाइसेंस** – प्रोडक्शन उपयोग के साथ प्रीमियम सपोर्ट।

## स्कैटर चार्ट Aspose को कस्टमाइज़ करने का चरण‑दर‑चरण गाइड

### 1️⃣ प्रेजेंटेशन फ़ाइलों के लिए फ़ोल्डर तैयार करें
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*क्यों जरूरी है:* आउटपुट फ़ोल्डर मौजूद न होने पर `FileNotFoundException` से बचा जा सकता है।

### 2️⃣ नई प्रेजेंटेशन बनाएं और पहली स्लाइड प्राप्त करें
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
एक नई `Presentation` साफ़ कैनवास देती है; पहली स्लाइड पर हम चार्ट रखेंगे।

### 3️⃣ स्मूथ लाइन्स के साथ स्कैटर चार्ट जोड़ें
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` स्मूथ‑लाइन स्कैटर चार्ट बनाता है, ट्रेंड विज़ुअलाइज़ेशन के लिए उपयुक्त।

### 4️⃣ डिफ़ॉल्ट सीरीज़ को हटाएँ और अपनी सीरीज़ जोड़ें
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
डिफ़ॉल्ट सीरीज़ हटाने से आप दिखाए जाने वाले डेटा पर पूरी पकड़ बना सकते हैं।

### 5️⃣ पहली सीरीज़ को डेटा पॉइंट्स से भरें
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` X‑वैल्यू सेल और Y‑वैल्यू सेल लेता है, जिससे स्कैटर प्लॉट पॉइंट‑बाय‑पॉइंट बनता है।

### 6️⃣ सीरीज़ प्रकार और मार्कर लुक को कस्टमाइज़ करें
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
यहाँ हम **कस्टमाइज़ स्कैटर चार्ट Aspose** करके स्ट्रेट लाइन्स, बड़े मार्कर और अलग‑अलग सिंबल (स्टार बनाम सर्कल) चुनते हैं ताकि विज़ुअल क्लैरिटी बढ़े।

### 7️⃣ प्रेजेंटेशन को सेव करें
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
`Pptx` के रूप में सेव करने से सभी चार्ट कस्टमाइज़ेशन सुरक्षित रहते हैं और फ़ाइल शेयरिंग या आगे एडिटिंग के लिए तैयार रहती है।

## कस्टमाइज़्ड स्कैटर चार्ट के सामान्य उपयोग केस
- **फ़ाइनेंशियल डैशबोर्ड** – स्टॉक प्राइस बनाम वॉल्यूम प्लॉट करें।  
- **साइंटिफिक रिसर्च** – एरर मार्कर के साथ एक्सपेरिमेंटल मेज़रमेंट दिखाएँ।  
- **प्रोजेक्ट मैनेजमेंट** – टास्क्स के बीच प्लान्ड बनाम एक्चुअल एफ़र्ट की तुलना करें।  

## परफॉर्मेंस टिप्स
- सेव करने के बाद `Presentation` ऑब्जेक्ट को `pres.dispose()` करके नेटीव रिसोर्सेज़ मुक्त करें।  
- बड़े डेटा सेट के लिए पहले वर्कबुक भरें और फिर सीरीज़ को बाइंड करें ताकि UI रिफ्रेश कम हो।  
- कई सीरीज़ जोड़ते समय एक ही `IChartDataWorkbook` इंस्टेंस को री‑यूज़ करें।

## अक्सर पूछे जाने वाले प्रश्न

### मार्कर का रंग कैसे बदलूँ?
`series.getMarker().getFillFormat().setFillColor(Color)` का उपयोग करें जहाँ `Color` `java.awt.Color` का इंस्टेंस है (उदा., `Color.RED`)।

### क्या स्कैटर चार्ट में दो से अधिक सीरीज़ जोड़ सकता हूँ?
बिल्कुल। प्रत्येक अतिरिक्त सीरीज़ के लिए `chart.getChartData().getSeries().add(...)` कॉल दोहराएँ और उसके डेटा पॉइंट्स भरें।

### क्या प्रत्येक सीरीज़ के लिए कस्टम लेजेंड सेट कर सकता हूँ?
हां। सीरीज़ बनाते समय `series.getLegend().setText("Your Legend Text")` कॉल करके डिफ़ॉल्ट नाम को ओवरराइड करें।

### चार्ट को PPTX की बजाय इमेज के रूप में एक्सपोर्ट कैसे करूँ?
चार्ट को कॉन्फ़िगर करने के बाद `chart.getImage().save("chart.png", ImageFormat.Png)` कॉल करें। इससे एक स्टैंडअलोन PNG फ़ाइल मिलती है।

### अगर स्कैटर पॉइंट्स को एनीमेट करना हो तो क्या करें?
Aspose.Slides एनीमेशन इफ़ेक्ट्स सपोर्ट करता है। `chart.getTimeline().getMainSequence().addEffect(...)` का उपयोग करके चार्ट या व्यक्तिगत सीरीज़ में एंट्रेंस या इम्पहैसिस एनीमेशन जोड़ें।

---

**अंतिम अपडेट:** 2026-02-24  
**टेस्टेड विथ:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}