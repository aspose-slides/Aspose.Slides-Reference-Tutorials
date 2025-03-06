---
title: जावा स्लाइड्स में हिस्टोग्राम चार्ट
linktitle: जावा स्लाइड्स में हिस्टोग्राम चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में हिस्टोग्राम चार्ट बनाना सीखें। डेटा विज़ुअलाइज़ेशन के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 19
url: /hi/java/chart-data-manipulation/histogram-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में हिस्टोग्राम चार्ट


## Aspose.Slides का उपयोग करके जावा स्लाइड्स में हिस्टोग्राम चार्ट का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java API का उपयोग करके PowerPoint प्रेजेंटेशन में हिस्टोग्राम चार्ट बनाने की प्रक्रिया के बारे में बताएंगे। हिस्टोग्राम चार्ट का उपयोग निरंतर अंतराल पर डेटा के वितरण को दर्शाने के लिए किया जाता है।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose वेबसाइट](https://releases.aspose.com/slides/java/).

## चरण 1: अपना प्रोजेक्ट आरंभ करें

एक जावा प्रोजेक्ट बनाएं और अपने प्रोजेक्ट की निर्भरताओं में Aspose.Slides लाइब्रेरी को शामिल करें।

## चरण 2: आवश्यक लाइब्रेरीज़ आयात करें

```java
import com.aspose.slides.*;
```

## चरण 3: मौजूदा प्रेजेंटेशन लोड करें

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 प्रतिस्थापित करना सुनिश्चित करें`"Your Document Directory"` अपने PowerPoint दस्तावेज़ के वास्तविक पथ के साथ.

## चरण 4: हिस्टोग्राम चार्ट बनाएं

अब, आइए प्रस्तुति में एक स्लाइड पर हिस्टोग्राम चार्ट बनाएं।

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

 इस कोड में, हम सबसे पहले चार्ट से मौजूदा श्रेणियों और श्रृंखलाओं को हटाते हैं। फिर, हम श्रृंखला में डेटा बिंदुओं को जोड़ते हैं`getDataPoints().addDataPointForHistogramSeries` अंत में, हम क्षैतिज अक्ष एकत्रीकरण प्रकार को स्वचालित पर सेट करते हैं और प्रस्तुति को सहेजते हैं।

## जावा स्लाइड्स में हिस्टोग्राम चार्ट के लिए पूर्ण स्रोत कोड

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

इस ट्यूटोरियल में, हमने Aspose.Slides for Java API का उपयोग करके PowerPoint प्रेजेंटेशन में हिस्टोग्राम चार्ट बनाने का तरीका खोजा है। हिस्टोग्राम चार्ट निरंतर अंतराल पर डेटा के वितरण को विज़ुअलाइज़ करने के लिए मूल्यवान उपकरण हैं, और वे आपकी प्रस्तुतियों के लिए एक शक्तिशाली अतिरिक्त हो सकते हैं, खासकर जब सांख्यिकीय या विश्लेषणात्मक सामग्री से निपटते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?

 आप Aspose.Slides for Java लाइब्रेरी को यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/)उनकी वेबसाइट पर दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

### हिस्टोग्राम चार्ट का उपयोग किस लिए किया जाता है?

हिस्टोग्राम चार्ट का उपयोग निरंतर अंतराल पर डेटा के वितरण को दर्शाने के लिए किया जाता है। इसका उपयोग आमतौर पर सांख्यिकी में आवृत्ति वितरण को दर्शाने के लिए किया जाता है।

### क्या मैं हिस्टोग्राम चार्ट के स्वरूप को अनुकूलित कर सकता हूँ?

हां, आप Aspose.Slides API का उपयोग करके चार्ट के रंग, लेबल और अक्ष सहित उसके स्वरूप को अनुकूलित कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
