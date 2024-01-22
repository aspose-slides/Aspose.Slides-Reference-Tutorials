---
title: जावा स्लाइड्स में मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में बदलें
linktitle: जावा स्लाइड्स में मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा स्लाइड का उपयोग करके मीडिया फ़ाइलों के साथ प्रस्तुतियों को HTML में परिवर्तित करना सीखें। Java API के लिए Aspose.Slides के साथ हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 30
url: /hi/java/presentation-conversion/convert-whole-presentation-html-media-files-java-slides/
---

## जावा स्लाइड्स में मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में बदलने का परिचय

आज के डिजिटल युग में, प्रस्तुतियों को HTML सहित विभिन्न प्रारूपों में परिवर्तित करने की आवश्यकता एक आम आवश्यकता है। जावा डेवलपर्स अक्सर खुद को इस चुनौती से जूझते हुए पाते हैं। सौभाग्य से, Aspose.Slides for Java API के साथ, यह कार्य कुशलतापूर्वक पूरा किया जा सकता है। इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि जावा स्लाइड का उपयोग करके मीडिया फ़ाइलों को संरक्षित करते हुए संपूर्ण प्रस्तुति को HTML में कैसे परिवर्तित किया जाए।

## आवश्यक शर्तें

इससे पहले कि हम कोडिंग पहलू में उतरें, आइए सुनिश्चित करें कि हमने सब कुछ सही ढंग से सेट किया है:

- जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है।
-  जावा के लिए Aspose.Slides: आपको जावा एपीआई के लिए Aspose.Slides इंस्टॉल करना होगा। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: आवश्यक पैकेज आयात करें

आरंभ करने के लिए, आपको आवश्यक पैकेज आयात करने होंगे। ये पैकेज हमारे कार्य के लिए आवश्यक कक्षाएं और विधियाँ प्रदान करेंगे।

```java
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SlideImageFormat;
import com.aspose.slides.SVGOptions;
import com.aspose.slides.VideoPlayerHtmlController;
```

## चरण 2: दस्तावेज़ निर्देशिका निर्दिष्ट करें

 अपनी दस्तावेज़ निर्देशिका का पथ परिभाषित करें जहां प्रस्तुति फ़ाइल स्थित है। प्रतिस्थापित करें`"Your Document Directory"` वास्तविक पथ के साथ.

```java
String dataDir = "Your Document Directory";
```

## चरण 3: प्रेजेंटेशन आरंभ करें

 वह प्रेजेंटेशन लोड करें जिसे आप HTML में कनवर्ट करना चाहते हैं। प्रतिस्थापित करना सुनिश्चित करें`"presentationWith.pptx"` आपकी प्रस्तुति के फ़ाइल नाम के साथ।

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## चरण 4: HTML नियंत्रक बनाएँ

 हम एक बनाएंगे`VideoPlayerHtmlController` रूपांतरण प्रक्रिया को संभालने के लिए. URL को अपने इच्छित वेब पते से बदलें।

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.example.com/");
```

## चरण 5: HTML और SVG विकल्प कॉन्फ़िगर करें

रूपांतरण के लिए HTML और SVG विकल्प सेट करें। यह वह जगह है जहां आप आवश्यकतानुसार फ़ॉर्मेटिंग को अनुकूलित कर सकते हैं।

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## चरण 6: प्रेजेंटेशन को HTML के रूप में सहेजें

अब, प्रस्तुतिकरण को मीडिया फ़ाइलों सहित HTML फ़ाइल के रूप में सहेजने का समय आ गया है।

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## जावा स्लाइड में मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में बदलने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
String htmlDocumentFileName = "presentationWithVideo.html";
Presentation pres = new Presentation("presentationWith.pptx");
try
{
	VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
			"", htmlDocumentFileName, "http://www.example.com/");
	HtmlOptions htmlOptions = new HtmlOptions(controller);
	SVGOptions svgOptions = new SVGOptions(controller);
	htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
	htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
	pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने जावा स्लाइड्स और जावा एपीआई के लिए Aspose.Slides का उपयोग करके मीडिया फ़ाइलों के साथ एक संपूर्ण प्रेजेंटेशन को HTML में परिवर्तित करने की प्रक्रिया से गुज़रा है। इन चरणों का पालन करके, आप सभी आवश्यक मीडिया तत्वों को संरक्षित करते हुए कुशलतापूर्वक अपनी प्रस्तुतियों को वेब-अनुकूल प्रारूप में बदल सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे स्थापित कर सकता हूं?

 जावा के लिए Aspose.Slides स्थापित करने के लिए, डाउनलोड पृष्ठ पर जाएँ[यहाँ](https://releases.aspose.com/slides/java/) और दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

### क्या मैं HTML आउटपुट को और अधिक अनुकूलित कर सकता हूँ?

 हाँ, आप HTML आउटपुट को अपनी आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं।`HtmlOptions` क्लास रूपांतरण प्रक्रिया को नियंत्रित करने के लिए फ़ॉर्मेटिंग और लेआउट विकल्पों सहित विभिन्न सेटिंग्स प्रदान करता है।

### क्या जावा के लिए Aspose.Slides अन्य आउटपुट स्वरूपों का समर्थन करता है?

हां, जावा के लिए Aspose.Slides पीडीएफ, पीपीटीएक्स और अन्य सहित विभिन्न आउटपुट स्वरूपों का समर्थन करता है। आप दस्तावेज़ीकरण में इन विकल्पों का पता लगा सकते हैं।

### क्या जावा के लिए Aspose.Slides व्यावसायिक परियोजनाओं के लिए उपयुक्त है?

हां, जावा अनुप्रयोगों में प्रस्तुति-संबंधी कार्यों को संभालने के लिए जावा के लिए Aspose.Slides एक मजबूत और व्यावसायिक रूप से व्यवहार्य समाधान है। इसका उपयोग उद्यम-स्तरीय परियोजनाओं में व्यापक रूप से किया जाता है।

### मैं परिवर्तित HTML प्रस्तुति तक कैसे पहुँच सकता हूँ?

 एक बार जब आप रूपांतरण पूरा कर लेते हैं, तो आप इसमें निर्दिष्ट फ़ाइल का पता लगाकर HTML प्रस्तुति तक पहुंच सकते हैं`htmlDocumentFileName` चर।