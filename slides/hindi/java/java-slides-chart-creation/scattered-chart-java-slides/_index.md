---
title: जावा स्लाइड्स में बिखरे हुए चार्ट
linktitle: जावा स्लाइड्स में बिखरे हुए चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके जावा में स्कैटर चार्ट बनाना सीखें। प्रस्तुतियों में डेटा विज़ुअलाइज़ेशन के लिए जावा स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 11
url: /hi/java/chart-creation/scattered-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides for Java में बिखरे हुए चार्ट का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके स्कैटर चार्ट बनाने की प्रक्रिया के बारे में बताएँगे। स्कैटर चार्ट दो-आयामी विमान पर डेटा बिंदुओं को विज़ुअलाइज़ करने के लिए उपयोगी होते हैं। हम चरण-दर-चरण निर्देश प्रदान करेंगे और आपकी सुविधा के लिए जावा स्रोत कोड शामिल करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. [जावा के लिए Aspose.Slides](https://products.aspose.com/slides/java) स्थापित.
2. एक जावा विकास वातावरण स्थापित किया गया।

## चरण 1: प्रस्तुति आरंभ करें

सबसे पहले, आवश्यक लाइब्रेरीज़ आयात करें और एक नई प्रस्तुति बनाएं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// एक नया प्रस्तुतिकरण बनाएं
Presentation pres = new Presentation();
```

## चरण 2: स्लाइड जोड़ें और स्कैटर चार्ट बनाएं

 इसके बाद, एक स्लाइड जोड़ें और उस पर स्कैटर चार्ट बनाएं। हम इसका उपयोग करेंगे`ScatterWithSmoothLines`इस उदाहरण में चार्ट प्रकार.

```java
// पहली स्लाइड प्राप्त करें
ISlide slide = pres.getSlides().get_Item(0);

// स्कैटर चार्ट बनाना
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## चरण 3: चार्ट डेटा तैयार करें

अब, आइए अपने स्कैटर चार्ट के लिए डेटा तैयार करें। हम दो सीरीज़ जोड़ेंगे, जिनमें से प्रत्येक में कई डेटा पॉइंट होंगे।

```java
// डिफ़ॉल्ट चार्ट डेटा वर्कशीट इंडेक्स प्राप्त करना
int defaultWorksheetIndex = 0;

// चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// डेमो श्रृंखला हटाएं
chart.getChartData().getSeries().clear();

// पहली श्रृंखला जोड़ें
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// पहली चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// पहली श्रृंखला में डेटा बिंदु जोड़ें
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// श्रृंखला का प्रकार संपादित करें
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // मार्कर का आकार बदलें
series.getMarker().setSymbol(MarkerStyleType.Star); // मार्कर प्रतीक बदलें

// दूसरी चार्ट श्रृंखला लीजिए
series = chart.getChartData().getSeries().get_Item(1);

// दूसरी श्रृंखला में डेटा बिंदु जोड़ें
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// दूसरी श्रृंखला के लिए मार्कर शैली बदलें
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## चरण 4: प्रस्तुति सहेजें

अंत में, स्कैटर चार्ट के साथ प्रस्तुति को PPTX फ़ाइल में सहेजें।

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

बस! आपने Aspose.Slides for Java का उपयोग करके सफलतापूर्वक स्कैटर चार्ट बना लिया है। अब आप इस उदाहरण को अपने विशिष्ट डेटा और डिज़ाइन आवश्यकताओं के अनुरूप और भी अनुकूलित कर सकते हैं।

## जावा स्लाइड्स में बिखरे हुए चार्ट के लिए पूर्ण स्रोत कोड
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//डिफ़ॉल्ट चार्ट बनाना
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// डिफ़ॉल्ट चार्ट डेटा वर्कशीट इंडेक्स प्राप्त करना
int defaultWorksheetIndex = 0;
// चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// डेमो श्रृंखला हटाएं
chart.getChartData().getSeries().clear();
// नई श्रृंखला जोड़ें
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// पहली चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// वहां नया बिंदु (1:3) जोड़ें.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// नया बिंदु जोड़ें (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// श्रृंखला का प्रकार संपादित करें
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// चार्ट श्रृंखला मार्कर बदलना
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// दूसरा चार्ट श्रृंखला लें
series = chart.getChartData().getSeries().get_Item(1);
// वहां नया बिंदु (5:2) जोड़ें.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// नया बिंदु जोड़ें (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// नया बिंदु जोड़ें (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// नया बिंदु जोड़ें (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// चार्ट श्रृंखला मार्कर बदलना
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने आपको Aspose.Slides for Java का उपयोग करके स्कैटर चार्ट बनाने की प्रक्रिया के बारे में बताया है। स्कैटर चार्ट दो-आयामी स्थान में डेटा बिंदुओं को विज़ुअलाइज़ करने के लिए शक्तिशाली उपकरण हैं, जिससे जटिल डेटा संबंधों का विश्लेषण और समझना आसान हो जाता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट का प्रकार कैसे बदल सकता हूँ?

 चार्ट प्रकार बदलने के लिए, का उपयोग करें`setType` चार्ट श्रृंखला पर विधि और वांछित चार्ट प्रकार प्रदान करें। उदाहरण के लिए,`series.setType(ChartType.Line)` श्रृंखला को लाइन चार्ट में बदल दिया जाएगा।

### मैं मार्कर का आकार और शैली कैसे अनुकूलित करूं?

 आप इसका उपयोग करके मार्कर का आकार और शैली बदल सकते हैं`getMarker` श्रृंखला पर विधि और फिर आकार और प्रतीक गुण सेट करें। उदाहरण के लिए:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Aspose.Slides for Java दस्तावेज़ में अधिक अनुकूलन विकल्पों का पता लगाने के लिए स्वतंत्र महसूस करें।

 प्रतिस्थापित करना याद रखें`"Your Document Directory"` उस वास्तविक पथ के साथ जहाँ आप प्रस्तुति को सहेजना चाहते हैं.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
