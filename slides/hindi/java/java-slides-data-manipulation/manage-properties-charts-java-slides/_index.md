---
title: जावा स्लाइड्स में गुण चार्ट प्रबंधित करें
linktitle: जावा स्लाइड्स में गुण चार्ट प्रबंधित करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ जावा स्लाइड में शानदार चार्ट बनाना और प्रॉपर्टीज़ को मैनेज करना सीखें। शक्तिशाली प्रस्तुतियों के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 13
url: /hi/java/data-manipulation/manage-properties-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में गुण चार्ट प्रबंधित करें


## Aspose.Slides का उपयोग करके जावा स्लाइड्स में गुण और चार्ट प्रबंधित करने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके जावा स्लाइड में प्रॉपर्टीज़ को प्रबंधित करने और चार्ट बनाने का तरीका जानेंगे। Aspose.Slides पावरपॉइंट प्रेजेंटेशन के साथ काम करने के लिए एक शक्तिशाली जावा API है। हम सोर्स कोड उदाहरणों सहित चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास जावा के लिए Aspose.Slides लाइब्रेरी स्थापित है और आपके प्रोजेक्ट में सेट अप है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## स्लाइड में चार्ट जोड़ना

किसी स्लाइड में चार्ट जोड़ने के लिए, इन चरणों का पालन करें:

1. आवश्यक क्लासेस को आयात करें और प्रेजेंटेशन क्लास का एक उदाहरण बनाएं।

```java
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
```

2. उस स्लाइड तक पहुँचें जहाँ आप चार्ट जोड़ना चाहते हैं। इस उदाहरण में, हम पहली स्लाइड तक पहुँचते हैं।

```java
// पहली स्लाइड तक पहुंचें
ISlide slide = presentation.getSlides().get_Item(0);
```

3. डिफ़ॉल्ट डेटा वाला चार्ट जोड़ें। इस मामले में, हम StackedColumn3D चार्ट जोड़ रहे हैं।

```java
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## चार्ट डेटा सेट करना

चार्ट डेटा सेट करने के लिए, हमें एक चार्ट डेटा वर्कबुक बनाने और श्रृंखला और श्रेणियाँ जोड़ने की आवश्यकता है। इन चरणों का पालन करें:

4. चार्ट डेटा शीट का सूचकांक सेट करें.

```java
// चार्ट डेटा शीट का इंडेक्स सेट करना
int defaultWorksheetIndex = 0;
```

5. चार्ट डेटा कार्यपुस्तिका प्राप्त करें.

```java
// चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. चार्ट में श्रृंखला जोड़ें। इस उदाहरण में, हम "श्रृंखला 1" और "श्रृंखला 2" नामक दो श्रृंखलाएँ जोड़ते हैं।

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. चार्ट में श्रेणियाँ जोड़ें: यहाँ, हम तीन श्रेणियाँ जोड़ते हैं।

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3D रोटेशन गुण सेट करना

अब, चार्ट के लिए 3D रोटेशन गुण सेट करें:

8. समकोण अक्ष सेट करें.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. X और Y अक्षों के लिए घूर्णन कोण सेट करें। इस उदाहरण में, हम X को 40 डिग्री और Y को 270 डिग्री घुमाते हैं।

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. गहराई प्रतिशत 150 पर सेट करें.

```java
chart.getRotation3D().setDepthPercents(150);
```

## श्रृंखला डेटा भरना

11. दूसरी चार्ट श्रृंखला लें और उसमें डेटा बिंदु भरें।

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// श्रृंखला डेटा भरें
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## ओवरलैप समायोजित करना

12. श्रृंखला के लिए ओवरलैप मान सेट करें। उदाहरण के लिए, आप इसे बिना ओवरलैप के लिए 100 पर सेट कर सकते हैं।

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## प्रस्तुति को सहेजना

अंत में, प्रस्तुति को डिस्क पर सहेजें।

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

बस! आपने Java में Aspose.Slides का उपयोग करके कस्टम गुणों के साथ एक 3D स्टैक्ड कॉलम चार्ट सफलतापूर्वक बना लिया है।

## जावा स्लाइड्स में गुण चार्ट प्रबंधित करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
// पहली स्लाइड तक पहुंचें
ISlide slide = presentation.getSlides().get_Item(0);
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// चार्ट डेटा शीट का इंडेक्स सेट करना
int defaultWorksheetIndex = 0;
// चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// श्रृंखला जोड़ें
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// श्रेणियाँ जोड़ें
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Rotation3D गुण सेट करें
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// दूसरा चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// अब श्रृंखला डेटा भरा जा रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// ओवरलैप मान सेट करें
series.getParentSeriesGroup().setOverlap((byte) 100);
// प्रस्तुति को डिस्क पर लिखें
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Slides का उपयोग करके जावा स्लाइड में प्रॉपर्टीज़ को प्रबंधित करने और चार्ट बनाने की दुनिया में गहराई से जाना। Aspose.Slides एक मजबूत जावा API है जो डेवलपर्स को पावरपॉइंट प्रेजेंटेशन के साथ कुशलतापूर्वक काम करने में सक्षम बनाता है। हमने आवश्यक चरणों को कवर किया और प्रक्रिया के माध्यम से आपका मार्गदर्शन करने के लिए स्रोत कोड उदाहरण प्रदान किए।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट का प्रकार कैसे बदल सकता हूँ?

 आप चार्ट प्रकार को संशोधित करके बदल सकते हैं`ChartType` चार्ट जोड़ते समय पैरामीटर। उपलब्ध चार्ट प्रकारों के लिए Aspose.Slides दस्तावेज़ देखें।

### क्या मैं चार्ट के रंगों को अनुकूलित कर सकता हूँ?

हां, आप श्रृंखला डेटा बिंदुओं या श्रेणियों के भरण गुण सेट करके चार्ट रंगों को अनुकूलित कर सकते हैं।

### मैं किसी श्रृंखला में अधिक डेटा बिंदु कैसे जोड़ूं?

 आप किसी श्रृंखला में अधिक डेटा बिंदु जोड़ सकते हैं`series.getDataPoints().addDataPointForBarSeries()` विधि और डेटा मान युक्त सेल को निर्दिष्ट करना।

### मैं अलग घूर्णन कोण कैसे निर्धारित कर सकता हूं?

 X और Y अक्षों के लिए अलग-अलग घूर्णन कोण सेट करने के लिए, उपयोग करें`chart.getRotation3D().setRotationX()` और`chart.getRotation3D().setRotationY()` वांछित कोण मानों के साथ।

### मैं अन्य कौन से 3D गुण अनुकूलित कर सकता हूँ?

आप Aspose.Slides दस्तावेज़न का संदर्भ लेकर चार्ट के अन्य 3D गुणों, जैसे गहराई, परिप्रेक्ष्य और प्रकाश व्यवस्था का पता लगा सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
