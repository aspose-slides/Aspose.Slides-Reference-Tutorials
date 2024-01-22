---
title: जावा स्लाइड्स में सनबर्स्ट चार्ट
linktitle: जावा स्लाइड्स में सनबर्स्ट चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ जावा स्लाइड्स में आश्चर्यजनक सनबर्स्ट चार्ट बनाएं। चरण-दर-चरण चार्ट निर्माण और डेटा हेरफेर सीखें।
type: docs
weight: 16
url: /hi/java/chart-elements/sunburst-chart-java-slides/
---

## Aspose.Slides के साथ जावा स्लाइड्स में सनबर्स्ट चार्ट का परिचय

इस ट्यूटोरियल में, आप सीखेंगे कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में सनबर्स्ट चार्ट कैसे बनाया जाए। सनबर्स्ट चार्ट एक रेडियल चार्ट है जिसका उपयोग पदानुक्रमित डेटा का प्रतिनिधित्व करने के लिए किया जाता है। हम स्रोत कोड के साथ चरण-दर-चरण निर्देश प्रदान करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित और कॉन्फ़िगर है। आप यहां से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: आवश्यक पुस्तकालय आयात करें

सबसे पहले, Aspose.Slides के साथ काम करने के लिए आवश्यक लाइब्रेरी आयात करें और अपने जावा एप्लिकेशन में एक सनबर्स्ट चार्ट बनाएं।

```java
import com.aspose.slides.*;
```

## चरण 2: प्रेजेंटेशन आरंभ करें

पावरपॉइंट प्रेजेंटेशन प्रारंभ करें और वह निर्देशिका निर्दिष्ट करें जहां आपकी प्रेजेंटेशन फ़ाइल सहेजी जाएगी।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## चरण 3: सनबर्स्ट चार्ट बनाएं

एक स्लाइड पर सनबर्स्ट चार्ट बनाएं। हम चार्ट की स्थिति (X, Y) और आयाम (चौड़ाई, ऊंचाई) निर्दिष्ट करते हैं।

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## चरण 4: चार्ट डेटा तैयार करें

चार्ट से किसी भी मौजूदा श्रेणी और श्रृंखला डेटा को साफ़ करें, और चार्ट के लिए एक डेटा वर्कबुक बनाएं।

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## चरण 5: चार्ट पदानुक्रम को परिभाषित करें

सनबर्स्ट चार्ट की पदानुक्रमित संरचना को परिभाषित करें। आप शाखाओं, तनों और पत्तियों को श्रेणियों के रूप में जोड़ सकते हैं।

```java
// शाखा 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// शाखा 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## चरण 6: चार्ट में डेटा जोड़ें

सनबर्स्ट चार्ट श्रृंखला में डेटा बिंदु जोड़ें।

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## चरण 7: प्रस्तुति सहेजें

अंत में, प्रस्तुति को सनबर्स्ट चार्ट के साथ सहेजें।

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में सनबर्स्ट चार्ट के लिए संपूर्ण स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//शाखा 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//शाखा 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में सनबर्स्ट चार्ट कैसे बनाया जाता है। आपने देखा है कि प्रेजेंटेशन को कैसे आरंभ किया जाए, चार्ट कैसे बनाया जाए, चार्ट पदानुक्रम को परिभाषित किया जाए, डेटा बिंदु जोड़े जाएं और प्रेजेंटेशन को कैसे बचाया जाए। अब आप इस ज्ञान का उपयोग अपने जावा अनुप्रयोगों में इंटरैक्टिव और सूचनात्मक सनबर्स्ट चार्ट बनाने के लिए कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं सनबर्स्ट चार्ट के स्वरूप को कैसे अनुकूलित करूँ?

आप रंग, लेबल और शैलियों जैसे गुणों को संशोधित करके सनबर्स्ट चार्ट की उपस्थिति को अनुकूलित कर सकते हैं। विस्तृत अनुकूलन विकल्पों के लिए Aspose.Slides दस्तावेज़ देखें।

### क्या मैं चार्ट में और डेटा पॉइंट जोड़ सकता हूँ?

 हाँ, आप इसका उपयोग करके चार्ट में अधिक डेटा बिंदु जोड़ सकते हैं`series.getDataPoints().addDataPointForSunburstSeries()` प्रत्येक डेटा बिंदु के लिए विधि जिसे आप शामिल करना चाहते हैं।

### मैं सनबर्स्ट चार्ट में टूलटिप्स कैसे जोड़ सकता हूँ?

सनबर्स्ट चार्ट में टूलटिप्स जोड़ने के लिए, आप चार्ट सेगमेंट पर होवर करते समय अतिरिक्त जानकारी, जैसे मान या विवरण प्रदर्शित करने के लिए डेटा लेबल प्रारूप सेट कर सकते हैं।

### क्या हाइपरलिंक के साथ इंटरैक्टिव सनबर्स्ट चार्ट बनाना संभव है?

हां, आप विशिष्ट चार्ट तत्वों या खंडों में हाइपरलिंक जोड़कर हाइपरलिंक के साथ इंटरैक्टिव सनबर्स्ट चार्ट बना सकते हैं। हाइपरलिंक जोड़ने के विवरण के लिए Aspose.Slides दस्तावेज़ देखें।