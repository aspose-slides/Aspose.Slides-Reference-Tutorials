---
"date": "2025-04-17"
"description": "Aspose.Slides for Java का उपयोग करके गतिशील स्कैटर चार्ट बनाना सीखें। अनुकूलन योग्य चार्ट सुविधाओं के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।"
"title": "Aspose.Slides के साथ जावा में स्कैटर चार्ट बनाएं और अनुकूलित करें"
"url": "/hi/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides के साथ जावा में स्कैटर चार्ट बनाएं और अनुकूलित करें

Aspose.Slides के साथ Java का उपयोग करके गतिशील स्कैटर चार्ट जोड़कर अपनी प्रस्तुतियों को बेहतर बनाएँ। यह व्यापक ट्यूटोरियल आपको निर्देशिकाएँ सेट करने, प्रस्तुतियाँ आरंभ करने, स्कैटर चार्ट बनाने, चार्ट डेटा प्रबंधित करने, श्रृंखला प्रकारों और मार्करों को अनुकूलित करने और अपने काम को सहेजने के बारे में मार्गदर्शन करेगा - सभी आसानी से।

**आप क्या सीखेंगे:**
- प्रस्तुति फ़ाइलों को संग्रहीत करने के लिए निर्देशिका सेट करना
- Aspose.Slides का उपयोग करके प्रस्तुतियों को आरंभ करना और उनमें परिवर्तन करना
- स्लाइड पर स्कैटर चार्ट बनाना
- चार्ट श्रृंखला में डेटा को प्रबंधित करना और जोड़ना
- चार्ट श्रृंखला प्रकार और मार्करों को अनुकूलित करना
- संशोधनों के साथ अपनी प्रस्तुति को सहेजना

आइये सबसे पहले यह सुनिश्चित करें कि आपके पास आवश्यक पूर्वापेक्षाएँ हैं।

## आवश्यक शर्तें

इस ट्यूटोरियल का अनुसरण करने के लिए, सुनिश्चित करें कि आपके पास ये हैं:
- **जावा के लिए Aspose.Slides**: संस्करण 25.4 या बाद का संस्करण आवश्यक है.
- **जावा डेवलपमेंट किट (JDK)**: JDK 8 या उच्चतर की आवश्यकता है.
- जावा प्रोग्रामिंग का बुनियादी ज्ञान और मावेन या ग्रेडल बिल्ड टूल्स से परिचित होना।

## Java के लिए Aspose.Slides सेट अप करना

कोडिंग शुरू करने से पहले, निम्नलिखित विधियों में से किसी एक का उपयोग करके Aspose.Slides को अपने प्रोजेक्ट में एकीकृत करें:

### मावेन
इस निर्भरता को अपने में शामिल करें `pom.xml` फ़ाइल:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ग्रैडल
इस पंक्ति को अपने में जोड़ें `build.gradle` फ़ाइल:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

