---
title: जावा स्लाइड्स में पाई चार्ट
linktitle: जावा स्लाइड्स में पाई चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में शानदार पाई चार्ट बनाना सीखें। जावा डेवलपर्स के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 23
url: /hi/java/chart-data-manipulation/pie-chart-java-slides/
---

## Aspose.Slides का उपयोग करके जावा स्लाइड्स में पाई चार्ट बनाने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में पाई चार्ट बनाने का तरीका दिखाएंगे। हम आपको आरंभ करने में सहायता के लिए चरण-दर-चरण निर्देश और Java स्रोत कोड प्रदान करेंगे। यह मार्गदर्शिका मानती है कि आपने पहले ही Aspose.Slides for Java के साथ अपना विकास वातावरण सेट कर लिया है।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित और कॉन्फ़िगर है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Aspose.Slides लाइब्रेरी से आवश्यक क्लासेस को आयात करना सुनिश्चित करें।

## चरण 2: प्रस्तुति आरंभ करें

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation presentation = new Presentation();
```

 अपनी PowerPoint फ़ाइल को प्रदर्शित करने के लिए एक नया प्रेजेंटेशन ऑब्जेक्ट बनाएँ।`"Your Document Directory"` उस वास्तविक पथ के साथ जहाँ आप प्रस्तुति को सहेजना चाहते हैं.

## चरण 3: स्लाइड जोड़ें

```java
// पहली स्लाइड पर पहुँचें
ISlide slide = presentation.getSlides().get_Item(0);
```

प्रस्तुति की वह पहली स्लाइड प्राप्त करें जहां आप पाई चार्ट जोड़ना चाहते हैं।

## चरण 4: पाई चार्ट जोड़ें

```java
//डिफ़ॉल्ट डेटा के साथ पाई चार्ट जोड़ें
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

स्लाइड में निर्दिष्ट स्थान और आकार पर पाई चार्ट जोड़ें।

## चरण 5: चार्ट शीर्षक सेट करें

```java
// चार्ट शीर्षक सेट करें
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

पाई चार्ट के लिए शीर्षक सेट करें। आप आवश्यकतानुसार शीर्षक को अनुकूलित कर सकते हैं।

## चरण 6: चार्ट डेटा को अनुकूलित करें

```java
// मान दिखाने के लिए पहली श्रृंखला सेट करें
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// चार्ट डेटा शीट का इंडेक्स सेट करना
int defaultWorksheetIndex = 0;

// चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// डिफ़ॉल्ट रूप से जनरेटेड श्रृंखला और श्रेणियां हटाएं
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// नई श्रेणियाँ जोड़ना
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// नई श्रृंखला जोड़ना
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// श्रृंखला डेटा भरना
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

श्रेणियाँ और श्रृंखलाएँ जोड़कर और उनके मान सेट करके चार्ट डेटा को कस्टमाइज़ करें। इस उदाहरण में, हमारे पास तीन श्रेणियाँ और संगत डेटा बिंदुओं वाली एक श्रृंखला है।

## चरण 7: पाई चार्ट सेक्टरों को अनुकूलित करें

```java
// सेक्टर रंग सेट करें
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// प्रत्येक क्षेत्र की उपस्थिति को अनुकूलित करें
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// सेक्टर बॉर्डर को अनुकूलित करें
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// अन्य क्षेत्रों को भी इसी तरह अनुकूलित करें
```

पाई चार्ट में प्रत्येक सेक्टर की उपस्थिति को अनुकूलित करें। आप रंग, बॉर्डर स्टाइल और अन्य दृश्य गुण बदल सकते हैं।

## चरण 8: डेटा लेबल अनुकूलित करें

```java
// डेटा लेबल अनुकूलित करें
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// इसी तरह से अन्य डेटा बिंदुओं के लिए डेटा लेबल अनुकूलित करें
```

पाई चार्ट में प्रत्येक डेटा बिंदु के लिए डेटा लेबल कस्टमाइज़ करें। आप नियंत्रित कर सकते हैं कि चार्ट पर कौन से मान प्रदर्शित किए जाएँ।

## चरण 9: लीडर लाइन्स दिखाएँ

```java
// चार्ट के लिए लीडर लाइन दिखाएँ
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

डेटा लेबल को उनके संगत सेक्टरों से जोड़ने के लिए लीडर लाइनों को सक्षम करें।

## चरण 10: पाई चार्ट रोटेशन कोण सेट करें

```java
// पाई चार्ट सेक्टरों के लिए रोटेशन कोण सेट करें
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

पाई चार्ट सेक्टरों के लिए रोटेशन कोण सेट करें। इस उदाहरण में, हमने इसे 180 डिग्री पर सेट किया है।

## चरण 11: प्रस्तुति सहेजें

