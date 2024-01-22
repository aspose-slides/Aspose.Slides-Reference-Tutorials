---
title: जावा स्लाइड्स में मौजूदा चार्ट
linktitle: जावा स्लाइड्स में मौजूदा चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Java के लिए Aspose.Slides के साथ अपनी PowerPoint प्रस्तुतियों को बेहतर बनाएं। मौजूदा चार्ट को प्रोग्रामेटिक रूप से संशोधित करना सीखें। चार्ट अनुकूलन के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 12
url: /hi/java/chart-elements/existing-chart-java-slides/
---

## जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में मौजूदा चार्ट का परिचय

इस ट्यूटोरियल में, हम दिखाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में मौजूदा चार्ट को कैसे संशोधित किया जाए। हम चार्ट डेटा, श्रेणी नाम, श्रृंखला नाम बदलने और चार्ट में एक नई श्रृंखला जोड़ने के चरणों से गुजरेंगे। सुनिश्चित करें कि आपके प्रोजेक्ट में जावा के लिए Aspose.Slides सेटअप है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1. जावा लाइब्रेरी के लिए Aspose.Slides आपके प्रोजेक्ट में शामिल हैं।
2. एक चार्ट के साथ एक मौजूदा पावरपॉइंट प्रस्तुति जिसे आप संशोधित करना चाहते हैं।
3. जावा विकास पर्यावरण की स्थापना।

## चरण 1: प्रस्तुति लोड करें

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// त्वरित प्रस्तुति वर्ग जो पीपीटीएक्स फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## चरण 2: स्लाइड और चार्ट तक पहुंचें

```java
// पहली स्लाइड तक पहुंचें
ISlide sld = pres.getSlides().get_Item(0);

// स्लाइड पर चार्ट तक पहुंचें
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## चरण 3: चार्ट डेटा और श्रेणी नाम बदलें

```java
// चार्ट डेटा शीट का सूचकांक सेट करना
int defaultWorksheetIndex = 0;

//चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// चार्ट श्रेणी के नाम बदलें
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## चरण 4: पहली चार्ट श्रृंखला अपडेट करें

```java
// पहली चार्ट श्रृंखला लीजिए
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// श्रृंखला का नाम अद्यतन करें
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// श्रृंखला डेटा अद्यतन करें
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## चरण 5: दूसरी चार्ट श्रृंखला अपडेट करें

```java
// दूसरी चार्ट श्रृंखला लीजिए
series = chart.getChartData().getSeries().get_Item(1);

// श्रृंखला का नाम अद्यतन करें
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// श्रृंखला डेटा अद्यतन करें
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## चरण 6: चार्ट में एक नई श्रृंखला जोड़ें

```java
// एक नई शृंखला जोड़ रहा हूँ
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// तीसरी चार्ट श्रृंखला लीजिए
series = chart.getChartData().getSeries().get_Item(2);

// श्रृंखला डेटा पॉप्युलेट करें
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## चरण 7: चार्ट प्रकार बदलें

```java
//चार्ट प्रकार को क्लस्टर्ड सिलेंडर में बदलें
chart.setType(ChartType.ClusteredCylinder);
```

## चरण 8: संशोधित प्रस्तुति सहेजें

```java
// संशोधित चार्ट के साथ प्रस्तुतिकरण सहेजें
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

बधाई हो! आपने जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुति में मौजूदा चार्ट को सफलतापूर्वक संशोधित किया है। अब आप इस कोड का उपयोग अपने पावरपॉइंट प्रस्तुतियों में चार्ट को प्रोग्रामेटिक रूप से अनुकूलित करने के लिए कर सकते हैं।

## जावा स्लाइड्स में मौजूदा चार्ट के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// इंस्टेंटिएट प्रेजेंटेशन क्लास जो पीपीटीएक्स फ़ाइल का प्रतिनिधित्व करता है // इंस्टेंटिएट प्रेजेंटेशन क्लास जो पीपीटीएक्स फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// पहले स्लाइडमार्कर तक पहुंचें
ISlide sld = pres.getSlides().get_Item(0);
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = (IChart) sld.getShapes().get_Item(0);
// चार्ट डेटा शीट का सूचकांक सेट करना
int defaultWorksheetIndex = 0;
//चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// चार्ट श्रेणी का नाम बदलना
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// पहली चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// अब सीरीज डेटा अपडेट हो रहा है
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// श्रृंखला का नाम संशोधित करना
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// दूसरा चार्ट श्रृंखला लें
series = chart.getChartData().getSeries().get_Item(1);
// अब सीरीज डेटा अपडेट हो रहा है
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// श्रृंखला का नाम संशोधित करना
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// अब, एक नई शृंखला जोड़ रहा हूँ
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// तीसरी चार्ट श्रृंखला लें
series = chart.getChartData().getSeries().get_Item(2);
// अब श्रृंखला डेटा आबाद हो रहा है
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// प्रस्तुतिकरण को चार्ट के साथ सहेजें
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## निष्कर्ष

इस व्यापक ट्यूटोरियल में, हमने सीखा है कि जावा के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में मौजूदा चार्ट को कैसे संशोधित किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और स्रोत कोड उदाहरणों का उपयोग करके, आप अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए चार्ट को आसानी से अनुकूलित और अपडेट कर सकते हैं। हमने जो कवर किया उसका पुनर्कथन यहां दिया गया है:

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट प्रकार कैसे बदल सकता हूँ?

 आप इसका उपयोग करके चार्ट प्रकार बदल सकते हैं`chart.setType(ChartType.ChartTypeHere)` तरीका। प्रतिस्थापित करें`ChartTypeHere` वांछित चार्ट प्रकार के साथ, जैसे`ChartType.ClusteredCylinder` हमारे उदाहरण में.

### क्या मैं किसी शृंखला में अधिक डेटा बिंदु जोड़ सकता हूँ?

 हां, आप इसका उपयोग करके किसी श्रृंखला में अधिक डेटा बिंदु जोड़ सकते हैं`series.getDataPoints().addDataPointForBarSeries(cell)` तरीका। उचित सेल डेटा प्रदान करना सुनिश्चित करें.

### मैं श्रेणी के नाम कैसे अपडेट करूं?

 आप इसका उपयोग करके श्रेणी के नाम अपडेट कर सकते हैं`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` नई श्रेणी के नाम सेट करने के लिए.

### मैं श्रृंखला के नाम कैसे संशोधित करूं?

 श्रृंखला नामों को संशोधित करने के लिए, उपयोग करें`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` नई शृंखला के नाम सेट करने के लिए.

### क्या चार्ट से किसी शृंखला को हटाने का कोई तरीका है?

 हां, आप इसका उपयोग करके चार्ट से एक श्रृंखला हटा सकते हैं`chart.getChartData().getSeries().removeAt(index)` विधि, कहाँ`index`उस श्रृंखला का सूचकांक है जिसे आप हटाना चाहते हैं।