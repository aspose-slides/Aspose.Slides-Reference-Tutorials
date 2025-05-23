---
"description": "Aspose.Slides for Java के साथ PowerPoint प्रस्तुतियों में शानदार मानचित्र चार्ट बनाएँ। Java डेवलपर्स के लिए चरण-दर-चरण मार्गदर्शिका और स्रोत कोड।"
"linktitle": "जावा स्लाइड्स में मानचित्र चार्ट"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में मानचित्र चार्ट"
"url": "/hi/java/chart-elements/map-chart-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में मानचित्र चार्ट


## जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में मानचित्र चार्ट का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में मैप चार्ट बनाने की प्रक्रिया के बारे में बताएँगे। मैप चार्ट आपके प्रेजेंटेशन में भौगोलिक डेटा को विज़ुअलाइज़ करने का एक शानदार तरीका है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी आपके Java प्रोजेक्ट में एकीकृत है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: अपना प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपने अपना जावा प्रोजेक्ट सेट अप कर लिया है और अपने प्रोजेक्ट के क्लासपाथ में Aspose.Slides for Java लाइब्रेरी जोड़ ली है।

## चरण 2: पावरपॉइंट प्रेजेंटेशन बनाएं

सबसे पहले, आइए एक नया पावरपॉइंट प्रेजेंटेशन बनाएं।

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## चरण 3: मानचित्र चार्ट जोड़ें

अब, हम प्रस्तुति में एक मानचित्र चार्ट जोड़ेंगे।

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## चरण 4: मानचित्र चार्ट में डेटा जोड़ें

आइए मानचित्र चार्ट में कुछ डेटा जोड़ें। हम एक श्रृंखला बनाएंगे और उसमें डेटा बिंदु जोड़ेंगे।

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

## चरण 6: डेटा पॉइंट्स को अनुकूलित करें

आप अलग-अलग डेटा पॉइंट को कस्टमाइज़ कर सकते हैं। इस उदाहरण में, हम किसी खास डेटा पॉइंट का रंग और मान बदलते हैं।

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## चरण 7: प्रस्तुति सहेजें

अंत में, मानचित्र चार्ट के साथ प्रस्तुति को सहेजें।

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

बस! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में मैप चार्ट बनाया है। आप चार्ट को और भी कस्टमाइज़ कर सकते हैं और अपनी प्रेजेंटेशन को बेहतर बनाने के लिए Aspose.Slides द्वारा दी जाने वाली अन्य सुविधाओं का पता लगा सकते हैं।

## जावा स्लाइड्स में मानचित्र चार्ट के लिए पूर्ण स्रोत कोड

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
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
	//श्रेणियाँ जोड़ें
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

इस ट्यूटोरियल में, हमने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में मैप चार्ट बनाने की प्रक्रिया को देखा है। मैप चार्ट भौगोलिक डेटा को विज़ुअलाइज़ करने का एक प्रभावी तरीका है, जो आपकी प्रेजेंटेशन को अधिक आकर्षक और जानकारीपूर्ण बनाता है। आइए मुख्य चरणों को संक्षेप में प्रस्तुत करें:

## अक्सर पूछे जाने वाले प्रश्न

### मैं मानचित्र चार्ट प्रकार कैसे बदल सकता हूँ?

आप चार्ट प्रकार को प्रतिस्थापित करके बदल सकते हैं `ChartType.Map` चरण 3 में चार्ट बनाते समय इच्छित चार्ट प्रकार का चयन करें।

### मैं मानचित्र चार्ट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

आप चार्ट के गुणों को संशोधित करके उसके स्वरूप को अनुकूलित कर सकते हैं `dataPoint` चरण 6 में ऑब्जेक्ट बदलें। आप रंग, मान और बहुत कुछ बदल सकते हैं।

### क्या मैं अधिक डेटा बिंदु और श्रेणियां जोड़ सकता हूं?

हां, आप आवश्यकतानुसार जितने चाहें उतने डेटा पॉइंट और श्रेणियां जोड़ सकते हैं। बस का उपयोग करें `series.getDataPoints().addDataPointForMapSeries()` और `chart.getChartData().getCategories().add()` उन्हें जोड़ने के तरीके.

### मैं अपने प्रोजेक्ट में Aspose.Slides for Java को कैसे एकीकृत करूं?

लाइब्रेरी को यहां से डाउनलोड करें [यहाँ](https://releases.aspose.com/slides/java/) और इसे अपने प्रोजेक्ट के क्लासपाथ में जोड़ें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}