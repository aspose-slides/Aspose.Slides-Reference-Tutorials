---
title: जावा स्लाइड्स में डेटा बिंदुओं में रंग जोड़ें
linktitle: जावा स्लाइड्स में डेटा बिंदुओं में रंग जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java स्लाइड्स में डेटा बिंदुओं में रंग जोड़ना सीखें।
weight: 10
url: /hi/java/chart-data-manipulation/add-color-data-points-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में डेटा बिंदुओं में रंग जोड़ने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके Java स्लाइड में डेटा पॉइंट में रंग जोड़ने का तरीका दिखाएंगे। इस चरण-दर-चरण मार्गदर्शिका में इस कार्य को पूरा करने में आपकी सहायता करने के लिए स्रोत कोड उदाहरण शामिल हैं।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा विकास पर्यावरण
- Aspose.Slides for Java लाइब्रेरी

## चरण 1: एक नई प्रस्तुति बनाएँ

सबसे पहले, हम Aspose.Slides for Java का उपयोग करके एक नई प्रस्तुति बनाएंगे। यह प्रस्तुति हमारे चार्ट के लिए कंटेनर के रूप में काम करेगी।

```java
Presentation pres = new Presentation();
```

## चरण 2: सनबर्स्ट चार्ट जोड़ें

अब, आइए प्रेजेंटेशन में सनबर्स्ट चार्ट जोड़ें। हम चार्ट का प्रकार, स्थिति और आकार निर्दिष्ट करते हैं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## चरण 3: डेटा पॉइंट तक पहुंचें

 चार्ट में डेटा बिंदुओं को संशोधित करने के लिए, हमें एक्सेस करने की आवश्यकता है`IChartDataPointCollection` वस्तु।

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## चरण 4: डेटा पॉइंट्स को अनुकूलित करें

इस चरण में, हम विशिष्ट डेटा बिंदुओं को कस्टमाइज़ करेंगे। यहाँ, हम डेटा बिंदुओं का रंग बदल रहे हैं और लेबल सेटिंग कॉन्फ़िगर कर रहे हैं।

```java
// डेटा बिंदु 0 को अनुकूलित करें
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// डेटा बिंदु 9 को अनुकूलित करें
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## चरण 5: प्रस्तुति सहेजें

अंत में, अनुकूलित चार्ट के साथ प्रस्तुति को सहेजें।

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

बस! आपने Aspose.Slides for Java का उपयोग करके Java स्लाइड में विशिष्ट डेटा बिंदुओं में सफलतापूर्वक रंग जोड़ दिया है।

## जावा स्लाइड्स में डेटा बिंदुओं में रंग जोड़ने के लिए पूर्ण स्रोत कोड

```java
Presentation pres = new Presentation();
try
{
	// दस्तावेज़ निर्देशिका का पथ.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//करने के लिए
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि Aspose.Slides for Java का उपयोग करके Java स्लाइड में डेटा पॉइंट में रंग कैसे जोड़ें। आप अपनी विशिष्ट आवश्यकताओं के आधार पर अपने चार्ट और प्रस्तुतियों को और भी अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं अन्य डेटा बिंदुओं का रंग कैसे बदल सकता हूँ?

अन्य डेटा बिंदुओं का रंग बदलने के लिए, आप चरण 4 में दिखाए गए समान दृष्टिकोण का पालन कर सकते हैं। उस डेटा बिंदु तक पहुँचें जिसे आप अनुकूलित करना चाहते हैं और उसके रंग और लेबल सेटिंग को संशोधित करें।

### क्या मैं चार्ट के अन्य पहलुओं को अनुकूलित कर सकता हूँ?

 हां, आप चार्ट के विभिन्न पहलुओं को अनुकूलित कर सकते हैं, जिसमें फ़ॉन्ट, लेबल, शीर्षक और बहुत कुछ शामिल है।[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/) विस्तृत अनुकूलन विकल्पों के लिए.

### मैं और अधिक उदाहरण और दस्तावेज कहां पा सकता हूं?

 आप जावा के लिए Aspose.Slides का उपयोग करने पर अधिक उदाहरण और विस्तृत दस्तावेज़ पा सकते हैं[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) वेबसाइट।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
