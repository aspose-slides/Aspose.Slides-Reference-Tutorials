---
title: जावा स्लाइड्स में चार्ट डेटा लेबल की वास्तविक स्थिति प्राप्त करें
linktitle: जावा स्लाइड्स में चार्ट डेटा लेबल की वास्तविक स्थिति प्राप्त करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में चार्ट डेटा लेबल की वास्तविक स्थिति कैसे प्राप्त करें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 18
url: /hi/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

## जावा स्लाइड्स में चार्ट डेटा लेबल की वास्तविक स्थिति प्राप्त करने का परिचय

इस ट्यूटोरियल में, आप सीखेंगे कि जावा के लिए Aspose.Slides का उपयोग करके चार्ट डेटा लेबल की वास्तविक स्थिति कैसे प्राप्त करें। हम एक जावा प्रोग्राम बनाएंगे जो एक चार्ट के साथ एक पावरपॉइंट प्रेजेंटेशन तैयार करता है, डेटा लेबल को कस्टमाइज़ करता है, और फिर इन डेटा लेबल की स्थिति का प्रतिनिधित्व करने वाले आकार जोड़ता है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Slides सेटअप है।

## चरण 1: एक पावरपॉइंट प्रेजेंटेशन बनाएं

सबसे पहले, आइए एक नया पावरपॉइंट प्रेजेंटेशन बनाएं और उसमें एक चार्ट जोड़ें। हम बाद में ट्यूटोरियल में चार्ट के डेटा लेबल को कस्टमाइज़ करेंगे।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## चरण 2: डेटा लेबल अनुकूलित करें
अब, आइए चार्ट श्रृंखला के लिए डेटा लेबल को कस्टमाइज़ करें। हम उनकी स्थिति निर्धारित करेंगे और मूल्य दिखाएंगे।

```java
try {
    // ... (पिछला कोड)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (शेष कोड)
} finally {
    if (pres != null) pres.dispose();
}
```

## चरण 3: डेटा लेबल की वास्तविक स्थिति प्राप्त करें
इस चरण में, हम चार्ट श्रृंखला के डेटा बिंदुओं के माध्यम से पुनरावृति करेंगे और डेटा लेबल की वास्तविक स्थिति को पुनः प्राप्त करेंगे जिनका मान 4 से अधिक है। फिर हम इन स्थितियों का प्रतिनिधित्व करने के लिए दीर्घवृत्त जोड़ देंगे।

```java
try {
    // ... (पिछला कोड)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (शेष कोड)
} finally {
    if (pres != null) pres.dispose();
}
```

## चरण 4: प्रस्तुति सहेजें
अंत में, जेनरेट की गई प्रस्तुति को एक फ़ाइल में सहेजें।

```java
try {
    // ... (पिछला कोड)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## जावा स्लाइड्स में चार्ट डेटा लेबल की वास्तविक स्थिति प्राप्त करने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//करने के लिए
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में चार्ट डेटा लेबल की वास्तविक स्थिति कैसे प्राप्त करें। अब आप इस ज्ञान का उपयोग अनुकूलित डेटा लेबल और उनकी स्थिति के दृश्य प्रतिनिधित्व के साथ अपनी पावरपॉइंट प्रस्तुतियों को बढ़ाने के लिए कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट में डेटा लेबल कैसे अनुकूलित कर सकता हूं?

 किसी चार्ट में डेटा लेबल को कस्टमाइज़ करने के लिए, आप इसका उपयोग कर सकते हैं`setDefaultDataLabelFormat` चार्ट श्रृंखला पर विधि और स्थिति और दृश्यता जैसे गुण सेट करें। उदाहरण के लिए:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### मैं डेटा लेबल स्थिति दर्शाने के लिए आकृतियाँ कैसे जोड़ सकता हूँ?

 आप चार्ट श्रृंखला के डेटा बिंदुओं के माध्यम से पुनरावृति कर सकते हैं और इसका उपयोग कर सकते हैं`getActualX`, `getActualY`, `getActualWidth` , और`getActualHeight`डेटा लेबल की स्थिति जानने के तरीके। फिर, आप इसका उपयोग करके आकृतियाँ जोड़ सकते हैं`addAutoShape` तरीका। यहाँ एक उदाहरण है:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### मैं जेनरेट की गई प्रस्तुति को कैसे सहेज सकता हूँ?

 आप इसका उपयोग करके जेनरेट किए गए प्रेजेंटेशन को सेव कर सकते हैं`save` तरीका। वांछित फ़ाइल पथ और प्रदान करें`SaveFormat` पैरामीटर के रूप में. उदाहरण के लिए:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```