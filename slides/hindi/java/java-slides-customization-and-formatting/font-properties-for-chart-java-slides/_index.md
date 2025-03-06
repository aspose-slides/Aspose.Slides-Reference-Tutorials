---
title: जावा स्लाइड्स में चार्ट के लिए फ़ॉन्ट गुण
linktitle: जावा स्लाइड्स में चार्ट के लिए फ़ॉन्ट गुण
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ Java स्लाइड्स में चार्ट फ़ॉन्ट गुण बढ़ाएँ। प्रभावशाली प्रस्तुतियों के लिए फ़ॉन्ट आकार, शैली और रंग को अनुकूलित करें।
weight: 11
url: /hi/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में चार्ट के लिए फ़ॉन्ट गुणों का परिचय

यह गाइड आपको Aspose.Slides का उपयोग करके Java Slides में चार्ट के लिए फ़ॉन्ट गुण सेट करने के बारे में बताएगी। आप अपनी प्रस्तुतियों की दृश्य अपील को बढ़ाने के लिए चार्ट टेक्स्ट के फ़ॉन्ट आकार और उपस्थिति को अनुकूलित कर सकते हैं।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides for Java API एकीकृत है। यदि आपने पहले से ऐसा नहीं किया है, तो आप इसे यहाँ से डाउनलोड कर सकते हैं।[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/).

## चरण 1: एक प्रस्तुति बनाएं

सबसे पहले, निम्नलिखित कोड का उपयोग करके एक नई प्रस्तुति बनाएं:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: चार्ट जोड़ें

अब, आइए अपनी प्रस्तुति में एक क्लस्टर कॉलम चार्ट जोड़ें:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

यहां, हम निर्देशांक (100, 100) पर पहली स्लाइड में 500 इकाइयों की चौड़ाई और 400 इकाइयों की ऊंचाई के साथ एक क्लस्टर कॉलम चार्ट जोड़ रहे हैं।

## चरण 3: फ़ॉन्ट गुण अनुकूलित करें

इसके बाद, हम चार्ट के फ़ॉन्ट गुणों को कस्टमाइज़ करेंगे। इस उदाहरण में, हम सभी चार्ट टेक्स्ट के लिए फ़ॉन्ट आकार 20 पर सेट कर रहे हैं:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

यह कोड चार्ट के भीतर सभी पाठ के लिए फ़ॉन्ट आकार को 20 पॉइंट पर सेट करता है।

## चरण 4: डेटा लेबल दिखाएँ

आप निम्नलिखित कोड का उपयोग करके चार्ट पर डेटा लेबल भी दिखा सकते हैं:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

कोड की यह पंक्ति चार्ट में पहली श्रृंखला के लिए डेटा लेबल सक्षम करती है, तथा चार्ट स्तंभों पर मान प्रदर्शित करती है।

## चरण 5: प्रस्तुति सहेजें

अंत में, अपनी अनुकूलित चार्ट फ़ॉन्ट विशेषताओं के साथ प्रस्तुति को सहेजें:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

यह कोड प्रस्तुति को "FontPropertiesForChart.pptx" फ़ाइल नाम के साथ निर्दिष्ट निर्देशिका में सहेज देगा।

## जावा स्लाइड्स में चार्ट के लिए फ़ॉन्ट गुणों के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Slides for Java का उपयोग करके Java Slides में चार्ट के लिए फ़ॉन्ट गुण कैसे अनुकूलित करें। आप अपने चार्ट और प्रस्तुतियों की उपस्थिति को बेहतर बनाने के लिए इन तकनीकों को लागू कर सकते हैं। में और अधिक विकल्प खोजें[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/).

## अक्सर पूछे जाने वाले प्रश्न

### मैं फ़ॉन्ट का रंग कैसे बदल सकता हूँ?

 चार्ट टेक्स्ट के लिए फ़ॉन्ट रंग बदलने के लिए, उपयोग करें`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , प्रतिस्थापित`Color.RED` इच्छित रंग के साथ.

### क्या मैं फ़ॉन्ट शैली (बोल्ड, इटैलिक, आदि) बदल सकता हूँ?

 हां, आप फ़ॉन्ट शैली बदल सकते हैं।`chart.getTextFormat().getPortionFormat().setFontBold(true);` फ़ॉन्ट को बोल्ड बनाने के लिए। इसी तरह, आप उपयोग कर सकते हैं`setFontItalic(true)` इसे इटैलिक बनाने के लिए.

### मैं विशिष्ट चार्ट तत्वों के लिए फ़ॉन्ट गुण कैसे अनुकूलित करूं?

विशिष्ट चार्ट तत्वों, जैसे अक्ष लेबल या लेजेंड पाठ, के लिए फ़ॉन्ट गुणों को अनुकूलित करने के लिए, आप उन तत्वों तक पहुँच सकते हैं और ऊपर दिखाए गए समान तरीकों का उपयोग करके उनके फ़ॉन्ट गुणों को सेट कर सकते हैं।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
