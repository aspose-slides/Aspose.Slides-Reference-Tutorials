---
title: जावा स्लाइड्स में कस्टम लाइन्स जोड़ना
linktitle: जावा स्लाइड्स में कस्टम लाइन्स जोड़ना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: कस्टम लाइनों के साथ अपनी जावा स्लाइड्स को बेहतर बनाएँ। Aspose.Slides for Java का उपयोग करने के लिए चरण-दर-चरण मार्गदर्शिका। प्रभावशाली दृश्यों के लिए प्रस्तुतियों में लाइनें जोड़ना और उन्हें अनुकूलित करना सीखें।
weight: 10
url: /hi/java/customization-and-formatting/adding-custom-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में कस्टम लाइन्स जोड़ना


## जावा स्लाइड्स में कस्टम लाइन्स जोड़ने का परिचय

इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Slides for Java का उपयोग करके अपनी Java स्लाइड में कस्टम लाइन कैसे जोड़ें। कस्टम लाइनों का उपयोग आपकी स्लाइड के विज़ुअल प्रतिनिधित्व को बढ़ाने और विशिष्ट सामग्री को हाइलाइट करने के लिए किया जा सकता है। हम आपको इसे प्राप्त करने के लिए स्रोत कोड के साथ चरण-दर-चरण निर्देश प्रदान करेंगे। चलिए शुरू करते हैं!

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में जावा के लिए Aspose.Slides लाइब्रेरी सेट अप है। आप वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## चरण 1: प्रस्तुति आरंभ करें

सबसे पहले, आपको एक नया प्रेजेंटेशन बनाना होगा। इस उदाहरण में, हम एक खाली प्रेजेंटेशन बनाएंगे।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: चार्ट जोड़ें

इसके बाद, हम स्लाइड में एक चार्ट जोड़ेंगे। इस उदाहरण में, हम एक क्लस्टर्ड कॉलम चार्ट जोड़ रहे हैं। आप अपनी ज़रूरतों के हिसाब से चार्ट का प्रकार चुन सकते हैं।

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## चरण 3: एक कस्टम लाइन जोड़ें

 अब, चार्ट में एक कस्टम लाइन जोड़ते हैं। हम एक कस्टम लाइन बनाएंगे।`IAutoShape` प्रकार का`ShapeType.Line` और उसे चार्ट में स्थान दें.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## चरण 4: लाइन को अनुकूलित करें

आप लाइन के गुणों को सेट करके उसके स्वरूप को अनुकूलित कर सकते हैं। इस उदाहरण में, हम लाइन का रंग लाल सेट कर रहे हैं।

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## चरण 5: प्रस्तुति सहेजें

अंत में, प्रस्तुति को अपने इच्छित स्थान पर सेव करें।

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में कस्टम लाइन्स जोड़ने के लिए पूरा सोर्स कोड

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

बधाई हो! आपने Aspose.Slides for Java का उपयोग करके अपनी Java स्लाइड में सफलतापूर्वक एक कस्टम लाइन जोड़ ली है। आप अपनी इच्छित दृश्य प्रभाव प्राप्त करने के लिए लाइन के गुणों को और भी अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं लाइन का रंग कैसे बदलूं?

लाइन का रंग बदलने के लिए निम्नलिखित कोड का उपयोग करें:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 प्रतिस्थापित करें`YOUR_COLOR` इच्छित रंग के साथ.

### क्या मैं अन्य आकृतियों में कस्टम लाइनें जोड़ सकता हूँ?

 हां, आप न केवल चार्ट बल्कि विभिन्न आकृतियों में कस्टम लाइन जोड़ सकते हैं। बस एक बनाएँ`IAutoShape` और अपनी आवश्यकताओं के अनुसार इसे अनुकूलित करें।

### मैं लाइन की मोटाई कैसे बदल सकता हूँ?

 आप लाइन की मोटाई को सेट करके बदल सकते हैं`Width` लाइन प्रारूप की संपत्ति। उदाहरण के लिए:
```java
shape.getLineFormat().setWidth(2); // रेखा की मोटाई 2 पॉइंट पर सेट करें
```

### क्या एक स्लाइड में एकाधिक लाइनें जोड़ना संभव है?

हां, आप इस ट्यूटोरियल में बताए गए चरणों को दोहराकर स्लाइड में कई लाइनें जोड़ सकते हैं। प्रत्येक लाइन को स्वतंत्र रूप से कस्टमाइज़ किया जा सकता है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
