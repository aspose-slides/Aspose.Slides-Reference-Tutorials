---
title: जावा स्लाइड में व्यक्तिगत श्रृंखला के लिए नकारात्मक होने पर उलटा करें
linktitle: जावा स्लाइड में व्यक्तिगत श्रृंखला के लिए नकारात्मक होने पर उलटा करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: PowerPoint प्रस्तुतियों में चार्ट विज़ुअल्स को बढ़ाने के लिए जावा के लिए Aspose.Slides में इनवर्ट इफ़ नेगेटिव सुविधा का उपयोग करना सीखें।
type: docs
weight: 11
url: /hi/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

## जावा स्लाइड्स में व्यक्तिगत श्रृंखला के लिए नकारात्मक होने पर उलटा करने का परिचय

जावा के लिए Aspose.Slides प्रस्तुतियों के साथ काम करने के लिए शक्तिशाली उपकरण प्रदान करता है, और एक दिलचस्प विशेषता यह नियंत्रित करने की क्षमता है कि चार्ट पर डेटा श्रृंखला कैसे प्रदर्शित की जाती है। इस लेख में, हम यह पता लगाएंगे कि जावा स्लाइड्स में व्यक्तिगत श्रृंखला के लिए "इनवर्ट इफ नेगेटिव" सुविधा का उपयोग कैसे करें। यह सुविधा आपको चार्ट में नकारात्मक डेटा बिंदुओं को दृष्टिगत रूप से अलग करने की अनुमति देती है, जिससे आपकी प्रस्तुतियाँ अधिक जानकारीपूर्ण और आकर्षक बन जाती हैं।

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Slides। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## अपना प्रोजेक्ट सेट करना

आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक नया जावा प्रोजेक्ट बनाएं। एक बार जब आपका प्रोजेक्ट सेट हो जाए, तो जावा स्लाइड्स में व्यक्तिगत श्रृंखला के लिए "इनवर्ट इफ नेगेटिव" सुविधा को लागू करने के लिए इन चरणों का पालन करें।

## चरण 1: Aspose.Slides लाइब्रेरी शामिल करें

सबसे पहले, आपको अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी को शामिल करना होगा। आप अपने प्रोजेक्ट के क्लासपाथ में लाइब्रेरी JAR फ़ाइल जोड़कर ऐसा कर सकते हैं। यह चरण सुनिश्चित करता है कि आप PowerPoint प्रस्तुतियों के साथ काम करने के लिए सभी आवश्यक कक्षाओं और विधियों तक पहुँच सकते हैं।

```java
import com.aspose.slides.*;
```

## चरण 2: एक प्रस्तुति बनाएं

 अब, आइए Aspose.Slides का उपयोग करके एक नया PowerPoint प्रेजेंटेशन बनाएं। आप उस निर्देशिका को परिभाषित कर सकते हैं जहां आप प्रेजेंटेशन को सहेजना चाहते हैं`dataDir` चर।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 3: एक चार्ट जोड़ें

इस चरण में, हम प्रेजेंटेशन में एक चार्ट जोड़ेंगे। उदाहरण के तौर पर हम क्लस्टर्ड कॉलम चार्ट का उपयोग करेंगे। आप अपनी आवश्यकताओं के आधार पर विभिन्न चार्ट प्रकार चुन सकते हैं।

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## चरण 4: चार्ट डेटा श्रृंखला कॉन्फ़िगर करें

इसके बाद, हम चार्ट की डेटा श्रृंखला को कॉन्फ़िगर करेंगे। "इनवर्ट इफ़ नेगेटिव" सुविधा को प्रदर्शित करने के लिए, हम सकारात्मक और नकारात्मक दोनों मानों के साथ एक नमूना डेटासेट बनाएंगे।

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// श्रृंखला में डेटा बिंदु जोड़ना
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## चरण 5: "यदि नकारात्मक हो तो उलटा करें" लागू करें

अब, हम डेटा बिंदुओं में से एक पर "इनवर्ट इफ़ नेगेटिव" सुविधा लागू करेंगे। यह नकारात्मक होने पर उस विशिष्ट डेटा बिंदु का रंग दृष्टिगत रूप से उलट देगा।

```java
series.get_Item(0).setInvertIfNegative(false); // डिफ़ॉल्ट रूप से पलटें नहीं
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // तीसरे डेटा बिंदु के लिए रंग उल्टा करें
```

## चरण 6: प्रस्तुति सहेजें

अंत में, प्रेजेंटेशन को अपनी निर्दिष्ट निर्देशिका में सहेजें।

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में व्यक्तिगत श्रृंखला के लिए नकारात्मक होने पर पलटने के लिए पूर्ण स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में व्यक्तिगत श्रृंखला के लिए "इनवर्ट इफ नेगेटिव" सुविधा का उपयोग कैसे करें। यह सुविधा आपको अपने चार्ट में नकारात्मक डेटा बिंदुओं को उजागर करने की अनुमति देती है, जिससे आपकी प्रस्तुतियाँ अधिक आकर्षक और जानकारीपूर्ण हो जाती हैं।

## अक्सर पूछे जाने वाले प्रश्न

### जावा के लिए Aspose.Slides में "इनवर्ट इफ़ नेगेटिव" सुविधा का उद्देश्य क्या है?

जावा के लिए Aspose.Slides में "इनवर्ट इफ नेगेटिव" सुविधा आपको चार्ट में नकारात्मक डेटा बिंदुओं को दृष्टिगत रूप से अलग करने की अनुमति देती है। यह विशिष्ट डेटा बिंदुओं को हाइलाइट करके आपकी प्रस्तुतियों को अधिक जानकारीपूर्ण और आकर्षक बनाने में मदद करता है।

### मैं अपने जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी को कैसे शामिल कर सकता हूं?

अपने जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी को शामिल करने के लिए, आपको लाइब्रेरी JAR फ़ाइल को अपने प्रोजेक्ट के क्लासपाथ में जोड़ना होगा। यह आपको PowerPoint प्रस्तुतियों के साथ काम करने के लिए सभी आवश्यक कक्षाओं और विधियों तक पहुँचने में सक्षम बनाता है।

### क्या मैं "इनवर्ट इफ़ नेगेटिव" सुविधा के साथ विभिन्न चार्ट प्रकारों का उपयोग कर सकता हूँ?

हां, आप "इनवर्ट इफ नेगेटिव" सुविधा के साथ विभिन्न चार्ट प्रकारों का उपयोग कर सकते हैं। इस ट्यूटोरियल में, हमने एक उदाहरण के रूप में क्लस्टर्ड कॉलम चार्ट का उपयोग किया है, लेकिन आप अपनी आवश्यकताओं के आधार पर इस सुविधा को विभिन्न चार्ट प्रकारों पर लागू कर सकते हैं।

### क्या उल्टे डेटा बिंदुओं की उपस्थिति को अनुकूलित करना संभव है?

हाँ, आप उल्टे डेटा बिंदुओं के स्वरूप को अनुकूलित कर सकते हैं। जावा के लिए Aspose.Slides डेटा बिंदुओं के रंग और शैली को नियंत्रित करने के लिए विकल्प प्रदान करता है जब वे "इनवर्ट इफ नेगेटिव" सेटिंग के कारण उलटे होते हैं।

### मैं जावा दस्तावेज़ के लिए Aspose.Slides तक कहां पहुंच सकता हूं?

 आप जावा के लिए Aspose.Slides के दस्तावेज़ तक पहुंच सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).