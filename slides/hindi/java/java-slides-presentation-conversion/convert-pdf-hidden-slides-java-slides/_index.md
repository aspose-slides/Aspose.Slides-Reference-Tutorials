---
title: जावा स्लाइड्स में छिपी हुई स्लाइड्स को पीडीएफ में बदलें
linktitle: जावा स्लाइड्स में छिपी हुई स्लाइड्स को पीडीएफ में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Aspose.Slides for Java का उपयोग करके छिपी हुई स्लाइड्स के साथ PowerPoint प्रस्तुतियों को PDF में कैसे परिवर्तित किया जाए। सहज PDF निर्माण के लिए स्रोत कोड के साथ हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 27
url: /hi/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## जावा के लिए Aspose.Slides का उपयोग करके छिपी हुई स्लाइड्स के साथ पावरपॉइंट प्रेजेंटेशन को पीडीएफ में बदलने का परिचय

इस चरण-दर-चरण मार्गदर्शिका में, आप सीखेंगे कि Aspose.Slides for Java का उपयोग करके छिपी हुई स्लाइडों को संरक्षित करते हुए PowerPoint प्रस्तुति को PDF में कैसे परिवर्तित किया जाए। छिपी हुई स्लाइडें वे हैं जो नियमित प्रस्तुति के दौरान प्रदर्शित नहीं होती हैं, लेकिन उन्हें PDF आउटपुट में शामिल किया जा सकता है। हम आपको इस कार्य को पूरा करने के लिए स्रोत कोड और विस्तृत निर्देश प्रदान करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1.  Aspose.Slides for Java लाइब्रेरी: सुनिश्चित करें कि आपके Java प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी सेट अप है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/).

2. जावा डेवलपमेंट एनवायरनमेंट: आपके सिस्टम पर जावा डेवलपमेंट एनवायरनमेंट स्थापित होना चाहिए।

## चरण 1: Java के लिए Aspose.Slides आयात करें

सबसे पहले, आपको अपने जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी को आयात करना होगा। सुनिश्चित करें कि आपने लाइब्रेरी को अपने प्रोजेक्ट के बिल्ड पथ में जोड़ दिया है।

```java
import com.aspose.slides.*;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन लोड करें

 आप उस पावरपॉइंट प्रेजेंटेशन को लोड करके शुरू करेंगे जिसे आप पीडीएफ में बदलना चाहते हैं।`"Your Document Directory"` और`"HiddingSlides.pptx"` उचित फ़ाइल पथ के साथ.

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## चरण 3: PDF विकल्प कॉन्फ़िगर करें

पीडीएफ आउटपुट में छिपी स्लाइड्स को शामिल करने के लिए पीडीएफ विकल्पों को कॉन्फ़िगर करें। आप इसे सेट करके कर सकते हैं`setShowHiddenSlides` की संपत्ति`PdfOptions` कक्षा से`true`.

```java
// PdfOptions वर्ग को तत्कालित करें
PdfOptions pdfOptions = new PdfOptions();
// निर्दिष्ट करें कि उत्पन्न दस्तावेज़ में छिपी हुई स्लाइडें शामिल होनी चाहिए
pdfOptions.setShowHiddenSlides(true);
```

## चरण 4: प्रस्तुति को PDF के रूप में सहेजें

 अब, निर्दिष्ट विकल्पों के साथ प्रस्तुति को एक पीडीएफ फाइल में सहेजें।`"PDFWithHiddenSlides_out.pdf"` अपने इच्छित आउटपुट फ़ाइल नाम के साथ.

```java
// निर्दिष्ट विकल्पों के साथ प्रस्तुति को PDF में सहेजें
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## चरण 5: संसाधनों की सफ़ाई करें

जब आप प्रस्तुतिकरण पूरा कर लें तो उसमें प्रयुक्त संसाधनों को अवश्य जारी करें।

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## जावा स्लाइड्स में छिपे हुए स्लाइड्स के साथ पीडीएफ में कनवर्ट करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// PdfOptions वर्ग को तत्कालित करें
	PdfOptions pdfOptions = new PdfOptions();
	// निर्दिष्ट करें कि उत्पन्न दस्तावेज़ में छिपी हुई स्लाइडें शामिल होनी चाहिए
	pdfOptions.setShowHiddenSlides(true);
	// निर्दिष्ट विकल्पों के साथ प्रस्तुति को PDF में सहेजें
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस विस्तृत गाइड में, आपने सीखा है कि Aspose.Slides for Java का उपयोग करके छिपी हुई स्लाइड्स को संरक्षित करते हुए PowerPoint प्रेजेंटेशन को PDF में कैसे परिवर्तित किया जाए। हमने आपको इस कार्य को सहजता से पूरा करने के लिए आवश्यक स्रोत कोड के साथ-साथ चरण-दर-चरण ट्यूटोरियल प्रदान किया है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पावरपॉइंट प्रेजेंटेशन में स्लाइड्स कैसे छिपा सकता हूँ?

PowerPoint प्रस्तुति में स्लाइड छिपाने के लिए, इन चरणों का पालन करें:
1. स्लाइड सॉर्टर दृश्य में वह स्लाइड चुनें जिसे आप छिपाना चाहते हैं।
2. चयनित स्लाइड पर राइट-क्लिक करें.
3. संदर्भ मेनू से "स्लाइड छिपाएँ" चुनें।

### क्या मैं Aspose.Slides for Java में छिपी हुई स्लाइडों को प्रोग्रामेटिक रूप से प्रदर्शित कर सकता हूँ?

 हां, आप Aspose.Slides for Java में छिपी हुई स्लाइड्स को प्रोग्रामेटिक रूप से सेट करके प्रदर्शित कर सकते हैं`Hidden` की संपत्ति`Slide` कक्षा से`false`. यहाँ एक उदाहरण है:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // स्लाइड इंडेक्स को छुपी हुई स्लाइड के इंडेक्स से बदलें
slide.setHidden(false);
```

### मैं Java के लिए Aspose.Slides कैसे डाउनलोड करूं?

 आप Aspose.Slides for Java को Aspose वेबसाइट से डाउनलोड कर सकते हैं।[Aspose.Slides for Java डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/) नवीनतम संस्करण प्राप्त करने के लिए.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
