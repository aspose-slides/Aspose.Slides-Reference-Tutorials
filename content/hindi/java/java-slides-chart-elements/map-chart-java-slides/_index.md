---
title: जावा स्लाइड्स में मानचित्र चार्ट
linktitle: जावा स्लाइड्स में मानचित्र चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides के साथ PowerPoint प्रेजेंटेशन में आश्चर्यजनक मानचित्र चार्ट बनाएं। जावा डेवलपर्स के लिए चरण-दर-चरण मार्गदर्शिका और स्रोत कोड।
type: docs
weight: 15
url: /hi/java/chart-elements/map-chart-java-slides/
---

## जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में मैप चार्ट का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में मैप चार्ट बनाने की प्रक्रिया में आपका मार्गदर्शन करेंगे। मानचित्र चार्ट आपकी प्रस्तुतियों में भौगोलिक डेटा को देखने का एक शानदार तरीका है।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी एकीकृत है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: अपना प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपने अपना जावा प्रोजेक्ट सेट अप कर लिया है और अपने प्रोजेक्ट के क्लासपाथ में जावा लाइब्रेरी के लिए Aspose.Slides जोड़ लिया है।

## चरण 2: एक पावरपॉइंट प्रेजेंटेशन बनाएं

सबसे पहले, आइए एक नया पावरपॉइंट प्रेजेंटेशन बनाएं।

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## चरण 3: एक मानचित्र चार्ट जोड़ें

अब, हम प्रस्तुतिकरण में एक मानचित्र चार्ट जोड़ेंगे।

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## चरण 4: मानचित्र चार्ट में डेटा जोड़ें

आइए मानचित्र चार्ट में कुछ डेटा जोड़ें। हम एक शृंखला बनाएंगे और उसमें डेटा बिंदु जोड़ेंगे।

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## चरण 5: श्रेणियाँ जोड़ें

हमें मानचित्र चार्ट में विभिन्न भौगोलिक क्षेत्रों का प्रतिनिधित्व करने वाली श्रेणियां जोड़ने की आवश्यकता है।

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## चरण 6: डेटा बिंदुओं को अनुकूलित करें

आप अलग-अलग डेटा बिंदुओं को कस्टमाइज़ कर सकते हैं. इस उदाहरण में, हम एक विशिष्ट डेटा बिंदु का रंग और मान बदलते हैं।

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## चरण 7: प्रस्तुति सहेजें

अंत में, प्रस्तुतिकरण को मानचित्र चार्ट के साथ सहेजें।

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

इतना ही! आपने Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुति में एक मानचित्र चार्ट बनाया है। आप अपनी प्रस्तुतियों को बेहतर बनाने के लिए चार्ट को और अधिक अनुकूलित कर सकते हैं और Aspose.Slides द्वारा दी गई अन्य सुविधाओं का पता लगा सकते हैं।

## जावा स्लाइड में मानचित्र चार्ट के लिए संपूर्ण स्रोत कोड

```java
String resultPath = RunExamples.getOutPath() +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//खाली चार्ट बनाएं
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//श्रृंखला और कुछ डेटा बिंदु जोड़ें
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//श्रेणियां जोड़ें
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//डेटा बिंदु मान बदलें
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//डेटा बिंदु उपस्थिति सेट करें
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में मैप चार्ट बनाने की प्रक्रिया के बारे में जाना है। मानचित्र चार्ट भौगोलिक डेटा को विज़ुअलाइज़ करने का एक प्रभावी तरीका है, जो आपकी प्रस्तुतियों को अधिक आकर्षक और जानकारीपूर्ण बनाता है। आइए प्रमुख चरणों का सारांश प्रस्तुत करें:

## अक्सर पूछे जाने वाले प्रश्न

### मैं मानचित्र चार्ट प्रकार कैसे बदल सकता हूँ?

 आप चार्ट प्रकार को प्रतिस्थापित करके बदल सकते हैं`ChartType.Map` चरण 3 में चार्ट बनाते समय वांछित चार्ट प्रकार के साथ।

### मैं मानचित्र चार्ट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

 आप चार्ट के गुणों को संशोधित करके उसके स्वरूप को अनुकूलित कर सकते हैं`dataPoint` चरण 6 में ऑब्जेक्ट। आप रंग, मान और बहुत कुछ बदल सकते हैं।

### क्या मैं और अधिक डेटा बिंदु और श्रेणियाँ जोड़ सकता हूँ?

 हां, आप आवश्यकतानुसार उतने डेटा बिंदु और श्रेणियां जोड़ सकते हैं। बस उपयोग करें`series.getDataPoints().addDataPointForMapSeries()` और`chart.getChartData().getCategories().add()` उन्हें जोड़ने के तरीके.

### मैं जावा के लिए Aspose.Slides को अपने प्रोजेक्ट में कैसे एकीकृत करूं?

 लाइब्रेरी यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/java/) और इसे अपने प्रोजेक्ट के क्लासपाथ में जोड़ें।