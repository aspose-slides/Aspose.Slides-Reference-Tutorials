---
"description": "Aspose.Slides for Java के साथ Java स्लाइड्स में सामान्य चार्ट बनाएँ। PowerPoint प्रस्तुतियों में चार्ट बनाने, अनुकूलित करने और सहेजने के लिए चरण-दर-चरण मार्गदर्शिका और स्रोत कोड।"
"linktitle": "जावा स्लाइड्स में सामान्य चार्ट"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में सामान्य चार्ट"
"url": "/hi/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में सामान्य चार्ट


## जावा स्लाइड्स में सामान्य चार्ट का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java API का उपयोग करके Java Slides में सामान्य चार्ट बनाने की प्रक्रिया के बारे में जानेंगे। हम PowerPoint प्रेजेंटेशन में क्लस्टर्ड कॉलम चार्ट बनाने का तरीका दिखाने के लिए सोर्स कोड के साथ-साथ चरण-दर-चरण निर्देशों का उपयोग करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. Aspose.Slides for Java API स्थापित.
2. एक जावा विकास वातावरण स्थापित किया गया।
3. जावा प्रोग्रामिंग का बुनियादी ज्ञान.

## चरण 1: प्रोजेक्ट की स्थापना

सुनिश्चित करें कि आपके पास अपने प्रोजेक्ट के लिए एक निर्देशिका है। आइए इसे "आपकी दस्तावेज़ निर्देशिका" कहें जैसा कि कोड में बताया गया है। आप इसे अपनी प्रोजेक्ट निर्देशिका के वास्तविक पथ से बदल सकते हैं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## चरण 2: प्रेजेंटेशन बनाना

अब, आइए एक पावरपॉइंट प्रेजेंटेशन बनाएं और इसकी पहली स्लाइड देखें।

```java
// PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation pres = new Presentation();
// पहली स्लाइड तक पहुंचें
ISlide sld = pres.getSlides().get_Item(0);
```

## चरण 3: चार्ट जोड़ना

हम स्लाइड में एक क्लस्टर कॉलम चार्ट जोड़ेंगे और उसका शीर्षक सेट करेंगे।

```java
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// सेटिंग चार्ट शीर्षक
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## चरण 4: चार्ट डेटा सेट करना

इसके बाद, हम श्रृंखला और श्रेणियों को परिभाषित करके चार्ट डेटा सेट करेंगे।

```java
// पहली श्रृंखला को मान दिखाएँ पर सेट करें
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// चार्ट डेटा शीट का इंडेक्स सेट करना
int defaultWorksheetIndex = 0;

// चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// डिफ़ॉल्ट रूप से जनरेटेड श्रृंखला और श्रेणियां हटाएं
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// नई श्रृंखला जोड़ना
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// नई श्रेणियाँ जोड़ना
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## चरण 5: श्रृंखला डेटा भरना

अब, चार्ट के लिए श्रृंखला डेटा बिंदु भरें।

```java
// पहली चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// श्रृंखला डेटा भरना
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// श्रृंखला के लिए भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// दूसरा चार्ट श्रृंखला लें
series = chart.getChartData().getSeries().get_Item(1);

// श्रृंखला डेटा भरना
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

// श्रृंखला नाम और विभाजक के साथ तीसरे लेबल के लिए मान दिखाएं
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## चरण 7: प्रस्तुति को सहेजना

अंत में, चार्ट के साथ प्रस्तुति को अपनी परियोजना निर्देशिका में सहेजें।

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

बस! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में क्लस्टर्ड कॉलम चार्ट सफलतापूर्वक बना लिया है। आप अपनी आवश्यकताओं के अनुसार इस चार्ट को और भी कस्टमाइज़ कर सकते हैं।

## जावा स्लाइड्स में सामान्य चार्ट के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation pres = new Presentation();
// पहली स्लाइड तक पहुंचें
ISlide sld = pres.getSlides().get_Item(0);
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// सेटिंग चार्ट शीर्षक
// Chart.getChartTitle().getTextFrameForOverriding().setText("नमूना शीर्षक");
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
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// नई श्रृंखला जोड़ना
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// नई श्रेणियाँ जोड़ना
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// पहली चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// अब श्रृंखला डेटा भरा जा रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// श्रृंखला के लिए भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// दूसरा चार्ट श्रृंखला लें
series = chart.getChartData().getSeries().get_Item(1);
// अब श्रृंखला डेटा भरा जा रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// श्रृंखला के लिए भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// पहला लेबल श्रेणी का नाम दिखाया जाएगा
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// तीसरे लेबल के लिए मान दिखाएँ
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// चार्ट के साथ प्रस्तुति सहेजें
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java API का उपयोग करके Java Slides में सामान्य चार्ट कैसे बनाएं। हमने PowerPoint प्रेजेंटेशन में क्लस्टर्ड कॉलम चार्ट बनाने के लिए सोर्स कोड के साथ चरण-दर-चरण गाइड के माध्यम से जाना।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट का प्रकार कैसे बदल सकता हूँ?

चार्ट प्रकार बदलने के लिए, संशोधित करें `ChartType` चार्ट जोड़ते समय पैरामीटर का उपयोग करें `sld.getShapes().addChart()`आप Aspose.Slides में उपलब्ध विभिन्न चार्ट प्रकारों में से चुन सकते हैं।

### क्या मैं चार्ट श्रृंखला का रंग बदल सकता हूँ?

हां, आप प्रत्येक श्रृंखला के लिए भरण रंग सेट करके चार्ट श्रृंखला के रंग बदल सकते हैं `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### मैं चार्ट में और अधिक श्रेणियाँ या श्रृंखलाएँ कैसे जोड़ूँ?

आप नए डेटा बिंदु और लेबल जोड़कर चार्ट में अधिक श्रेणियाँ या श्रृंखलाएँ जोड़ सकते हैं `chart.getChartData().getCategories().add()` और `chart.getChartData().getSeries().add()` तरीके.

### मैं चार्ट शीर्षक को और अधिक अनुकूलित कैसे कर सकता हूं?

आप चार्ट शीर्षक के गुणों को संशोधित करके इसे और भी अनुकूलित कर सकते हैं `chart.getChartTitle()` जैसे पाठ संरेखण, फ़ॉन्ट आकार और रंग।

### मैं चार्ट को भिन्न फ़ाइल प्रारूप में कैसे सहेजूँ?

चार्ट को किसी भिन्न फ़ाइल प्रारूप में सहेजने के लिए, बदलें `SaveFormat` पैरामीटर में `pres.save()` विधि को वांछित प्रारूप में परिवर्तित करें (जैसे, पीडीएफ, पीएनजी, जेपीईजी)।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}