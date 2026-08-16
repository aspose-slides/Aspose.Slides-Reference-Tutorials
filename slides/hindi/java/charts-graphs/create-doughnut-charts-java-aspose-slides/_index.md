---
date: '2026-08-16'
description: Aspose.Slides का उपयोग करके Java में doughnut charts कैसे जोड़ें सीखें।
  यह चरण‑दर‑चरण गाइड Maven डिपेंडेंसी सेटअप, chart कॉन्फ़िगरेशन, रंग, लेबल और PPTX
  को सहेजने को कवर करता है।
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Java में Aspose.Slides का उपयोग करके doughnut charts कैसे जोड़ें।
  Maven सेटअप करने, रंग, लेबल को कस्टमाइज़ करने और PPTX फ़ाइलें जेनरेट करने के लिए
  इस गाइड का पालन करें।
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Java में Aspose.Slides के साथ doughnut chart कैसे जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Java में Aspose.Slides के साथ doughnut chart कैसे जोड़ें
url: /hi/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java में Aspose.Slides के साथ डोनट चार्ट कैसे जोड़ें

## परिचय

प्रोग्रामेटिक रूप से **डोनट चार्ट** बनाना कच्चे आंकड़ों को एक आकर्षक दृश्य में बदल सकता है जो तुरंत कहानी बताता है। Java में, **Aspose.Slides** इस प्रक्रिया को सरल बनाता है, जिससे आप PowerPoint खोले बिना प्रस्तुति‑तैयार चार्ट बना सकते हैं। इस ट्यूटोरियल में आप चरण‑दर‑चरण सीखेंगे कि **डोनट जोड़ने का तरीका** चार्ट को PPTX फ़ाइल में कैसे जोड़ें— Maven Aspose Slides निर्भरता सेटअप करने से लेकर श्रृंखला, श्रेणियाँ, रंग और लेबल को अनुकूलित करने तक, और अंत में प्रस्तुति को सहेजना।

इस गाइड के अंत तक आप किसी भी PPTX फ़ाइल में गतिशील डोनट चार्ट एम्बेड कर सकेंगे, जो रिपोर्ट, डैशबोर्ड या स्वचालित स्लाइड डेक्स के लिए उपयुक्त हैं।

### त्वरित उत्तर
- **कौन सी लाइब्रेरी उपयोग की जाती है?** Aspose.Slides for Java  
- **मुख्य कार्य?** Add a doughnut chart in a PPTX file  
- **लाइब्रेरी कैसे जोड़ें?** Use the Maven Aspose Slides dependency (or Gradle)  
- **न्यूनतम Java संस्करण?** JDK 16 or higher  
- **क्या मैं रंग और लेबल कस्टमाइज़ कर सकता हूँ?** Yes, the API provides full formatting control  

## डोनट चार्ट क्या है और इसे क्यों उपयोग करें?

डोनट चार्ट पाई चार्ट का एक रूपांतर है जिसमें केंद्र खाली रहता है, जिससे कई डेटा श्रृंखलाएँ समानांतर रिंग्स के रूप में प्रदर्शित की जा सकती हैं।  
**यह कई श्रेणियों में भाग‑से‑सम्पूर्ण को दर्शाता है जबकि केंद्र में अतिरिक्त जानकारी के लिए स्थान सुरक्षित रखता है।**  
यह कई तिमाहियों में क्षेत्र के अनुसार बिक्री की तुलना, विभागों के बीच बजट आवंटन, या किसी भी स्थिति में पदानुक्रमित अनुपात डेटा दिखाने के लिए आदर्श बनाता है।

## Java के लिए Aspose.Slides क्यों उपयोग करें?

