---
title: जावा स्लाइड्स में फ़नल चार्ट
linktitle: जावा स्लाइड्स में फ़नल चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: चरण-दर-चरण ट्यूटोरियल के साथ जावा के लिए Aspose.Slides का अन्वेषण करें। शानदार फ़नल चार्ट और बहुत कुछ बनाएं।
type: docs
weight: 14
url: /hi/java/chart-elements/funnel-chart-java-slides/
---

## जावा स्लाइड्स में फ़नल चार्ट का परिचय

इस ट्यूटोरियल में, हम दिखाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके फ़नल चार्ट कैसे बनाया जाए। फ़नल चार्ट क्रमिक प्रक्रिया को देखने के लिए उपयोगी होते हैं, जिसमें चरण धीरे-धीरे कम होते जाते हैं, जैसे बिक्री रूपांतरण या ग्राहक अधिग्रहण।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी जोड़ी गई है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: प्रस्तुति आरंभ करें

सबसे पहले, आइए एक प्रेजेंटेशन शुरू करें और उसमें एक स्लाइड जोड़ें जहां हम अपना फ़नल चार्ट रखेंगे।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 प्रतिस्थापित करना सुनिश्चित करें`"Your Document Directory"` आपकी प्रोजेक्ट निर्देशिका के वास्तविक पथ के साथ।

## चरण 2: फ़नल चार्ट बनाएं

अब, फ़नल चार्ट बनाएं और स्लाइड पर उसके आयाम सेट करें।

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

उपरोक्त कोड में, हम पहली स्लाइड में निर्देशांक (50, 50) पर 500 की चौड़ाई और 400 पिक्सेल की ऊंचाई के साथ एक फ़नल चार्ट जोड़ते हैं।

## चरण 3: चार्ट डेटा को परिभाषित करें

इसके बाद, हम अपने फ़नल चार्ट के लिए डेटा परिभाषित करेंगे। हम चार्ट के लिए श्रेणियां और श्रृंखला निर्धारित करेंगे।

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
```

यहां, हम किसी भी मौजूदा डेटा को साफ़ करते हैं, श्रेणियां जोड़ते हैं (इस मामले में, फ़नल के चरण), और उनके लेबल सेट करते हैं।

## चरण 4: डेटा पॉइंट जोड़ें

अब, आइए अपनी फ़नल चार्ट श्रृंखला में डेटा बिंदु जोड़ें।

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

इस चरण में, हम अपने फ़नल चार्ट के लिए एक श्रृंखला बनाते हैं और फ़नल के प्रत्येक चरण में मानों का प्रतिनिधित्व करने वाले डेटा बिंदु जोड़ते हैं।

## चरण 5: प्रस्तुति सहेजें

अंत में, हम फ़नल चार्ट के साथ प्रेजेंटेशन को PowerPoint फ़ाइल में सहेजते हैं।

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 प्रतिस्थापित करना सुनिश्चित करें`"Your Document Directory"` अपने इच्छित सेव स्थान के साथ।

## जावा स्लाइड्स में फ़नल चार्ट के लिए संपूर्ण स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
	pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने आपको दिखाया है कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में फ़नल चार्ट कैसे बनाया जाए। आप अपनी विशिष्ट आवश्यकताओं के अनुरूप रंग, लेबल और अन्य गुणों को समायोजित करके चार्ट को और अधिक अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं फ़नल चार्ट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

आप चार्ट, श्रृंखला और डेटा बिंदुओं के गुणों को संशोधित करके फ़नल चार्ट के स्वरूप को अनुकूलित कर सकते हैं। विस्तृत अनुकूलन विकल्पों के लिए Aspose.Slides दस्तावेज़ देखें।

### क्या मैं फ़नल चार्ट में अधिक श्रेणियाँ या डेटा बिंदु जोड़ सकता हूँ?

हां, आप चरण 3 और चरण 4 में कोड को तदनुसार बढ़ाकर फ़नल चार्ट में अधिक श्रेणियां और डेटा बिंदु जोड़ सकते हैं।

### क्या चार्ट प्रकार को फ़नल के अलावा किसी अन्य चीज़ में बदलना संभव है?

 हाँ, Aspose.Slides विभिन्न चार्ट प्रकारों का समर्थन करता है। आप चार्ट प्रकार को प्रतिस्थापित करके बदल सकते हैं`ChartType.Funnel` चरण 2 में वांछित चार्ट प्रकार के साथ।

### Aspose.Slides के साथ काम करते समय मैं त्रुटियों या अपवादों को कैसे संभालूँ?

आप मानक जावा अपवाद हैंडलिंग तंत्र का उपयोग करके त्रुटियों और अपवादों को संभाल सकते हैं। सुनिश्चित करें कि अप्रत्याशित स्थितियों को शालीनता से संभालने के लिए आपके कोड में उचित त्रुटि प्रबंधन है।

### जावा के लिए Aspose.Slides के लिए मुझे और अधिक उदाहरण और दस्तावेज़ कहां मिल सकते हैं?

 आप जावा के लिए Aspose.Slides का उपयोग करने पर अधिक उदाहरण और विस्तृत दस्तावेज़ पा सकते हैं[प्रलेखन](https://docs.aspose.com/slides/java/).