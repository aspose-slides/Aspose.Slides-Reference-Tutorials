---
"description": "Aspose.Slides for Java का उपयोग करके चार्ट में डिफ़ॉल्ट मार्कर के साथ Java स्लाइड बनाना सीखें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।"
"linktitle": "जावा स्लाइड्स में चार्ट में डिफ़ॉल्ट मार्कर"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में चार्ट में डिफ़ॉल्ट मार्कर"
"url": "/hi/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में चार्ट में डिफ़ॉल्ट मार्कर


## जावा स्लाइड्स में चार्ट में डिफ़ॉल्ट मार्कर का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके डिफ़ॉल्ट मार्कर के साथ चार्ट बनाने का तरीका जानेंगे। डिफ़ॉल्ट मार्कर, चार्ट में डेटा बिंदुओं पर उन्हें हाइलाइट करने के लिए जोड़े गए प्रतीक या आकृतियाँ हैं। हम डेटा को विज़ुअलाइज़ करने के लिए मार्कर के साथ एक लाइन चार्ट बनाएंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java प्रोजेक्ट में सेट अप है।

## चरण 1: एक प्रस्तुति बनाएं

सबसे पहले, आइए एक प्रेजेंटेशन बनाएं और उसमें एक स्लाइड जोड़ें। फिर हम स्लाइड में एक चार्ट जोड़ेंगे।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## चरण 2: मार्कर के साथ लाइन चार्ट जोड़ें

अब, स्लाइड में मार्कर के साथ एक लाइन चार्ट जोड़ें। हम चार्ट से कोई भी डिफ़ॉल्ट डेटा भी साफ़ कर देंगे।

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## चरण 3: चार्ट डेटा भरें

हम चार्ट को सैंपल डेटा से भरेंगे। इस उदाहरण में, हम डेटा पॉइंट और श्रेणियों के साथ दो सीरीज़ बनाएंगे।

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// श्रृंखला 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// श्रृंखला 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// श्रृंखला डेटा भरना
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## चरण 4: चार्ट को अनुकूलित करें

आप चार्ट को और भी अनुकूलित कर सकते हैं, जैसे कि लेजेंड जोड़ना और उसका स्वरूप समायोजित करना।

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## चरण 5: प्रस्तुति सहेजें

अंत में, चार्ट के साथ प्रस्तुति को अपने इच्छित स्थान पर सहेजें।

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

बस! आपने Aspose.Slides for Java का उपयोग करके डिफ़ॉल्ट मार्करों के साथ एक लाइन चार्ट बनाया है।

## जावा स्लाइड्स में चार्ट में डिफ़ॉल्ट मार्करों के लिए पूर्ण स्रोत कोड

```java
        // दस्तावेज़ निर्देशिका का पथ.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //दूसरा चार्ट श्रृंखला लें
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //अब श्रृंखला डेटा भरा जा रहा है
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## निष्कर्ष

इस विस्तृत ट्यूटोरियल में, आपने Aspose.Slides for Java का उपयोग करके चार्ट में डिफ़ॉल्ट मार्कर के साथ Java स्लाइड बनाना सीखा है। हमने प्रेजेंटेशन सेट करने से लेकर चार्ट के स्वरूप को अनुकूलित करने और परिणाम को सहेजने तक की पूरी प्रक्रिया को कवर किया है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं मार्कर प्रतीकों को कैसे बदल सकता हूँ?

आप प्रत्येक डेटा बिंदु के लिए मार्कर शैली सेट करके मार्कर प्रतीकों को अनुकूलित कर सकते हैं। `IDataPoint.setMarkerStyle()` मार्कर प्रतीक बदलने के लिए.

### मैं चार्ट के रंग कैसे समायोजित करूं?

चार्ट के रंगों को संशोधित करने के लिए, आप इसका उपयोग कर सकते हैं `IChartSeriesFormat` और `IShapeFillFormat` भरण और पंक्ति गुण सेट करने के लिए इंटरफेस.

### क्या मैं डेटा बिंदुओं में लेबल जोड़ सकता हूँ?

हां, आप इसका उपयोग करके डेटा बिंदुओं में लेबल जोड़ सकते हैं `IDataPoint.getLabel()` विधि का चयन करें और आवश्यकतानुसार उन्हें अनुकूलित करें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}