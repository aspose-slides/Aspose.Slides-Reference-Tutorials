---
title: जावा स्लाइड्स में व्यक्तिगत लेजेंड के लिए फ़ॉन्ट गुण
linktitle: जावा स्लाइड्स में व्यक्तिगत लेजेंड के लिए फ़ॉन्ट गुण
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java स्लाइड्स में व्यक्तिगत लेजेंड के लिए कस्टम फ़ॉन्ट शैलियों, आकारों और रंगों के साथ PowerPoint प्रस्तुतियों को बेहतर बनाएँ।
weight: 12
url: /hi/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## जावा स्लाइड्स में व्यक्तिगत लेजेंड के लिए फ़ॉन्ट गुणों का परिचय

इस ट्यूटोरियल में, हम जावा स्लाइड्स में Aspose.Slides for Java का उपयोग करके किसी व्यक्तिगत लेजेंड के लिए फ़ॉन्ट गुण सेट करने का तरीका जानेंगे। फ़ॉन्ट गुणों को अनुकूलित करके, आप अपने पावरपॉइंट प्रेजेंटेशन में अपने लेजेंड को अधिक आकर्षक और जानकारीपूर्ण बना सकते हैं।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी एकीकृत है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Slides for Java दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/).

## चरण 1: प्रस्तुति आरंभ करें और चार्ट जोड़ें

सबसे पहले, आइए एक पावरपॉइंट प्रेजेंटेशन को आरंभ करके और उसमें एक चार्ट जोड़कर शुरू करें। इस उदाहरण में, हम एक चित्रण के रूप में एक क्लस्टर कॉलम चार्ट का उपयोग करेंगे।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // शेष कोड यहां है
} finally {
    if (pres != null) pres.dispose();
}
```

 प्रतिस्थापित करें`"Your Document Directory"` वास्तविक निर्देशिका के साथ जहां आपका पावरपॉइंट दस्तावेज़ स्थित है।

## चरण 2: लेजेंड के लिए फ़ॉन्ट गुण अनुकूलित करें

अब, चार्ट के भीतर एक व्यक्तिगत लेजेंड प्रविष्टि के लिए फ़ॉन्ट गुणों को अनुकूलित करें। इस उदाहरण में, हम दूसरी लेजेंड प्रविष्टि (इंडेक्स 1) को लक्षित कर रहे हैं, लेकिन आप अपनी विशिष्ट आवश्यकताओं के अनुसार इंडेक्स को समायोजित कर सकते हैं।

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

कोड की प्रत्येक पंक्ति क्या करती है, यहां बताया गया है:

- `get_Item(1)` दूसरी लेजेंड प्रविष्टि (इंडेक्स 1) प्राप्त करता है। आप किसी भिन्न लेजेंड प्रविष्टि को लक्षित करने के लिए इंडेक्स को बदल सकते हैं।
- `setFontBold(NullableBool.True)` फ़ॉन्ट को बोल्ड पर सेट करता है.
- `setFontHeight(20)` फ़ॉन्ट का आकार 20 पॉइंट पर सेट करता है.
- `setFontItalic(NullableBool.True)` फ़ॉन्ट को इटैलिक पर सेट करता है.
- `setFillType(FillType.Solid)` निर्दिष्ट करता है कि किंवदंती प्रविष्टि पाठ में एक ठोस भरण होना चाहिए।
- `getSolidFillColor().setColor(Color.BLUE)` भरण रंग को नीला सेट करता है। आप इसे बदल सकते हैं`Color.BLUE` अपने इच्छित रंग के साथ.

## चरण 3: संशोधित प्रस्तुति को सहेजें

अंत में, अपने परिवर्तनों को सुरक्षित रखने के लिए संशोधित प्रस्तुति को एक नई फ़ाइल में सहेजें।

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 प्रतिस्थापित करें`"output.pptx"` अपने पसंदीदा आउटपुट फ़ाइल नाम के साथ.

बस! आपने Aspose.Slides for Java का उपयोग करके Java स्लाइड्स प्रेजेंटेशन में एक व्यक्तिगत लेजेंड प्रविष्टि के लिए फ़ॉन्ट गुणों को सफलतापूर्वक अनुकूलित कर लिया है।

## जावा स्लाइड्स में व्यक्तिगत लेजेंड के लिए फ़ॉन्ट गुणों हेतु पूर्ण स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Slides for Java का उपयोग करके Java Slides में किसी व्यक्तिगत लेजेंड के लिए फ़ॉन्ट गुणों को कैसे अनुकूलित किया जाए। फ़ॉन्ट शैलियों, आकारों और रंगों को समायोजित करके, आप अपने PowerPoint प्रस्तुतियों की दृश्य अपील और स्पष्टता को बढ़ा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं फ़ॉन्ट का रंग कैसे बदल सकता हूँ?

 फ़ॉन्ट का रंग बदलने के लिए, उपयोग करें`tf.getPortionFormat().getFontColor().setColor(yourColor)` भरण रंग बदलने के बजाय।`yourColor` इच्छित फ़ॉन्ट रंग के साथ.

### मैं अन्य लेजेंड गुणों को कैसे संशोधित करूँ?

आप लीजेंड के विभिन्न अन्य गुणों को संशोधित कर सकते हैं, जैसे कि स्थिति, आकार और प्रारूप। लीजेंड के साथ काम करने के बारे में विस्तृत जानकारी के लिए Aspose.Slides for Java दस्तावेज़ देखें।

### क्या मैं इन परिवर्तनों को एकाधिक लेजेंड प्रविष्टियों पर लागू कर सकता हूँ?

 हां, आप लीजेंड प्रविष्टियों के माध्यम से लूप कर सकते हैं और इंडेक्स को समायोजित करके इन परिवर्तनों को एकाधिक प्रविष्टियों पर लागू कर सकते हैं`get_Item(index)` और अनुकूलन कोड को दोहराएँ.

जब आप संसाधन जारी करने का काम पूरा कर लें तो प्रस्तुति ऑब्जेक्ट को हटाना याद रखें:

```java
if (pres != null) pres.dispose();
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
