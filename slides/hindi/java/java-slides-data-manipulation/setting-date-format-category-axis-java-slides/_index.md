---
title: जावा स्लाइड्स में श्रेणी अक्ष के लिए दिनांक प्रारूप सेट करना
linktitle: जावा स्लाइड्स में श्रेणी अक्ष के लिए दिनांक प्रारूप सेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint चार्ट में श्रेणी अक्ष के लिए दिनांक प्रारूप सेट करना सीखें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 26
url: /hi/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## जावा स्लाइड्स में श्रेणी अक्ष के लिए दिनांक प्रारूप सेट करने का परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint चार्ट में श्रेणी अक्ष के लिए दिनांक प्रारूप कैसे सेट करें। Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो आपको प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियाँ बनाने, हेरफेर करने और प्रबंधित करने की अनुमति देती है।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. Aspose.Slides for Java लाइब्रेरी (आप इसे यहां से डाउनलोड कर सकते हैं)[यहाँ](https://releases.aspose.com/slides/java/).
2. जावा विकास वातावरण की स्थापना.

## चरण 1: पावरपॉइंट प्रेजेंटेशन बनाएं

सबसे पहले, हमें एक पावरपॉइंट प्रेजेंटेशन बनाना होगा, जहाँ हम एक चार्ट जोड़ेंगे। सुनिश्चित करें कि आपने आवश्यक Aspose.Slides क्लासेस आयात कर ली हैं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: स्लाइड में चार्ट जोड़ें

अब, आइए PowerPoint स्लाइड में एक चार्ट जोड़ें। हम इस उदाहरण में एक एरिया चार्ट का उपयोग करेंगे।

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## चरण 3: चार्ट डेटा तैयार करें

हम चार्ट डेटा और श्रेणियाँ सेट अप करेंगे। इस उदाहरण में, हम दिनांक श्रेणियों का उपयोग करेंगे।

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// तिथि श्रेणियाँ जोड़ना
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// डेटा श्रृंखला जोड़ना
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## चरण 4: श्रेणी अक्ष को अनुकूलित करें
अब, दिनांकों को एक विशिष्ट प्रारूप (जैसे, yyyy) में प्रदर्शित करने के लिए श्रेणी अक्ष को अनुकूलित करें।

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## चरण 5: प्रस्तुति सहेजें
अंत में, पावरपॉइंट प्रेजेंटेशन को सेव करें।

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

बस! आपने Aspose.Slides for Java का उपयोग करके PowerPoint चार्ट में श्रेणी अक्ष के लिए सफलतापूर्वक दिनांक प्रारूप सेट कर लिया है।

## जावा स्लाइड्स में श्रेणी अक्ष के लिए दिनांक प्रारूप सेट करने के लिए पूर्ण स्रोत कोड

```java
	// दस्तावेज़ निर्देशिका का पथ.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##निष्कर्ष

आपने Aspose.Slides for Java का उपयोग करके Java स्लाइड चार्ट में श्रेणी अक्ष के लिए दिनांक प्रारूप को सफलतापूर्वक अनुकूलित किया है। यह आपको अपने चार्ट पर वांछित प्रारूप में दिनांक मान प्रस्तुत करने की अनुमति देता है। अपनी विशिष्ट आवश्यकताओं के आधार पर आगे के अनुकूलन विकल्पों का पता लगाने के लिए स्वतंत्र महसूस करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं श्रेणी अक्ष के लिए दिनांक प्रारूप कैसे बदलूं?

 श्रेणी अक्ष के लिए दिनांक प्रारूप बदलने के लिए, का उपयोग करें`setNumberFormat` श्रेणी अक्ष पर विधि और वांछित दिनांक प्रारूप पैटर्न प्रदान करें, जैसे "yyyy-MM-dd" या "MM/yyyy"। सेट करना सुनिश्चित करें`setNumberFormatLinkedToSource(false)` डिफ़ॉल्ट प्रारूप को ओवरराइड करने के लिए.

### क्या मैं एक ही प्रस्तुति में अलग-अलग चार्ट के लिए अलग-अलग दिनांक प्रारूप का उपयोग कर सकता हूँ?

हां, आप एक ही प्रस्तुति में अलग-अलग चार्ट में श्रेणी अक्षों के लिए अलग-अलग तिथि प्रारूप सेट कर सकते हैं। बस ज़रूरत के हिसाब से हर चार्ट के लिए श्रेणी अक्ष को कस्टमाइज़ करें।

### मैं चार्ट में अधिक डेटा बिंदु कैसे जोड़ूं?

 चार्ट में अधिक डेटा बिंदु जोड़ने के लिए, का उपयोग करें`getDataPoints().addDataPointForLineSeries`डेटा श्रृंखला पर विधि और डेटा मान प्रदान करें।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
