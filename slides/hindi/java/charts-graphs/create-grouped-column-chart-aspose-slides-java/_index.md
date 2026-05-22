---
date: '2026-03-20'
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में क्लस्टर्ड
  कॉलम चार्ट जोड़ना, PowerPoint चार्ट को कस्टमाइज़ करना, और डेटा सीरीज़ चार्ट सम्मिलित
  करना सीखें।
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Aspose.Slides for Java का उपयोग करके PowerPoint में क्लस्टर्ड कॉलम चार्ट कैसे
  जोड़ें
url: /hi/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint में Aspose.Slides for Java का उपयोग करके क्लस्टर्ड कॉलम चार्ट कैसे जोड़ें

## परिचय

जब आपको PowerPoint डेक में **क्लस्टर्ड कॉलम चार्ट** जोड़ने की आवश्यकता होती है, एक स्पष्ट दृश्य कच्चे आंकड़ों को तुरंत समझ में आने वाली कहानी में बदल सकता है। PowerPoint में इसे मैन्युअल रूप से करना समय‑साध्य हो सकता है, विशेषकर जब आपको प्रोग्रामेटिक रूप से कई स्लाइड्स बनानी हों। **Aspose.Slides for Java** इस जटिलता को दूर करता है – यह आपको कुछ ही कोड लाइनों से PowerPoint चार्ट बनाने, कस्टमाइज़ करने और डेटा सीरीज़ चार्ट सम्मिलित करने देता है।

इस ट्यूटोरियल में आप सीखेंगे:
- Aspose.Slides for Java के साथ एक नया PowerPoint प्रस्तुति प्रारंभ करना।
- **स्लाइड में चार्ट जोड़ें** और इसे क्लस्टर्ड कॉलम चार्ट के रूप में कॉन्फ़िगर करें।
- श्रेणियों के लिए ग्रुपिंग लेवल परिभाषित करके **ग्रुप्ड कॉलम चार्ट बनाएं**।
- **डेटा सीरीज़ चार्ट सम्मिलित करें** ताकि आपका डेटा सही ढंग से प्रदर्शित हो।
- पूरा प्रस्तुति को PPTX फ़ाइल के रूप में सहेजें।

कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास सभी आवश्यक चीज़ें हैं।

## त्वरित उत्तर
- **प्राथमिक क्लास कौन सा है?** `Presentation` from `com.aspose.slides`।
- **कौन सा चार्ट प्रकार उपयोग किया जाता है?** `ChartType.ClusteredColumn`।
- **क्या परीक्षण के लिए लाइसेंस चाहिए?** एक फ्री ट्रायल काम करता है, लेकिन लाइसेंस मूल्यांकन सीमाओं को हटाता है।
- **कौन सा Java संस्करण समर्थित है?** JDK 16 या नया (उदाहरण में JDK 16 उपयोग किया गया है)।
- **सैंपल कैसे चलाएँ?** Maven/Gradle डिपेंडेंसी जोड़ें, कंपाइल करें, और `main` मेथड चलाएँ।

## “क्लस्टर्ड कॉलम चार्ट जोड़ना” क्या है?
*क्लस्टर्ड कॉलम चार्ट* (जिसे ग्रुप्ड कॉलम चार्ट भी कहा जाता है) प्रत्येक श्रेणी के लिए कई डेटा सीरीज़ को बगल‑बगल दिखाता है, जिससे समूहों के बीच मानों की तुलना आसान हो जाती है। PowerPoint में यह चार्ट प्रकार त्रैमासिक बिक्री, सर्वे परिणाम, या किसी भी स्थिति के लिए आदर्श है जहाँ आपको एक ही श्रेणी में कई डेटा सेटों की तुलना करनी होती है।

## क्लस्टर्ड कॉलम चार्ट जोड़ने के लिए Aspose.Slides क्यों उपयोग करें?
- **पूर्ण स्वचालन** – मैनुअल प्रयास के बिना दर्जनों स्लाइड्स उत्पन्न करें।
- **सूक्ष्म अनुकूलन** – रंग, लेबल, ग्रुपिंग लेवल और अधिक नियंत्रित करें।
- **क्रॉस‑प्लेटफ़ॉर्म** – किसी भी OS पर काम करता है जो Java को सपोर्ट करता है।
- **ऑफ़िस इंस्टॉलेशन की आवश्यकता नहीं** – सर्वर या CI पाइपलाइन पर PPTX फ़ाइलें जनरेट करें।

## पूर्वापेक्षाएँ
- **Aspose.Slides for Java** लाइब्रेरी (नवीनतम संस्करण की सिफ़ारिश की जाती है)।
- JDK 16 या बाद का संस्करण।
- Maven या Gradle बिल्ड टूल (या आप JAR मैन्युअली जोड़ सकते हैं)।
- Java कोड चलाने के लिए एक IDE या टेक्स्ट एडिटर।

## Aspose.Slides for Java सेटअप करना
अपने प्रोजेक्ट में लाइब्रेरी जोड़ने के लिए नीचे दिए गए बिल्ड स्क्रिप्ट्स में से किसी एक का उपयोग करें।

**Maven**

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

वैकल्पिक रूप से, आप सीधे नवीनतम रिलीज़ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड कर सकते हैं।

