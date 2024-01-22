---
title: जावा स्लाइड्स में फ़ॉन्ट गुण सेट करना
linktitle: जावा स्लाइड्स में फ़ॉन्ट गुण सेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में फ़ॉन्ट गुण सेट करना सीखें। इस चरण-दर-चरण मार्गदर्शिका में कोड उदाहरण और अक्सर पूछे जाने वाले प्रश्न शामिल हैं।
type: docs
weight: 15
url: /hi/java/customization-and-formatting/setting-font-properties-java-slides/
---

## जावा स्लाइड्स में फ़ॉन्ट गुण सेट करने का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में टेक्स्ट के लिए फ़ॉन्ट गुण कैसे सेट करें। बोल्डनेस और फ़ॉन्ट आकार जैसे फ़ॉन्ट गुणों को आपकी स्लाइड की उपस्थिति को बढ़ाने के लिए अनुकूलित किया जा सकता है।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Slides जोड़ा गया है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: प्रस्तुति आरंभ करें

 सबसे पहले, आपको मौजूदा PowerPoint फ़ाइल को लोड करके एक प्रेजेंटेशन ऑब्जेक्ट को प्रारंभ करना होगा। प्रतिस्थापित करें`"Your Document Directory"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## चरण 2: एक चार्ट जोड़ें

इस उदाहरण में, हम पहली स्लाइड पर एक चार्ट के साथ काम करेंगे। आप अपनी आवश्यकता के अनुसार स्लाइड इंडेक्स को बदल सकते हैं। हम एक क्लस्टर्ड कॉलम चार्ट जोड़ेंगे और डेटा तालिका सक्षम करेंगे।

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## चरण 3: फ़ॉन्ट गुणों को अनुकूलित करें

अब, आइए चार्ट डेटा तालिका के फ़ॉन्ट गुणों को अनुकूलित करें। हम फ़ॉन्ट को बोल्ड करने के लिए सेट करेंगे और फ़ॉन्ट की ऊंचाई (आकार) समायोजित करेंगे।

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`: यह पंक्ति फ़ॉन्ट को बोल्ड करने के लिए सेट करती है।
- `setFontHeight(20)`: यह पंक्ति फ़ॉन्ट ऊंचाई को 20 बिंदुओं पर सेट करती है। आप इस मान को आवश्यकतानुसार समायोजित कर सकते हैं।

## चरण 4: प्रस्तुति सहेजें

अंत में, संशोधित प्रस्तुति को एक नई फ़ाइल में सहेजें। आप आउटपुट स्वरूप निर्दिष्ट कर सकते हैं; इस मामले में, हम इसे PPTX फ़ाइल के रूप में सहेज रहे हैं।

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में फ़ॉन्ट गुण सेट करने के लिए संपूर्ण स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.setDataTable(true);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में टेक्स्ट के लिए फ़ॉन्ट गुण कैसे सेट करें। आप अपनी पावरपॉइंट प्रस्तुतियों में टेक्स्ट की उपस्थिति को बढ़ाने के लिए इन तकनीकों को लागू कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं फ़ॉन्ट का रंग कैसे बदलूं?

 फ़ॉन्ट रंग बदलने के लिए, का उपयोग करें`setFontColor` विधि और वांछित रंग निर्दिष्ट करें। उदाहरण के लिए:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### क्या मैं स्लाइड में अन्य टेक्स्ट के लिए फ़ॉन्ट बदल सकता हूँ?

हां, आप स्लाइड में अन्य टेक्स्ट तत्वों, जैसे शीर्षक और लेबल, के लिए फ़ॉन्ट बदल सकते हैं। विशिष्ट पाठ तत्वों के लिए फ़ॉन्ट गुणों तक पहुँचने और अनुकूलित करने के लिए उपयुक्त वस्तुओं और विधियों का उपयोग करें।

### मैं इटैलिक फ़ॉन्ट शैली कैसे सेट करूं?

 फ़ॉन्ट शैली को इटैलिक पर सेट करने के लिए, इसका उपयोग करें`setFontItalic` तरीका:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

 समायोजित`NullableBool.True` इटैलिक शैली को सक्षम या अक्षम करने के लिए आवश्यक पैरामीटर।

### मैं चार्ट में डेटा लेबल के लिए फ़ॉन्ट कैसे बदल सकता हूँ?

चार्ट में डेटा लेबल के लिए फ़ॉन्ट बदलने के लिए, आपको उचित तरीकों का उपयोग करके डेटा लेबल टेक्स्ट प्रारूप तक पहुंचने की आवश्यकता है। उदाहरण के लिए:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // आवश्यकतानुसार सूचकांक बदलें
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

यह कोड पहली श्रृंखला में डेटा लेबल के फ़ॉन्ट को बोल्ड में सेट करता है।

### मैं पाठ के किसी विशिष्ट भाग के लिए फ़ॉन्ट कैसे बदलूं?

 यदि आप टेक्स्ट तत्व के भीतर टेक्स्ट के किसी विशिष्ट भाग के लिए फ़ॉन्ट बदलना चाहते हैं, तो आप इसका उपयोग कर सकते हैं`PortionFormat` कक्षा। उस हिस्से तक पहुंचें जिसे आप संशोधित करना चाहते हैं और फिर वांछित फ़ॉन्ट गुण सेट करें।

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // आवश्यकतानुसार सूचकांक बदलें
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // आवश्यकतानुसार सूचकांक बदलें
IPortion portion = paragraph.getPortions().get_Item(0); // आवश्यकतानुसार सूचकांक बदलें

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

यह कोड किसी आकृति के भीतर पाठ के पहले भाग के फ़ॉन्ट को बोल्ड में सेट करता है और फ़ॉन्ट की ऊंचाई को समायोजित करता है।

### मैं प्रेजेंटेशन में सभी स्लाइड्स पर फ़ॉन्ट परिवर्तन कैसे लागू कर सकता हूं?

किसी प्रस्तुतिकरण में सभी स्लाइडों में फ़ॉन्ट परिवर्तन लागू करने के लिए, आप स्लाइडों के माध्यम से पुनरावृति कर सकते हैं और आवश्यकतानुसार फ़ॉन्ट गुणों को समायोजित कर सकते हैं। प्रत्येक स्लाइड और उनके भीतर के टेक्स्ट तत्वों तक पहुंचने के लिए एक लूप का उपयोग करें, फिर फ़ॉन्ट गुणों को कस्टमाइज़ करें।

```java
for (ISlide slide : pres.getSlides()) {
    // यहां टेक्स्ट तत्वों के फ़ॉन्ट गुणों तक पहुंचें और उन्हें अनुकूलित करें
}
```