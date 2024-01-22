---
title: जावा स्लाइड्स में बाहरी कार्यपुस्तिका सेट करें
linktitle: जावा स्लाइड्स में बाहरी कार्यपुस्तिका सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में बाहरी कार्यपुस्तिकाएँ सेट करना सीखें। एक्सेल डेटा एकीकरण के साथ गतिशील प्रस्तुतियाँ बनाएँ।
type: docs
weight: 19
url: /hi/java/data-manipulation/set-external-workbook-java-slides/
---

## जावा स्लाइड्स में बाहरी वर्कबुक सेट करने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके जावा स्लाइड्स में एक बाहरी कार्यपुस्तिका कैसे सेट करें, इसका पता लगाएंगे। आप सीखेंगे कि बाहरी एक्सेल वर्कबुक से डेटा को संदर्भित करने वाले चार्ट के साथ पावरपॉइंट प्रेजेंटेशन कैसे बनाया जाए। इस गाइड के अंत तक, आपको इस बात की स्पष्ट समझ हो जाएगी कि बाहरी डेटा को अपनी जावा स्लाइड प्रस्तुतियों में कैसे एकीकृत किया जाए।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
- जावा लाइब्रेरी के लिए Aspose.Slides आपके प्रोजेक्ट में जोड़ा गया।
- उस डेटा के साथ एक एक्सेल वर्कबुक जिसे आप अपनी प्रस्तुति में संदर्भित करना चाहते हैं।

## चरण 1: एक नई प्रस्तुति बनाएं

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

हम Aspose.Slides का उपयोग करके एक नई PowerPoint प्रस्तुति बनाकर शुरुआत करते हैं।

## चरण 2: एक चार्ट जोड़ें

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

इसके बाद, हम प्रेजेंटेशन में एक पाई चार्ट सम्मिलित करते हैं। आप आवश्यकतानुसार चार्ट प्रकार और स्थिति को अनुकूलित कर सकते हैं।

## चरण 3: बाहरी कार्यपुस्तिका तक पहुंचें

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 बाहरी कार्यपुस्तिका तक पहुँचने के लिए, हम इसका उपयोग करते हैं`setExternalWorkbook` विधि और डेटा युक्त Excel कार्यपुस्तिका के लिए पथ प्रदान करें।

## चरण 4: चार्ट डेटा को बाइंड करें

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

हम श्रृंखला और श्रेणियों के लिए सेल संदर्भ निर्दिष्ट करके चार्ट को बाहरी कार्यपुस्तिका के डेटा से जोड़ते हैं।

## चरण 5: प्रस्तुति सहेजें

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

अंत में, हम प्रेजेंटेशन को बाहरी कार्यपुस्तिका संदर्भ के साथ PowerPoint फ़ाइल के रूप में सहेजते हैं।

## जावा स्लाइड्स में बाहरी कार्यपुस्तिका सेट करने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Slides का उपयोग करके जावा स्लाइड्स में एक बाहरी कार्यपुस्तिका कैसे सेट करें। अब आप ऐसी प्रस्तुतियाँ बना सकते हैं जो एक्सेल वर्कबुक से डेटा को गतिशील रूप से संदर्भित करती हैं, जिससे आपकी स्लाइड्स का लचीलापन और अन्तरक्रियाशीलता बढ़ती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे स्थापित करूं?

जावा के लिए Aspose.Slides को आपके जावा प्रोजेक्ट में लाइब्रेरी जोड़कर स्थापित किया जा सकता है। आप Aspose वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं और दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन कर सकते हैं।

### क्या मैं बाहरी कार्यपुस्तिकाओं के साथ विभिन्न चार्ट प्रकारों का उपयोग कर सकता हूँ?

हां, आप Aspose.Slides द्वारा समर्थित विभिन्न चार्ट प्रकारों का उपयोग कर सकते हैं और उन्हें बाहरी कार्यपुस्तिकाओं के डेटा से जोड़ सकते हैं। आपके द्वारा चुने गए चार्ट प्रकार के आधार पर प्रक्रिया थोड़ी भिन्न हो सकती है।

### यदि मेरी बाहरी कार्यपुस्तिका की डेटा संरचना बदल जाए तो क्या होगा?

यदि आपकी बाहरी कार्यपुस्तिका के डेटा की संरचना बदलती है, तो आपको यह सुनिश्चित करने के लिए अपने जावा कोड में सेल संदर्भों को अपडेट करने की आवश्यकता हो सकती है कि चार्ट डेटा सटीक बना रहे।

### क्या Aspose.Slides नवीनतम जावा संस्करणों के साथ संगत है?

नवीनतम जावा संस्करणों के साथ संगतता सुनिश्चित करने के लिए जावा के लिए Aspose.Slides को नियमित रूप से अपडेट किया जाता है। अद्यतनों की जांच अवश्य करें और इष्टतम प्रदर्शन और अनुकूलता के लिए लाइब्रेरी के नवीनतम संस्करण का उपयोग करें।

### क्या मैं एक ही बाहरी कार्यपुस्तिका को संदर्भित करने वाले एकाधिक चार्ट जोड़ सकता हूँ?

हां, आप अपनी प्रस्तुति में एकाधिक चार्ट जोड़ सकते हैं, सभी एक ही बाहरी कार्यपुस्तिका को संदर्भित करते हैं। आप जिस चार्ट को बनाना चाहते हैं, उसके लिए बस इस ट्यूटोरियल में बताए गए चरणों को दोहराएं।