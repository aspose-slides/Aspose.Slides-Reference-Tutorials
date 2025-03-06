---
title: जावा स्लाइड्स में चार्ट के लिए दूसरा प्लॉट विकल्प
linktitle: जावा स्लाइड्स में चार्ट के लिए दूसरा प्लॉट विकल्प
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java Slides में चार्ट को कस्टमाइज़ करना सीखें। दूसरे प्लॉट विकल्पों का अन्वेषण करें और अपनी प्रस्तुतियों को बेहतर बनाएँ।
weight: 12
url: /hi/java/chart-creation/second-plot-options-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में चार्ट के लिए द्वितीय प्लॉट विकल्पों का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके चार्ट में दूसरा प्लॉट विकल्प जोड़ने का तरीका जानेंगे। दूसरा प्लॉट विकल्प आपको चार्ट की उपस्थिति और व्यवहार को अनुकूलित करने की अनुमति देता है, विशेष रूप से पाई ऑफ़ पाई चार्ट जैसे परिदृश्यों में। हम इसे प्राप्त करने के लिए चरण-दर-चरण निर्देश और स्रोत कोड उदाहरण प्रदान करेंगे। 

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java स्थापित है और आपके Java प्रोजेक्ट में सेट अप है।

## चरण 1: एक प्रस्तुति बनाएं
आइए एक नई प्रस्तुति बनाकर शुरुआत करें:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
```

## चरण 2: स्लाइड में चार्ट जोड़ें
इसके बाद, हम स्लाइड में एक चार्ट जोड़ेंगे। इस उदाहरण में, हम पाई ऑफ़ पाई चार्ट बनाएंगे:

```java
// स्लाइड पर चार्ट जोड़ें
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## चरण 3: चार्ट गुण अनुकूलित करें
अब, आइए चार्ट के लिए विभिन्न गुणधर्म निर्धारित करें, जिसमें दूसरा प्लॉट विकल्प भी शामिल है:

```java
// पहली श्रृंखला के लिए डेटा लेबल दिखाएं
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// दूसरे पाई का आकार निर्धारित करें (प्रतिशत में)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// पाई को प्रतिशत के आधार पर विभाजित करें
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// विभाजन की स्थिति निर्धारित करें
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## चरण 4: प्रस्तुति सहेजें
अंत में, चार्ट और दूसरे प्लॉट विकल्पों के साथ प्रस्तुति को सहेजें:

```java
// प्रस्तुति को डिस्क पर लिखें
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## दूसरे प्लॉट विकल्पों के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
// स्लाइड पर चार्ट जोड़ें
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// विभिन्न गुण सेट करें
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// प्रस्तुति को डिस्क पर लिखें
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके Java Slides में चार्ट में दूसरा प्लॉट विकल्प कैसे जोड़ा जाता है। आप अपने चार्ट की उपस्थिति और कार्यक्षमता को बढ़ाने के लिए विभिन्न गुणों को अनुकूलित कर सकते हैं, जिससे आपकी प्रस्तुतियाँ अधिक जानकारीपूर्ण और नेत्रहीन आकर्षक बन सकती हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पाई ऑफ पाई चार्ट में दूसरे पाई का आकार कैसे बदल सकता हूँ?

पाई ऑफ पाई चार्ट में दूसरे पाई का आकार बदलने के लिए, का उपयोग करें`setSecondPieSize` विधि जैसा कि ऊपर दिए गए कोड उदाहरण में दिखाया गया है। आकार को प्रतिशत में निर्दिष्ट करने के लिए मान समायोजित करें।

###  क्या करता है`PieSplitBy` control in a Pie of Pie chart?

`PieSplitBy` प्रॉपर्टी नियंत्रित करती है कि पाई चार्ट कैसे विभाजित किया जाता है। आप इसे या तो सेट कर सकते हैं`PieSplitType.ByPercentage` या`PieSplitType.ByValue` चार्ट को क्रमशः प्रतिशत या किसी विशिष्ट मान के आधार पर विभाजित करने के लिए।

### मैं पाई ऑफ पाई चार्ट में विभाजन की स्थिति कैसे निर्धारित करूं?

 आप पाई ऑफ पाई चार्ट में विभाजन की स्थिति निर्धारित करने के लिए निम्न का उपयोग कर सकते हैं:`setPieSplitPosition` विधि। वांछित स्थिति निर्दिष्ट करने के लिए मान समायोजित करें।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
