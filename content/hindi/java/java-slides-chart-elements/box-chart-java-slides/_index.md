---
title: जावा स्लाइड्स में बॉक्स चार्ट
linktitle: जावा स्लाइड्स में बॉक्स चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ जावा प्रेजेंटेशन में बॉक्स चार्ट बनाना सीखें। प्रभावी डेटा विज़ुअलाइज़ेशन के लिए चरण-दर-चरण मार्गदर्शिका और स्रोत कोड शामिल हैं।
type: docs
weight: 10
url: /hi/java/chart-elements/box-chart-java-slides/
---

## जावा के लिए Aspose.Slides में बॉक्स चार्ट का परिचय

इस ट्यूटोरियल में, हम आपको जावा के लिए Aspose.Slides का उपयोग करके एक बॉक्स चार्ट बनाने की प्रक्रिया के बारे में बताएंगे। बॉक्स चार्ट विभिन्न चतुर्थक और आउटलेर के साथ सांख्यिकीय डेटा को देखने के लिए उपयोगी होते हैं। आरंभ करने में आपकी सहायता के लिए हम स्रोत कोड के साथ चरण-दर-चरण निर्देश प्रदान करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा लाइब्रेरी के लिए Aspose.Slides स्थापित और कॉन्फ़िगर किया गया।
- एक जावा विकास वातावरण स्थापित किया गया।

## चरण 1: प्रेजेंटेशन आरंभ करें

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

इस चरण में, हम मौजूदा पावरपॉइंट फ़ाइल (इस उदाहरण में "test.pptx") के पथ का उपयोग करके एक प्रेजेंटेशन ऑब्जेक्ट को प्रारंभ करते हैं।

## चरण 2: बॉक्स चार्ट बनाएं

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

इस चरण में, हम प्रेजेंटेशन की पहली स्लाइड पर एक बॉक्स चार्ट आकार बनाते हैं। हम चार्ट से सभी मौजूदा श्रेणियों और श्रृंखलाओं को भी हटा देते हैं।

## चरण 3: श्रेणियाँ परिभाषित करें

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 इस चरण में, हम बॉक्स चार्ट के लिए श्रेणियां परिभाषित करते हैं। हम उपयोग करते हैं`IChartDataWorkbook`श्रेणियाँ जोड़ने और उन्हें तदनुसार लेबल करने के लिए।

## चरण 4: श्रृंखला बनाएं

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

यहां, हम चार्ट के लिए एक BoxAndWhisker श्रृंखला बनाते हैं और चतुर्थक विधि, माध्य रेखा, माध्य मार्कर, आंतरिक बिंदु और बाह्य बिंदु जैसे विभिन्न विकल्पों को कॉन्फ़िगर करते हैं।

## चरण 5: डेटा पॉइंट जोड़ें

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

इस चरण में, हम BoxAndWhisker श्रृंखला में डेटा बिंदु जोड़ते हैं। ये डेटा बिंदु चार्ट के लिए सांख्यिकीय डेटा का प्रतिनिधित्व करते हैं।

## चरण 6: प्रस्तुति सहेजें

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

अंत में, हम प्रेजेंटेशन को बॉक्स चार्ट के साथ "BoxAndWhisker.pptx" नाम की एक नई PowerPoint फ़ाइल में सहेजते हैं।

बधाई हो! आपने जावा के लिए Aspose.Slides का उपयोग करके सफलतापूर्वक एक बॉक्स चार्ट बनाया है। आप विभिन्न गुणों को समायोजित करके और आवश्यकतानुसार अधिक डेटा बिंदु जोड़कर चार्ट को और अधिक अनुकूलित कर सकते हैं।

## जावा स्लाइड्स में बॉक्स चार्ट के लिए संपूर्ण स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि जावा के लिए Aspose.Slides का उपयोग करके एक बॉक्स चार्ट कैसे बनाया जाता है। बॉक्स चार्ट चतुर्थक और आउटलेर सहित सांख्यिकीय डेटा को देखने के लिए मूल्यवान उपकरण हैं। हमने आपके जावा अनुप्रयोगों में बॉक्स चार्ट बनाने में मदद करने के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका प्रदान की है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं बॉक्स चार्ट का स्वरूप कैसे बदल सकता हूँ?

आप लाइन शैलियों, रंगों और फ़ॉन्ट जैसे गुणों को संशोधित करके बॉक्स चार्ट की उपस्थिति को अनुकूलित कर सकते हैं। चार्ट अनुकूलन पर विवरण के लिए जावा दस्तावेज़ के लिए Aspose.Slides देखें।

### क्या मैं बॉक्स चार्ट में अतिरिक्त डेटा श्रृंखला जोड़ सकता हूँ?

 हां, आप अतिरिक्त बनाकर बॉक्स चार्ट में एकाधिक डेटा श्रृंखला जोड़ सकते हैं`IChartSeries` ऑब्जेक्ट और उनमें डेटा पॉइंट जोड़ना।

### क्वार्टाइलमेथोडटाइप.एक्सक्लूसिव का क्या मतलब है?

`QuartileMethodType.Exclusive` सेटिंग निर्दिष्ट करती है कि चतुर्थक गणना विशिष्ट विधि का उपयोग करके की जानी चाहिए। आप अपने डेटा और आवश्यकताओं के आधार पर विभिन्न चतुर्थक गणना विधियाँ चुन सकते हैं।