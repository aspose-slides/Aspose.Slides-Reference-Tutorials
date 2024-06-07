---
title: जावा स्लाइड्स में स्वचालित पाई चार्ट स्लाइस रंग सेट करना
linktitle: जावा स्लाइड्स में स्वचालित पाई चार्ट स्लाइस रंग सेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java PowerPoint प्रस्तुतियों में स्वचालित स्लाइस रंगों के साथ गतिशील पाई चार्ट बनाना सीखें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 24
url: /hi/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

## जावा स्लाइड्स में स्वचालित पाई चार्ट स्लाइस रंग सेट करने का परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में पाई चार्ट कैसे बनाया जाता है और चार्ट के लिए स्वचालित स्लाइस रंग कैसे सेट किए जाते हैं। हम सोर्स कोड के साथ चरण-दर-चरण मार्गदर्शन प्रदान करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java प्रोजेक्ट में सेट अप है। आप Aspose वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं:[Java के लिए Aspose.Slides डाउनलोड करें](https://releases.aspose.com/slides/java/).

## चरण 1: आवश्यक पैकेज आयात करें

सबसे पहले, आपको Aspose.Slides for Java से आवश्यक पैकेज आयात करने होंगे:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन बनाएं

 उदाहरण प्रस्तुत करें`Presentation` नया पावरपॉइंट प्रेजेंटेशन बनाने के लिए क्लास का उपयोग करें:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## चरण 3: स्लाइड जोड़ें

प्रस्तुति की पहली स्लाइड तक पहुंचें और उसमें डिफ़ॉल्ट डेटा के साथ एक चार्ट जोड़ें:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## चरण 4: चार्ट शीर्षक सेट करें

चार्ट के लिए शीर्षक निर्धारित करें:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## चरण 5: चार्ट डेटा कॉन्फ़िगर करें

चार्ट को प्रथम श्रृंखला के मान दिखाने के लिए सेट करें और चार्ट डेटा कॉन्फ़िगर करें:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## चरण 6: श्रेणियाँ और श्रृंखला जोड़ें

चार्ट में नई श्रेणियाँ और श्रृंखलाएँ जोड़ें:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## चरण 7: श्रृंखला डेटा भरें

पाई चार्ट के लिए श्रृंखला डेटा भरें:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## चरण 8: विविध स्लाइस रंग सक्षम करें

पाई चार्ट के लिए विविध स्लाइस रंग सक्षम करें:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## चरण 9: प्रेजेंटेशन सहेजें

अंत में, प्रस्तुति को पावरपॉइंट फ़ाइल में सहेजें:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में स्वचालित पाई चार्ट स्लाइस रंग सेट करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation presentation = new Presentation();
try
{
	// पहली स्लाइड तक पहुंचें
	ISlide slides = presentation.getSlides().get_Item(0);
	// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// सेटिंग चार्ट शीर्षक
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// पहली श्रृंखला को मान दिखाएँ पर सेट करें
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// चार्ट डेटा शीट का इंडेक्स सेट करना
	int defaultWorksheetIndex = 0;
	// चार्ट डेटा वर्कशीट प्राप्त करना
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// डिफ़ॉल्ट रूप से जनरेटेड श्रृंखला और श्रेणियां हटाएं
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// नई श्रेणियाँ जोड़ना
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// नई श्रृंखला जोड़ना
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	//अब श्रृंखला डेटा भरा जा रहा है
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में पाई चार्ट सफलतापूर्वक बनाया है और इसे स्वचालित स्लाइस रंग देने के लिए कॉन्फ़िगर किया है। यह चरण-दर-चरण मार्गदर्शिका आपको इसे प्राप्त करने के लिए आवश्यक स्रोत कोड प्रदान करती है। आप आवश्यकतानुसार चार्ट और प्रस्तुति को और भी अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पाई चार्ट में अलग-अलग स्लाइस के रंगों को कैसे अनुकूलित कर सकता हूं?

 पाई चार्ट में अलग-अलग स्लाइस के रंगों को अनुकूलित करने के लिए, आप इसका उपयोग कर सकते हैं`getAutomaticSeriesColors` डिफ़ॉल्ट रंग योजना को पुनः प्राप्त करने और फिर आवश्यकतानुसार रंगों को संशोधित करने की विधि। यहाँ एक उदाहरण दिया गया है:

```java
//डिफ़ॉल्ट रंग योजना प्राप्त करें
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// आवश्यकतानुसार रंगों को संशोधित करें
colors.get_Item(0).setColor(Color.RED); // पहले स्लाइस का रंग लाल सेट करें
colors.get_Item(1).setColor(Color.BLUE); // दूसरे स्लाइस का रंग नीला सेट करें
// आवश्यकतानुसार अधिक रंग संशोधन जोड़ें
```

### मैं पाई चार्ट में लेजेंड कैसे जोड़ सकता हूँ?

 पाई चार्ट में लेजेंड जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`getLegend` विधि और इसे निम्नानुसार कॉन्फ़िगर करें:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // किंवदंती स्थिति सेट करें
legend.setOverlay(true); // चार्ट पर किंवदंती प्रदर्शित करें
```

### क्या मैं शीर्षक का फ़ॉन्ट और शैली बदल सकता हूँ?

हां, आप शीर्षक फ़ॉन्ट और शैली बदल सकते हैं। शीर्षक फ़ॉन्ट और शैली सेट करने के लिए निम्न कोड का उपयोग करें:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // फ़ॉन्ट आकार सेट करें
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // शीर्षक को बोल्ड बनाएं
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // शीर्षक को इटैलिक बनाएं
```

आप आवश्यकतानुसार फ़ॉन्ट का आकार, बोल्डनेस और इटैलिक शैली समायोजित कर सकते हैं।