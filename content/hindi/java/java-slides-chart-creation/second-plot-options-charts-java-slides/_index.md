---
title: जावा स्लाइड में चार्ट के लिए दूसरा प्लॉट विकल्प
linktitle: जावा स्लाइड में चार्ट के लिए दूसरा प्लॉट विकल्प
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में चार्ट को अनुकूलित करना सीखें। दूसरे प्लॉट विकल्पों का अन्वेषण करें और अपनी प्रस्तुतियों को बेहतर बनाएं।
type: docs
weight: 12
url: /hi/java/chart-creation/second-plot-options-charts-java-slides/
---

## जावा स्लाइड में चार्ट के लिए दूसरे प्लॉट विकल्प का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि Java के लिए Aspose.Slides का उपयोग करके चार्ट में दूसरे प्लॉट विकल्प कैसे जोड़ें। दूसरे प्लॉट विकल्प आपको चार्ट के स्वरूप और व्यवहार को अनुकूलित करने की अनुमति देते हैं, विशेष रूप से पाई ऑफ पाई चार्ट जैसे परिदृश्यों में। इसे प्राप्त करने के लिए हम चरण-दर-चरण निर्देश और स्रोत कोड उदाहरण प्रदान करेंगे। 

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java स्थापित और सेटअप है।

## चरण 1: एक प्रेजेंटेशन बनाएं
आइए एक नई प्रस्तुति बनाकर शुरुआत करें:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएं
Presentation presentation = new Presentation();
```

## चरण 2: स्लाइड में एक चार्ट जोड़ें
इसके बाद, हम स्लाइड में एक चार्ट जोड़ेंगे। इस उदाहरण में, हम पाई ऑफ पाई चार्ट बनाएंगे:

```java
// स्लाइड पर चार्ट जोड़ें
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## चरण 3: चार्ट गुणों को अनुकूलित करें
अब, आइए चार्ट के लिए दूसरे प्लॉट विकल्प सहित अलग-अलग गुण सेट करें:

```java
// पहली श्रृंखला के लिए डेटा लेबल दिखाएं
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// दूसरी पाई का आकार निर्धारित करें (प्रतिशत में)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// पाई को प्रतिशत से विभाजित करें
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// विभाजन की स्थिति निर्धारित करें
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## चरण 4: प्रस्तुति सहेजें
अंत में, प्रस्तुति को चार्ट और दूसरे प्लॉट विकल्पों के साथ सहेजें:

```java
// डिस्क पर प्रेजेंटेशन लिखें
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## दूसरे प्लॉट विकल्पों के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएं
Presentation presentation = new Presentation();
// स्लाइड पर चार्ट जोड़ें
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// अलग-अलग गुण सेट करें
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// डिस्क पर प्रेजेंटेशन लिखें
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में चार्ट में दूसरे प्लॉट विकल्प कैसे जोड़ें। आप अपने चार्ट की उपस्थिति और कार्यक्षमता को बढ़ाने के लिए विभिन्न गुणों को अनुकूलित कर सकते हैं, जिससे आपकी प्रस्तुतियाँ अधिक जानकारीपूर्ण और देखने में आकर्षक बन जाएंगी।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पाई ऑफ़ पाई चार्ट में दूसरी पाई का आकार कैसे बदल सकता हूँ?

 पाई ऑफ़ पाई चार्ट में दूसरी पाई का आकार बदलने के लिए, इसका उपयोग करें`setSecondPieSize` विधि जैसा कि ऊपर दिए गए कोड उदाहरण में दिखाया गया है। प्रतिशत में आकार निर्दिष्ट करने के लिए मान समायोजित करें।

###  क्या करता है`PieSplitBy` control in a Pie of Pie chart?

`PieSplitBy`संपत्ति नियंत्रित करती है कि पाई चार्ट कैसे विभाजित होता है। आप इसे या तो सेट कर सकते हैं`PieSplitType.ByPercentage` या`PieSplitType.ByValue` चार्ट को क्रमशः प्रतिशत या विशिष्ट मान से विभाजित करना।

### मैं पाई ऑफ पाई चार्ट में विभाजन की स्थिति कैसे निर्धारित करूं?

 आप इसका उपयोग करके पाई ऑफ़ पाई चार्ट में विभाजन की स्थिति निर्धारित कर सकते हैं`setPieSplitPosition` तरीका। वांछित स्थिति निर्दिष्ट करने के लिए मान समायोजित करें।