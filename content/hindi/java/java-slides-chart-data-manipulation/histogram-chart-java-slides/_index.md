---
title: जावा स्लाइड्स में हिस्टोग्राम चार्ट
linktitle: जावा स्लाइड्स में हिस्टोग्राम चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में हिस्टोग्राम चार्ट बनाना सीखें। डेटा विज़ुअलाइज़ेशन के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 19
url: /hi/java/chart-data-manipulation/histogram-chart-java-slides/
---

## Aspose.Slides का उपयोग करके जावा स्लाइड्स में हिस्टोग्राम चार्ट का परिचय

इस ट्यूटोरियल में, हम जावा एपीआई के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में हिस्टोग्राम चार्ट बनाने की प्रक्रिया में आपका मार्गदर्शन करेंगे। एक हिस्टोग्राम चार्ट का उपयोग निरंतर अंतराल पर डेटा के वितरण को दर्शाने के लिए किया जाता है।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास जावा लाइब्रेरी के लिए Aspose.Slides स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[Aspose वेबसाइट](https://releases.aspose.com/slides/java/).

## चरण 1: अपना प्रोजेक्ट प्रारंभ करें

एक जावा प्रोजेक्ट बनाएं और अपने प्रोजेक्ट की निर्भरता में Aspose.Slides लाइब्रेरी को शामिल करें।

## चरण 2: आवश्यक पुस्तकालय आयात करें

```java
import com.aspose.slides.*;
```

## चरण 3: मौजूदा प्रस्तुति लोड करें

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 प्रतिस्थापित करना सुनिश्चित करें`"Your Document Directory"` आपके PowerPoint दस्तावेज़ के वास्तविक पथ के साथ।

## चरण 4: एक हिस्टोग्राम चार्ट बनाएं

अब, प्रेजेंटेशन में एक स्लाइड पर हिस्टोग्राम चार्ट बनाएं।

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // श्रृंखला में डेटा बिंदु जोड़ें
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // क्षैतिज अक्ष एकत्रीकरण प्रकार को स्वचालित पर सेट करें
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // प्रस्तुति सहेजें
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

इस कोड में, हम पहले चार्ट से किसी भी मौजूदा श्रेणी और श्रृंखला को साफ़ करते हैं। फिर, हम इसका उपयोग करके श्रृंखला में डेटा बिंदु जोड़ते हैं`getDataPoints().addDataPointForHistogramSeries` तरीका। अंत में, हम क्षैतिज अक्ष एकत्रीकरण प्रकार को स्वचालित पर सेट करते हैं और प्रस्तुति को सहेजते हैं।

## जावा स्लाइड्स में हिस्टोग्राम चार्ट के लिए संपूर्ण स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया है कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में हिस्टोग्राम चार्ट कैसे बनाया जाए। हिस्टोग्राम चार्ट निरंतर अंतराल पर डेटा के वितरण को देखने के लिए मूल्यवान उपकरण हैं, और वे आपकी प्रस्तुतियों के लिए एक शक्तिशाली अतिरिक्त हो सकते हैं, खासकर जब सांख्यिकीय या विश्लेषणात्मक सामग्री से निपटते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे स्थापित करूं?

 आप जावा लाइब्रेरी के लिए Aspose.Slides डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/). उनकी वेबसाइट पर दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

### हिस्टोग्राम चार्ट का उपयोग किसके लिए किया जाता है?

एक हिस्टोग्राम चार्ट का उपयोग निरंतर अंतराल पर डेटा के वितरण को देखने के लिए किया जाता है। इसका उपयोग आमतौर पर आँकड़ों में आवृत्ति वितरण को दर्शाने के लिए किया जाता है।

### क्या मैं हिस्टोग्राम चार्ट के स्वरूप को अनुकूलित कर सकता हूँ?

हां, आप Aspose.Slides API का उपयोग करके चार्ट के रंग, लेबल और अक्षों सहित उसके स्वरूप को अनुकूलित कर सकते हैं।