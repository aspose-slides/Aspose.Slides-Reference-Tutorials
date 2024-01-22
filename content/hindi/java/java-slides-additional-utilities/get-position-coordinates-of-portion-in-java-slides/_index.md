---
title: जावा स्लाइड्स में भाग के स्थिति निर्देशांक प्राप्त करें
linktitle: जावा स्लाइड्स में भाग के स्थिति निर्देशांक प्राप्त करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में टेक्स्ट भाग निर्देशांक पुनर्प्राप्त करना सीखें। PowerPoint प्रस्तुतियों में टेक्स्ट प्लेसमेंट पर सटीक नियंत्रण प्राप्त करें।
type: docs
weight: 12
url: /hi/java/additional-utilities/get-position-coordinates-of-portion-in-java-slides/
---

## जावा स्लाइड्स में भाग के स्थिति निर्देशांक प्राप्त करने का परिचय

इस व्यापक गाइड में, हम यह पता लगाएंगे कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड के भीतर एक हिस्से के स्थिति निर्देशांक कैसे प्राप्त करें। आप सीखेंगे कि स्लाइड में टेक्स्ट भागों तक कैसे पहुंचें और हेरफेर करें और उनके एक्स और वाई निर्देशांक कैसे निकालें। इस चरण-दर-चरण ट्यूटोरियल में इस कार्य में महारत हासिल करने में आपकी सहायता के लिए स्रोत कोड उदाहरण और मूल्यवान अंतर्दृष्टि शामिल हैं।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा डेवलपमेंट किट (जेडीके) स्थापित किया गया
- जावा लाइब्रेरी के लिए Aspose.Slides डाउनलोड और कॉन्फ़िगर किया गया
- आपकी पसंद का जावा इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (आईडीई)।

अब, आइए कार्यान्वयन के साथ शुरुआत करें।

## चरण 1: अपना प्रोजेक्ट स्थापित करना

इससे पहले कि हम जावा के लिए Aspose.Slides के साथ काम कर सकें, हमें एक जावा प्रोजेक्ट स्थापित करने और लाइब्रेरी को कॉन्फ़िगर करने की आवश्यकता है। अपना प्रोजेक्ट तैयार करने के लिए इन चरणों का पालन करें:

1. अपनी आईडीई में एक नया जावा प्रोजेक्ट बनाएं।
2. अपने प्रोजेक्ट की निर्भरता में जावा लाइब्रेरी के लिए Aspose.Slides जोड़ें।
3. अपनी जावा फ़ाइल की शुरुआत में आवश्यक Aspose.Slides कक्षाएं आयात करें।

```java
import com.aspose.slides.*;
import java.awt.geom.Point2D;
```

## चरण 2: प्रस्तुति लोड हो रही है

 इस चरण में, हम पावरपॉइंट प्रेजेंटेशन को लोड करेंगे जिसमें वह स्लाइड है जिसके साथ हम काम करना चाहते हैं। प्रतिस्थापित करें`"Your Document Directory"` आपकी PowerPoint फ़ाइल के वास्तविक पथ के साथ।

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
```

## चरण 3: पाठ भाग और निर्देशांक तक पहुँचना

अब, हम स्लाइड के भीतर पाठ भागों तक पहुंचेंगे और उनके एक्स और वाई निर्देशांक पुनः प्राप्त करेंगे। इसे प्राप्त करने के लिए हम अनुच्छेदों और भागों के माध्यम से पुनरावृत्ति करेंगे। यहाँ कोड स्निपेट है:

```java
try
{
    IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
    ITextFrame textFrame = shape.getTextFrame();
    for (IParagraph paragraph : textFrame.getParagraphs())
    {
        for (IPortion portion : paragraph.getPortions())
        {
            Point2D.Float point = portion.getCoordinates();
            System.out.println("Coordinates X =" + point.getX() + " Coordinates Y =" + point.getY());
        }
    }
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

यह कोड निर्दिष्ट स्लाइड में पाठ के प्रत्येक भाग के लिए X और Y निर्देशांक पुनर्प्राप्त करता है। आप इसे अपनी विशिष्ट आवश्यकताओं के अनुरूप संशोधित कर सकते हैं।

## जावा स्लाइड्स में भाग के स्थान निर्देशांक प्राप्त करने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
try
{
	IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
	ITextFrame textFrame = shape.getTextFrame();
	for (IParagraph paragraph : textFrame.getParagraphs())
	{
		for (IPortion portion : paragraph.getPortions())
		{
			Point2D.Float point = portion.getCoordinates();
			System.out.println("Corrdinates X =" + point.getX() + " Corrdinates Y =" + point.getY());
		}
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड के भीतर टेक्स्ट भागों के स्थिति निर्देशांक प्राप्त करने का तरीका बताया है। यह ज्ञान विशेष रूप से तब उपयोगी हो सकता है जब आपको अपने पावरपॉइंट प्रेजेंटेशन में टेक्स्ट तत्वों के स्थान पर सटीक नियंत्रण की आवश्यकता होती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे डाउनलोड कर सकता हूं?

 आप निम्नलिखित लिंक का उपयोग करके वेबसाइट से जावा के लिए Aspose.Slides डाउनलोड कर सकते हैं:[जावा के लिए Aspose.Slides डाउनलोड करें](https://releases.aspose.com/slides/java/)

### मैं जावा के लिए Aspose.Slides के लिए दस्तावेज़ कहां पा सकता हूं?

 जावा के लिए Aspose.Slides का दस्तावेज़ यहां उपलब्ध है:[जावा दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/java/)

### क्या मैं अपनी व्यावसायिक परियोजनाओं में जावा के लिए Aspose.Slides का उपयोग कर सकता हूँ?

हां, जावा के लिए Aspose.Slides का उपयोग व्यावसायिक परियोजनाओं में किया जा सकता है। हालाँकि, Aspose द्वारा प्रदान की गई लाइसेंसिंग शर्तों की समीक्षा करना सुनिश्चित करें।

### क्या जावा के लिए Aspose.Slides विभिन्न PowerPoint फ़ाइल स्वरूपों के साथ संगत है?

हाँ, Java के लिए Aspose.Slides PPTX, PPT और अन्य सहित विभिन्न PowerPoint फ़ाइल स्वरूपों का समर्थन करता है।

### मैं जावा के लिए Aspose.Slides के साथ और अधिक समर्थन या सहायता कैसे प्राप्त कर सकता हूं?

आप Aspose वेबसाइट पर अतिरिक्त सहायता और संसाधनों तक पहुंच सकते हैं। वे उपयोगकर्ताओं के लिए फ़ोरम, दस्तावेज़ीकरण और प्रीमियम सहायता विकल्प प्रदान करते हैं।