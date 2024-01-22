---
title: जावा स्लाइड्स में स्वचालित पाई चार्ट स्लाइस रंग सेट करना
linktitle: जावा स्लाइड्स में स्वचालित पाई चार्ट स्लाइस रंग सेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा पावरपॉइंट प्रस्तुतियों में स्वचालित स्लाइस रंगों के साथ डायनामिक पाई चार्ट बनाना सीखें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 24
url: /hi/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

## जावा स्लाइड्स में स्वचालित पाई चार्ट स्लाइस रंग सेट करने का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रेजेंटेशन में पाई चार्ट बनाने और चार्ट के लिए स्वचालित स्लाइस रंग सेट करने का तरीका जानेंगे। हम स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शन प्रदान करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित और सेटअप है। आप लाइब्रेरी को Aspose वेबसाइट से डाउनलोड कर सकते हैं:[जावा के लिए Aspose.Slides डाउनलोड करें](https://releases.aspose.com/slides/java/).

## चरण 1: आवश्यक पैकेज आयात करें

सबसे पहले, आपको जावा के लिए Aspose.Slides से आवश्यक पैकेज आयात करने होंगे:

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

## चरण 2: एक पावरपॉइंट प्रेजेंटेशन बनाएं

 त्वरित करें`Presentation` एक नई पावरपॉइंट प्रेजेंटेशन बनाने के लिए क्लास:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## चरण 3: एक स्लाइड जोड़ें

प्रेजेंटेशन की पहली स्लाइड तक पहुंचें और उसमें डिफ़ॉल्ट डेटा के साथ एक चार्ट जोड़ें:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## चरण 4: चार्ट शीर्षक सेट करें

चार्ट के लिए एक शीर्षक सेट करें:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## चरण 5: चार्ट डेटा कॉन्फ़िगर करें

पहली श्रृंखला के लिए मान दिखाने के लिए चार्ट सेट करें और चार्ट डेटा कॉन्फ़िगर करें:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## चरण 6: श्रेणियाँ और श्रृंखला जोड़ें

चार्ट में नई श्रेणियां और श्रृंखला जोड़ें:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## चरण 7: श्रृंखला डेटा पॉप्युलेट करें

पाई चार्ट के लिए श्रृंखला डेटा पॉप्युलेट करें:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## चरण 8: विभिन्न स्लाइस रंग सक्षम करें

पाई चार्ट के लिए विभिन्न स्लाइस रंग सक्षम करें:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## चरण 9: प्रस्तुति सहेजें

अंत में, प्रेजेंटेशन को PowerPoint फ़ाइल में सहेजें:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में स्वचालित पाई चार्ट स्लाइस रंग सेट करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// त्वरित प्रस्तुति वर्ग जो पीपीटीएक्स फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation();
try
{
	// पहली स्लाइड तक पहुंचें
	ISlide slides = presentation.getSlides().get_Item(0);
	// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// चार्ट शीर्षक सेट करना
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// मान दिखाने के लिए पहली श्रृंखला सेट करें
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// चार्ट डेटा शीट का सूचकांक सेट करना
	int defaultWorksheetIndex = 0;
	//चार्ट डेटा वर्कशीट प्राप्त करना
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// डिफ़ॉल्ट रूप से जेनरेट की गई श्रृंखला और श्रेणियां हटाएं
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// नई श्रेणियां जोड़ना
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// नई श्रृंखला जोड़ी जा रही है
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// अब श्रृंखला डेटा आबाद हो रहा है
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

आपने Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रेजेंटेशन में सफलतापूर्वक एक पाई चार्ट बनाया है और इसे स्वचालित स्लाइस रंगों के लिए कॉन्फ़िगर किया है। यह चरण-दर-चरण मार्गदर्शिका आपको इसे प्राप्त करने के लिए आवश्यक स्रोत कोड प्रदान करती है। आप आवश्यकतानुसार चार्ट और प्रस्तुति को और अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पाई चार्ट में अलग-अलग स्लाइस के रंगों को कैसे अनुकूलित कर सकता हूं?

 पाई चार्ट में अलग-अलग स्लाइस के रंगों को अनुकूलित करने के लिए, आप इसका उपयोग कर सकते हैं`getAutomaticSeriesColors`डिफ़ॉल्ट रंग योजना को पुनः प्राप्त करने और फिर आवश्यकतानुसार रंगों को संशोधित करने की विधि। यहाँ एक उदाहरण है:

```java
// डिफ़ॉल्ट रंग योजना प्राप्त करें
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// आवश्यकतानुसार रंगों को संशोधित करें
colors.get_Item(0).setColor(Color.RED); // पहले टुकड़े का रंग लाल पर सेट करें
colors.get_Item(1).setColor(Color.BLUE); // दूसरे स्लाइस का रंग नीला पर सेट करें
// आवश्यकतानुसार अधिक रंग संशोधन जोड़ें
```

### मैं पाई चार्ट में लेजेंड कैसे जोड़ सकता हूँ?

 पाई चार्ट में एक लेजेंड जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`getLegend` विधि और इसे निम्नानुसार कॉन्फ़िगर करें:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // किंवदंती स्थिति निर्धारित करें
legend.setOverlay(true); // चार्ट पर किंवदंती प्रदर्शित करें
```

### क्या मैं शीर्षक का फ़ॉन्ट और शैली बदल सकता हूँ?

हाँ, आप शीर्षक फ़ॉन्ट और शैली बदल सकते हैं। शीर्षक फ़ॉन्ट और शैली सेट करने के लिए निम्नलिखित कोड का उपयोग करें:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // फ़ॉन्ट आकार सेट करें
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // शीर्षक को बोल्ड बनाएं
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // शीर्षक को इटैलिक बनाएं
```

आप आवश्यकतानुसार फ़ॉन्ट आकार, बोल्डनेस और इटैलिक शैली को समायोजित कर सकते हैं।