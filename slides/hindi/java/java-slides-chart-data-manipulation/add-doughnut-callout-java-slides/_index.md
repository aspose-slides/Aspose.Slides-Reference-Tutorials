---
title: जावा स्लाइड्स में डोनट कॉलआउट जोड़ें
linktitle: जावा स्लाइड्स में डोनट कॉलआउट जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java स्लाइड में डोनट कॉलआउट जोड़ना सीखें। बेहतर प्रस्तुतियों के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 12
url: /hi/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java का उपयोग करके Java स्लाइड्स में डोनट कॉलआउट जोड़ने का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके जावा में स्लाइड में डोनट कॉलआउट जोड़ने की प्रक्रिया से अवगत कराएँगे। डोनट कॉलआउट एक चार्ट तत्व है जिसका उपयोग डोनट चार्ट में विशिष्ट डेटा बिंदुओं को हाइलाइट करने के लिए किया जा सकता है। हम आपकी सुविधा के लिए आपको चरण-दर-चरण निर्देश और संपूर्ण स्रोत कोड प्रदान करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. जावा विकास पर्यावरण
2. Aspose.Slides for Java लाइब्रेरी
3. एकीकृत विकास वातावरण (IDE) जैसे कि एक्लिप्स या इंटेलीज आईडिया
4. एक पावरपॉइंट प्रेजेंटेशन जहां आप डोनट कॉलआउट जोड़ना चाहते हैं

## चरण 1: अपना जावा प्रोजेक्ट सेट अप करें

1. अपने चुने हुए IDE में एक नया जावा प्रोजेक्ट बनाएं।
2. Aspose.Slides for Java लाइब्रेरी को अपनी परियोजना में निर्भरता के रूप में जोड़ें।

## चरण 2: प्रस्तुति आरंभ करें

आरंभ करने के लिए, आपको एक पावरपॉइंट प्रेजेंटेशन आरंभ करना होगा और एक स्लाइड बनानी होगी जहाँ आप डोनट कॉलआउट जोड़ना चाहते हैं। इसे प्राप्त करने के लिए कोड यहाँ दिया गया है:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 प्रतिस्थापित करना सुनिश्चित करें`"Your Document Directory"` अपनी पावरपॉइंट प्रेजेंटेशन फ़ाइल के वास्तविक पथ के साथ।

## चरण 3: डोनट चार्ट बनाएं

इसके बाद, आप स्लाइड पर डोनट चार्ट बनाएंगे। आप अपनी ज़रूरतों के हिसाब से चार्ट की स्थिति और आकार को कस्टमाइज़ कर सकते हैं। डोनट चार्ट जोड़ने के लिए कोड यहाँ दिया गया है:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## चरण 4: डोनट चार्ट को अनुकूलित करें

अब, डोनट चार्ट को कस्टमाइज़ करने का समय आ गया है। हम लेजेंड को हटाने, छेद के आकार को कॉन्फ़िगर करने और पहले स्लाइस कोण को समायोजित करने जैसे विभिन्न गुण सेट करेंगे। यहाँ कोड है:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

यह कोड स्निपेट डोनट चार्ट के लिए गुण सेट करता है। आप अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए मान समायोजित कर सकते हैं।

## चरण 5: डोनट चार्ट में डेटा जोड़ें

अब, डोनट चार्ट में डेटा जोड़ते हैं। हम डेटा बिंदुओं की उपस्थिति को भी अनुकूलित करेंगे। इसे पूरा करने के लिए कोड यहाँ दिया गया है:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // डेटा बिंदु उपस्थिति को यहां अनुकूलित करें
        i++;
    }
    categoryIndex++;
}
```

इस कोड में, हम डोनट चार्ट में श्रेणियाँ और डेटा पॉइंट जोड़ रहे हैं। आप आवश्यकतानुसार डेटा पॉइंट के स्वरूप को और भी अनुकूलित कर सकते हैं।

## चरण 6: प्रेजेंटेशन सहेजें

अंत में, डोनट कॉलआउट जोड़ने के बाद अपनी प्रेजेंटेशन को सेव करना न भूलें। प्रेजेंटेशन को सेव करने के लिए कोड इस प्रकार है:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 प्रतिस्थापित करना सुनिश्चित करें`"chart.pptx"` अपने इच्छित फ़ाइल नाम के साथ.

बधाई हो! आपने Aspose.Slides for Java का उपयोग करके Java स्लाइड में डोनट कॉलआउट सफलतापूर्वक जोड़ लिया है। अब आप डोनट चार्ट और कॉलआउट के साथ पावरपॉइंट प्रेजेंटेशन बनाने के लिए अपना Java एप्लिकेशन चला सकते हैं।

## जावा स्लाइड्स में डोनट कॉलआउट जोड़ने के लिए पूरा स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(सत्य);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Slides for Java का उपयोग करके जावा स्लाइड में डोनट कॉलआउट जोड़ने की प्रक्रिया को कवर किया है। आपने डोनट चार्ट बनाना, उसका स्वरूप अनुकूलित करना और डेटा पॉइंट जोड़ना सीखा है। इस शक्तिशाली लाइब्रेरी के साथ अपनी प्रस्तुतियों को और बेहतर बनाने और अधिक चार्टिंग विकल्पों का पता लगाने के लिए स्वतंत्र महसूस करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं डोनट कॉलआउट का स्वरूप कैसे बदल सकता हूँ?

आप चार्ट में डेटा बिंदुओं के गुणों को संशोधित करके डोनट कॉलआउट की उपस्थिति को अनुकूलित कर सकते हैं। दिए गए कोड में, आप देख सकते हैं कि डेटा बिंदुओं के भरण रंग, रेखा रंग, फ़ॉन्ट शैली और अन्य विशेषताओं को कैसे सेट किया जाए।

### क्या मैं डोनट चार्ट में और अधिक डेटा बिंदु जोड़ सकता हूँ?

हां, आप डोनट चार्ट में जितने चाहें उतने डेटा पॉइंट जोड़ सकते हैं। कोड में लूप को बस बढ़ाएं जहां श्रेणियां और डेटा पॉइंट जोड़े जाते हैं, और उचित डेटा और फ़ॉर्मेटिंग प्रदान करें।

### मैं स्लाइड पर डोनट चार्ट की स्थिति और आकार को कैसे समायोजित कर सकता हूं?

 आप डोनट चार्ट में पैरामीटर संशोधित करके इसकी स्थिति और आकार बदल सकते हैं।`addChart` विधि। उस विधि में चार संख्याएं क्रमशः चार्ट के ऊपरी-बाएं कोने के X और Y निर्देशांक तथा उसकी चौड़ाई और ऊंचाई के अनुरूप होती हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
