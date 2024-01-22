---
title: जावा स्लाइड्स में फ़ॉन्ट आकार लीजेंड
linktitle: जावा स्लाइड्स में फ़ॉन्ट आकार लीजेंड
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Java के लिए Aspose.Slides के साथ PowerPoint प्रस्तुतियों को बेहतर बनाएं। हमारी चरण-दर-चरण मार्गदर्शिका में जानें कि लेजेंड फ़ॉन्ट आकार और अधिक को कैसे अनुकूलित करें।
type: docs
weight: 13
url: /hi/java/chart-elements/font-size-legend-java-slides/
---

## जावा स्लाइड्स में फॉन्ट साइज लेजेंड का परिचय

इस ट्यूटोरियल में, आप सीखेंगे कि जावा के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड में लेजेंड के फ़ॉन्ट आकार को कैसे अनुकूलित किया जाए। हम इस कार्य को प्राप्त करने के लिए चरण-दर-चरण निर्देश और स्रोत कोड प्रदान करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित और सेटअप है। आप यहां से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: प्रेजेंटेशन आरंभ करें

सबसे पहले, आवश्यक कक्षाएं आयात करें और अपनी पावरपॉइंट प्रस्तुति प्रारंभ करें।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 प्रतिस्थापित करें`"Your Document Directory"` आपकी PowerPoint फ़ाइल के वास्तविक पथ के साथ।

## चरण 2: एक चार्ट जोड़ें

इसके बाद, हम स्लाइड में एक चार्ट जोड़ेंगे और लेजेंड का फ़ॉन्ट आकार सेट करेंगे।

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 इस कोड में, हम पहली स्लाइड पर एक क्लस्टर्ड कॉलम चार्ट बनाते हैं और लेजेंड टेक्स्ट का फ़ॉन्ट आकार 20 बिंदुओं पर सेट करते हैं। आप समायोजित कर सकते हैं`setFontHeight`आवश्यकतानुसार फ़ॉन्ट आकार बदलने के लिए मान।

## चरण 3: अक्ष मानों को अनुकूलित करें

अब, आइए चार्ट के ऊर्ध्वाधर अक्ष मानों को अनुकूलित करें।

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

यहां, हम ऊर्ध्वाधर अक्ष के लिए न्यूनतम और अधिकतम मान निर्धारित करते हैं। आप अपनी डेटा आवश्यकताओं के अनुसार मानों को संशोधित कर सकते हैं।

## चरण 4: प्रस्तुति सहेजें

अंत में, संशोधित प्रस्तुति को एक नई फ़ाइल में सहेजें।

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

यह कोड संशोधित प्रस्तुति को निर्दिष्ट निर्देशिका में "आउटपुट.पीपीटीएक्स" के रूप में सहेजता है।

## जावा स्लाइड्स में फ़ॉन्ट आकार लीजेंड के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

आपने Java के लिए Aspose.Slides का उपयोग करके Java PowerPoint स्लाइड में लेजेंड के फ़ॉन्ट आकार को सफलतापूर्वक अनुकूलित कर लिया है। आप इंटरैक्टिव और देखने में आकर्षक प्रस्तुतियाँ बनाने के लिए Aspose.Slides की क्षमताओं का और पता लगा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट में लेजेंड टेक्स्ट का फ़ॉन्ट आकार कैसे बदलूं?

किसी चार्ट में लेजेंड टेक्स्ट का फ़ॉन्ट आकार बदलने के लिए, आप निम्न कोड का उपयोग कर सकते हैं:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 इस कोड में, हम एक चार्ट बनाते हैं और लेजेंड टेक्स्ट का फ़ॉन्ट आकार 20 बिंदुओं पर सेट करते हैं। आप समायोजित कर सकते हैं`setFontHeight`फ़ॉन्ट आकार बदलने के लिए मान.

### क्या मैं चार्ट में लेजेंड के अन्य गुणों को अनुकूलित कर सकता हूँ?

हाँ, आप Aspose.Slides का उपयोग करके चार्ट में लेजेंड के विभिन्न गुणों को अनुकूलित कर सकते हैं। कुछ सामान्य गुण जिन्हें आप अनुकूलित कर सकते हैं उनमें टेक्स्ट फ़ॉर्मेटिंग, स्थिति, दृश्यता और बहुत कुछ शामिल हैं। उदाहरण के लिए, लेजेंड की स्थिति बदलने के लिए, आप इसका उपयोग कर सकते हैं:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

यह कोड लेजेंड को चार्ट के नीचे प्रदर्शित होने के लिए सेट करता है। अधिक अनुकूलन विकल्पों के लिए Aspose.Slides दस्तावेज़ का अन्वेषण करें।

### मैं चार्ट में ऊर्ध्वाधर अक्ष के लिए न्यूनतम और अधिकतम मान कैसे निर्धारित करूं?

चार्ट में ऊर्ध्वाधर अक्ष के लिए न्यूनतम और अधिकतम मान सेट करने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

यहां, हम स्वचालित अक्ष स्केलिंग को अक्षम करते हैं और ऊर्ध्वाधर अक्ष के लिए न्यूनतम और अधिकतम मान निर्दिष्ट करते हैं। अपने चार्ट डेटा के लिए आवश्यकतानुसार मान समायोजित करें।

### Aspose.Slides के लिए मुझे अधिक जानकारी और दस्तावेज़ कहां मिल सकते हैं?

आप Aspose दस्तावेज़ीकरण वेबसाइट पर Java के लिए Aspose.Slides के लिए व्यापक दस्तावेज़ और API संदर्भ पा सकते हैं। मिलने जाना[यहाँ](https://reference.aspose.com/slides/java/) पुस्तकालय के उपयोग के बारे में विस्तृत जानकारी के लिए।