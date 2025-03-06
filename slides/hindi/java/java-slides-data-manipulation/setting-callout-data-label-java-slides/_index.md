---
title: जावा स्लाइड्स में डेटा लेबल के लिए कॉलआउट सेट करना
linktitle: जावा स्लाइड्स में डेटा लेबल के लिए कॉलआउट सेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java में डेटा लेबल के लिए कॉलआउट सेट अप करना सीखें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 25
url: /hi/java/data-manipulation/setting-callout-data-label-java-slides/
---

## Aspose.Slides for Java में डेटा लेबल के लिए कॉलआउट सेट करने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके चार्ट में डेटा लेबल के लिए कॉलआउट सेट अप करने का तरीका दिखाएंगे। कॉलआउट आपके चार्ट में विशिष्ट डेटा बिंदुओं को हाइलाइट करने के लिए उपयोगी हो सकते हैं। हम कोड को चरण दर चरण समझाएँगे और आवश्यक स्रोत कोड प्रदान करेंगे।

## आवश्यक शर्तें

- आपके पास Aspose.Slides for Java स्थापित होना चाहिए।
- एक जावा प्रोजेक्ट बनाएं और अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी जोड़ें।

## चरण 1: एक प्रस्तुति बनाएं और एक चार्ट जोड़ें

 सबसे पहले, हमें एक प्रेजेंटेशन बनाना होगा और स्लाइड में एक चार्ट जोड़ना होगा।`"Your Document Directory"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## चरण 2: चार्ट कॉन्फ़िगर करें

इसके बाद, हम लेजेंड, श्रृंखला और श्रेणियों जैसे गुण सेट करके चार्ट को कॉन्फ़िगर करेंगे।

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// श्रृंखला और श्रेणियाँ कॉन्फ़िगर करें (आप श्रृंखला और श्रेणियों की संख्या समायोजित कर सकते हैं)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // यहां डेटा बिंदु जोड़ें
        // ...
        i++;
    }
    categoryIndex++;
}
```

## चरण 3: डेटा लेबल अनुकूलित करें

अब, हम डेटा लेबल को कस्टमाइज़ करेंगे, जिसमें अंतिम श्रृंखला के लिए कॉलआउट सेट करना भी शामिल है।

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // डेटा बिंदु स्वरूपण अनुकूलित करें (भरण, रेखा, आदि)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //लेबल स्वरूपण अनुकूलित करें (फ़ॉन्ट, भरण, आदि)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // कॉलआउट सक्षम करें
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## चरण 4: प्रस्तुति सहेजें

अंत में, कॉन्फ़िगर किए गए चार्ट के साथ प्रस्तुति को सहेजें।

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

अब, आपने Aspose.Slides for Java का उपयोग करके चार्ट में डेटा लेबल के लिए कॉलआउट सफलतापूर्वक सेट कर लिए हैं। अपने विशिष्ट चार्ट और डेटा आवश्यकताओं के अनुसार कोड को कस्टमाइज़ करें।

## जावा स्लाइड्स में डेटा लेबल के लिए कॉलआउट सेट करने हेतु पूर्ण स्रोत कोड

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
pres.save("chart.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Slides for Java का उपयोग करके चार्ट में डेटा लेबल के लिए कॉलआउट सेट अप करने का तरीका खोजा है। कॉलआउट आपके चार्ट और प्रस्तुतियों में विशिष्ट डेटा बिंदुओं पर जोर देने के लिए मूल्यवान उपकरण हैं। हमने इस अनुकूलन को प्राप्त करने में आपकी सहायता के लिए स्रोत कोड के साथ-साथ चरण-दर-चरण मार्गदर्शिका प्रदान की है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं डेटा लेबल का स्वरूप कैसे अनुकूलित करूँ?

डेटा लेबल की उपस्थिति को अनुकूलित करने के लिए, आप फ़ॉन्ट, भरण और रेखा शैलियों जैसे गुणों को संशोधित कर सकते हैं। उदाहरण के लिए:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### मैं डेटा लेबल के लिए कॉलआउट कैसे सक्षम या अक्षम कर सकता हूं?

 डेटा लेबल के लिए कॉलआउट सक्षम या अक्षम करने के लिए, का उपयोग करें`setShowLabelAsDataCallout` विधि. इसे इस पर सेट करें`true` कॉलआउट सक्षम करने के लिए और`false`उन्हें निष्क्रिय करने के लिए.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // कॉलआउट सक्षम करें
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // कॉलआउट अक्षम करें
```

### क्या मैं डेटा लेबल के लिए लीडर लाइनों को अनुकूलित कर सकता हूँ?

हां, आप लाइन स्टाइल, रंग और चौड़ाई जैसे गुणों का उपयोग करके डेटा लेबल के लिए लीडर लाइनों को कस्टमाइज़ कर सकते हैं। उदाहरण के लिए:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // लीडर लाइन सक्षम करें
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Aspose.Slides for Java में डेटा लेबल और कॉलआउट के लिए ये कुछ सामान्य अनुकूलन विकल्प हैं। आप अपनी विशिष्ट आवश्यकताओं के अनुसार उपस्थिति को और भी अनुकूलित कर सकते हैं।