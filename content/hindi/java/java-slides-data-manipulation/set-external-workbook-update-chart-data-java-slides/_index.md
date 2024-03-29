---
title: जावा स्लाइड्स में अद्यतन चार्ट डेटा के साथ बाहरी कार्यपुस्तिका सेट करें
linktitle: जावा स्लाइड्स में अद्यतन चार्ट डेटा के साथ बाहरी कार्यपुस्तिका सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में बाहरी कार्यपुस्तिकाएँ सेट करने और चार्ट डेटा अपडेट करने का तरीका जानें। अपने पावरपॉइंट ऑटोमेशन कौशल को बढ़ाएं।
type: docs
weight: 20
url: /hi/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

## जावा स्लाइड्स में अपडेट चार्ट डेटा के साथ बाहरी वर्कबुक सेट करने का परिचय

इस व्यापक गाइड में, हम आपको जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में अद्यतन चार्ट डेटा के साथ एक बाहरी कार्यपुस्तिका सेट करने की प्रक्रिया के बारे में बताएंगे। यह शक्तिशाली लाइब्रेरी आपको PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देती है, जिससे बाहरी स्रोत से चार्ट डेटा को अपडेट करने जैसे कार्यों को स्वचालित करना आसान हो जाता है। इस ट्यूटोरियल के अंत तक, आपको इस बात की स्पष्ट समझ हो जाएगी कि चरण-दर-चरण निर्देशों और संलग्न जावा कोड के साथ इस कार्य को कैसे पूरा किया जाए।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1.  जावा के लिए Aspose.Slides: आपके पास जावा लाइब्रेरी के लिए Aspose.Slides स्थापित होना चाहिए। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

2. जावा विकास वातावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा विकास वातावरण स्थापित है।

## चरण 1: एक नई प्रस्तुति बनाएं

आरंभ करने के लिए, आइए Java के लिए Aspose.Slides का उपयोग करके एक नया PowerPoint प्रेजेंटेशन बनाएं। ऐसा करने के लिए यहां जावा कोड है:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: एक चार्ट जोड़ें

अब, आइए अपनी प्रस्तुति में एक चार्ट जोड़ें। हम इस उदाहरण में एक पाई चार्ट बनाएंगे:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## चरण 3: बाहरी कार्यपुस्तिका सेट करें

यह वह जगह है जहां हम बाहरी कार्यपुस्तिका को अपने चार्ट के लिए डेटा स्रोत के रूप में सेट करते हैं। आपको बाहरी कार्यपुस्तिका में यूआरएल प्रदान करना होगा, भले ही वह अभी मौजूद न हो:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://पथ/नहीं/मौजूद है", ग़लत);
```

## चरण 4: प्रस्तुति सहेजें

अंत में, प्रस्तुतिकरण को अद्यतन चार्ट डेटा के साथ सहेजें:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में अद्यतन चार्ट डेटा के साथ सेट बाहरी कार्यपुस्तिका के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://पथ/नहीं/मौजूद है", ग़लत);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

बधाई हो! आपने सीखा है कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में अद्यतन चार्ट डेटा के साथ एक बाहरी कार्यपुस्तिका कैसे सेट की जाती है। यह बाहरी डेटा स्रोतों से आपके पावरपॉइंट प्रस्तुतियों में चार्ट को गतिशील रूप से अपडेट करने के लिए अविश्वसनीय रूप से उपयोगी हो सकता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट के लिए बाह्य कार्यपुस्तिका डेटा को कैसे अद्यतन कर सकता हूँ?

चार्ट के लिए बाहरी कार्यपुस्तिका डेटा को अपडेट करने के लिए, आपको बस निर्दिष्ट यूआरएल पर बाहरी कार्यपुस्तिका में डेटा को संशोधित करना होगा। अगली बार जब आप प्रेजेंटेशन खोलेंगे, तो जावा के लिए Aspose.Slides बाहरी कार्यपुस्तिका से अद्यतन डेटा लाएगा और तदनुसार चार्ट को अपडेट करेगा।

### क्या मैं बाहरी कार्यपुस्तिका के रूप में स्थानीय फ़ाइल का उपयोग कर सकता हूँ?

हां, आप यूआरएल के बजाय फ़ाइल पथ प्रदान करके स्थानीय फ़ाइल को बाहरी कार्यपुस्तिका के रूप में उपयोग कर सकते हैं। बस सुनिश्चित करें कि फ़ाइल पथ सही है और आपके जावा एप्लिकेशन से पहुंच योग्य है।

### क्या जावा के लिए Aspose.Slides के साथ बाहरी कार्यपुस्तिकाओं का उपयोग करने की कोई सीमाएँ हैं?

जबकि बाहरी कार्यपुस्तिकाओं का उपयोग एक शक्तिशाली सुविधा है, ध्यान रखें कि बाहरी कार्यपुस्तिका के डेटा की उपलब्धता प्रदान किए गए यूआरएल या फ़ाइल पथ पर इसकी पहुंच पर निर्भर करती है। सुनिश्चित करें कि डेटा पुनर्प्राप्ति समस्याओं से बचने के लिए जब आप प्रेजेंटेशन खोलें तो बाहरी डेटा स्रोत उपलब्ध है।

### क्या मैं बाह्य कार्यपुस्तिका सेट करने के बाद चार्ट स्वरूप को अनुकूलित कर सकता हूँ?

हां, आप बाहरी कार्यपुस्तिका सेट करने के बाद भी चार्ट के स्वरूप को अनुकूलित कर सकते हैं, जिसमें उसका शीर्षक, लेबल, रंग और बहुत कुछ शामिल है। जावा के लिए Aspose.Slides आपकी आवश्यकताओं को पूरा करने के लिए व्यापक चार्ट फ़ॉर्मेटिंग विकल्प प्रदान करता है।

### जावा के लिए Aspose.Slides के लिए मुझे अधिक दस्तावेज़ और संसाधन कहां मिल सकते हैं?

 विस्तृत दस्तावेज़ीकरण और अतिरिक्त संसाधनों के लिए, जावा दस्तावेज़ीकरण के लिए Aspose.Slides पर जाएँ[यहाँ](https://reference.aspose.com/slides/java/).