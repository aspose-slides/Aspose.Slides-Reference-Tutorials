---
"description": "Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में स्वचालित श्रृंखला रंग के साथ गतिशील चार्ट बनाना सीखें। अपने डेटा विज़ुअलाइज़ेशन को सहजता से बढ़ाएँ।"
"linktitle": "जावा स्लाइड्स में स्वचालित चार्ट श्रृंखला रंग"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में स्वचालित चार्ट श्रृंखला रंग"
"url": "/hi/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में स्वचालित चार्ट श्रृंखला रंग


## Aspose.Slides for Java में स्वचालित चार्ट श्रृंखला रंग का परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके चार्ट के साथ PowerPoint प्रेजेंटेशन कैसे बनाया जाता है और चार्ट श्रृंखला के लिए स्वचालित भरण रंग कैसे सेट किए जाते हैं। स्वचालित भरण रंग आपके चार्ट को अधिक आकर्षक बना सकते हैं और लाइब्रेरी को आपके लिए रंग चुनने देकर आपका समय बचा सकते हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: एक नई प्रस्तुति बनाएँ

सबसे पहले, हम एक नया पावरपॉइंट प्रेजेंटेशन बनाएंगे और उसमें एक स्लाइड जोड़ेंगे।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
```

## चरण 2: स्लाइड में चार्ट जोड़ें

इसके बाद, हम स्लाइड में एक क्लस्टर्ड कॉलम चार्ट जोड़ेंगे। हम मान दिखाने के लिए पहली श्रृंखला भी सेट करेंगे।

```java
// पहली स्लाइड तक पहुंचें
ISlide slide = presentation.getSlides().get_Item(0);
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// पहली श्रृंखला को मान दिखाएँ पर सेट करें
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## चरण 3: चार्ट डेटा भरें

अब, हम चार्ट को डेटा से भरेंगे। हम डिफ़ॉल्ट रूप से जेनरेट की गई श्रृंखला और श्रेणियों को हटाकर शुरू करेंगे और फिर नई श्रृंखला और श्रेणियां जोड़ेंगे।

```java
// चार्ट डेटा शीट का इंडेक्स सेट करना
int defaultWorksheetIndex = 0;
// चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// डिफ़ॉल्ट रूप से जनरेटेड श्रृंखला और श्रेणियां हटाएं
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// नई श्रृंखला जोड़ना
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// नई श्रेणियाँ जोड़ना
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## चरण 4: श्रृंखला डेटा भरें

हम श्रृंखला 1 और श्रृंखला 2 दोनों के लिए श्रृंखला डेटा भरेंगे।

```java
// पहली चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// अब श्रृंखला डेटा भरा जा रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// दूसरा चार्ट श्रृंखला लें
series = chart.getChartData().getSeries().get_Item(1);
// अब श्रृंखला डेटा भरा जा रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## चरण 5: श्रृंखला के लिए स्वचालित भरण रंग सेट करें

अब, चार्ट श्रृंखला के लिए स्वचालित भरण रंग सेट करें। इससे लाइब्रेरी हमारे लिए रंग चुन लेगी।

```java
// श्रृंखला के लिए स्वचालित भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## चरण 6: प्रस्तुति सहेजें

अंत में, हम चार्ट के साथ प्रस्तुति को पावरपॉइंट फ़ाइल में सहेज लेंगे।

```java
// चार्ट के साथ प्रस्तुति सहेजें
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में स्वचालित चार्ट श्रृंखला रंग के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
try
{
	// पहली स्लाइड तक पहुंचें
	ISlide slide = presentation.getSlides().get_Item(0);
	// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// पहली श्रृंखला को मान दिखाएँ पर सेट करें
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// चार्ट डेटा शीट का इंडेक्स सेट करना
	int defaultWorksheetIndex = 0;
	// चार्ट डेटा वर्कशीट प्राप्त करना
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// डिफ़ॉल्ट रूप से जनरेटेड श्रृंखला और श्रेणियां हटाएं
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// नई श्रृंखला जोड़ना
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// नई श्रेणियाँ जोड़ना
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// पहली चार्ट श्रृंखला लें
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// अब श्रृंखला डेटा भरा जा रहा है
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// श्रृंखला के लिए स्वचालित भरण रंग सेट करना
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// दूसरा चार्ट श्रृंखला लें
	series = chart.getChartData().getSeries().get_Item(1);
	// अब श्रृंखला डेटा भरा जा रहा है
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// श्रृंखला के लिए भरण रंग सेट करना
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// चार्ट के साथ प्रस्तुति सहेजें
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके चार्ट के साथ PowerPoint प्रेजेंटेशन कैसे बनाया जाता है और चार्ट श्रृंखला के लिए स्वचालित भरण रंग कैसे सेट किए जाते हैं। स्वचालित रंग आपके चार्ट की दृश्य अपील को बढ़ा सकते हैं और आपकी प्रस्तुतियों को अधिक आकर्षक बना सकते हैं। आप अपनी विशिष्ट आवश्यकताओं के अनुसार चार्ट को और भी अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Aspose.Slides for Java में चार्ट श्रृंखला के लिए स्वचालित भरण रंग कैसे सेट करूं?

Aspose.Slides for Java में चार्ट श्रृंखला के लिए स्वचालित भरण रंग सेट करने के लिए, निम्नलिखित कोड का उपयोग करें:

```java
// श्रृंखला के लिए स्वचालित भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

यह कोड लाइब्रेरी को चार्ट श्रृंखला के लिए स्वचालित रूप से रंग चुनने देगा।

### यदि आवश्यक हो तो क्या मैं चार्ट के रंगों को अनुकूलित कर सकता हूँ?

हां, आप चार्ट के रंगों को आवश्यकतानुसार कस्टमाइज़ कर सकते हैं। दिए गए उदाहरण में, हमने स्वचालित भरण रंगों का उपयोग किया है, लेकिन आप चार्ट के रंग को संशोधित करके विशिष्ट रंग सेट कर सकते हैं। `FillType` और `SolidFillColor` श्रृंखला के प्रारूप के गुण.

### मैं चार्ट में अतिरिक्त श्रृंखला या श्रेणियां कैसे जोड़ सकता हूं?

चार्ट में अतिरिक्त श्रृंखला या श्रेणियाँ जोड़ने के लिए, का उपयोग करें `getSeries()` और `getCategories()` चार्ट के तरीके `ChartData` आप उनके डेटा और लेबल निर्दिष्ट करके नई श्रृंखला और श्रेणियां जोड़ सकते हैं।

### क्या चार्ट और लेबल को और अधिक प्रारूपित करना संभव है?

हां, आप चार्ट, सीरीज और लेबल को आवश्यकतानुसार और भी प्रारूपित कर सकते हैं। Aspose.Slides for Java चार्ट के लिए व्यापक प्रारूपण विकल्प प्रदान करता है, जिसमें फ़ॉन्ट, रंग, शैलियाँ और बहुत कुछ शामिल है। प्रारूपण विकल्पों के बारे में अधिक जानकारी के लिए आप दस्तावेज़ देख सकते हैं।

### मैं Java के लिए Aspose.Slides के साथ काम करने के बारे में अधिक जानकारी कहां पा सकता हूं?

Aspose.Slides for Java पर अधिक जानकारी और विस्तृत दस्तावेज़ीकरण के लिए, आप संदर्भ दस्तावेज़ देख सकते हैं [यहाँ](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}