आप Microsoft Office स्थापित किए बिना डोनट चार्ट जोड़ सकते हैं, और लाइब्रेरी **50 + से अधिक इनपुट और आउटपुट फ़ॉर्मेट** को प्रोसेस करती है जबकि 500 से अधिक स्लाइड वाली प्रस्तुतियों को संभालती है।  
Aspose.Slides समान हार्डवेयर पर मूल Office ऑटोमेशन की तुलना में **3× तक तेज़ रेंडरिंग** प्रदान करता है, और यह Windows, Linux और macOS पर काम करता है।  
इन मापनीय लाभों का मतलब है कि आप हेडलेस सर्वरों पर पूर्वानुमानित प्रदर्शन के साथ बड़े स्लाइड डेक बना सकते हैं।

## पूर्वापेक्षाएँ

- **आवश्यक लाइब्रेरीज़**  
  - Aspose.Slides for Java 25.4 or later (the library that enables you to add doughnut charts).  

- **पर्यावरण**  
  - JDK 16 or higher installed on your machine.  
  - An IDE such as IntelliJ IDEA, Eclipse or NetBeans.  

- **ज्ञान**  
  - Basic Java syntax and object‑oriented concepts.  
  - Familiarity with Maven or Gradle for dependency management.  

## Maven Aspose Slides निर्भरता

अपने `pom.xml` में निम्नलिखित Maven निर्भरता जोड़ें। यह वह **maven aspose slides dependency** है जिसे आपको लाइब्रेरी को अपने प्रोजेक्ट में लाने के लिए चाहिए।

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

यदि आप Gradle पसंद करते हैं, तो नीचे दिया गया समकक्ष स्निपेट उपयोग करें।

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

आप आधिकारिक रिलीज पेज से JAR को सीधे डाउनलोड भी कर सकते हैं:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### लाइसेंस प्राप्त करना

मूल्यांकन वॉटरमार्क हटाने और पूरी फीचर सेट को अनलॉक करने के लिए:

