---
title: जावा स्लाइड्स में लेआउट प्रारूप तक पहुंचें
linktitle: जावा स्लाइड्स में लेआउट प्रारूप तक पहुंचें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides के साथ जावा स्लाइड्स में लेआउट प्रारूपों तक पहुंचने और उनमें हेरफेर करने का तरीका जानें। PowerPoint प्रस्तुतियों में आकृति और रेखा शैलियों को सहजता से अनुकूलित करें।
type: docs
weight: 10
url: /hi/java/presentation-properties/access-layout-formats-in-java-slides/
---

## जावा स्लाइड्स में एक्सेस लेआउट फॉर्मेट का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में लेआउट प्रारूपों तक कैसे पहुंचें और उनके साथ कैसे काम करें। लेआउट प्रारूप आपको प्रस्तुति के लेआउट स्लाइड के भीतर आकृतियों और रेखाओं की उपस्थिति को नियंत्रित करने की अनुमति देते हैं। हम लेआउट स्लाइड्स पर आकृतियों के लिए भरण प्रारूपों और लाइन प्रारूपों को पुनः प्राप्त करने का तरीका कवर करेंगे।

## आवश्यक शर्तें

1. जावा लाइब्रेरी के लिए Aspose.Slides।
2. लेआउट स्लाइड के साथ एक पावरपॉइंट प्रेजेंटेशन (पीपीटीएक्स प्रारूप)।

## चरण 1: प्रस्तुति लोड करें

 सबसे पहले, हमें पावरपॉइंट प्रेजेंटेशन को लोड करना होगा जिसमें लेआउट स्लाइड्स हैं। प्रतिस्थापित करें`"Your Document Directory"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## चरण 2: लेआउट प्रारूप तक पहुंचें

अब, प्रेजेंटेशन में लेआउट स्लाइड्स के माध्यम से लूप करें और प्रत्येक लेआउट स्लाइड पर आकृतियों के भरण प्रारूपों और लाइन प्रारूपों तक पहुंचें।

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // आकृतियों के भरण प्रारूपों तक पहुँचें
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // आकृतियों के एक्सेस लाइन प्रारूप
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

उपरोक्त कोड में:

- हम प्रत्येक लेआउट स्लाइड को a का उपयोग करके पुनरावृत्त करते हैं`for` कुंडली।
- प्रत्येक लेआउट स्लाइड के लिए, हम उस स्लाइड पर आकृतियों के लिए भरण प्रारूप और लाइन प्रारूप संग्रहीत करने के लिए सरणियाँ बनाते हैं।
-  हम नेस्टेड का उपयोग करते हैं`for` लेआउट स्लाइड पर आकृतियों के माध्यम से पुनरावृति करने और उनके भरण और रेखा प्रारूपों को पुनः प्राप्त करने के लिए लूप।

## चरण 3: लेआउट प्रारूपों के साथ कार्य करें

अब जब हमने लेआउट स्लाइड पर आकृतियों के लिए भरण प्रारूप और लाइन प्रारूप तक पहुंच प्राप्त कर ली है, तो आप आवश्यकतानुसार उन पर विभिन्न ऑपरेशन कर सकते हैं। उदाहरण के लिए, आप भरण रंग, रेखा शैली, या आकृतियों के अन्य गुण बदल सकते हैं।

## जावा स्लाइड्स में एक्सेस लेआउट प्रारूपों के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने यह पता लगाया है कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में लेआउट प्रारूपों तक कैसे पहुंचें और उनमें हेरफेर करें। PowerPoint प्रस्तुतियों में लेआउट स्लाइड के भीतर आकृतियों और रेखाओं की उपस्थिति को नियंत्रित करने के लिए लेआउट प्रारूप आवश्यक हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं किसी आकृति का भरण रंग कैसे बदलूं?

 किसी आकृति का भरण रंग बदलने के लिए, आप इसका उपयोग कर सकते हैं`IFillFormat`ऑब्जेक्ट के तरीके. यहाँ एक उदाहरण है:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // भरण प्रकार को ठोस रंग पर सेट करें
fillFormat.getSolidFillColor().setColor(Color.RED); // भरण रंग को लाल पर सेट करें
```

### मैं किसी आकृति की रेखा शैली कैसे बदलूं?

 किसी आकृति की रेखा शैली को बदलने के लिए, आप इसका उपयोग कर सकते हैं`ILineFormat`ऑब्जेक्ट के तरीके. यहाँ एक उदाहरण है:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // लाइन शैली को एकल पर सेट करें
lineFormat.setWidth(2.0); // लाइन की चौड़ाई 2.0 अंक पर सेट करें
lineFormat.getSolidFillColor().setColor(Color.BLUE); // लाइन का रंग नीला पर सेट करें
```

### मैं लेआउट स्लाइड पर किसी आकृति में इन परिवर्तनों को कैसे लागू करूं?

लेआउट स्लाइड पर किसी विशिष्ट आकार में इन परिवर्तनों को लागू करने के लिए, आप लेआउट स्लाइड के आकार संग्रह में इसके सूचकांक का उपयोग करके आकार तक पहुंच सकते हैं। उदाहरण के लिए:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // लेआउट स्लाइड पर पहले आकार तक पहुंचें
```

 फिर आप इसका उपयोग कर सकते हैं`IFillFormat` और`ILineFormat` आकृति के भरण और रेखा स्वरूपों को संशोधित करने के लिए पिछले उत्तरों में दिखाए गए तरीके।