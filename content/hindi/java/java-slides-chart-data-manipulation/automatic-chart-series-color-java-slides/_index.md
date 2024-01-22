---
title: जावा स्लाइड्स में स्वचालित चार्ट श्रृंखला रंग
linktitle: जावा स्लाइड्स में स्वचालित चार्ट श्रृंखला रंग
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में स्वचालित श्रृंखला रंग के साथ डायनामिक चार्ट बनाना सीखें। अपने डेटा विज़ुअलाइज़ेशन को सहजता से बढ़ाएं।
type: docs
weight: 14
url: /hi/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## जावा के लिए Aspose.Slides में स्वचालित चार्ट श्रृंखला रंग का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके चार्ट के साथ पावरपॉइंट प्रेजेंटेशन कैसे बनाया जाए और चार्ट श्रृंखला के लिए स्वचालित भरण रंग कैसे सेट करें। स्वचालित भरण रंग आपके चार्ट को अधिक आकर्षक बना सकते हैं और लाइब्रेरी को आपके लिए रंग चुनने की अनुमति देकर आपका समय बचा सकते हैं।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Slides स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: एक नई प्रस्तुति बनाएं

सबसे पहले, हम एक नया पावरपॉइंट प्रेजेंटेशन बनाएंगे और उसमें एक स्लाइड जोड़ेंगे।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएं
Presentation presentation = new Presentation();
```

## चरण 2: स्लाइड में एक चार्ट जोड़ें

इसके बाद, हम स्लाइड में एक क्लस्टर्ड कॉलम चार्ट जोड़ेंगे। हम मान दिखाने के लिए पहली श्रृंखला भी सेट करेंगे।

```java
// पहली स्लाइड तक पहुंचें
ISlide slide = presentation.getSlides().get_Item(0);
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// मान दिखाने के लिए पहली श्रृंखला सेट करें
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## चरण 3: चार्ट डेटा पॉप्युलेट करें

अब, हम चार्ट को डेटा से भर देंगे। हम डिफ़ॉल्ट रूप से उत्पन्न श्रृंखला और श्रेणियों को हटाकर शुरुआत करेंगे और फिर नई श्रृंखला और श्रेणियां जोड़ेंगे।

```java
// चार्ट डेटा शीट का सूचकांक सेट करना
int defaultWorksheetIndex = 0;
//चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// डिफ़ॉल्ट रूप से जेनरेट की गई श्रृंखला और श्रेणियां हटाएं
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// नई श्रृंखला जोड़ी जा रही है
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// नई श्रेणियां जोड़ना
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## चरण 4: श्रृंखला डेटा पॉप्युलेट करें

हम शृंखला 1 और शृंखला 2 दोनों के लिए शृंखला डेटा भरेंगे।

```java
// पहली चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// अब श्रृंखला डेटा आबाद हो रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// दूसरी चार्ट श्रृंखला लें
series = chart.getChartData().getSeries().get_Item(1);
// अब श्रृंखला डेटा आबाद हो रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## चरण 5: श्रृंखला के लिए स्वचालित भरण रंग सेट करें

अब, चार्ट श्रृंखला के लिए स्वचालित भरण रंग सेट करें। इससे लाइब्रेरी हमारे लिए रंग चुनेगी।

```java
// श्रृंखला के लिए स्वचालित भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## चरण 6: प्रस्तुति सहेजें

अंत में, हम प्रस्तुतिकरण को चार्ट के साथ एक PowerPoint फ़ाइल में सहेजेंगे।

```java
// प्रस्तुतिकरण को चार्ट के साथ सहेजें
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में स्वचालित चार्ट श्रृंखला रंग के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएं
Presentation presentation = new Presentation();
try
{
	// पहली स्लाइड तक पहुंचें
	ISlide slide = presentation.getSlides().get_Item(0);
	// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// मान दिखाने के लिए पहली श्रृंखला सेट करें
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// चार्ट डेटा शीट का सूचकांक सेट करना
	int defaultWorksheetIndex = 0;
	//चार्ट डेटा वर्कशीट प्राप्त करना
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// डिफ़ॉल्ट रूप से जेनरेट की गई श्रृंखला और श्रेणियां हटाएं
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// नई श्रृंखला जोड़ी जा रही है
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// नई श्रेणियां जोड़ना
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// पहली चार्ट श्रृंखला लें
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// अब श्रृंखला डेटा आबाद हो रहा है
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// श्रृंखला के लिए स्वचालित भरण रंग सेट करना
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// दूसरी चार्ट श्रृंखला लें
	series = chart.getChartData().getSeries().get_Item(1);
	// अब श्रृंखला डेटा आबाद हो रहा है
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// श्रृंखला के लिए भरण रंग सेट करना
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// प्रस्तुतिकरण को चार्ट के साथ सहेजें
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके चार्ट के साथ पावरपॉइंट प्रेजेंटेशन कैसे बनाएं और चार्ट श्रृंखला के लिए स्वचालित भरण रंग कैसे सेट करें। स्वचालित रंग आपके चार्ट की दृश्य अपील को बढ़ा सकते हैं और आपकी प्रस्तुतियों को अधिक आकर्षक बना सकते हैं। आप अपनी विशिष्ट आवश्यकताओं के लिए आवश्यकतानुसार चार्ट को और अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides में चार्ट श्रृंखला के लिए स्वचालित भरण रंग कैसे सेट करूं?

जावा के लिए Aspose.Slides में चार्ट श्रृंखला के लिए स्वचालित भरण रंग सेट करने के लिए, निम्नलिखित कोड का उपयोग करें:

```java
// श्रृंखला के लिए स्वचालित भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

यह कोड लाइब्रेरी को चार्ट श्रृंखला के लिए स्वचालित रूप से रंग चुनने देगा।

### यदि आवश्यक हो तो क्या मैं चार्ट के रंगों को अनुकूलित कर सकता हूँ?

 हाँ, आप आवश्यकतानुसार चार्ट रंगों को अनुकूलित कर सकते हैं। दिए गए उदाहरण में, हमने स्वचालित भरण रंगों का उपयोग किया है, लेकिन आप संशोधित करके विशिष्ट रंग सेट कर सकते हैं`FillType` और`SolidFillColor` श्रृंखला के प्रारूप के गुण.

### मैं चार्ट में अतिरिक्त श्रृंखला या श्रेणियाँ कैसे जोड़ सकता हूँ?

 चार्ट में अतिरिक्त श्रृंखला या श्रेणियां जोड़ने के लिए, इसका उपयोग करें`getSeries()` और`getCategories()` चार्ट के तरीके`ChartData` वस्तु। आप उनके डेटा और लेबल निर्दिष्ट करके नई श्रृंखला और श्रेणियां जोड़ सकते हैं।

### क्या चार्ट और लेबल को आगे प्रारूपित करना संभव है?

हां, आप आवश्यकतानुसार चार्ट, श्रृंखला और लेबल को और प्रारूपित कर सकते हैं। जावा के लिए Aspose.Slides फ़ॉन्ट, रंग, शैली और बहुत कुछ सहित चार्ट के लिए व्यापक स्वरूपण विकल्प प्रदान करता है। आप फ़ॉर्मेटिंग विकल्पों पर अधिक विवरण के लिए दस्तावेज़ का पता लगा सकते हैं।

### जावा के लिए Aspose.Slides के साथ काम करने के बारे में मुझे अधिक जानकारी कहां मिल सकती है?

 जावा के लिए Aspose.Slides पर अधिक जानकारी और विस्तृत दस्तावेज़ीकरण के लिए, आप संदर्भ दस्तावेज़ पर जा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).