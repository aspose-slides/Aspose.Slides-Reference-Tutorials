---
title: जावा स्लाइड्स में लेआउट प्रारूप तक पहुंचें
linktitle: जावा स्लाइड्स में लेआउट प्रारूप तक पहुंचें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ Java स्लाइड्स में लेआउट फ़ॉर्मेट को एक्सेस और मैनिपुलेट करना सीखें। PowerPoint प्रेजेंटेशन में आसानी से आकार और लाइन स्टाइल को कस्टमाइज़ करें।
weight: 10
url: /hi/java/presentation-properties/access-layout-formats-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में एक्सेस लेआउट प्रारूपों का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java API का उपयोग करके Java स्लाइड में लेआउट फ़ॉर्मेट तक पहुँचने और उनके साथ काम करने का तरीका जानेंगे। लेआउट फ़ॉर्मेट आपको प्रेजेंटेशन की लेआउट स्लाइड में आकृतियों और रेखाओं की उपस्थिति को नियंत्रित करने की अनुमति देते हैं। हम लेआउट स्लाइड पर आकृतियों के लिए भरण फ़ॉर्मेट और रेखा फ़ॉर्मेट को पुनः प्राप्त करने का तरीका बताएंगे।

## आवश्यक शर्तें

1. Aspose.Slides for Java लाइब्रेरी.
2. लेआउट स्लाइडों के साथ एक पावरपॉइंट प्रस्तुति (पीपीटीएक्स प्रारूप)।

## चरण 1: प्रस्तुति लोड करें

 सबसे पहले, हमें पावरपॉइंट प्रेजेंटेशन को लोड करना होगा जिसमें लेआउट स्लाइड्स शामिल हैं।`"Your Document Directory"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## चरण 2: लेआउट प्रारूप तक पहुँचें

अब, आइए प्रस्तुति में लेआउट स्लाइडों को देखें और प्रत्येक लेआउट स्लाइड पर आकृतियों के भरण प्रारूपों और रेखा प्रारूपों तक पहुंचें।

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
        
        // आकृतियों के लाइन प्रारूपों तक पहुँचें
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

- हम प्रत्येक लेआउट स्लाइड को एक का उपयोग करके पुनरावृत्त करते हैं`for` कुंडली।
- प्रत्येक लेआउट स्लाइड के लिए, हम उस स्लाइड पर आकृतियों के लिए भरण प्रारूप और रेखा प्रारूप को संग्रहीत करने के लिए सरणियाँ बनाते हैं।
-  हम नेस्टेड का उपयोग करते हैं`for` लेआउट स्लाइड पर आकृतियों के माध्यम से पुनरावृति करने और उनके भरण और रेखा प्रारूपों को पुनः प्राप्त करने के लिए लूप।

## चरण 3: लेआउट प्रारूपों के साथ कार्य करें

अब जब हमने लेआउट स्लाइड पर आकृतियों के लिए भरण प्रारूप और रेखा प्रारूपों तक पहुँच प्राप्त कर ली है, तो आप आवश्यकतानुसार उन पर विभिन्न कार्य कर सकते हैं। उदाहरण के लिए, आप आकृतियों के भरण रंग, रेखा शैली या अन्य गुण बदल सकते हैं।

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

इस ट्यूटोरियल में, हमने Aspose.Slides for Java API का उपयोग करके Java स्लाइड में लेआउट फ़ॉर्मेट तक पहुँचने और उसमें हेरफेर करने का तरीका खोजा है। PowerPoint प्रस्तुतियों में लेआउट स्लाइड के भीतर आकृतियों और रेखाओं की उपस्थिति को नियंत्रित करने के लिए लेआउट फ़ॉर्मेट आवश्यक हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं किसी आकृति का भरण रंग कैसे बदलूं?

 किसी आकृति का भरण रंग बदलने के लिए, आप इसका उपयोग कर सकते हैं`IFillFormat`ऑब्जेक्ट की विधियाँ। यहाँ एक उदाहरण है:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // भरण प्रकार को ठोस रंग पर सेट करें
fillFormat.getSolidFillColor().setColor(Color.RED); // भरण रंग को लाल पर सेट करें
```

### मैं किसी आकृति की रेखा शैली कैसे बदलूं?

 किसी आकृति की रेखा शैली बदलने के लिए, आप इसका उपयोग कर सकते हैं`ILineFormat`ऑब्जेक्ट की विधियाँ। यहाँ एक उदाहरण है:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // लाइन शैली को एकल पर सेट करें
lineFormat.setWidth(2.0); // लाइन की चौड़ाई 2.0 पॉइंट पर सेट करें
lineFormat.getSolidFillColor().setColor(Color.BLUE); // रेखा का रंग नीला सेट करें
```

### मैं लेआउट स्लाइड पर किसी आकृति में ये परिवर्तन कैसे लागू करूँ?

लेआउट स्लाइड पर किसी विशिष्ट आकृति पर ये परिवर्तन लागू करने के लिए, आप लेआउट स्लाइड के आकृति संग्रह में इसके अनुक्रमणिका का उपयोग करके आकृति तक पहुँच सकते हैं। उदाहरण के लिए:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // लेआउट स्लाइड पर पहली आकृति तक पहुँचें
```

 फिर आप इसका उपयोग कर सकते हैं`IFillFormat` और`ILineFormat` आकृति के भरण और रेखा प्रारूपों को संशोधित करने के लिए पिछले उत्तरों में दिखाए गए तरीकों का उपयोग करें।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
