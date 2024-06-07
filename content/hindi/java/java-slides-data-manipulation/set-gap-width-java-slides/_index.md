---
title: जावा स्लाइड्स में गैप की चौड़ाई सेट करें
linktitle: जावा स्लाइड्स में गैप की चौड़ाई सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ Java स्लाइड में गैप की चौड़ाई सेट करना सीखें। अपने PowerPoint प्रेजेंटेशन के लिए चार्ट विज़ुअल को बेहतर बनाएँ।
type: docs
weight: 21
url: /hi/java/data-manipulation/set-gap-width-java-slides/
---

## Aspose.Slides for Java में गैप की चौड़ाई निर्धारित करने का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में चार्ट के लिए गैप चौड़ाई सेट करने की प्रक्रिया के बारे में बताएंगे। गैप चौड़ाई चार्ट में कॉलम या बार के बीच की दूरी निर्धारित करती है, जिससे आप चार्ट के दृश्य स्वरूप को नियंत्रित कर सकते हैं।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी इंस्टॉल है। आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण-दर-चरण मार्गदर्शिका

Aspose.Slides for Java का उपयोग करके चार्ट में गैप चौड़ाई सेट करने के लिए इन चरणों का पालन करें:

### 1. एक खाली प्रेजेंटेशन बनाएं

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// रिक्त प्रस्तुति बनाना
Presentation presentation = new Presentation();
```

### 2. पहली स्लाइड तक पहुंचें

```java
// पहली स्लाइड पर पहुँचें
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. डिफ़ॉल्ट डेटा के साथ एक चार्ट जोड़ें

```java
// डिफ़ॉल्ट डेटा वाला चार्ट जोड़ें
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. चार्ट डेटा शीट का इंडेक्स सेट करें

```java
// चार्ट डेटा शीट का इंडेक्स सेट करना
int defaultWorksheetIndex = 0;
```

### 5. चार्ट डेटा वर्कबुक प्राप्त करें

```java
// चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. चार्ट में श्रृंखला जोड़ें

```java
// चार्ट में श्रृंखला जोड़ें
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. चार्ट में श्रेणियाँ जोड़ें

```java
// चार्ट में श्रेणियाँ जोड़ें
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. श्रृंखला डेटा भरें

```java
// श्रृंखला डेटा भरें
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// श्रृंखला डेटा बिंदुओं को भरना
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. गैप की चौड़ाई निर्धारित करें

```java
// गैप चौड़ाई मान सेट करें
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. प्रेजेंटेशन सेव करें

```java
// चार्ट के साथ प्रस्तुति सहेजें
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में सेट गैप चौड़ाई के लिए पूरा स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// खाली प्रस्तुति बनाना
Presentation presentation = new Presentation();
// पहली स्लाइड तक पहुंचें
ISlide slide = presentation.getSlides().get_Item(0);
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
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
// दूसरा चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//अब श्रृंखला डेटा भरा जा रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// GapWidth मान सेट करें
series.getParentSeriesGroup().setGapWidth(50);
// चार्ट के साथ प्रस्तुति सहेजें
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में चार्ट के लिए गैप की चौड़ाई कैसे सेट करें। गैप की चौड़ाई को समायोजित करने से आप अपने चार्ट में कॉलम या बार के बीच की दूरी को नियंत्रित कर सकते हैं, जिससे आपके डेटा का दृश्य प्रतिनिधित्व बेहतर हो जाता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं गैप चौड़ाई मान कैसे बदलूं?

 गैप की चौड़ाई बदलने के लिए, का उपयोग करें`setGapWidth` विधि पर`ParentSeriesGroup`चार्ट श्रृंखला का। दिए गए उदाहरण में, हमने गैप चौड़ाई को 50 पर सेट किया है, लेकिन आप इस मान को अपनी इच्छित रिक्ति के अनुसार समायोजित कर सकते हैं।

### क्या मैं अन्य चार्ट गुणधर्मों को अनुकूलित कर सकता हूँ?

हां, Aspose.Slides for Java चार्ट अनुकूलन के लिए व्यापक क्षमताएं प्रदान करता है। आप विभिन्न चार्ट गुणों, जैसे रंग, लेबल, शीर्षक, और बहुत कुछ को संशोधित कर सकते हैं। चार्ट अनुकूलन विकल्पों पर विस्तृत जानकारी के लिए API संदर्भ देखें।

### मैं अधिक संसाधन और दस्तावेज कहां पा सकता हूं?

 आप Aspose.Slides for Java पर व्यापक दस्तावेज़ीकरण और अतिरिक्त संसाधन पा सकते हैं[Aspose वेबसाइट](https://reference.aspose.com/slides/java/).