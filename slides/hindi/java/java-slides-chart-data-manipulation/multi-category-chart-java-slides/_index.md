---
title: जावा स्लाइड्स में बहु-श्रेणी चार्ट
linktitle: जावा स्लाइड्स में बहु-श्रेणी चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java स्लाइड्स में बहु-श्रेणी चार्ट बनाएँ। प्रस्तुतियों में प्रभावशाली डेटा विज़ुअलाइज़ेशन के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 20
url: /hi/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides के साथ जावा स्लाइड्स में मल्टी-कैटेगरी चार्ट का परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java API का उपयोग करके Java स्लाइड में मल्टी-कैटेगरी चार्ट कैसे बनाया जाता है। यह गाइड आपको कई श्रेणियों और श्रृंखलाओं के साथ क्लस्टर किए गए कॉलम चार्ट बनाने में मदद करने के लिए स्रोत कोड के साथ चरण-दर-चरण निर्देश प्रदान करेगा।

## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java विकास परिवेश में सेट अप है।

## चरण 1: वातावरण की स्थापना
सबसे पहले, आवश्यक क्लासेस आयात करें और स्लाइड्स के साथ काम करने के लिए एक नया प्रेजेंटेशन ऑब्जेक्ट बनाएं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: स्लाइड और चार्ट जोड़ना
इसके बाद, एक स्लाइड बनाएं और उसमें एक क्लस्टर कॉलम चार्ट जोड़ें।

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## चरण 3: मौजूदा डेटा साफ़ करना
चार्ट से कोई भी मौजूदा डेटा साफ़ करें.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## चरण 4: डेटा श्रेणियाँ सेट करना
अब, चार्ट के लिए डेटा श्रेणियाँ सेट करते हैं। हम कई श्रेणियाँ बनाएंगे और उन्हें समूहीकृत करेंगे।

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// श्रेणियाँ जोड़ें और उन्हें समूहीकृत करें
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
अंत में, चार्ट के साथ प्रस्तुति को सेव करें।

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

बस! आपने Aspose.Slides का उपयोग करके जावा स्लाइड में सफलतापूर्वक एक बहु-श्रेणी चार्ट बनाया है। आप अपनी विशिष्ट आवश्यकताओं के अनुरूप इस चार्ट को और भी अनुकूलित कर सकते हैं।

## जावा स्लाइड्स में बहु-श्रेणी चार्ट के लिए पूर्ण स्रोत कोड

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
// श्रृंखला जोड़ना
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
// चार्ट के साथ प्रस्तुति सहेजें
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java API का उपयोग करके Java स्लाइड में मल्टी-कैटेगरी चार्ट कैसे बनाया जाता है। हमने कई श्रेणियों और श्रृंखलाओं के साथ क्लस्टर किए गए कॉलम चार्ट बनाने के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका का उपयोग किया।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

आप रंग, फ़ॉन्ट और स्टाइल जैसे गुणों को संशोधित करके चार्ट की उपस्थिति को अनुकूलित कर सकते हैं। विस्तृत अनुकूलन विकल्पों के लिए Aspose.Slides दस्तावेज़ देखें।

### क्या मैं चार्ट में और श्रृंखलाएं जोड़ सकता हूं?

हां, आप चरण 5 में दर्शाई गई समान प्रक्रिया का पालन करके चार्ट में अतिरिक्त श्रृंखला जोड़ सकते हैं।

### मैं चार्ट का प्रकार कैसे बदलूं?

 चार्ट प्रकार बदलने के लिए, प्रतिस्थापित करें`ChartType.ClusteredColumn` चरण 2 में चार्ट जोड़ते समय इच्छित चार्ट प्रकार के साथ।

### मैं चार्ट में शीर्षक कैसे जोड़ सकता हूँ?

 आप चार्ट में शीर्षक जोड़ सकते हैं`ch.getChartTitle().getTextFrame().setText("Chart Title");` तरीका।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