- **फ़्री ट्रायल** – एक अस्थायी लाइसेंस के साथ शुरू करें।  
- **अस्थायी लाइसेंस** – [Aspose वेबसाइट](https://purchase.aspose.com/temporary-license/) से अनुरोध करें।  
- **व्यावसायिक लाइसेंस** – उत्पादन उपयोग के लिए खरीदें।

अपने कोड में लाइसेंस लागू करें:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## कार्यान्वयन गाइड

### प्रेजेंटेशन को इनिशियलाइज़ करना और डोनट चार्ट जोड़ना

Presentation Aspose.Slides क्लास है जो PowerPoint प्रस्तुति को दर्शाता है।  
एक मौजूदा PPTX लोड करें या नया `Presentation` ऑब्जेक्ट बनाएं, फिर पहले स्लाइड में डोनट चार्ट जोड़ें।

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### चार्ट डेटा वर्कबुक को कॉन्फ़िगर करना और मौजूदा डेटा साफ़ करना

वर्कबुक एक आंतरिक स्प्रेडशीट है जो चार्ट का डेटा संग्रहीत करता है।  
चार्ट को सपोर्ट करने वाला वर्कबुक प्राप्त करें, फिर किसी भी डिफ़ॉल्ट श्रृंखला या श्रेणियों को साफ़ करें ताकि आप एक साफ़ स्लेट से शुरू कर सकें।

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### चार्ट में श्रृंखला जोड़ना

एक श्रृंखला डेटा पॉइंट्स का संग्रह दर्शाती है जो चार्ट पर प्लॉट होते हैं।  
आप अधिकतम 15 श्रृंखलाएँ जोड़ सकते हैं। प्रत्येक श्रृंखला को कस्टमाइज़ किया जा सकता है—यहाँ हम एक्सप्लोजन, डोनट‑होल आकार, और पहला‑स्लाइस एंगल सेट करते हैं।

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### श्रेणियाँ और डेटा पॉइंट्स जोड़ना

श्रेणियाँ चार्ट की धुरी के साथ प्रत्येक डेटा पॉइंट के लेबल होते हैं।  
15 श्रेणियाँ बनाएं और प्रत्येक श्रृंखला को एक डेटा पॉइंट से भरें। अंतिम श्रृंखला को विशेष लेबल फॉर्मेटिंग मिलती है।

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### रंग और डेटा लेबल्स को कस्टमाइज़ करना

`FillType.Solid` चार्ट तत्वों के लिए सॉलिड फ़िल रंग निर्दिष्ट करता है।  
प्रत्येक श्रृंखला के लिए सॉलिड फ़िल रंग सेट करें और डेटा लेबल्स सक्षम करें। अंतिम श्रृंखला के लिए हम लेबल फ़ॉन्ट रंग भी बदलते हैं।

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### प्रेजेंटेशन को सहेजना

`save` चयनित फ़ॉर्मेट में प्रेजेंटेशन को फ़ाइल में लिखता है।  
अपडेटेड प्रेजेंटेशन को डिस्क पर PPTX फ़ॉर्मेट में लिखें, या आवश्यकता होने पर PDF में निर्यात करें।

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## सामान्य समस्याएँ और समाधान

- **लाइसेंस नहीं मिला** – `license.lic` का पथ सही है और फ़ाइल पढ़ी जा सकती है, यह सत्यापित करें।  
- **चार्ट खाली दिख रहा है** – नई श्रृंखला/श्रेणियाँ जोड़ने से पहले मौजूदा को साफ़ किया है, यह सुनिश्चित करें।  
- **गलत रंग** – सुनिश्चित करें कि `FillType.Solid` दोनों फ़िल और लाइन फ़ॉर्मेट्स के लिए सेट है।  
- **कई श्रृंखलाओं के साथ प्रदर्शन** – श्रृंखला/श्रेणियों की संख्या सीमित करें या मेमोरी उपयोग को नियंत्रित रखने के लिए वर्कबुक सेल्स को पुन: उपयोग करें।  

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं प्री‑एक्ज़िस्टिंग PPTX फ़ाइल के बिना डोनट चार्ट जनरेट कर सकता हूँ?**  
**A:** हाँ, `new Presentation()` इंस्टैंसिएट करके एक खाली स्लाइड डेक से शुरू करें, फिर ऊपर दिखाए अनुसार चार्ट जोड़ें।

**Q: क्या Aspose.Slides PDF में एक्सपोर्ट करने का समर्थन करता है?**  
**A:** बिल्कुल। चार्ट बनाने के बाद, `pres.save("output.pdf", SaveFormat.Pdf);` कॉल करके स्लाइड का PDF संस्करण प्राप्त करें।

**Q: मैं डोनट होल का आकार कैसे बदलूँ?**  
**A:** `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` उपयोग करें जहाँ `value` 0 से 100 के बीच होता है।

**Q: क्या सभी श्रृंखलाओं में डेटा लेबल जोड़ना संभव है, केवल अंतिम में नहीं?**  
**A:** हाँ, लेबल‑फ़ॉर्मेटिंग ब्लॉक को `if (i == ...)` शर्त के बाहर ले जाएँ और प्रत्येक `dataPoint` पर लागू करें।

**Q: Java के कौन से संस्करण समर्थित हैं?**  
**A:** Aspose.Slides 25.4 JDK 16 और उसके बाद के संस्करणों को समर्थन देता है। पुराने JDK के लिए Maven निर्भरता में उपयुक्त क्लासिफ़ायर आवश्यक है।

**अंतिम अपडेट:** 2026-08-16  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**लेखक:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```
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
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## संबंधित ट्यूटोरियल

- [Aspose.Slides for Java का उपयोग करके PowerPoint में चार्ट कैसे जोड़ें: चरण‑दर‑चरण गाइड](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides के साथ Java में पाई चार्ट रंग कैसे कस्टमाइज़ करें – पूर्ण गाइड](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Aspose.Slides for Java के साथ PowerPoint चार्ट श्रेणियों को एनीमेट करें | चरण‑दर‑चरण गाइड](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}