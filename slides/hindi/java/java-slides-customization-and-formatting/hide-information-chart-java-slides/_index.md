---
title: जावा स्लाइड्स में चार्ट से जानकारी छिपाएँ
linktitle: जावा स्लाइड्स में चार्ट से जानकारी छिपाएँ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ Java स्लाइड में चार्ट तत्वों को छिपाने का तरीका जानें। चरण-दर-चरण मार्गदर्शन और स्रोत कोड के साथ स्पष्टता और सौंदर्य के लिए प्रस्तुतियों को अनुकूलित करें।
weight: 13
url: /hi/java/customization-and-formatting/hide-information-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में चार्ट से जानकारी छिपाएँ


## जावा स्लाइड्स में चार्ट से जानकारी छिपाने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java API का उपयोग करके Java Slides में चार्ट से विभिन्न तत्वों को छिपाने का तरीका जानेंगे। आप अपने प्रेजेंटेशन के लिए आवश्यकतानुसार अपने चार्ट को कस्टमाइज़ करने के लिए इस कोड का उपयोग कर सकते हैं।

## चरण 1: वातावरण की स्थापना

 शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी जोड़ी गई है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 2: एक नई प्रस्तुति बनाएँ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 3: स्लाइड में चार्ट जोड़ना

हम स्लाइड में मार्करों के साथ एक लाइन चार्ट जोड़ेंगे और फिर चार्ट के विभिन्न तत्वों को छिपाने के लिए आगे बढ़ेंगे।

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## चरण 4: चार्ट शीर्षक छिपाएँ

आप चार्ट शीर्षक को निम्न प्रकार से छिपा सकते हैं:

```java
chart.setTitle(false);
```

## चरण 5: मान अक्ष छिपाएँ

मान अक्ष (ऊर्ध्वाधर अक्ष) को छिपाने के लिए, निम्नलिखित कोड का उपयोग करें:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## चरण 6: श्रेणी अक्ष छिपाएँ

श्रेणी अक्ष (क्षैतिज अक्ष) को छिपाने के लिए, इस कोड का उपयोग करें:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## चरण 7: लेजेंड छिपाएँ

आप चार्ट की लेजेंड को इस प्रकार छिपा सकते हैं:

```java
chart.setLegend(false);
```

## चरण 8: प्रमुख ग्रिड लाइनों को छिपाएँ

क्षैतिज अक्ष की प्रमुख ग्रिड लाइनों को छिपाने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## चरण 9: श्रृंखला हटाएँ

यदि आप चार्ट से सभी श्रृंखलाएं हटाना चाहते हैं, तो आप इस तरह लूप का उपयोग कर सकते हैं:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## चरण 10: चार्ट श्रृंखला अनुकूलित करें

आप चार्ट श्रृंखला को आवश्यकतानुसार अनुकूलित कर सकते हैं। इस उदाहरण में, हम मार्कर शैली, डेटा लेबल स्थिति, मार्कर आकार, रेखा रंग और डैश शैली बदलते हैं:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## चरण 11: प्रस्तुति सहेजें

अंत में, प्रस्तुति को एक फ़ाइल में सहेजें:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

बस! आपने Aspose.Slides for Java का उपयोग करके Java Slides में चार्ट से विभिन्न तत्वों को सफलतापूर्वक छिपा दिया है। आप अपनी विशिष्ट आवश्यकताओं के अनुसार अपने चार्ट और प्रस्तुतियों को और भी अनुकूलित कर सकते हैं।

## जावा स्लाइड्स में चार्ट से जानकारी छिपाने के लिए पूरा स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//चार्ट शीर्षक छिपाया जा रहा है
	chart.setTitle(false);
	///मान छिपाना अक्ष
	chart.getAxes().getVerticalAxis().setVisible(false);
	//श्रेणी अक्ष दृश्यता
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//किंवदंती छिपाना
	chart.setLegend(false);
	//मेजरग्रिडलाइन्स छिपाना
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//श्रृंखला रेखा रंग सेट करना
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## निष्कर्ष

इस चरण-दर-चरण मार्गदर्शिका में, हमने Aspose.Slides for Java API का उपयोग करके Java Slides में चार्ट से विभिन्न तत्वों को छिपाने का तरीका खोजा है। यह तब अविश्वसनीय रूप से उपयोगी हो सकता है जब आपको प्रस्तुतियों के लिए अपने चार्ट को अनुकूलित करने और उन्हें अधिक आकर्षक बनाने या अपनी विशिष्ट आवश्यकताओं के अनुरूप बनाने की आवश्यकता हो।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट तत्वों के स्वरूप को और अधिक अनुकूलित कैसे करूँ?

आप चार्ट श्रृंखला, मार्कर, लेबल और प्रारूप के संगत गुणों तक पहुँच कर चार्ट तत्वों के विभिन्न गुणों जैसे लाइन रंग, भरण रंग, मार्कर शैली आदि को अनुकूलित कर सकते हैं।

### क्या मैं चार्ट में विशिष्ट डेटा बिंदु छिपा सकता हूँ?

हां, आप चार्ट सीरीज में डेटा में हेरफेर करके विशिष्ट डेटा पॉइंट छिपा सकते हैं। आप डेटा पॉइंट को हटा सकते हैं या उन्हें छिपाने के लिए उनके मान को शून्य पर सेट कर सकते हैं।

### मैं चार्ट में अतिरिक्त श्रृंखला कैसे जोड़ सकता हूँ?

 आप इसका उपयोग करके चार्ट में अधिक श्रृंखलाएँ जोड़ सकते हैं`IChartData.getSeries().add` विधि का उपयोग करना और नई श्रृंखला के लिए डेटा बिंदु निर्दिष्ट करना।

### क्या चार्ट प्रकार को गतिशील रूप से बदलना संभव है?

हां, आप इच्छित प्रकार का नया चार्ट बनाकर और पुराने चार्ट से डेटा को नए चार्ट में कॉपी करके चार्ट प्रकार को गतिशील रूप से बदल सकते हैं।

### मैं चार्ट का शीर्षक और अक्ष लेबल प्रोग्रामेटिक रूप से कैसे बदल सकता हूँ?

आप चार्ट और अक्षों के शीर्षक और लेबल को उनके संबंधित गुणों तक पहुंचकर और वांछित पाठ और स्वरूपण सेट करके सेट कर सकते हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
