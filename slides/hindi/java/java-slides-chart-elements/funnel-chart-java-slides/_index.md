---
"description": "चरण-दर-चरण ट्यूटोरियल के साथ Java के लिए Aspose.Slides का अन्वेषण करें। शानदार फ़नल चार्ट और बहुत कुछ बनाएँ।"
"linktitle": "जावा स्लाइड्स में फ़नल चार्ट"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में फ़नल चार्ट"
"url": "/hi/java/chart-elements/funnel-chart-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में फ़नल चार्ट


## जावा स्लाइड्स में फ़नल चार्ट का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके फ़नल चार्ट बनाने का तरीका प्रदर्शित करेंगे। फ़नल चार्ट क्रमिक प्रक्रिया को विज़ुअलाइज़ करने के लिए उपयोगी होते हैं, जिसमें क्रमिक रूप से संकीर्ण चरण होते हैं, जैसे बिक्री रूपांतरण या ग्राहक अधिग्रहण।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी जोड़ी गई है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: प्रस्तुति आरंभ करें

सबसे पहले, आइए एक प्रस्तुति आरंभ करें और उसमें एक स्लाइड जोड़ें जहां हम अपना फ़नल चार्ट रखेंगे।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

प्रतिस्थापित करना सुनिश्चित करें `"Your Document Directory"` आपके प्रोजेक्ट निर्देशिका के वास्तविक पथ के साथ.

## चरण 2: फ़नल चार्ट बनाएं

अब, आइए फ़नल चार्ट बनाएं और स्लाइड पर इसके आयाम सेट करें।

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

उपरोक्त कोड में, हम निर्देशांक (50, 50) पर पहली स्लाइड में 500 की चौड़ाई और 400 पिक्सेल की ऊंचाई के साथ एक फ़नल चार्ट जोड़ते हैं।

## चरण 3: चार्ट डेटा परिभाषित करें

इसके बाद, हम अपने फ़नल चार्ट के लिए डेटा परिभाषित करेंगे। हम चार्ट के लिए श्रेणियाँ और श्रृंखलाएँ निर्धारित करेंगे।

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

## चरण 4: डेटा बिंदु जोड़ें

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

इस चरण में, हम अपने फ़नल चार्ट के लिए एक श्रृंखला बनाते हैं और फ़नल के प्रत्येक चरण पर मानों का प्रतिनिधित्व करने वाले डेटा बिंदु जोड़ते हैं।

## चरण 5: प्रस्तुति सहेजें

अंत में, हम फ़नल चार्ट के साथ प्रस्तुति को पावरपॉइंट फ़ाइल में सहेजते हैं।

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

प्रतिस्थापित करना सुनिश्चित करें `"Your Document Directory"` अपने इच्छित स्थान के साथ सहेजें.

## जावा स्लाइड्स में फ़नल चार्ट के लिए पूर्ण स्रोत कोड

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

इस ट्यूटोरियल में, हमने आपको Aspose.Slides for Java का उपयोग करके Java Slides में फ़नल चार्ट बनाने का तरीका दिखाया है। आप अपनी विशिष्ट आवश्यकताओं के अनुसार रंग, लेबल और अन्य गुणों को समायोजित करके चार्ट को और भी अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं फ़नल चार्ट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

आप चार्ट, श्रृंखला और डेटा बिंदुओं के गुणों को संशोधित करके फ़नल चार्ट की उपस्थिति को अनुकूलित कर सकते हैं। विस्तृत अनुकूलन विकल्पों के लिए Aspose.Slides दस्तावेज़ देखें।

### क्या मैं फ़नल चार्ट में और अधिक श्रेणियाँ या डेटा बिंदु जोड़ सकता हूँ?

हां, आप चरण 3 और चरण 4 में कोड को विस्तारित करके फ़नल चार्ट में अधिक श्रेणियां और डेटा बिंदु जोड़ सकते हैं।

### क्या चार्ट प्रकार को फ़नल के अलावा किसी अन्य प्रकार में बदलना संभव है?

हां, Aspose.Slides विभिन्न चार्ट प्रकारों का समर्थन करता है। आप चार्ट प्रकार को बदलकर बदल सकते हैं `ChartType.Funnel` चरण 2 में वांछित चार्ट प्रकार के साथ।

### Aspose.Slides के साथ काम करते समय मैं त्रुटियों या अपवादों को कैसे संभालूँ?

आप मानक जावा अपवाद हैंडलिंग तंत्र का उपयोग करके त्रुटियों और अपवादों को संभाल सकते हैं। सुनिश्चित करें कि अप्रत्याशित स्थितियों को सुचारू रूप से संभालने के लिए आपके कोड में उचित त्रुटि हैंडलिंग है।

### मैं Aspose.Slides for Java के लिए और अधिक उदाहरण और दस्तावेज़ कहां पा सकता हूं?

आप जावा के लिए Aspose.Slides का उपयोग करने पर अधिक उदाहरण और विस्तृत दस्तावेज़ पा सकते हैं [प्रलेखन](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}