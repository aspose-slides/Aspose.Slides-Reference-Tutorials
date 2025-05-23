---
"description": "Aspose.Slides for Java API का उपयोग करके Java स्लाइड में टेक्स्ट भाग निर्देशांक प्राप्त करना सीखें। PowerPoint प्रस्तुतियों में टेक्स्ट प्लेसमेंट पर सटीक नियंत्रण प्राप्त करें।"
"linktitle": "जावा स्लाइड्स में भाग के स्थिति निर्देशांक प्राप्त करें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में भाग के स्थिति निर्देशांक प्राप्त करें"
"url": "/hi/java/additional-utilities/get-position-coordinates-of-portion-in-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में भाग के स्थिति निर्देशांक प्राप्त करें


## जावा स्लाइड्स में भाग के स्थिति निर्देशांक प्राप्त करने का परिचय

इस विस्तृत गाइड में, हम यह पता लगाएंगे कि Aspose.Slides for Java API का उपयोग करके Java स्लाइड के भीतर किसी भाग के स्थिति निर्देशांक कैसे प्राप्त करें। आप सीखेंगे कि स्लाइड में टेक्स्ट भागों तक कैसे पहुँचें और उनमें हेरफेर करें तथा उनके X और Y निर्देशांक कैसे निकालें। इस चरण-दर-चरण ट्यूटोरियल में स्रोत कोड उदाहरण और मूल्यवान जानकारी शामिल है जो आपको इस कार्य में निपुण होने में मदद करेगी।

## आवश्यक शर्तें

इससे पहले कि हम कार्यान्वयन में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा डेवलपमेंट किट (JDK) स्थापित
- Aspose.Slides for Java लाइब्रेरी डाउनलोड और कॉन्फ़िगर की गई
- आपकी पसंद का जावा एकीकृत विकास वातावरण (आईडीई)

अब, आइये कार्यान्वयन शुरू करें।

## चरण 1: अपना प्रोजेक्ट सेट अप करना

इससे पहले कि हम Aspose.Slides for Java के साथ काम कर सकें, हमें एक Java प्रोजेक्ट सेट अप करना होगा और लाइब्रेरी को कॉन्फ़िगर करना होगा। अपना प्रोजेक्ट तैयार करने के लिए इन चरणों का पालन करें:

1. अपने IDE में एक नया जावा प्रोजेक्ट बनाएं।
2. अपनी परियोजना की निर्भरताओं में Aspose.Slides for Java लाइब्रेरी जोड़ें।
3. अपनी जावा फ़ाइल के आरंभ में आवश्यक Aspose.Slides क्लासेस आयात करें।

```java
import com.aspose.slides.*;
import java.awt.geom.Point2D;
```

## चरण 2: प्रस्तुति लोड करना

इस चरण में, हम पावरपॉइंट प्रेजेंटेशन को लोड करेंगे जिसमें वह स्लाइड होगी जिसके साथ हम काम करना चाहते हैं। `"Your Document Directory"` अपनी PowerPoint फ़ाइल के वास्तविक पथ के साथ.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
```

## चरण 3: पाठ्य भाग और निर्देशांक तक पहुँचना

अब, हम स्लाइड के भीतर टेक्स्ट भागों तक पहुंचेंगे और उनके X और Y निर्देशांक प्राप्त करेंगे। हम इसे प्राप्त करने के लिए पैराग्राफ और भागों के माध्यम से पुनरावृत्ति करेंगे। यहाँ कोड स्निपेट है:

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

यह कोड निर्दिष्ट स्लाइड में पाठ के प्रत्येक भाग के लिए X और Y निर्देशांक प्राप्त करता है। आप इसे अपनी विशिष्ट आवश्यकताओं के अनुरूप संशोधित कर सकते हैं।

## जावा स्लाइड्स में भाग के स्थिति निर्देशांक प्राप्त करने के लिए पूर्ण स्रोत कोड

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

इस ट्यूटोरियल में, हमने बताया है कि Aspose.Slides for Java API का उपयोग करके Java स्लाइड के भीतर टेक्स्ट भागों के स्थान निर्देशांक कैसे प्राप्त करें। यह ज्ञान विशेष रूप से तब उपयोगी हो सकता है जब आपको अपने PowerPoint प्रस्तुतियों में टेक्स्ट तत्वों के स्थान पर सटीक नियंत्रण की आवश्यकता हो।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides कैसे डाउनलोड कर सकता हूँ?

आप निम्न लिंक का उपयोग करके वेबसाइट से Aspose.Slides for Java डाउनलोड कर सकते हैं: [Java के लिए Aspose.Slides डाउनलोड करें](https://releases.aspose.com/slides/java/)

### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?

Java के लिए Aspose.Slides का दस्तावेज़ यहां उपलब्ध है: [Aspose.Slides for Java दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/)

### क्या मैं अपनी व्यावसायिक परियोजनाओं में Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?

हां, Aspose.Slides for Java का इस्तेमाल व्यावसायिक परियोजनाओं में किया जा सकता है। हालाँकि, Aspose द्वारा प्रदान की गई लाइसेंसिंग शर्तों की समीक्षा करना सुनिश्चित करें।

### क्या Aspose.Slides for Java विभिन्न PowerPoint फ़ाइल स्वरूपों के साथ संगत है?

हां, Aspose.Slides for Java विभिन्न PowerPoint फ़ाइल स्वरूपों का समर्थन करता है, जिनमें PPTX, PPT, और अन्य शामिल हैं।

### मैं Aspose.Slides for Java के लिए आगे समर्थन या सहायता कैसे प्राप्त कर सकता हूं?

आप Aspose वेबसाइट पर अतिरिक्त सहायता और संसाधन प्राप्त कर सकते हैं। वे उपयोगकर्ताओं के लिए फ़ोरम, दस्तावेज़ और प्रीमियम सहायता विकल्प प्रदान करते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}