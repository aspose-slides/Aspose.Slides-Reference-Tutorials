---
title: जावा स्लाइड्स में बहु-श्रेणी चार्ट
linktitle: जावा स्लाइड्स में बहु-श्रेणी चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में बहु-श्रेणी चार्ट बनाएं। प्रस्तुतियों में प्रभावशाली डेटा विज़ुअलाइज़ेशन के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 20
url: /hi/java/chart-data-manipulation/multi-category-chart-java-slides/
---

## Aspose.Slides के साथ जावा स्लाइड्स में बहु-श्रेणी चार्ट का परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में एक बहु-श्रेणी चार्ट कैसे बनाया जाए। यह मार्गदर्शिका आपको कई श्रेणियों और श्रृंखलाओं के साथ क्लस्टर्ड कॉलम चार्ट बनाने में मदद करने के लिए स्रोत कोड के साथ चरण-दर-चरण निर्देश प्रदान करेगी।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास जावा लाइब्रेरी के लिए Aspose.Slides आपके जावा विकास परिवेश में स्थापित और सेटअप है।

## चरण 1: पर्यावरण की स्थापना
सबसे पहले, आवश्यक कक्षाएं आयात करें और स्लाइड के साथ काम करने के लिए एक नया प्रेजेंटेशन ऑब्जेक्ट बनाएं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: एक स्लाइड और चार्ट जोड़ना
इसके बाद, एक स्लाइड बनाएं और उसमें एक क्लस्टर्ड कॉलम चार्ट जोड़ें।

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## चरण 3: मौजूदा डेटा साफ़ करना
चार्ट से कोई भी मौजूदा डेटा साफ़ करें।

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## चरण 4: डेटा श्रेणियाँ स्थापित करना
अब, चार्ट के लिए डेटा श्रेणियां सेट करते हैं। हम कई श्रेणियां बनाएंगे और उन्हें समूहित करेंगे।

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// श्रेणियां जोड़ें और उन्हें समूहित करें
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## चरण 5: श्रृंखला जोड़ना
अब, आइए डेटा बिंदुओं के साथ चार्ट में एक श्रृंखला जोड़ें।

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## चरण 6: प्रस्तुति को सहेजना
अंत में, प्रस्तुतिकरण को चार्ट के साथ सहेजें।

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

इतना ही! आपने Aspose.Slides का उपयोग करके जावा स्लाइड में सफलतापूर्वक एक बहु-श्रेणी चार्ट बनाया है। आप अपनी विशिष्ट आवश्यकताओं के अनुरूप इस चार्ट को और अधिक अनुकूलित कर सकते हैं।

## जावा स्लाइड्स में बहु-श्रेणी चार्ट के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// शृंखला जोड़ना
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// प्रस्तुतिकरण को चार्ट के साथ सहेजें
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में एक बहु-श्रेणी चार्ट कैसे बनाया जाए। हमने कई श्रेणियों और श्रृंखलाओं के साथ क्लस्टर्ड कॉलम चार्ट बनाने के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका का अध्ययन किया।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट स्वरूप को कैसे अनुकूलित कर सकता हूँ?

आप रंग, फ़ॉन्ट और शैली जैसे गुणों को संशोधित करके चार्ट उपस्थिति को अनुकूलित कर सकते हैं। विस्तृत अनुकूलन विकल्पों के लिए Aspose.Slides दस्तावेज़ देखें।

### क्या मैं चार्ट में और श्रृंखलाएँ जोड़ सकता हूँ?

हां, आप चरण 5 में दिखाए गए समान प्रक्रिया का पालन करके चार्ट में अतिरिक्त श्रृंखला जोड़ सकते हैं।

### मैं चार्ट प्रकार कैसे बदलूं?

 चार्ट प्रकार बदलने के लिए, बदलें`ChartType.ClusteredColumn` चरण 2 में चार्ट जोड़ते समय वांछित चार्ट प्रकार के साथ।

### मैं चार्ट में शीर्षक कैसे जोड़ सकता हूँ?

 आप इसका उपयोग करके चार्ट में एक शीर्षक जोड़ सकते हैं`ch.getChartTitle().getTextFrame().setText("Chart Title");` तरीका।