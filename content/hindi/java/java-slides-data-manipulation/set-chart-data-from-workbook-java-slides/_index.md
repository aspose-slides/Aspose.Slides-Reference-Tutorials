---
title: जावा स्लाइड्स में वर्कबुक से चार्ट डेटा सेट करें
linktitle: जावा स्लाइड्स में वर्कबुक से चार्ट डेटा सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके जावा स्लाइड्स में एक्सेल वर्कबुक से चार्ट डेटा सेट करना सीखें। गतिशील प्रस्तुतियों के लिए कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 15
url: /hi/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## जावा स्लाइड्स में वर्कबुक से चार्ट डेटा सेट करने का परिचय

जावा के लिए Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है। यह PowerPoint स्लाइड बनाने, हेरफेर करने और प्रबंधित करने के लिए व्यापक सुविधाएँ प्रदान करता है। प्रस्तुतियों के साथ काम करते समय एक सामान्य आवश्यकता एक्सेल वर्कबुक जैसे बाहरी डेटा स्रोत से चार्ट डेटा को गतिशील रूप से सेट करना है। इस ट्यूटोरियल में, हम प्रदर्शित करेंगे कि जावा का उपयोग करके इसे कैसे प्राप्त किया जाए।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
- जावा लाइब्रेरी के लिए Aspose.Slides आपके प्रोजेक्ट में जोड़ा गया।
- उस डेटा के साथ एक एक्सेल वर्कबुक जिसे आप चार्ट के लिए उपयोग करना चाहते हैं।

## चरण 1: एक प्रेजेंटेशन बनाएं

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
```

हम Java के लिए Aspose.Slides का उपयोग करके एक नई PowerPoint प्रस्तुति बनाकर शुरुआत करते हैं।

## चरण 2: एक चार्ट जोड़ें

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

इसके बाद, हम प्रेजेंटेशन में किसी एक स्लाइड में एक चार्ट जोड़ते हैं। इस उदाहरण में, हम एक पाई चार्ट जोड़ रहे हैं, लेकिन आप वह चार्ट प्रकार चुन सकते हैं जो आपकी आवश्यकताओं के अनुरूप हो।

## चरण 3: चार्ट डेटा साफ़ करें

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

हम एक्सेल वर्कबुक से नए डेटा के लिए तैयार करने के लिए चार्ट से किसी भी मौजूदा डेटा को साफ़ करते हैं।

## चरण 4: एक्सेल वर्कबुक लोड करें

```java
Workbook workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
```

 हम एक्सेल वर्कबुक को लोड करते हैं जिसमें वह डेटा होता है जिसे हम चार्ट के लिए उपयोग करना चाहते हैं। प्रतिस्थापित करें`"book1.xlsx"` आपकी एक्सेल फ़ाइल के पथ के साथ।

## चरण 5: डेटा को चार्ट करने के लिए वर्कबुक स्ट्रीम लिखें

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

हम एक्सेल वर्कबुक डेटा को एक स्ट्रीम में परिवर्तित करते हैं और इसे चार्ट डेटा में लिखते हैं।

## चरण 6: चार्ट डेटा रेंज सेट करें

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

हम Excel कार्यपुस्तिका से कक्षों की श्रेणी निर्दिष्ट करते हैं जिनका उपयोग चार्ट के लिए डेटा के रूप में किया जाना चाहिए। अपने डेटा के लिए आवश्यकतानुसार सीमा समायोजित करें।

## चरण 7: चार्ट श्रृंखला को अनुकूलित करें

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

आप अपनी आवश्यकताओं से मेल खाने के लिए चार्ट श्रृंखला के विभिन्न गुणों को अनुकूलित कर सकते हैं। इस उदाहरण में, हम चार्ट श्रृंखला के लिए विभिन्न रंगों को सक्षम करते हैं।

## चरण 8: प्रस्तुति सहेजें

```java
pres.save(outPath, SaveFormat.Pptx);
```

अंत में, हम प्रेजेंटेशन को अद्यतन चार्ट डेटा के साथ निर्दिष्ट आउटपुट पथ पर सहेजते हैं।

## जावा स्लाइड्स में वर्कबुक से सेट चार्ट डेटा के लिए पूर्ण स्रोत कोड

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि जावा लाइब्रेरी के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में एक्सेल वर्कबुक से चार्ट डेटा कैसे सेट किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड उदाहरणों का उपयोग करके, आप आसानी से डायनामिक चार्ट डेटा को अपनी पावरपॉइंट प्रस्तुतियों में एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं अपनी प्रस्तुति में चार्ट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

आप रंग, फ़ॉन्ट, लेबल और अन्य गुणों को संशोधित करके चार्ट के स्वरूप को अनुकूलित कर सकते हैं। चार्ट अनुकूलन विकल्पों पर विस्तृत जानकारी के लिए जावा दस्तावेज़ के लिए Aspose.Slides देखें।

### क्या मैं चार्ट के लिए किसी भिन्न एक्सेल फ़ाइल से डेटा का उपयोग कर सकता हूँ?

हां, आप कोड में कार्यपुस्तिका लोड करते समय सही फ़ाइल पथ निर्दिष्ट करके किसी भी एक्सेल फ़ाइल से डेटा का उपयोग कर सकते हैं।

### जावा के लिए Aspose.Slides के साथ मैं अन्य किस प्रकार के चार्ट बना सकता हूं?

जावा के लिए Aspose.Slides विभिन्न चार्ट प्रकारों का समर्थन करता है, जिसमें बार चार्ट, लाइन चार्ट, स्कैटर चार्ट और बहुत कुछ शामिल हैं। आप वह चार्ट प्रकार चुन सकते हैं जो आपकी डेटा प्रतिनिधित्व आवश्यकताओं के लिए सबसे उपयुक्त हो।

### क्या चालू प्रेजेंटेशन में चार्ट डेटा को गतिशील रूप से अपडेट करना संभव है?

हाँ, आप अंतर्निहित कार्यपुस्तिका को संशोधित करके और फिर चार्ट डेटा को ताज़ा करके किसी प्रस्तुति में चार्ट डेटा को गतिशील रूप से अपडेट कर सकते हैं।

### जावा के लिए Aspose.Slides के साथ काम करने के लिए मुझे और अधिक उदाहरण और संसाधन कहां मिल सकते हैं?

 आप पर अतिरिक्त उदाहरण और संसाधन तलाश सकते हैं[Aspose वेबसाइट](https://www.aspose.com/). इसके अतिरिक्त, जावा दस्तावेज़ीकरण के लिए Aspose.Slides लाइब्रेरी के साथ काम करने पर व्यापक मार्गदर्शन प्रदान करता है।