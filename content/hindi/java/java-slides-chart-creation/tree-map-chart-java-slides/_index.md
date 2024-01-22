---
title: जावा स्लाइड्स में ट्री मैप चार्ट
linktitle: जावा स्लाइड्स में ट्री मैप चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में ट्री मैप चार्ट बनाएं। पदानुक्रमित डेटा को देखने के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 13
url: /hi/java/chart-creation/tree-map-chart-java-slides/
---

## जावा स्लाइड्स में ट्री मैप चार्ट का परिचय

इस ट्यूटोरियल में, हम दिखाएंगे कि जावा लाइब्रेरी के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में ट्री मैप चार्ट कैसे बनाया जाए। ट्री मैप चार्ट पदानुक्रमित डेटा को देखने का एक प्रभावी तरीका है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Slides सेटअप है।

## चरण 1: आवश्यक पुस्तकालय आयात करें

```java
import com.aspose.slides.*;
```

## चरण 2: प्रस्तुति लोड करें

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## चरण 3: एक वृक्ष मानचित्र चार्ट बनाएं

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    //शाखा बनाएं 1
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // शाखा बनाएं 2
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // डेटा बिंदु जोड़ें
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // प्रेजेंटेशन को ट्री मैप चार्ट के साथ सहेजें
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## जावा स्लाइड्स में ट्री मैप चार्ट के लिए संपूर्ण स्रोत कोड
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//शाखा 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//शाखा 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि जावा लाइब्रेरी के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में ट्री मैप चार्ट कैसे बनाया जाता है। ट्री मैप चार्ट पदानुक्रमित डेटा को विज़ुअलाइज़ करने के लिए एक मूल्यवान उपकरण हैं, जो आपकी प्रस्तुतियों को अधिक जानकारीपूर्ण और आकर्षक बनाते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं ट्री मैप चार्ट में डेटा कैसे जोड़ूँ?

 ट्री मैप चार्ट में डेटा जोड़ने के लिए, इसका उपयोग करें`series.getDataPoints().addDataPointForTreemapSeries()` विधि, डेटा मानों को पैरामीटर के रूप में पास करना।

### मैं ट्री मैप चार्ट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

 आप विभिन्न गुणों को संशोधित करके ट्री मैप चार्ट की उपस्थिति को अनुकूलित कर सकते हैं`chart` और`series` ऑब्जेक्ट, जैसे रंग, लेबल और लेआउट।

### क्या मैं एक ही प्रेजेंटेशन में एकाधिक ट्री मैप चार्ट बना सकता हूँ?

हां, आप समान चरणों का पालन करके और विभिन्न स्लाइड स्थितियों को निर्दिष्ट करके एक ही प्रस्तुति में एकाधिक ट्री मैप चार्ट बना सकते हैं।

### मैं ट्री मैप चार्ट के साथ प्रस्तुतिकरण को कैसे सहेजूँ?

 उपयोग`pres.save()` प्रेजेंटेशन को ट्री मैप चार्ट के साथ वांछित प्रारूप (उदाहरण के लिए, पीपीटीएक्स) में सहेजने की विधि।