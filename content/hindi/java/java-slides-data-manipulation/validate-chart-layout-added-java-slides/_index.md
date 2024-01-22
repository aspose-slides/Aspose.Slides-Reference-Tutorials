---
title: जावा स्लाइड्स में मान्य चार्ट लेआउट जोड़ा गया
linktitle: जावा स्लाइड्स में मान्य चार्ट लेआउट जोड़ा गया
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides के साथ PowerPoint में मास्टर चार्ट लेआउट सत्यापन। आश्चर्यजनक प्रस्तुतियों के लिए प्रोग्रामेटिक रूप से चार्ट में हेरफेर करना सीखें।
type: docs
weight: 10
url: /hi/java/data-manipulation/validate-chart-layout-added-java-slides/
---

## जावा के लिए Aspose.Slides में चार्ट लेआउट को मान्य करने का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में चार्ट लेआउट को कैसे मान्य किया जाए। यह लाइब्रेरी आपको PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है, जिससे चार्ट सहित विभिन्न तत्वों में हेरफेर और सत्यापन करना आसान हो जाता है।

## चरण 1: प्रेजेंटेशन आरंभ करना

सबसे पहले, हमें एक प्रेजेंटेशन ऑब्जेक्ट को इनिशियलाइज़ करना होगा और एक मौजूदा पावरपॉइंट प्रेजेंटेशन को लोड करना होगा। प्रतिस्थापित करें`"Your Document Directory"` आपकी प्रस्तुति फ़ाइल के वास्तविक पथ के साथ (`test.pptx` इस उदाहरण में)।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## चरण 2: एक चार्ट जोड़ना

 इसके बाद, हम प्रेजेंटेशन में एक चार्ट जोड़ेंगे। इस उदाहरण में, हम एक क्लस्टर्ड कॉलम चार्ट जोड़ रहे हैं, लेकिन आप इसे बदल सकते हैं`ChartType` जरुरत के अनुसार।

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## चरण 3: चार्ट लेआउट को मान्य करना

 अब, हम इसका उपयोग करके चार्ट लेआउट को सत्यापित करेंगे`validateChartLayout()` तरीका। यह सुनिश्चित करता है कि चार्ट स्लाइड के भीतर ठीक से रखा गया है।

```java
chart.validateChartLayout();
```

## चरण 4: चार्ट स्थिति और आकार पुनः प्राप्त करना

चार्ट लेआउट को सत्यापित करने के बाद, आप इसकी स्थिति और आकार के बारे में जानकारी पुनः प्राप्त करना चाह सकते हैं। हम वास्तविक एक्स और वाई निर्देशांक, साथ ही चार्ट के प्लॉट क्षेत्र की चौड़ाई और ऊंचाई प्राप्त कर सकते हैं।

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## चरण 5: प्रस्तुति को सहेजना

 अंत में, संशोधित प्रस्तुति को सहेजना न भूलें। इस उदाहरण में, हम इसे इस रूप में सहेज रहे हैं`Result.pptx`, लेकिन यदि आवश्यक हो तो आप एक अलग फ़ाइल नाम निर्दिष्ट कर सकते हैं।

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में मान्य चार्ट लेआउट के लिए पूर्ण स्रोत कोड जोड़ा गया

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// प्रस्तुतिकरण सहेजा जा रहा है
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में चार्ट के साथ काम करने की दुनिया के बारे में गहराई से जानकारी प्राप्त की। हमने चार्ट लेआउट को सत्यापित करने, उसकी स्थिति और आकार पुनः प्राप्त करने और संशोधित प्रस्तुति को सहेजने के लिए आवश्यक चरणों को कवर किया है। यहाँ एक त्वरित पुनर्कथन है:

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट प्रकार कैसे बदलूं?

 चार्ट प्रकार बदलने के लिए, बस बदलें`ChartType.ClusteredColumn` वांछित चार्ट प्रकार के साथ`addChart()` तरीका।

### क्या मैं चार्ट डेटा को अनुकूलित कर सकता हूँ?

हां, आप डेटा श्रृंखला, श्रेणियों और मूल्यों को जोड़कर और संशोधित करके चार्ट डेटा को अनुकूलित कर सकते हैं। अधिक विवरण के लिए Aspose.Slides दस्तावेज़ देखें।

### यदि मैं अन्य चार्ट गुणों को संशोधित करना चाहूँ तो क्या होगा?

आप विभिन्न चार्ट संपत्तियों तक पहुंच सकते हैं और उन्हें अपनी आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं। चार्ट हेरफेर पर व्यापक जानकारी के लिए Aspose.Slides दस्तावेज़ का अन्वेषण करें।
