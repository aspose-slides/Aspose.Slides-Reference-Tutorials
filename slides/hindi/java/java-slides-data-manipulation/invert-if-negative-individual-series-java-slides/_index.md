---
title: जावा स्लाइड्स में व्यक्तिगत श्रृंखला के लिए ऋणात्मक होने पर उलटा करें
linktitle: जावा स्लाइड्स में व्यक्तिगत श्रृंखला के लिए ऋणात्मक होने पर उलटा करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि PowerPoint प्रस्तुतियों में चार्ट दृश्यों को बेहतर बनाने के लिए Aspose.Slides for Java में Invert If Negative सुविधा का उपयोग कैसे करें।
weight: 11
url: /hi/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में व्यक्तिगत श्रृंखला के लिए इनवर्ट इफ नेगेटिव का परिचय

Aspose.Slides for Java प्रस्तुतियों के साथ काम करने के लिए शक्तिशाली उपकरण प्रदान करता है, और एक दिलचस्प विशेषता यह नियंत्रित करने की क्षमता है कि चार्ट पर डेटा श्रृंखला कैसे प्रदर्शित की जाती है। इस लेख में, हम यह पता लगाएंगे कि Java Slides में अलग-अलग श्रृंखलाओं के लिए "इनवर्ट इफ नेगेटिव" सुविधा का उपयोग कैसे करें। यह सुविधा आपको चार्ट में नकारात्मक डेटा बिंदुओं को दृष्टिगत रूप से अलग करने की अनुमति देती है, जिससे आपकी प्रस्तुतियाँ अधिक जानकारीपूर्ण और आकर्षक बन जाती हैं।

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## अपना प्रोजेक्ट सेट अप करना

आरंभ करने के लिए, अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक नया जावा प्रोजेक्ट बनाएँ। एक बार जब आपका प्रोजेक्ट सेट हो जाए, तो जावा स्लाइड्स में अलग-अलग सीरीज़ के लिए "इनवर्ट इफ नेगेटिव" सुविधा को लागू करने के लिए इन चरणों का पालन करें।

## चरण 1: Aspose.Slides लाइब्रेरी शामिल करें

सबसे पहले, आपको अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी को शामिल करना होगा। आप अपने प्रोजेक्ट के क्लासपाथ में लाइब्रेरी JAR फ़ाइल जोड़कर ऐसा कर सकते हैं। यह कदम सुनिश्चित करता है कि आप PowerPoint प्रस्तुतियों के साथ काम करने के लिए सभी आवश्यक कक्षाओं और विधियों तक पहुँच सकते हैं।

```java
import com.aspose.slides.*;
```

## चरण 2: एक प्रस्तुति बनाएं

 अब, Aspose.Slides का उपयोग करके एक नया PowerPoint प्रेजेंटेशन बनाएँ। आप उस निर्देशिका को परिभाषित कर सकते हैं जहाँ आप प्रेजेंटेशन को सहेजना चाहते हैं।`dataDir` चर।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 3: चार्ट जोड़ें

इस चरण में, हम प्रस्तुति में एक चार्ट जोड़ेंगे। हम एक उदाहरण के रूप में क्लस्टर किए गए कॉलम चार्ट का उपयोग करेंगे। आप अपनी आवश्यकताओं के आधार पर विभिन्न चार्ट प्रकार चुन सकते हैं।

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## चरण 4: चार्ट डेटा श्रृंखला कॉन्फ़िगर करें

इसके बाद, हम चार्ट की डेटा श्रृंखला को कॉन्फ़िगर करेंगे। "इनवर्ट इफ नेगेटिव" सुविधा को प्रदर्शित करने के लिए, हम सकारात्मक और नकारात्मक दोनों मानों के साथ एक नमूना डेटासेट बनाएंगे।

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

## चरण 5: "इनवर्ट इफ नेगेटिव" लागू करें

अब, हम किसी एक डेटा पॉइंट पर "इनवर्ट इफ नेगेटिव" फीचर लागू करेंगे। यह उस विशिष्ट डेटा पॉइंट के रंग को तब विज़ुअली इनवर्ट कर देगा जब वह नेगेटिव होगा।

```java
series.get_Item(0).setInvertIfNegative(false); // डिफ़ॉल्ट रूप से उलटा न करें
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // तीसरे डेटा बिंदु के लिए रंग उलटें
```

## चरण 6: प्रेजेंटेशन सहेजें

अंत में, प्रस्तुति को अपनी निर्दिष्ट निर्देशिका में सहेजें।

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में अलग-अलग श्रृंखला के लिए इनवर्ट इफ नेगेटिव के लिए पूरा स्रोत कोड

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

इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके Java स्लाइड्स में अलग-अलग सीरीज़ के लिए "इनवर्ट इफ नेगेटिव" सुविधा का उपयोग कैसे करें। यह सुविधा आपको अपने चार्ट में नकारात्मक डेटा बिंदुओं को हाइलाइट करने की अनुमति देती है, जिससे आपकी प्रस्तुतियाँ अधिक आकर्षक और जानकारीपूर्ण बन जाती हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Aspose.Slides for Java में "इनवर्ट इफ नेगेटिव" सुविधा का उद्देश्य क्या है?

Aspose.Slides for Java में "इनवर्ट इफ नेगेटिव" सुविधा आपको चार्ट में नकारात्मक डेटा बिंदुओं को दृष्टिगत रूप से अलग करने की अनुमति देती है। यह विशिष्ट डेटा बिंदुओं को हाइलाइट करके आपकी प्रस्तुतियों को अधिक जानकारीपूर्ण और आकर्षक बनाने में मदद करता है।

### मैं अपने जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी को कैसे शामिल कर सकता हूं?

अपने जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी को शामिल करने के लिए, आपको अपने प्रोजेक्ट के क्लासपाथ में लाइब्रेरी JAR फ़ाइल को जोड़ना होगा। यह आपको PowerPoint प्रस्तुतियों के साथ काम करने के लिए सभी आवश्यक कक्षाओं और विधियों तक पहुँचने में सक्षम बनाता है।

### क्या मैं "इनवर्ट इफ नेगेटिव" सुविधा के साथ विभिन्न चार्ट प्रकारों का उपयोग कर सकता हूँ?

हां, आप "इनवर्ट इफ नेगेटिव" सुविधा के साथ विभिन्न चार्ट प्रकारों का उपयोग कर सकते हैं। इस ट्यूटोरियल में, हमने एक उदाहरण के रूप में क्लस्टर्ड कॉलम चार्ट का उपयोग किया है, लेकिन आप अपनी आवश्यकताओं के आधार पर विभिन्न चार्ट प्रकारों पर इस सुविधा को लागू कर सकते हैं।

### क्या उल्टे डेटा बिंदुओं के स्वरूप को अनुकूलित करना संभव है?

हां, आप उल्टे डेटा बिंदुओं की उपस्थिति को अनुकूलित कर सकते हैं। Aspose.Slides for Java "इनवर्ट इफ नेगेटिव" सेटिंग के कारण उल्टे होने पर डेटा बिंदुओं के रंग और शैली को नियंत्रित करने के लिए विकल्प प्रदान करता है।

### मैं Aspose.Slides for Java दस्तावेज़न कहां से प्राप्त कर सकता हूं?

आप Aspose.Slides for Java के दस्तावेज़ों तक यहां पहुंच सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
