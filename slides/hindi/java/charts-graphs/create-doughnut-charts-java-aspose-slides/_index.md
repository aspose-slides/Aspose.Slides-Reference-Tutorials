---
date: '2026-03-07'
description: Aspose.Slides का उपयोग करके जावा में डोनट चार्ट बनाना सीखें। यह चरण‑दर‑चरण
  गाइड Maven Aspose Slides निर्भरता सेटअप, चार्ट कॉन्फ़िगरेशन और प्रेजेंटेशन को सहेजने
  को कवर करता है।
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Aspose.Slides गाइड के साथ जावा में डोनट चार्ट बनाएं
url: /hi/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides के साथ जावा में डोनट चार्ट बनाना गाइड

## परिचय

प्रोग्रामेटिक रूप से **डोनट चार्ट** बनाना कच्चे आंकड़ों को एक आकर्षक दृश्य में बदल सकता है जो तुरंत कहानी बताता है। जावा में, **Aspose.Slides** इस प्रक्रिया को सरल बनाता है, जिससे आप PowerPoint खोले बिना ही प्रस्तुति‑तैयार चार्ट बना सकते हैं। इस ट्यूटोरियल में आप चरण‑दर‑चरण **डोनट चार्ट जावा** बनाना सीखेंगे— Maven Aspose Slides डिपेंडेंसी सेट करने से लेकर सीरीज़, कैटेगरीज को कस्टमाइज़ करने और अंत में प्रेजेंटेशन सहेजने तक।

इस गाइड के अंत तक आप किसी भी PPTX फ़ाइल में डायनामिक डोनट चार्ट एम्बेड कर पाएँगे, जो रिपोर्ट, डैशबोर्ड या ऑटोमेटेड स्लाइड डेक्स के लिए उपयुक्त है।

### त्वरित उत्तर
- **कौन सी लाइब्रेरी उपयोग की जाती है?** Aspose.Slides for Java  
- **मुख्य कार्य?** PPTX फ़ाइल में डोनट चार्ट जावा बनाना  
- **लाइब्रेरी कैसे जोड़ें?** Maven Aspose Slides डिपेंडेंसी (या Gradle) का उपयोग करें  
- **न्यूनतम जावा संस्करण?** JDK 16 or higher  
- **क्या मैं रंग और लेबल कस्टमाइज़ कर सकता हूँ?** हाँ, API पूर्ण फ़ॉर्मेटिंग नियंत्रण प्रदान करती है।

## डोनट चार्ट क्या है और इसका उपयोग क्यों करें?

डोनट चार्ट पाई चार्ट का एक वैरिएशन है जिसमें मध्य में खाली जगह होती है, जिससे आप कई डेटा सीरीज़ को concentric रिंग्स में दिखा सकते हैं। यह कई श्रेणियों में पूरे के भागों की तुलना करने के लिए आदर्श है—जैसे विभिन्न तिमाहियों में क्षेत्र के अनुसार बिक्री या विभागों में बजट आवंटन।

## जावा के लिए Aspose.Slides क्यों उपयोग करें?

- **ऑफ़िस इंस्टॉलेशन की आवश्यकता नहीं** – किसी भी सर्वर पर PPTX फ़ाइलें जनरेट करें।  
- **समृद्ध API** – चार्ट प्रकार, डेटा पॉइंट्स और स्टाइलिंग पर पूर्ण नियंत्रण।  
- **उच्च प्रदर्शन** – बड़ी प्रेजेंटेशन के लिए अनुकूलित।  
- **क्रॉस‑प्लेटफ़ॉर्म** – Windows, Linux, और macOS पर काम करता है।

## आवश्यकताएँ

- **आवश्यक लाइब्रेरीज़:**  
  - Aspose.Slides for Java version 25.4 or later.  

- **पर्यावरण सेटअप:**  
  - JDK 16 or higher.  
  - आपका पसंदीदा IDE (IntelliJ IDEA, Eclipse, NetBeans, आदि)।  

- **ज्ञान आवश्यकताएँ:**  
  - बुनियादी जावा प्रोग्रामिंग।  
  - डिपेंडेंसी मैनेजमेंट के लिए Maven या Gradle की परिचितता।

## Maven Aspose Slides डिपेंडेंसी

अपने `pom.xml` में निम्नलिखित Maven डिपेंडेंसी जोड़ें। यह **maven aspose slides dependency** है जिसे आपको लाइब्रेरी को प्रोजेक्ट में लाने के लिए चाहिए।

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

