---
title: जावा स्लाइड्स में रडार चार्ट बनाना
linktitle: जावा स्लाइड्स में रडार चार्ट बनाना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा पावरपॉइंट प्रस्तुतियों में रडार चार्ट बनाना सीखें।
type: docs
weight: 10
url: /hi/java/chart-creation/radar-chart-creating-java-slides/
---

## जावा स्लाइड्स में रडार चार्ट बनाने का परिचय

इस ट्यूटोरियल में, हम जावा एपीआई के लिए Aspose.Slides का उपयोग करके रडार चार्ट बनाने की प्रक्रिया में आपका मार्गदर्शन करेंगे। रडार चार्ट डेटा को गोलाकार पैटर्न में देखने के लिए उपयोगी होते हैं, जिससे कई डेटा श्रृंखलाओं की तुलना करना आसान हो जाता है। हम जावा स्रोत कोड के साथ चरण-दर-चरण निर्देश प्रदान करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास जावा लाइब्रेरी के लिए Aspose.Slides आपके प्रोजेक्ट में एकीकृत है। आप यहां से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: प्रस्तुतिकरण सेट करना

आइए एक नया पावरपॉइंट प्रेजेंटेशन सेट करके और उसमें एक स्लाइड जोड़कर शुरुआत करें।

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## चरण 2: एक रडार चार्ट जोड़ना

इसके बाद, हम स्लाइड में एक रडार चार्ट जोड़ेंगे। हम चार्ट की स्थिति और आयाम निर्दिष्ट करेंगे।

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## चरण 3: चार्ट डेटा सेट करना

अब हम चार्ट डेटा सेट करेंगे। इसमें डेटा वर्कबुक बनाना, श्रेणियां जोड़ना और श्रृंखला जोड़ना शामिल है।

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// चार्ट शीर्षक सेट करें
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// डिफ़ॉल्ट रूप से जेनरेट की गई श्रृंखला और श्रेणियां हटाएं
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// नई श्रेणियां जोड़ना
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// नई श्रृंखला जोड़ी जा रही है
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## चरण 4: श्रृंखला डेटा को पॉप्युलेट करना

अब, हम अपने रडार चार्ट के लिए श्रृंखला डेटा भरेंगे।

```java
// शृंखला 1 के लिए शृंखला डेटा पॉप्युलेट करें
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// श्रृंखला का रंग सेट करें
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// शृंखला 2 के लिए शृंखला डेटा पॉप्युलेट करें
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// श्रृंखला का रंग सेट करें
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## चरण 5: एक्सिस और लेजेंड्स को अनुकूलित करना

आइए अपने रडार चार्ट के लिए अक्ष और लेजेंड्स को अनुकूलित करें।

```java
// लीजेंड स्थिति सेट करें
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// श्रेणी अक्ष टेक्स्ट गुण सेट करना
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// महापुरूष पाठ गुण सेट करना
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// वैल्यू एक्सिस टेक्स्ट गुण सेट करना
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// मान अक्ष संख्या स्वरूप सेट करना
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// चार्ट प्रमुख इकाई मान सेट करना
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## चरण 6: प्रस्तुति को सहेजना

अंत में, तैयार प्रस्तुति को रडार चार्ट के साथ सहेजें

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

इतना ही! आपने Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रेजेंटेशन में सफलतापूर्वक एक रडार चार्ट बनाया है। अब आप अपनी विशिष्ट आवश्यकताओं के अनुरूप इस उदाहरण को और अधिक अनुकूलित कर सकते हैं।

## जावा स्लाइड्स में रडार चार्ट बनाने के लिए संपूर्ण स्रोत कोड

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// पहली स्लाइड तक पहुंचें
	ISlide sld = pres.getSlides().get_Item(0);
	// रडार चार्ट जोड़ें
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// चार्ट डेटा शीट का सूचकांक सेट करना
	int defaultWorksheetIndex = 0;
	// चार्ट डेटा वर्कशीट प्राप्त करना
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// चार्ट शीर्षक सेट करें
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// डिफ़ॉल्ट रूप से जेनरेट की गई श्रृंखला और श्रेणियां हटाएं
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// नई श्रेणियां जोड़ना
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// नई श्रृंखला जोड़ी जा रही है
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// अब श्रृंखला डेटा आबाद हो रहा है
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// श्रृंखला का रंग सेट करें
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// अब एक और श्रृंखला का डेटा आबाद हो रहा है
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// श्रृंखला का रंग सेट करें
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// लीजेंड स्थिति सेट करें
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// श्रेणी अक्ष टेक्स्ट गुण सेट करना
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// महापुरूष पाठ गुण सेट करना
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// वैल्यू एक्सिस टेक्स्ट गुण सेट करना
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// मान अक्ष संख्या स्वरूप सेट करना
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// चार्ट प्रमुख इकाई मान सेट करना
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// उत्पन्न प्रस्तुति सहेजें
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रेजेंटेशन में रडार चार्ट कैसे बनाया जाता है। आप अपने जावा अनुप्रयोगों में अपने डेटा को प्रभावी ढंग से देखने और प्रस्तुत करने के लिए इन अवधारणाओं को लागू कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट का शीर्षक कैसे बदल सकता हूँ?

चार्ट शीर्षक बदलने के लिए, निम्नलिखित पंक्ति को संशोधित करें:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### क्या मैं रडार चार्ट में अधिक डेटा श्रृंखला जोड़ सकता हूँ?

हाँ, आप प्रत्येक अतिरिक्त श्रृंखला के लिए "चरण 3" और "चरण 4" में दिए गए चरणों का पालन करके अधिक डेटा श्रृंखला जोड़ सकते हैं।

### मैं चार्ट के रंगों को कैसे अनुकूलित करूँ?

 आप सेट करने वाली रेखाओं को संशोधित करके श्रृंखला के रंगों को अनुकूलित कर सकते हैं`SolidFillColor` प्रत्येक श्रृंखला के लिए संपत्ति. उदाहरण के लिए:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### मैं अक्ष लेबल और स्वरूपण कैसे बदल सकता हूँ?

फ़ॉन्ट आकार और रंग सहित अक्ष लेबल और फ़ॉर्मेटिंग को अनुकूलित करने के लिए "चरण 5" देखें।

### मैं चार्ट को किसी भिन्न फ़ाइल स्वरूप में कैसे सहेजूँ?

 आप फ़ाइल एक्सटेंशन को संशोधित करके आउटपुट स्वरूप बदल सकते हैं`outPath` परिवर्तनीय और उपयुक्त का उपयोग करना`SaveFormat` . उदाहरण के लिए, पीडीएफ के रूप में सहेजने के लिए, उपयोग करें`SaveFormat.Pdf`.