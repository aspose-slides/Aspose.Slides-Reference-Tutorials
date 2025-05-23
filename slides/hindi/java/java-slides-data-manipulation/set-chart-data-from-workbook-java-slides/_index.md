---
"description": "Aspose.Slides का उपयोग करके जावा स्लाइड्स में एक्सेल वर्कबुक से चार्ट डेटा सेट करना सीखें। गतिशील प्रस्तुतियों के लिए कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।"
"linktitle": "जावा स्लाइड्स में वर्कबुक से चार्ट डेटा सेट करें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में वर्कबुक से चार्ट डेटा सेट करें"
"url": "/hi/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में वर्कबुक से चार्ट डेटा सेट करें


## जावा स्लाइड्स में वर्कबुक से चार्ट डेटा सेट करने का परिचय

Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है। यह PowerPoint स्लाइड बनाने, हेरफेर करने और प्रबंधित करने के लिए व्यापक सुविधाएँ प्रदान करता है। प्रस्तुतियों के साथ काम करते समय एक सामान्य आवश्यकता बाहरी डेटा स्रोत, जैसे कि Excel कार्यपुस्तिका से गतिशील रूप से चार्ट डेटा सेट करना है। इस ट्यूटोरियल में, हम यह प्रदर्शित करेंगे कि जावा का उपयोग करके इसे कैसे प्राप्त किया जाए।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
- Aspose.Slides for Java लाइब्रेरी आपके प्रोजेक्ट में जोड़ दी गई।
- एक Excel कार्यपुस्तिका जिसमें वह डेटा हो जिसे आप चार्ट के लिए उपयोग करना चाहते हैं।

## चरण 1: एक प्रस्तुति बनाएं

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

हम Java के लिए Aspose.Slides का उपयोग करके एक नया पावरपॉइंट प्रेजेंटेशन बनाकर शुरुआत करते हैं।

## चरण 2: चार्ट जोड़ें

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

इसके बाद, हम प्रस्तुति में किसी एक स्लाइड में चार्ट जोड़ते हैं। इस उदाहरण में, हम पाई चार्ट जोड़ रहे हैं, लेकिन आप अपनी ज़रूरत के हिसाब से चार्ट का प्रकार चुन सकते हैं।

## चरण 3: चार्ट डेटा साफ़ करें

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

हम चार्ट से मौजूदा डेटा को हटा देते हैं ताकि उसे Excel कार्यपुस्तिका से नए डेटा के लिए तैयार किया जा सके।

## चरण 4: एक्सेल वर्कबुक लोड करें

```java
Workbook workbook = new Workbook("Your Document Directory";
```

हम एक्सेल वर्कबुक को लोड करते हैं जिसमें वह डेटा होता है जिसे हम चार्ट के लिए उपयोग करना चाहते हैं। `"book1.xlsx"` अपनी एक्सेल फ़ाइल के पथ के साथ.

## चरण 5: वर्कबुक स्ट्रीम को चार्ट डेटा में लिखें

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

हम एक्सेल वर्कबुक डेटा को स्ट्रीम में परिवर्तित करते हैं और उसे चार्ट डेटा में लिखते हैं।

## चरण 6: चार्ट डेटा रेंज सेट करें

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

हम Excel कार्यपुस्तिका से उन कक्षों की श्रेणी निर्दिष्ट करते हैं जिन्हें चार्ट के लिए डेटा के रूप में उपयोग किया जाना चाहिए। अपने डेटा के लिए आवश्यकतानुसार श्रेणी समायोजित करें।

## चरण 7: चार्ट श्रृंखला अनुकूलित करें

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

आप अपनी आवश्यकताओं के अनुसार चार्ट श्रृंखला के विभिन्न गुणों को अनुकूलित कर सकते हैं। इस उदाहरण में, हमने चार्ट श्रृंखला के लिए विभिन्न रंगों को सक्षम किया है।

## चरण 8: प्रस्तुति सहेजें

```java
pres.save(outPath, SaveFormat.Pptx);
```

अंत में, हम अद्यतन चार्ट डेटा के साथ प्रस्तुति को निर्दिष्ट आउटपुट पथ पर सहेजते हैं।

## जावा स्लाइड्स में वर्कबुक से चार्ट डेटा सेट करने के लिए पूरा स्रोत कोड

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
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

इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java लाइब्रेरी का उपयोग करके Java स्लाइड्स में Excel वर्कबुक से चार्ट डेटा कैसे सेट किया जाता है। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए स्रोत कोड उदाहरणों का उपयोग करके, आप आसानी से अपने PowerPoint प्रस्तुतियों में गतिशील चार्ट डेटा को एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं अपनी प्रस्तुति में चार्ट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

आप रंग, फ़ॉन्ट, लेबल और अन्य जैसे गुणों को संशोधित करके चार्ट की उपस्थिति को अनुकूलित कर सकते हैं। चार्ट अनुकूलन विकल्पों पर विस्तृत जानकारी के लिए Aspose.Slides for Java दस्तावेज़ देखें।

### क्या मैं चार्ट के लिए किसी भिन्न एक्सेल फ़ाइल से डेटा का उपयोग कर सकता हूँ?

हां, आप कोड में कार्यपुस्तिका लोड करते समय सही फ़ाइल पथ निर्दिष्ट करके किसी भी एक्सेल फ़ाइल से डेटा का उपयोग कर सकते हैं।

### मैं Aspose.Slides for Java के साथ अन्य किस प्रकार के चार्ट बना सकता हूँ?

Aspose.Slides for Java विभिन्न चार्ट प्रकारों का समर्थन करता है, जिसमें बार चार्ट, लाइन चार्ट, स्कैटर चार्ट और बहुत कुछ शामिल है। आप वह चार्ट प्रकार चुन सकते हैं जो आपकी डेटा प्रस्तुति आवश्यकताओं के लिए सबसे उपयुक्त हो।

### क्या चल रहे प्रस्तुतीकरण में चार्ट डेटा को गतिशील रूप से अद्यतन करना संभव है?

हां, आप अंतर्निहित कार्यपुस्तिका को संशोधित करके और फिर चार्ट डेटा को ताज़ा करके प्रस्तुति में चार्ट डेटा को गतिशील रूप से अपडेट कर सकते हैं।

### मैं Aspose.Slides for Java के साथ काम करने के लिए और अधिक उदाहरण और संसाधन कहां पा सकता हूं?

आप अतिरिक्त उदाहरण और संसाधन देख सकते हैं [Aspose वेबसाइट](https://www.aspose.com/)इसके अतिरिक्त, Aspose.Slides for Java दस्तावेज़ लाइब्रेरी के साथ काम करने पर व्यापक मार्गदर्शन प्रदान करता है।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}