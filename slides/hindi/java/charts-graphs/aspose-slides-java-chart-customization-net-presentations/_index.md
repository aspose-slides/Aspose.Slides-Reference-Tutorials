---
date: '2026-01-17'
description: Aspose.Slides for Java का उपयोग करके .NET प्रस्तुतियों में चार्ट में
  सीरीज़ जोड़ना और स्टैक्ड कॉलम चार्ट को कस्टमाइज़ करना सीखें।
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Aspose.Slides for Java का उपयोग करके .NET में चार्ट में सीरीज़ जोड़ें
url: /hi/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java का उपयोग करके .NET प्रस्तुतियों में चार्ट अनुकूलन में महारत हासिल करना

## परिचय
डेटा‑आधारित प्रस्तुतियों के क्षेत्र में, चार्ट अनिवार्य उपकरण हैं जो कच्चे आंकड़ों को आकर्षक दृश्य कहानियों में बदलते हैं। जब आपको प्रोग्रामेटिक रूप से **add series to chart** करने की आवश्यकता होती है, विशेष रूप से .NET प्रस्तुति फ़ाइलों के भीतर, तो कार्य भारी लग सकता है। सौभाग्य से, **Aspose.Slides for Java** एक शक्तिशाली, भाषा‑निर्भर नहीं API प्रदान करता है जो चार्ट निर्माण और अनुकूलन को सरल बनाता है—भले ही आपका लक्ष्य फ़ॉर्मेट .NET PPTX हो।

इस ट्यूटोरियल में आप सीखेंगे कि कैसे **add series to chart** किया जाता है, कैसे **how to add chart** को स्टैक्ड कॉलम प्रकार में जोड़ा जाता है, और कैसे गैप विड्थ जैसे दृश्य पहलुओं को बारीकी से समायोजित किया जाता है। अंत तक, आप गतिशील, डेटा‑समृद्ध स्लाइड्स बना पाएँगे जो परिष्कृत और पेशेवर दिखेंगी।

**आप क्या सीखेंगे**
- Aspose.Slides का उपयोग करके खाली प्रस्तुति कैसे बनाएं
- स्लाइड में **add stacked column chart** कैसे जोड़ें
- **add series to chart** कैसे करें और श्रेणियाँ निर्धारित करें
- डेटा पॉइंट्स को भरें और दृश्य सेटिंग्स को समायोजित करें

आइए आपका विकास वातावरण तैयार करें।

## त्वरित उत्तर
- **प्रेजेंटेशन शुरू करने के लिए मुख्य क्लास कौन सा है?** `Presentation`  
- **कौन सा मेथड स्लाइड में चार्ट जोड़ता है?** `slide.getShapes().addChart(...)`  
- **नया सीरीज़ कैसे जोड़ते हैं?** `chart.getChartData().getSeries().add(...)`  
- **क्या आप बार के बीच गैप विड्थ बदल सकते हैं?** हाँ, सीरीज़ ग्रुप पर `setGapWidth()` का उपयोग करके  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** हाँ, एक वैध Aspose.Slides for Java लाइसेंस आवश्यक है  

## “add series to chart” क्या है?
चार्ट में एक सीरीज़ जोड़ना का अर्थ है नई डेटा कलेक्शन डालना जिसे चार्ट एक अलग दृश्य तत्व (जैसे नया बार, लाइन, या स्लाइस) के रूप में रेंडर करेगा। प्रत्येक सीरीज़ के पास अपने मान, रंग, और फॉर्मेटिंग हो सकते हैं, जिससे आप कई डेटा सेट्स की साइड‑बाय‑साइड तुलना कर सकते हैं।

## .NET प्रस्तुतियों को संशोधित करने के लिए Aspose.Slides for Java क्यों उपयोग करें?
- **क्रॉस‑प्लेटफ़ॉर्म**: Java कोड एक बार लिखें और .NET एप्लिकेशन द्वारा उपयोग किए जाने वाले PPTX फ़ाइलों को लक्षित करें।  
- **कोई COM या Office निर्भरताएँ नहीं**: सर्वर, CI पाइपलाइन, और कंटेनरों पर काम करता है।  
- **समृद्ध चार्ट API**: 50 से अधिक चार्ट प्रकारों का समर्थन करता है, जिसमें स्टैक्ड कॉलम चार्ट शामिल हैं।  

## आवश्यकताएँ
1. **Aspose.Slides for Java** लाइब्रेरी (संस्करण 25.4 या बाद का)।  
2. Maven या Gradle बिल्ड टूल, या मैन्युअल JAR डाउनलोड।  
3. बुनियादी Java ज्ञान और PPTX संरचना की परिचितता।  