### लाइसेंस प्राप्त करना
प्रोडक्शन में डिप्लॉय करने से पहले लाइसेंस प्राप्त करें:
- **फ़्री ट्रायल** – बिना खरीद के सभी फीचर्स का अन्वेषण करें।
- **अस्थायी लाइसेंस** – सीमित अवधि के लिए विस्तारित क्षमताओं का मूल्यांकन करें।
- **पूर्ण लाइसेंस** – असीमित उपयोग अनलॉक करें। इसे [Aspose's purchase page](https://purchase.aspose.com/buy) से प्राप्त करें।

## कार्यान्वयन गाइड
हम प्रत्येक चरण को चलेंगे, साथ ही **चार्ट कैसे जोड़ें** और **PowerPoint चार्ट को कस्टमाइज़ करें** समझाते हुए।

### प्रस्तुति प्रारंभ करें
First, create a new `Presentation` object and grab the default slide.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### स्लाइड में चार्ट जोड़ें
Now we **add chart to slide** using the `ClusteredColumn` type and clear any default data.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### चार्ट डेटा वर्कबुक तैयार करें
The chart stores its data in an internal workbook. We clear it to start fresh.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### ग्रुपिंग लेवल के साथ श्रेणियाँ जोड़ें
Grouping categories creates the **grouped column chart** effect. Each category can belong to a logical group.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### चार्ट में डेटा सीरीज़ जोड़ें
Here we **insert data series chart** entries that will be visualized as separate columns.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### चार्ट के साथ प्रस्तुति सहेजें
Finally, write the PPTX file to disk.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## व्यावहारिक अनुप्रयोग
- **व्यावसायिक रिपोर्ट** – क्षेत्रों के बीच त्रैमासिक राजस्व की तुलना करें।
- **शैक्षणिक अनुसंधान** – परीक्षण स्थितियों के अनुसार समूहित प्रयोगात्मक परिणाम दिखाएँ।
- **प्रोजेक्ट मैनेजमेंट** – एक ही स्लाइड पर कई टीमों की कार्य पूर्णता दर को विज़ुअलाइज़ करें।

## प्रदर्शन संबंधी विचार
- **मेमोरी प्रबंधन** – उपयोग के बाद बड़े वर्कबुक को रिलीज़ करें।
- **बैच ऑपरेशन्स** – चार्ट को कड़े लूप्स में अपडेट करने से बचें; पहले डेटा इकट्ठा करें, फिर लागू करें।
- **इन‑बिल्ट ऑप्टिमाइज़ेशन** – Aspose.Slides बड़े फ़ाइलों के लिए `Presentation.optimize()` जैसे मेथड प्रदान करता है।

## सामान्य समस्याएँ और टिप्स
- **समस्या:** मौजूदा सीरीज़/श्रेणियों को साफ़ करना भूल जाना डुप्लिकेट डेटा का कारण बन सकता है।  
  **टिप:** नई डेटा भरने से पहले हमेशा `clear()` कॉल करें।  
- **समस्या:** गलत सेल एड्रेस उपयोग करना (जैसे `"c2"` की बजाय `"C2"`)।  
  **टिप:** सेल रेफ़रेंसेज़ केस‑इन्सेंसिटिव हैं, लेकिन पठनीयता के लिए उन्हें सुसंगत रखें।  
- **टिप:** अर्थपूर्ण ग्रुप लेबल बनाने के लिए `setGroupingItem` का उपयोग करें; ये चार्ट लेजेंड में स्वचालित रूप से दिखते हैं।

## अक्सर पूछे जाने वाले प्रश्न
**Q1: मैं अपने चार्ट में कई सीरीज़ कैसे जोड़ सकता हूँ?**  
A1: `ch.getChartData().getSeries().add()` को बार‑बार कॉल करें, प्रत्येक सीरीज़ के लिए एक अनूठा नाम और डेटा पॉइंट्स प्रदान करें।

**Q2: Aspose.Slides चार्ट्स के साथ सामान्य समस्याएँ क्या हैं?**  
A2: समस्याएँ अक्सर डेटा रेंज में असंगति या वर्कबुक सेल्स के अभाव से उत्पन्न होती हैं। सुनिश्चित करें कि प्रत्येक श्रेणी और डेटा पॉइंट का संबंधित सेल मौजूद हो।

**Q3: क्या मैं Aspose.Slides को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
A3: हाँ, Aspose .NET, C++, Python आदि के लिए समकक्ष लाइब्रेरी प्रदान करता है।

**Q4: मैं प्रस्तुति में मौजूदा चार्ट को कैसे अपडेट करूँ?**  
A4: प्रस्तुति लोड करें, `slide.getShapes().get_Item(index)` के माध्यम से चार्ट खोजें, फिर आवश्यकतानुसार उसकी सीरीज़ या फ़ॉर्मेटिंग को संशोधित करें।

**Q5: Aspose.Slides में चार्ट प्रकारों पर कोई सीमाएँ हैं क्या?**  
A5: लाइब्रेरी कई प्रकार के चार्ट्स को सपोर्ट करती है, लेकिन हमेशा नवीनतम दस्तावेज़ देखें ताकि किसी नए जोड़े गए या डिप्रिकेटेड प्रकार की जानकारी मिल सके।

## संसाधन
- **दस्तावेज़ीकरण**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **डाउनलोड**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **खरीद**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **फ़्री ट्रायल**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **अस्थायी लाइसेंस**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **सपोर्ट फ़ोरम**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-03-20  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (JDK 16)  
**लेखक:** Aspose