```java
// पाई चार्ट के साथ प्रस्तुति को सहेजें
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

पाई चार्ट के साथ प्रस्तुति को निर्दिष्ट निर्देशिका में सहेजें।

## जावा स्लाइड्स में पाई चार्ट के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation presentation = new Presentation();
// पहली स्लाइड तक पहुंचें
ISlide slides = presentation.getSlides().get_Item(0);
// डिफ़ॉल्ट डेटा के साथ चार्ट जोड़ें
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// सेटिंग चार्ट शीर्षक
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
// नई श्रेणियाँ जोड़ना
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// नई श्रृंखला जोड़ना
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
//अब श्रृंखला डेटा भरा जा रहा है
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// नये संस्करण में काम नहीं कर रहा
// नये बिन्दु जोड़ना और सेक्टर का रंग निर्धारित करना
// श्रृंखला.IsColorVaried = सच;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// सेक्टर सीमा निर्धारित करना
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// सेक्टर सीमा निर्धारित करना
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// सेक्टर सीमा निर्धारित करना
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// नई श्रृंखला के लिए प्रत्येक श्रेणी के लिए कस्टम लेबल बनाएं
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(सत्य);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// चार्ट के लिए लीडर लाइन्स दिखाना
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// पाई चार्ट सेक्टरों के लिए रोटेशन कोण सेट करना
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// चार्ट के साथ प्रस्तुति सहेजें
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में पाई चार्ट सफलतापूर्वक बनाया है। आप अपनी विशिष्ट आवश्यकताओं के अनुसार चार्ट की उपस्थिति और डेटा लेबल को अनुकूलित कर सकते हैं। यह ट्यूटोरियल एक बुनियादी उदाहरण प्रदान करता है, और आप आवश्यकतानुसार अपने चार्ट को और भी बेहतर और अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पाई चार्ट में अलग-अलग सेक्टरों का रंग कैसे बदल सकता हूँ?

 पाई चार्ट में अलग-अलग सेक्टर के रंग बदलने के लिए, आप प्रत्येक डेटा पॉइंट के लिए भरण रंग को कस्टमाइज़ कर सकते हैं। दिए गए कोड उदाहरण में, हमने दिखाया कि प्रत्येक सेक्टर के लिए भरण रंग कैसे सेट किया जाए`getSolidFillColor().setColor()` विधि। आप वांछित उपस्थिति प्राप्त करने के लिए रंग मानों को संशोधित कर सकते हैं।

### क्या मैं पाई चार्ट में अधिक श्रेणियां और डेटा श्रृंखला जोड़ सकता हूं?

 हां, आप पाई चार्ट में अतिरिक्त श्रेणियां और डेटा श्रृंखला जोड़ सकते हैं। ऐसा करने के लिए, आप इसका उपयोग कर सकते हैं`getChartData().getCategories().add()` और`getChartData().getSeries().add()` उदाहरण में दिखाए गए तरीके। अपने चार्ट का विस्तार करने के लिए नई श्रेणियों और श्रृंखलाओं के लिए बस उचित डेटा और लेबल प्रदान करें।

### मैं डेटा लेबल का स्वरूप कैसे अनुकूलित करूँ?

 आप डेटा लेबल के स्वरूप को अनुकूलित कर सकते हैं`getDataLabelFormat()` प्रत्येक डेटा बिंदु के लेबल पर विधि। उदाहरण में, हमने दिखाया कि डेटा लेबल पर मान को कैसे दिखाया जाए`getDataLabelFormat().setShowValue(true)`आप यह नियंत्रित करके कि कौन से मान प्रदर्शित किए जाएं, लेजेंड कुंजियां दिखाएं, और अन्य स्वरूपण विकल्पों को समायोजित करके डेटा लेबल को और अधिक अनुकूलित कर सकते हैं।

### क्या मैं पाई चार्ट का शीर्षक बदल सकता हूँ?

 हां, आप पाई चार्ट का शीर्षक बदल सकते हैं। दिए गए कोड में, हमने चार्ट का शीर्षक सेट किया है`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . आप प्रतिस्थापित कर सकते हैं`"Sample Title"` अपने इच्छित शीर्षक पाठ के साथ.

### मैं पाई चार्ट के साथ तैयार प्रस्तुति को कैसे सहेजूँ?

 पाई चार्ट के साथ प्रस्तुति को सहेजने के लिए, का उपयोग करें`presentation.save()` विधि। वांछित फ़ाइल पथ और नाम के साथ-साथ वह प्रारूप प्रदान करें जिसमें आप प्रस्तुति को सहेजना चाहते हैं। उदाहरण के लिए:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

सही फ़ाइल पथ और प्रारूप निर्दिष्ट करना सुनिश्चित करें.

### क्या मैं Java के लिए Aspose.Slides का उपयोग करके अन्य प्रकार के चार्ट बना सकता हूँ?

हां, Aspose.Slides for Java विभिन्न चार्ट प्रकारों का समर्थन करता है, जिसमें बार चार्ट, लाइन चार्ट और बहुत कुछ शामिल है। आप चार्ट के प्रकार को बदलकर विभिन्न प्रकार के चार्ट बना सकते हैं।`ChartType` चार्ट जोड़ते समय। विभिन्न प्रकार के चार्ट बनाने के बारे में अधिक जानकारी के लिए Aspose.Slides दस्तावेज़ देखें।

### मैं Java के लिए Aspose.Slides के साथ काम करने के लिए अधिक जानकारी और उदाहरण कैसे पा सकता हूं?

 अधिक जानकारी, विस्तृत दस्तावेज़ीकरण और अतिरिक्त उदाहरणों के लिए, आप यहां जा सकते हैं[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/)यह आपको पुस्तकालय का प्रभावी ढंग से उपयोग करने में मदद करने के लिए व्यापक संसाधन प्रदान करता है।