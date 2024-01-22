---
title: जावा स्लाइड्स में नोट्स के साथ स्लाइड्स को पीडीएफ में बदलें
linktitle: जावा स्लाइड्स में नोट्स के साथ स्लाइड्स को पीडीएफ में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा में नोट्स के साथ PowerPoint स्लाइड को पीडीएफ में परिवर्तित करना सीखें। जावा डेवलपर्स के लिए चरण-दर-चरण मार्गदर्शिका। अपनी प्रस्तुति साझाकरण बढ़ाएँ।
type: docs
weight: 19
url: /hi/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## जावा में नोट्स के साथ स्लाइड को पीडीएफ में बदलने का परिचय

डिजिटल प्रस्तुतियों की दुनिया में, नोट्स के साथ स्लाइड को पीडीएफ में बदलने की क्षमता एक मूल्यवान विशेषता है। जावा डेवलपर्स जावा लाइब्रेरी के लिए Aspose.Slides का उपयोग करके इसे प्राप्त कर सकते हैं, जो प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों के साथ काम करने के लिए उपकरणों का एक मजबूत सेट प्रदान करता है। इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि जावा और Aspose.Slides for Java का उपयोग करके नोट्स के साथ स्लाइड को पीडीएफ में कैसे परिवर्तित किया जाए।

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Slides। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

अब जब हमारे पास अपनी रूपरेखा है, तो आइए चरण दर चरण कार्यान्वयन पर ध्यान दें।
## चरण 1: परियोजना की स्थापना

सबसे पहले, एक जावा प्रोजेक्ट बनाएं और अपने प्रोजेक्ट की निर्भरता में जावा लाइब्रेरी के लिए Aspose.Slides जोड़ें।

## चरण 2: प्रस्तुति लोड हो रही है

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## चरण 3: एक नई प्रस्तुति बनाना

```java
Presentation auxPresentation = new Presentation();
```

## चरण 4: स्लाइड्स की प्रतिलिपि बनाना

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## चरण 5: स्लाइड का आकार समायोजित करना

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## चरण 6: पीडीएफ विकल्पों को कॉन्फ़िगर करना

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## चरण 7: पीडीएफ के रूप में सहेजा जा रहा है

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## जावा स्लाइड्स में नोट्स के साथ स्लाइड्स को पीडीएफ में बदलने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रेजेंटेशन ऑब्जेक्ट को इंस्टेंट करें जो एक प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// स्लाइड प्रकार और आकार सेट करना
		//auxPresentation.getSlideSize().setSize(प्रस्तुति.getSlideSize().getSize().getWidth(), प्रेजेंटेशन.getSlideSize().getSize().getHeight(), SlideSizeScaleType.EnsureFit);
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

इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके जावा में नोट्स के साथ स्लाइड को पीडीएफ में कैसे परिवर्तित किया जाए। हमने प्रोजेक्ट स्थापित करना, प्रेजेंटेशन लोड करना, नई प्रेजेंटेशन बनाना, स्लाइड कॉपी करना, स्लाइड का आकार समायोजित करना, पीडीएफ विकल्पों को कॉन्फ़िगर करना और अंत में प्रेजेंटेशन को नोट्स के साथ पीडीएफ के रूप में सहेजना शामिल किया।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे स्थापित करूं?

जावा के लिए Aspose.Slides स्थापित करने के लिए, इन चरणों का पालन करें:
1.  लाइब्रेरी यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/java/).
2. अपने जावा प्रोजेक्ट के क्लासपाथ में JAR फ़ाइल जोड़ें।

### क्या मैं जेनरेट की गई पीडीएफ में नोट्स की स्थिति को अनुकूलित कर सकता हूं?

 हां, आप नोट्स की स्थिति को संशोधित करके अनुकूलित कर सकते हैं`NotesPositions` पीडीएफ विकल्पों में सूचीबद्ध करें। इस ट्यूटोरियल में, हमने इसे सेट किया है`BottomFull`, लेकिन आप अन्य विकल्प भी तलाश सकते हैं।

### क्या जावा के लिए Aspose.Slides का उपयोग करने के लिए कोई लाइसेंसिंग आवश्यकताएं हैं?

हाँ, Aspose.Slides for Java एक व्यावसायिक लाइब्रेरी है, और उत्पादन में इसका उपयोग करने के लिए आपको लाइसेंस प्राप्त करने की आवश्यकता हो सकती है। लाइसेंसिंग विवरण के लिए Aspose वेबसाइट पर जाएँ।

### क्या मैं एक साथ अनेक स्लाइड परिवर्तित कर सकता हूँ?

निश्चित रूप से! आप अपनी प्रेजेंटेशन में स्लाइड्स को लूप कर सकते हैं और उन्हें नई प्रेजेंटेशन में क्लोन कर सकते हैं, जिससे आप एक ही बार में कई स्लाइड्स को नोट्स के साथ पीडीएफ में बदल सकते हैं।

### जावा के लिए Aspose.Slides के लिए मुझे और दस्तावेज़ कहां मिल सकते हैं?

 आप साइट पर जावा के लिए Aspose.Slides के लिए विस्तृत दस्तावेज़ पा सकते हैं:[जावा एपीआई संदर्भ के लिए Aspose.Slides](https://reference.aspose.com/slides/java/).