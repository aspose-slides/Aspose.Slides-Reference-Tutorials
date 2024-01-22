---
title: जावा स्लाइड्स में व्यक्तिगत लीजेंड के लिए फ़ॉन्ट गुण
linktitle: जावा स्लाइड्स में व्यक्तिगत लीजेंड के लिए फ़ॉन्ट गुण
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में व्यक्तिगत किंवदंतियों के लिए कस्टम फ़ॉन्ट शैलियों, आकारों और रंगों के साथ पावरपॉइंट प्रस्तुतियों को बढ़ाएं।
type: docs
weight: 12
url: /hi/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

## जावा स्लाइड्स में व्यक्तिगत लीजेंड के लिए फ़ॉन्ट गुणों का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में एक व्यक्तिगत लेजेंड के लिए फ़ॉन्ट गुण कैसे सेट करें। फ़ॉन्ट गुणों को अनुकूलित करके, आप अपनी पावरपॉइंट प्रस्तुतियों में अपनी किंवदंतियों को अधिक आकर्षक और जानकारीपूर्ण बना सकते हैं।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास जावा लाइब्रेरी के लिए Aspose.Slides आपके प्रोजेक्ट में एकीकृत है। आप इसे यहां से डाउनलोड कर सकते हैं[जावा दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/java/).

## चरण 1: प्रेजेंटेशन शुरू करें और चार्ट जोड़ें

सबसे पहले, आइए एक पावरपॉइंट प्रेजेंटेशन को आरंभ करके और उसमें एक चार्ट जोड़कर शुरुआत करें। इस उदाहरण में, हम चित्रण के रूप में एक क्लस्टर्ड कॉलम चार्ट का उपयोग करेंगे।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // बाकी कोड यहां जाता है
} finally {
    if (pres != null) pres.dispose();
}
```

 प्रतिस्थापित करें`"Your Document Directory"` उस वास्तविक निर्देशिका के साथ जहां आपका PowerPoint दस्तावेज़ स्थित है।

## चरण 2: लीजेंड के लिए फ़ॉन्ट गुण अनुकूलित करें

अब, आइए चार्ट के भीतर एक व्यक्तिगत लेजेंड प्रविष्टि के लिए फ़ॉन्ट गुणों को अनुकूलित करें। इस उदाहरण में, हम दूसरी लेजेंड प्रविष्टि (सूचकांक 1) को लक्षित कर रहे हैं, लेकिन आप अपनी विशिष्ट आवश्यकताओं के अनुसार सूचकांक को समायोजित कर सकते हैं।

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

यहां बताया गया है कि कोड की प्रत्येक पंक्ति क्या करती है:

- `get_Item(1)` दूसरी लेजेंड प्रविष्टि (सूचकांक 1) पुनः प्राप्त करता है। आप किसी भिन्न लेजेंड प्रविष्टि को लक्षित करने के लिए अनुक्रमणिका को बदल सकते हैं।
- `setFontBold(NullableBool.True)` फ़ॉन्ट को बोल्ड पर सेट करता है।
- `setFontHeight(20)` फ़ॉन्ट आकार को 20 बिंदुओं पर सेट करता है।
- `setFontItalic(NullableBool.True)` फ़ॉन्ट को इटैलिक पर सेट करता है।
- `setFillType(FillType.Solid)` निर्दिष्ट करता है कि लेजेंड प्रविष्टि पाठ में ठोस भरण होना चाहिए।
- `getSolidFillColor().setColor(Color.BLUE)` भरण रंग को नीला पर सेट करता है। आप प्रतिस्थापित कर सकते हैं`Color.BLUE` अपने मनचाहे रंग के साथ.

## चरण 3: संशोधित प्रस्तुति सहेजें

अंत में, अपने परिवर्तनों को संरक्षित करने के लिए संशोधित प्रस्तुति को एक नई फ़ाइल में सहेजें।

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 प्रतिस्थापित करें`"output.pptx"` आपके पसंदीदा आउटपुट फ़ाइल नाम के साथ।

इतना ही! आपने जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड प्रस्तुति में एक व्यक्तिगत लेजेंड प्रविष्टि के लिए फ़ॉन्ट गुणों को सफलतापूर्वक अनुकूलित किया है।

## जावा स्लाइड्स में व्यक्तिगत लीजेंड के लिए फ़ॉन्ट गुणों के लिए संपूर्ण स्रोत कोड

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

इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में एक व्यक्तिगत लेजेंड के लिए फ़ॉन्ट गुणों को कैसे अनुकूलित किया जाए। फ़ॉन्ट शैलियों, आकारों और रंगों को समायोजित करके, आप अपनी पावरपॉइंट प्रस्तुतियों की दृश्य अपील और स्पष्टता को बढ़ा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं फ़ॉन्ट का रंग कैसे बदल सकता हूँ?

 फ़ॉन्ट रंग बदलने के लिए, उपयोग करें`tf.getPortionFormat().getFontColor().setColor(yourColor)` भरण रंग बदलने के बजाय। प्रतिस्थापित करें`yourColor` वांछित फ़ॉन्ट रंग के साथ.

### मैं अन्य लेजेंड संपत्तियों को कैसे संशोधित करूं?

आप लेजेंड के विभिन्न अन्य गुणों, जैसे स्थिति, आकार और प्रारूप को संशोधित कर सकते हैं। किंवदंतियों के साथ काम करने की विस्तृत जानकारी के लिए जावा दस्तावेज़ के लिए Aspose.Slides देखें।

### क्या मैं इन परिवर्तनों को एकाधिक लेजेंड प्रविष्टियों पर लागू कर सकता हूँ?

 हां, आप लेजेंड प्रविष्टियों के माध्यम से लूप कर सकते हैं और इंडेक्स को समायोजित करके इन परिवर्तनों को एकाधिक प्रविष्टियों पर लागू कर सकते हैं`get_Item(index)` और अनुकूलन कोड को दोहराना।

जब आप संसाधन जारी करने का काम पूरा कर लें तो प्रेजेंटेशन ऑब्जेक्ट का निपटान करना याद रखें:

```java
if (pres != null) pres.dispose();
```