वैकल्पिक रूप से, Java के लिए नवीनतम Aspose.Slides को यहां से डाउनलोड करें [एस्पोज रिलीज](https://releases.aspose.com/slides/java/).

#### लाइसेंस अधिग्रहण
- **मुफ्त परीक्षण**: सुविधाओं का पता लगाने के लिए 30-दिन के निःशुल्क परीक्षण से शुरुआत करें।
- **अस्थायी लाइसेंस**विस्तारित परीक्षण के लिए अस्थायी लाइसेंस प्राप्त करें।
- **खरीदना**पूर्ण पहुंच और समर्थन के लिए लाइसेंस खरीदें।

अब, नीचे दिखाए अनुसार आवश्यक आयातों को जोड़कर अपने जावा अनुप्रयोग में Aspose.Slides को आरंभ करें।

## कार्यान्वयन मार्गदर्शिका

### निर्देशिका सेटअप
सबसे पहले, सुनिश्चित करें कि हमारी निर्देशिका प्रेजेंटेशन फ़ाइलों को संग्रहीत करने के लिए मौजूद है। यह कदम फ़ाइल सहेजने के दौरान त्रुटियों को रोकता है।

#### यदि निर्देशिका मौजूद नहीं है तो उसे बनाएँ
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // निर्देशिका बनाएं
    new File(dataDir).mkdirs();
}
```
यह स्निपेट निर्दिष्ट निर्देशिका की जांच करता है और यदि वह मौजूद नहीं है तो उसे बनाता है। `File.exists()` उपस्थिति सत्यापित करने के लिए और `File.mkdirs()` निर्देशिकाएँ बनाने के लिए.

### प्रस्तुति आरंभीकरण

इसके बाद, अपने प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें जहां आप स्कैटर चार्ट जोड़ेंगे।

#### अपनी प्रस्तुति आरंभ करें
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
यहाँ, `new Presentation()` एक खाली प्रस्तुति बनाता है। हम इसके साथ सीधे काम करने के लिए पहली स्लाइड तक पहुंचते हैं।

### चार्ट निर्माण
अगला चरण हमारी आरंभीकृत स्लाइड पर स्कैटर चार्ट बनाना है।

#### स्लाइड में स्कैटर चार्ट जोड़ें
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
यह कोड स्निपेट पहली स्लाइड में चिकनी रेखाओं वाला एक स्कैटर चार्ट जोड़ता है। पैरामीटर चार्ट की स्थिति और आकार को परिभाषित करते हैं।

### चार्ट डेटा प्रबंधन
अब आइए किसी भी मौजूदा श्रृंखला को हटाकर और नई श्रृंखला जोड़कर अपने चार्ट डेटा का प्रबंधन करें।

#### चार्ट श्रृंखला प्रबंधित करें
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// चार्ट में नई श्रृंखला जोड़ना
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
यह अनुभाग मौजूदा डेटा को साफ़ करता है और हमारे स्कैटर चार्ट में दो नई श्रृंखलाएँ जोड़ता है।

### स्कैटर श्रृंखला के लिए डेटा बिंदु जोड़ना
अपने डेटा को दृश्यमान बनाने के लिए, हम स्कैटर चार्ट में प्रत्येक श्रृंखला में बिंदु जोड़ते हैं।

#### डेटा पॉइंट जोड़ें
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
हम उपयोग करते हैं `addDataPointForScatterSeries()` हमारी पहली श्रृंखला में डेटा बिंदु जोड़ने के लिए। पैरामीटर X और Y मान परिभाषित करते हैं।

### श्रृंखला प्रकार और मार्कर संशोधन
प्रत्येक श्रृंखला में मार्करों के प्रकार और शैली को बदलकर अपने चार्ट के स्वरूप को अनुकूलित करें।

#### श्रृंखला अनुकूलित करें
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// दूसरी श्रृंखला को संशोधित करना
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
ये परिवर्तन श्रृंखला प्रकार को सीधी रेखाओं और मार्करों का उपयोग करने के लिए समायोजित करते हैं। हम दृश्य भेद के लिए मार्कर का आकार और प्रतीक भी निर्धारित करते हैं।

### प्रस्तुति सहेजना
अंत में, अपने प्रस्तुतीकरण को सभी संशोधनों के साथ सुरक्षित कर लें।

#### अपनी प्रस्तुति सहेजें
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
उपयोग `SaveFormat.Pptx` अपनी फ़ाइल को सहेजने के लिए PowerPoint फ़ॉर्मेट निर्दिष्ट करने के लिए यह चरण सभी परिवर्तनों को संरक्षित करने के लिए महत्वपूर्ण है।

## व्यावहारिक अनुप्रयोगों
यहां कुछ वास्तविक दुनिया के उपयोग के मामले दिए गए हैं:
1. **वित्तीय विश्लेषण**: समय के साथ स्टॉक रुझान प्रदर्शित करने के लिए स्कैटर चार्ट का उपयोग करें।
2. **वैज्ञानिक अनुसंधान**विश्लेषण के लिए प्रयोगात्मक डेटा बिंदुओं का प्रतिनिधित्व करें।
3. **परियोजना प्रबंधन**संसाधन आवंटन और प्रगति मेट्रिक्स को विज़ुअलाइज़ करें।

अपने सिस्टम में Aspose.Slides को एकीकृत करने से आप रिपोर्ट निर्माण को स्वचालित कर सकते हैं, जिससे उत्पादकता और सटीकता बढ़ जाती है।

## प्रदर्शन संबंधी विचार
इष्टतम प्रदर्शन के लिए:
- प्रस्तुतियों को सहेजने के बाद उनका निपटान करके मेमोरी उपयोग का प्रबंधन करें।
- बड़े डेटासेट के लिए कुशल डेटा संरचनाओं का उपयोग करें।
- लूप के भीतर संसाधन-गहन परिचालनों को न्यूनतम करें।

सर्वोत्तम अभ्यास जटिल चार्ट हेरफेर के साथ भी सुचारू निष्पादन सुनिश्चित करते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, आपने निर्देशिकाएँ सेट करना, Aspose.Slides प्रस्तुतियाँ आरंभ करना, स्कैटर चार्ट बनाना और उन्हें कस्टमाइज़ करना, श्रृंखला डेटा प्रबंधित करना, मार्कर संशोधित करना और अपना काम सहेजना सीखा है। Aspose.Slides क्षमताओं को और अधिक जानने के लिए, एनिमेशन और स्लाइड ट्रांज़िशन जैसी अधिक उन्नत सुविधाओं पर विचार करें।

**अगले कदम**: विभिन्न चार्ट प्रकारों के साथ प्रयोग करें या इन तकनीकों को एक बड़े जावा प्रोजेक्ट में एकीकृत करें।

## सामान्य प्रश्न

### मैं मार्करों का रंग कैसे बदल सकता हूँ?
मार्कर का रंग बदलने के लिए, उपयोग करें `series.getMarker().getFillFormat().setFillColor(ColorObject)`, कहाँ `ColorObject` आपका इच्छित रंग है.

### क्या मैं स्कैटर चार्ट में दो से अधिक श्रृंखलाएं जोड़ सकता हूं?
हां, आप नई श्रृंखला और डेटा बिंदु जोड़ने की प्रक्रिया को दोहराकर आवश्यकतानुसार जितनी भी श्रृंखलाएं जोड़ सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}