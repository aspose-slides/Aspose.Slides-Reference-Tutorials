---
title: जावा स्लाइड्स में सामान्य चार्ट
linktitle: जावा स्लाइड्स में सामान्य चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides के साथ जावा स्लाइड्स में सामान्य चार्ट बनाएं। PowerPoint प्रस्तुतियों में चार्ट बनाने, अनुकूलित करने और सहेजने के लिए चरण-दर-चरण मार्गदर्शिका और स्रोत कोड।
type: docs
weight: 21
url: /hi/java/chart-data-manipulation/normal-charts-java-slides/
---

## जावा स्लाइड्स में सामान्य चार्ट का परिचय

इस ट्यूटोरियल में, हम जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में सामान्य चार्ट बनाने की प्रक्रिया के बारे में जानेंगे। पावरपॉइंट प्रेजेंटेशन में क्लस्टर्ड कॉलम चार्ट बनाने का तरीका दिखाने के लिए हम स्रोत कोड के साथ चरण-दर-चरण निर्देशों का उपयोग करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1. जावा एपीआई के लिए Aspose.Slides स्थापित।
2. एक जावा विकास वातावरण स्थापित किया गया।
3. जावा प्रोग्रामिंग का बुनियादी ज्ञान।

## चरण 1: परियोजना की स्थापना

सुनिश्चित करें कि आपके पास अपने प्रोजेक्ट के लिए एक निर्देशिका है। आइए इसे कोड में बताए अनुसार "आपकी दस्तावेज़ निर्देशिका" कहें। आप इसे अपनी प्रोजेक्ट निर्देशिका के वास्तविक पथ से बदल सकते हैं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि यह पहले से मौजूद नहीं है तो निर्देशिका बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## चरण 2: एक प्रस्तुति बनाना

अब, एक PowerPoint प्रेजेंटेशन बनाएं और उसकी पहली स्लाइड तक पहुंचें।

```java
// त्वरित प्रस्तुति वर्ग जो पीपीटीएक्स फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation();
// पहली स्लाइड तक पहुंचें
ISlide sld = pres.getSlides().get_Item(0);
```

## चरण 3: एक चार्ट जोड़ना

हम स्लाइड में एक क्लस्टर्ड कॉलम चार्ट जोड़ेंगे और उसका शीर्षक सेट करेंगे।

```java
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// चार्ट शीर्षक सेट करना
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## चरण 4: चार्ट डेटा सेट करना

इसके बाद, हम श्रृंखला और श्रेणियों को परिभाषित करके चार्ट डेटा सेट करेंगे।

```java
// मान दिखाने के लिए पहली श्रृंखला सेट करें
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

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

## चरण 5: श्रृंखला डेटा को पॉप्युलेट करना

अब, आइए चार्ट के लिए श्रृंखला डेटा बिंदुओं को पॉप्युलेट करें।

```java
// पहली चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// श्रृंखला डेटा पॉप्युलेट करना
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// श्रृंखला के लिए भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// दूसरी चार्ट श्रृंखला लें
series = chart.getChartData().getSeries().get_Item(1);

// श्रृंखला डेटा पॉप्युलेट करना
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// श्रृंखला के लिए भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## चरण 6: लेबल को अनुकूलित करना

आइए चार्ट श्रृंखला के लिए डेटा लेबल को अनुकूलित करें।

```java
// पहला लेबल श्रेणी का नाम दिखाएगा
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// श्रृंखला नाम और विभाजक के साथ तीसरे लेबल के लिए मान दिखाएँ
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## चरण 7: प्रस्तुति को सहेजना

अंत में, चार्ट के साथ प्रेजेंटेशन को अपनी प्रोजेक्ट निर्देशिका में सहेजें।

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

इतना ही! आपने Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रेजेंटेशन में एक क्लस्टर्ड कॉलम चार्ट सफलतापूर्वक बनाया है। आप अपनी आवश्यकताओं के अनुसार इस चार्ट को और अधिक अनुकूलित कर सकते हैं।

## जावा स्लाइड्स में सामान्य चार्ट के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि यह पहले से मौजूद नहीं है तो निर्देशिका बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// त्वरित प्रस्तुति वर्ग जो पीपीटीएक्स फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation();
// पहली स्लाइड तक पहुंचें
ISlide sld = pres.getSlides().get_Item(0);
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// चार्ट शीर्षक सेट करना
// Chart.getChartTitle().getTextFrameForOverriding().setText('नमूना शीर्षक');
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
// श्रृंखला के लिए भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// दूसरी चार्ट श्रृंखला लें
series = chart.getChartData().getSeries().get_Item(1);
// अब श्रृंखला डेटा आबाद हो रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// श्रृंखला के लिए भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
//पहला लेबल श्रेणी का नाम दिखाएगा
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// तीसरे लेबल के लिए मान दिखाएँ
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// प्रस्तुतिकरण को चार्ट के साथ सहेजें
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में सामान्य चार्ट कैसे बनाएं। पावरपॉइंट प्रेजेंटेशन में क्लस्टर्ड कॉलम चार्ट बनाने के लिए हमने स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका का पालन किया।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट प्रकार कैसे बदल सकता हूँ?

 चार्ट प्रकार बदलने के लिए, संशोधित करें`ChartType` चार्ट का उपयोग करते समय पैरामीटर`sld.getShapes().addChart()`. आप Aspose.Slides में उपलब्ध विभिन्न चार्ट प्रकारों में से चुन सकते हैं।

### क्या मैं चार्ट श्रृंखला के रंग बदल सकता हूँ?

 हां, आप प्रत्येक श्रृंखला के लिए भरण रंग सेट करके चार्ट श्रृंखला के रंग बदल सकते हैं`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### मैं चार्ट में और अधिक श्रेणियां या श्रृंखला कैसे जोड़ूं?

 आप इसका उपयोग करके नए डेटा बिंदु और लेबल जोड़कर चार्ट में अधिक श्रेणियां या श्रृंखला जोड़ सकते हैं`chart.getChartData().getCategories().add()` और`chart.getChartData().getSeries().add()` तरीके.

### मैं चार्ट शीर्षक को और अधिक कैसे अनुकूलित कर सकता हूँ?

 आप गुणों को संशोधित करके चार्ट शीर्षक को और अधिक अनुकूलित कर सकते हैं`chart.getChartTitle()` जैसे पाठ संरेखण, फ़ॉन्ट आकार और रंग।

### मैं चार्ट को किसी भिन्न फ़ाइल स्वरूप में कैसे सहेजूँ?

चार्ट को किसी भिन्न फ़ाइल स्वरूप में सहेजने के लिए, बदलें`SaveFormat` में पैरामीटर`pres.save()` वांछित प्रारूप में विधि (उदाहरण के लिए, पीडीएफ, पीएनजी, जेपीईजी)।