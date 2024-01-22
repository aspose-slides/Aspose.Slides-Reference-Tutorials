---
title: जावा स्लाइड्स में कस्टम लाइन्स जोड़ना
linktitle: जावा स्लाइड्स में कस्टम लाइन्स जोड़ना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: कस्टम लाइन्स के साथ अपनी जावा स्लाइड्स को बेहतर बनाएं। जावा के लिए Aspose.Slides का उपयोग करके चरण-दर-चरण मार्गदर्शिका। प्रभावशाली दृश्यों के लिए प्रस्तुतियों में पंक्तियाँ जोड़ना और अनुकूलित करना सीखें।
type: docs
weight: 10
url: /hi/java/customization-and-formatting/adding-custom-lines-java-slides/
---

## जावा स्लाइड्स में कस्टम लाइन्स जोड़ने का परिचय

इस ट्यूटोरियल में, आप सीखेंगे कि जावा के लिए Aspose.Slides का उपयोग करके अपनी जावा स्लाइड्स में कस्टम लाइनें कैसे जोड़ें। कस्टम लाइनों का उपयोग आपकी स्लाइड के दृश्य प्रतिनिधित्व को बढ़ाने और विशिष्ट सामग्री को हाइलाइट करने के लिए किया जा सकता है। इसे प्राप्त करने के लिए हम आपको स्रोत कोड के साथ चरण-दर-चरण निर्देश प्रदान करेंगे। आएँ शुरू करें!

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Slides सेटअप है। आप वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं:[जावा के लिए Aspose.Slides](https://releases.aspose.com/slides/java/)

## चरण 1: प्रेजेंटेशन आरंभ करें

सबसे पहले, आपको एक नई प्रस्तुति बनानी होगी. इस उदाहरण में, हम एक रिक्त प्रस्तुतिकरण बनाएंगे.

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: एक चार्ट जोड़ें

इसके बाद, हम स्लाइड में एक चार्ट जोड़ेंगे। इस उदाहरण में, हम एक क्लस्टर्ड कॉलम चार्ट जोड़ रहे हैं। आप वह चार्ट प्रकार चुन सकते हैं जो आपकी आवश्यकताओं के अनुरूप हो।

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## चरण 3: एक कस्टम लाइन जोड़ें

 अब, चार्ट में एक कस्टम लाइन जोड़ें। हम एक बनाएंगे`IAutoShape` प्रकार का`ShapeType.Line` और इसे चार्ट के भीतर रखें।

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## चरण 4: लाइन को कस्टमाइज़ करें

आप लाइन के गुणों को सेट करके उसके स्वरूप को अनुकूलित कर सकते हैं। इस उदाहरण में, हम लाइन का रंग लाल पर सेट कर रहे हैं।

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## चरण 5: प्रस्तुति सहेजें

अंत में, प्रेजेंटेशन को अपने इच्छित स्थान पर सहेजें।

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में कस्टम लाइन्स जोड़ने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

बधाई हो! आपने जावा के लिए Aspose.Slides का उपयोग करके अपनी जावा स्लाइड में सफलतापूर्वक एक कस्टम लाइन जोड़ दी है। आप अपने वांछित दृश्य प्रभावों को प्राप्त करने के लिए लाइन के गुणों को और अधिक अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं लाइन का रंग कैसे बदलूं?

लाइन का रंग बदलने के लिए, निम्नलिखित कोड का उपयोग करें:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 प्रतिस्थापित करें`YOUR_COLOR` वांछित रंग के साथ.

### क्या मैं अन्य आकृतियों में कस्टम रेखाएँ जोड़ सकता हूँ?

 हां, आप केवल चार्ट ही नहीं, बल्कि विभिन्न आकृतियों में कस्टम लाइनें जोड़ सकते हैं। बस एक बनाएं`IAutoShape` और इसे अपनी आवश्यकताओं के अनुसार अनुकूलित करें।

### मैं लाइन की मोटाई कैसे बदल सकता हूँ?

 आप सेट करके लाइन की मोटाई बदल सकते हैं`Width` लाइन प्रारूप की संपत्ति. उदाहरण के लिए:
```java
shape.getLineFormat().setWidth(2); // लाइन की मोटाई को 2 बिंदुओं पर सेट करें
```

### क्या किसी स्लाइड में एकाधिक पंक्तियाँ जोड़ना संभव है?

हाँ, आप इस ट्यूटोरियल में बताए गए चरणों को दोहराकर एक स्लाइड में कई पंक्तियाँ जोड़ सकते हैं। प्रत्येक पंक्ति को स्वतंत्र रूप से अनुकूलित किया जा सकता है।