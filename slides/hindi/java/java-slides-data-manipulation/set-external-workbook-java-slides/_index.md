---
title: जावा स्लाइड्स में बाह्य कार्यपुस्तिका सेट करें
linktitle: जावा स्लाइड्स में बाह्य कार्यपुस्तिका सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java Slides में बाहरी कार्यपुस्तिकाएँ सेट करना सीखें। Excel डेटा एकीकरण के साथ गतिशील प्रस्तुतियाँ बनाएँ।
weight: 19
url: /hi/java/data-manipulation/set-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में बाह्य कार्यपुस्तिका सेट करें


## जावा स्लाइड्स में बाह्य कार्यपुस्तिका सेट करने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके Java Slides में बाहरी वर्कबुक सेट करने का तरीका जानेंगे। आप सीखेंगे कि एक चार्ट के साथ PowerPoint प्रेजेंटेशन कैसे बनाया जाता है जो बाहरी Excel वर्कबुक से डेटा को संदर्भित करता है। इस गाइड के अंत तक, आपको अपने Java Slides प्रेजेंटेशन में बाहरी डेटा को एकीकृत करने के तरीके के बारे में स्पष्ट समझ होगी।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
- Aspose.Slides for Java लाइब्रेरी आपके प्रोजेक्ट में जोड़ दी गई।
- एक Excel कार्यपुस्तिका जिसमें वह डेटा है जिसे आप अपनी प्रस्तुति में संदर्भित करना चाहते हैं।

## चरण 1: एक नई प्रस्तुति बनाएँ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

हम Aspose.Slides का उपयोग करके एक नया पावरपॉइंट प्रेजेंटेशन बनाकर शुरुआत करते हैं।

## चरण 2: चार्ट जोड़ें

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

इसके बाद, हम प्रेजेंटेशन में पाई चार्ट डालते हैं। आप चार्ट के प्रकार और स्थिति को आवश्यकतानुसार अनुकूलित कर सकते हैं।

## चरण 3: बाहरी कार्यपुस्तिका तक पहुँचें

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 बाहरी कार्यपुस्तिका तक पहुँचने के लिए, हम उपयोग करते हैं`setExternalWorkbook` विधि और डेटा युक्त एक्सेल कार्यपुस्तिका के लिए पथ प्रदान करें।

## चरण 4: चार्ट डेटा बाँधें

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

हम श्रृंखला और श्रेणियों के लिए सेल संदर्भ निर्दिष्ट करके चार्ट को बाह्य कार्यपुस्तिका के डेटा से जोड़ते हैं।

## चरण 5: प्रस्तुति सहेजें

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

अंत में, हम प्रस्तुति को बाह्य कार्यपुस्तिका संदर्भ के साथ PowerPoint फ़ाइल के रूप में सहेजते हैं।

## जावा स्लाइड्स में सेट एक्सटर्नल वर्कबुक के लिए पूरा सोर्स कोड

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

इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides का उपयोग करके Java Slides में बाहरी वर्कबुक कैसे सेट करें। अब आप ऐसे प्रेजेंटेशन बना सकते हैं जो एक्सेल वर्कबुक से डेटा को गतिशील रूप से संदर्भित करते हैं, जिससे आपकी स्लाइड्स की लचीलापन और अन्तरक्रियाशीलता बढ़ जाती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?

Aspose.Slides for Java को आपके Java प्रोजेक्ट में लाइब्रेरी जोड़कर इंस्टॉल किया जा सकता है। आप Aspose वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं और डॉक्यूमेंटेशन में दिए गए इंस्टॉलेशन निर्देशों का पालन कर सकते हैं।

### क्या मैं बाहरी कार्यपुस्तिकाओं के साथ विभिन्न चार्ट प्रकारों का उपयोग कर सकता हूँ?

हां, आप Aspose.Slides द्वारा समर्थित विभिन्न चार्ट प्रकारों का उपयोग कर सकते हैं और उन्हें बाहरी कार्यपुस्तिकाओं से डेटा से बांध सकते हैं। आपके द्वारा चुने गए चार्ट प्रकार के आधार पर प्रक्रिया थोड़ी भिन्न हो सकती है।

### यदि मेरी बाह्य कार्यपुस्तिका की डेटा संरचना बदल जाए तो क्या होगा?

यदि आपकी बाह्य कार्यपुस्तिका के डेटा की संरचना बदलती है, तो आपको यह सुनिश्चित करने के लिए अपने जावा कोड में सेल संदर्भों को अद्यतन करने की आवश्यकता हो सकती है कि चार्ट डेटा सटीक बना रहे।

### क्या Aspose.Slides नवीनतम Java संस्करणों के साथ संगत है?

Aspose.Slides for Java को नियमित रूप से अपडेट किया जाता है ताकि नवीनतम Java संस्करणों के साथ संगतता सुनिश्चित की जा सके। अपडेट की जांच करना सुनिश्चित करें और इष्टतम प्रदर्शन और संगतता के लिए लाइब्रेरी के नवीनतम संस्करण का उपयोग करें।

### क्या मैं एक ही बाह्य कार्यपुस्तिका को संदर्भित करते हुए एकाधिक चार्ट जोड़ सकता हूँ?

हां, आप अपनी प्रस्तुति में कई चार्ट जोड़ सकते हैं, जो सभी एक ही बाहरी कार्यपुस्तिका को संदर्भित करते हैं। बस प्रत्येक चार्ट के लिए इस ट्यूटोरियल में बताए गए चरणों को दोहराएं जिसे आप बनाना चाहते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
