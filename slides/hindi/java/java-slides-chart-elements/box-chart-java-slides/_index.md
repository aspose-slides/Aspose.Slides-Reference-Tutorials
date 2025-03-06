---
title: जावा स्लाइड्स में बॉक्स चार्ट
linktitle: जावा स्लाइड्स में बॉक्स चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ जावा प्रेजेंटेशन में बॉक्स चार्ट बनाना सीखें। प्रभावी डेटा विज़ुअलाइज़ेशन के लिए चरण-दर-चरण मार्गदर्शिका और स्रोत कोड शामिल है।
weight: 10
url: /hi/java/chart-elements/box-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java में बॉक्स चार्ट का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके बॉक्स चार्ट बनाने की प्रक्रिया से परिचित कराएँगे। बॉक्स चार्ट विभिन्न क्वार्टाइल और आउटलायर्स के साथ सांख्यिकीय डेटा को विज़ुअलाइज़ करने के लिए उपयोगी होते हैं। हम आपको आरंभ करने में मदद करने के लिए स्रोत कोड के साथ चरण-दर-चरण निर्देश प्रदान करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Aspose.Slides for Java लाइब्रेरी स्थापित और कॉन्फ़िगर की गई।
- एक जावा विकास वातावरण स्थापित किया गया।

## चरण 1: प्रस्तुति आरंभ करें

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

इस चरण में, हम एक मौजूदा PowerPoint फ़ाइल (इस उदाहरण में "test.pptx") के पथ का उपयोग करके एक प्रस्तुति ऑब्जेक्ट को आरंभीकृत करते हैं।

## चरण 2: बॉक्स चार्ट बनाएं

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

इस चरण में, हम प्रस्तुति की पहली स्लाइड पर एक बॉक्स चार्ट आकार बनाते हैं। हम चार्ट से किसी भी मौजूदा श्रेणियों और श्रृंखला को भी साफ़ करते हैं।

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

 इस चरण में, हम बॉक्स चार्ट के लिए श्रेणियाँ परिभाषित करते हैं।`IChartDataWorkbook` श्रेणियाँ जोड़ने और उन्हें तदनुसार लेबल करने के लिए.

## चरण 4: श्रृंखला बनाएं

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

यहां, हम चार्ट के लिए BoxAndWhisker श्रृंखला बनाते हैं और विभिन्न विकल्पों जैसे चतुर्थक विधि, माध्य रेखा, माध्य मार्कर, आंतरिक बिंदु और बाह्य बिंदु को कॉन्फ़िगर करते हैं।

## चरण 5: डेटा बिंदु जोड़ें

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

इस चरण में, हम BoxAndWhisker श्रृंखला में डेटा बिंदु जोड़ते हैं। ये डेटा बिंदु चार्ट के लिए सांख्यिकीय डेटा का प्रतिनिधित्व करते हैं।

## चरण 6: प्रेजेंटेशन सहेजें

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

अंत में, हम बॉक्स चार्ट के साथ प्रस्तुति को "BoxAndWhisker.pptx" नामक एक नई पावरपॉइंट फ़ाइल में सहेजते हैं।

बधाई हो! आपने Aspose.Slides for Java का उपयोग करके सफलतापूर्वक एक बॉक्स चार्ट बनाया है। आप विभिन्न गुणों को समायोजित करके और आवश्यकतानुसार अधिक डेटा बिंदु जोड़कर चार्ट को और अधिक अनुकूलित कर सकते हैं।

## जावा स्लाइड्स में बॉक्स चार्ट के लिए पूर्ण स्रोत कोड

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

इस ट्यूटोरियल में, हमने सीखा है कि जावा के लिए Aspose.Slides का उपयोग करके बॉक्स चार्ट कैसे बनाया जाता है। बॉक्स चार्ट क्वार्टाइल और आउटलायर्स सहित सांख्यिकीय डेटा को विज़ुअलाइज़ करने के लिए मूल्यवान उपकरण हैं। हमने आपके जावा अनुप्रयोगों में बॉक्स चार्ट बनाने में आपकी सहायता करने के लिए स्रोत कोड के साथ-साथ चरण-दर-चरण मार्गदर्शिका प्रदान की है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं बॉक्स चार्ट का स्वरूप कैसे बदल सकता हूँ?

आप लाइन स्टाइल, रंग और फ़ॉन्ट जैसे गुणों को संशोधित करके बॉक्स चार्ट की उपस्थिति को अनुकूलित कर सकते हैं। चार्ट अनुकूलन पर विवरण के लिए Aspose.Slides for Java दस्तावेज़ देखें।

### क्या मैं बॉक्स चार्ट में अतिरिक्त डेटा श्रृंखला जोड़ सकता हूँ?

 हां, आप अतिरिक्त बनाकर बॉक्स चार्ट में कई डेटा श्रृंखलाएं जोड़ सकते हैं`IChartSeries` ऑब्जेक्ट्स और उनमें डेटा बिंदु जोड़ना।

### QuartileMethodType.Exclusive का क्या अर्थ है?

`QuartileMethodType.Exclusive` सेटिंग निर्दिष्ट करती है कि चतुर्थक गणना अनन्य विधि का उपयोग करके की जानी चाहिए। आप अपने डेटा और आवश्यकताओं के आधार पर अलग-अलग चतुर्थक गणना विधियाँ चुन सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