## Aspose.Slides for Java सेटअप करना
### Maven इंस्टॉलेशन
अपने `pom.xml` में निम्नलिखित निर्भरता जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle इंस्टॉलेशन
अपने `build.gradle` फ़ाइल में यह पंक्ति शामिल करें:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### डायरेक्ट डाउनलोड
वैकल्पिक रूप से, आधिकारिक रिलीज़ पेज से नवीनतम JAR प्राप्त करें: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**लाइसेंस प्राप्ति**  
एक मुफ्त ट्रायल शुरू करने के लिए [यहाँ](https://purchase.aspose.com/temporary-license/) से टेम्पररी लाइसेंस डाउनलोड करें। उत्पादन उपयोग के लिए सभी फीचर्स अनलॉक करने हेतु पूर्ण लाइसेंस खरीदें।

## चरण‑दर‑चरण कार्यान्वयन गाइड
नीचे प्रत्येक चरण में आपको एक संक्षिप्त कोड स्निपेट (मूल ट्यूटोरियल से अपरिवर्तित) मिलेगा, जिसके बाद उसका कार्य समझाया गया है।

### चरण 1: एक खाली प्रस्तुति बनाएं
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*हम एक साफ़ PPTX फ़ाइल से शुरू करते हैं, जो हमें चार्ट जोड़ने के लिए एक कैनवास प्रदान करती है।*

### चरण 2: स्लाइड में स्टैक्ड कॉलम चार्ट जोड़ें
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*`addChart` मेथड एक **add stacked column chart** बनाता है और इसे स्लाइड के टॉप‑लेफ़्ट कोने में रखता है।*

### चरण 3: चार्ट में सीरीज़ जोड़ें (मुख्य लक्ष्य)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*यहाँ हम **add series to chart** करते हैं – प्रत्येक कॉल एक नया डेटा सीरीज़ बनाता है जो अलग कॉलम ग्रुप के रूप में दिखाई देगा।*

### चरण 4: चार्ट में श्रेणियाँ जोड़ें
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*श्रेणियाँ X‑अक्ष लेबल के रूप में कार्य करती हैं, प्रत्येक कॉलम को अर्थ प्रदान करती हैं।*

### चरण 5: सीरीज़ डेटा भरें
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*डेटा पॉइंट्स प्रत्येक सीरीज़ को उसके संख्यात्मक मान देते हैं, जिन्हें चार्ट बार की ऊँचाई के रूप में रेंडर करेगा।*

### चरण 6: चार्ट सीरीज़ ग्रुप के लिए गैप विड्थ सेट करें
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*गैप विड्थ को समायोजित करने से पठनीयता बढ़ती है, विशेषकर जब कई श्रेणियाँ मौजूद हों।*

## सामान्य उपयोग मामलों
- **वित्तीय रिपोर्टिंग** – विभिन्न व्यावसायिक इकाइयों में त्रैमासिक राजस्व की तुलना।  
- **प्रोजेक्ट डैशबोर्ड** – प्रत्येक टीम के कार्य पूर्णता प्रतिशत दिखाएँ।  
- **मार्केटिंग एनालिटिक्स** – अभियान प्रदर्शन को साइड‑बाय‑साइड विज़ुअलाइज़ करें।  

## प्रदर्शन सुझाव
- `Presentation` ऑब्जेक्ट को कई चार्ट बनाते समय पुन: उपयोग करें ताकि मेमोरी ओवरहेड कम हो।  
- डेटा पॉइंट्स की संख्या को केवल दृश्य कहानी के लिए आवश्यक तक सीमित रखें।  
- सेव करने के बाद ऑब्जेक्ट्स को डिस्पोज़ (`presentation.dispose()`) करें ताकि संसाधन मुक्त हों।  

## अक्सर पूछे जाने वाले प्रश्न
**प्रश्न: क्या मैं स्टैक्ड कॉलम के अलावा अन्य चार्ट प्रकार जोड़ सकता हूँ?**  
उत्तर: हाँ, Aspose.Slides लाइन, पाई, एरिया और कई अन्य चार्ट प्रकारों का समर्थन करता है।

**प्रश्न: क्या .NET आउटपुट के लिए अलग लाइसेंस चाहिए?**  
उत्तर: नहीं, वही Java लाइसेंस सभी आउटपुट फ़ॉर्मेट्स, जिसमें .NET PPTX फ़ाइलें शामिल हैं, के लिए काम करता है।

**प्रश्न: चार्ट का कलर पैलेट कैसे बदलें?**  
उत्तर: `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` का उपयोग करें और इच्छित `Color` सेट करें।

**प्रश्न: क्या प्रोग्रामेटिक रूप से डेटा लेबल जोड़ना संभव है?**  
उत्तर: बिल्कुल। `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` कॉल करके मान प्रदर्शित करें।

**प्रश्न: यदि मुझे मौजूदा प्रस्तुति को अपडेट करना हो तो क्या करें?**  
उत्तर: फ़ाइल को `new Presentation("existing.pptx")` से लोड करें, चार्ट संशोधित करें, और फिर सेव करें।

## निष्कर्ष
अब आपके पास एक पूर्ण, एंड‑टू‑एंड गाइड है कि कैसे **add series to chart** किया जाए, **stacked column chart** बनाया जाए, और Aspose.Slides for Java का उपयोग करके .NET प्रस्तुतियों में उसकी उपस्थिति को बारीकी से समायोजित किया जाए। विभिन्न चार्ट प्रकारों, रंगों, और डेटा स्रोतों के साथ प्रयोग करें ताकि आकर्षक दृश्य रिपोर्ट बन सकें जो हितधारकों को प्रभावित करें।

---

**अंतिम अद्यतन:** 2026-01-17  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (jdk16)  
**लेखक:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