यदि आप Gradle पसंद करते हैं, तो नीचे दिया गया समतुल्य स्निपेट उपयोग करें।

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

आप आधिकारिक रिलीज़ पेज से JAR सीधे डाउनलोड भी कर सकते हैं:  
[ Aspose.Slides for Java रिलीज़ ](https://releases.aspose.com/slides/java/)

### लाइसेंस प्राप्त करना

इवैल्यूएशन वॉटरमार्क हटाने और पूरी फीचर सेट अनलॉक करने के लिए:

- **फ़्री ट्रायल** – अस्थायी लाइसेंस के साथ शुरू करें।  
- **अस्थायी लाइसेंस** – एक प्राप्त करने के लिए [Aspose वेबसाइट](https://purchase.aspose.com/temporary-license/) से अनुरोध करें।  
- **वाणिज्यिक लाइसेंस** – उत्पादन उपयोग के लिए खरीदें।

अपने कोड में लाइसेंस लागू करें:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## कार्यान्वयन गाइड

### प्रेजेंटेशन को इनिशियलाइज़ करना और डोनट चार्ट जोड़ना

पहले, एक प्रेजेंटेशन बनाएं या लोड करें और पहले स्लाइड में डोनट चार्ट जोड़ें।

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### चार्ट डेटा वर्कबुक कॉन्फ़िगर करना और मौजूदा डेटा साफ़ करना

अगला, चार्ट के पीछे का वर्कबुक प्राप्त करें और किसी भी डिफ़ॉल्ट सीरीज़ या कैटेगरी को साफ़ करें।

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### चार्ट में सीरीज़ जोड़ना

अब हम अधिकतम 15 सीरीज़ जोड़ेंगे। प्रत्येक सीरीज़ को कस्टमाइज़ किया जा सकता है—यहाँ हम एक्सप्लोजन, डोनट‑होल साइज, और फ़र्स्ट‑स्लाइस एंगल सेट करते हैं।

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### कैटेगरीज और डेटा पॉइंट्स जोड़ना

हम 15 कैटेगरीज बनाएँगे और प्रत्येक सीरीज़ को एक डेटा पॉइंट से भरेंगे। अंतिम सीरीज़ को विशेष लेबल फ़ॉर्मेटिंग मिलेगी।

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### प्रेजेंटेशन सहेजना

अंत में, अपडेटेड प्रेजेंटेशन को डिस्क पर लिखें।

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## सामान्य समस्याएँ और समाधान

- **लाइसेंस नहीं मिला** – जाँचें कि `license.lic` का पथ सही है और फ़ाइल पढ़ी जा सकती है।  
- **चार्ट खाली दिख रहा है** – नए जोड़ने से पहले सुनिश्चित करें कि आपने मौजूदा सीरीज़/कैटेगरीज को साफ़ किया है।  
- **गलत रंग** – `FillType.Solid` दोनों fill और line फ़ॉर्मेट्स के लिए सेट है या नहीं, जाँचें।  
- **कई सीरीज़ के साथ प्रदर्शन** – सीरीज़/कैटेगरीज की संख्या सीमित करें या वर्कबुक सेल्स को पुन: उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं बिना मौजूदा PPTX फ़ाइल के डोनट चार्ट जनरेट कर सकता हूँ?**  
A: हाँ, `new Presentation()` को इंस्टैंसिएट करके एक खाली स्लाइड डेक से शुरू करें।

**Q: क्या Aspose.Slides PDF में एक्सपोर्ट करने का समर्थन करता है?**  
A: बिल्कुल। चार्ट बनाने के बाद, `pres.save("output.pdf", SaveFormat.Pdf);` को कॉल करें।

**Q: डोनट होल साइज कैसे बदलूँ?**  
A: `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` का उपयोग करें जहाँ value 0‑100 है।

**Q: क्या सभी सीरीज़ में डेटा लेबल जोड़ना संभव है, न कि केवल अंतिम में?**  
A: हाँ, `if (i == ...)` शर्त के बाहर लेबल‑फ़ॉर्मेटिंग ब्लॉक को ले जाएँ और प्रत्येक `dataPoint` पर लागू करें।

**Q: कौन से जावा संस्करण समर्थित हैं?**  
A: Aspose.Slides 25.4 JDK 16 और उसके बाद के संस्करणों को सपोर्ट करता है। पुराने JDKs को उचित क्लासिफ़ायर की आवश्यकता होती है।

---

**अंतिम अपडेट:** 2026-03-07  
**परीक्षण किया गया:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}