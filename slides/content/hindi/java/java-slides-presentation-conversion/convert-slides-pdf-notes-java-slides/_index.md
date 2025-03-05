---
title: जावा स्लाइड्स में नोट्स के साथ स्लाइड्स को पीडीएफ में बदलें
linktitle: जावा स्लाइड्स में नोट्स के साथ स्लाइड्स को पीडीएफ में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड को नोट्स के साथ PDF में कनवर्ट करना सीखें। Java डेवलपर्स के लिए चरण-दर-चरण मार्गदर्शिका। अपनी प्रेजेंटेशन शेयरिंग को बेहतर बनाएँ।
type: docs
weight: 19
url: /hi/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## जावा में नोट्स के साथ स्लाइड्स को पीडीएफ में बदलने का परिचय

डिजिटल प्रस्तुतियों की दुनिया में, स्लाइड को नोट्स के साथ पीडीएफ में बदलने की क्षमता एक मूल्यवान विशेषता है। जावा डेवलपर्स Aspose.Slides for Java लाइब्रेरी का उपयोग करके इसे प्राप्त कर सकते हैं, जो प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों के साथ काम करने के लिए उपकरणों का एक मजबूत सेट प्रदान करता है। इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि जावा और Aspose.Slides for Java का उपयोग करके स्लाइड को नोट्स के साथ पीडीएफ में कैसे बदला जाए।

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

अब जब हमारे पास रूपरेखा तैयार हो गई है, तो आइए चरण दर चरण कार्यान्वयन पर नजर डालें।
## चरण 1: प्रोजेक्ट की स्थापना

सबसे पहले, एक जावा प्रोजेक्ट बनाएं और अपने प्रोजेक्ट की निर्भरताओं में Aspose.Slides for Java लाइब्रेरी जोड़ें।

## चरण 2: प्रस्तुति लोड करना

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## चरण 3: एक नई प्रस्तुति बनाना

```java
Presentation auxPresentation = new Presentation();
```

## चरण 4: स्लाइड कॉपी करना

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## चरण 5: स्लाइड का आकार समायोजित करना

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## चरण 6: पीडीएफ विकल्प कॉन्फ़िगर करना

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## चरण 7: PDF के रूप में सहेजना

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## जावा स्लाइड्स में नोट्स के साथ स्लाइड्स को पीडीएफ में बदलने के लिए पूरा स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// स्लाइड प्रकार और आकार सेट करना
		//auxPresentation.getSlideSize().setSize(प्रस्तुति.getSlideSize().getSize().getWidth(), प्रस्तुति.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Slides for Java का उपयोग करके जावा में नोट्स के साथ स्लाइड को PDF में कैसे बदला जाए। हमने प्रोजेक्ट सेट अप करना, प्रेजेंटेशन लोड करना, नया प्रेजेंटेशन बनाना, स्लाइड कॉपी करना, स्लाइड का आकार एडजस्ट करना, PDF विकल्प कॉन्फ़िगर करना और अंत में, प्रेजेंटेशन को नोट्स के साथ PDF के रूप में सेव करना सिखाया।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?

Java के लिए Aspose.Slides स्थापित करने के लिए, इन चरणों का पालन करें:
1.  लाइब्रेरी को यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/java/).
2. अपने जावा प्रोजेक्ट के क्लासपाथ में JAR फ़ाइल जोड़ें।

### क्या मैं उत्पन्न पीडीएफ में नोट्स की स्थिति को अनुकूलित कर सकता हूं?

 हां, आप नोट्स की स्थिति को संशोधित करके अनुकूलित कर सकते हैं`NotesPositions` पीडीएफ विकल्पों में enum। इस ट्यूटोरियल में, हमने इसे सेट किया है`BottomFull`, लेकिन आप अन्य विकल्प भी तलाश सकते हैं।

### क्या Java के लिए Aspose.Slides का उपयोग करने के लिए कोई लाइसेंसिंग आवश्यकताएं हैं?

हां, Aspose.Slides for Java एक व्यावसायिक लाइब्रेरी है, और आपको इसे उत्पादन में उपयोग करने के लिए लाइसेंस प्राप्त करने की आवश्यकता हो सकती है। लाइसेंसिंग विवरण के लिए Aspose वेबसाइट पर जाएं।

### क्या मैं एक साथ कई स्लाइडों को परिवर्तित कर सकता हूँ?

निश्चित रूप से! आप अपनी प्रस्तुति में स्लाइडों को लूप कर सकते हैं और उन्हें नई प्रस्तुति में क्लोन कर सकते हैं, जिससे आप एक ही बार में कई स्लाइडों को नोट्स के साथ पीडीएफ में परिवर्तित कर सकते हैं।

### मैं Aspose.Slides for Java के लिए और अधिक दस्तावेज़ कहां पा सकता हूं?

 आप इस साइट पर Aspose.Slides for Java के लिए विस्तृत दस्तावेज़ पा सकते हैं:[Aspose.Slides for Java API संदर्भ](https://reference.aspose.com/slides/java/).