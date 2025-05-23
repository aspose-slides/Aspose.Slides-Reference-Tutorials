---
"description": "Java Slides का उपयोग करके मीडिया फ़ाइलों के साथ प्रस्तुतियों को HTML में परिवर्तित करना सीखें। Aspose.Slides for Java API के साथ हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"linktitle": "जावा स्लाइड्स में मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में बदलें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में बदलें"
"url": "/hi/java/presentation-conversion/convert-whole-presentation-html-media-files-java-slides/"
"weight": 30
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में बदलें


## जावा स्लाइड्स में मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में परिवर्तित करने का परिचय

आज के डिजिटल युग में, HTML सहित विभिन्न प्रारूपों में प्रस्तुतियों को परिवर्तित करने की आवश्यकता एक सामान्य आवश्यकता है। जावा डेवलपर्स अक्सर खुद को इस चुनौती का सामना करते हुए पाते हैं। सौभाग्य से, Aspose.Slides for Java API के साथ, यह कार्य कुशलतापूर्वक पूरा किया जा सकता है। इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि जावा स्लाइड का उपयोग करके मीडिया फ़ाइलों को संरक्षित करते हुए एक संपूर्ण प्रस्तुति को HTML में कैसे परिवर्तित किया जाए।

## आवश्यक शर्तें

इससे पहले कि हम कोडिंग पहलू में उतरें, आइए सुनिश्चित करें कि हमने सब कुछ सही ढंग से सेट किया है:

- जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है।
- Aspose.Slides for Java: आपको Aspose.Slides for Java API इंस्टॉल करना होगा। आप इसे डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: आवश्यक पैकेज आयात करें

आरंभ करने के लिए, आपको आवश्यक पैकेज आयात करने की आवश्यकता है। ये पैकेज हमारे कार्य के लिए आवश्यक क्लास और विधियाँ प्रदान करेंगे।

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

अपनी दस्तावेज़ निर्देशिका का पथ निर्धारित करें जहाँ प्रस्तुति फ़ाइल स्थित है। `"Your Document Directory"` वास्तविक पथ के साथ.

```java
String dataDir = "Your Document Directory";
```

## चरण 3: प्रस्तुति आरंभ करें

वह प्रेजेंटेशन लोड करें जिसे आप HTML में बदलना चाहते हैं। `"presentationWith.pptx"` अपनी प्रस्तुति के फ़ाइल नाम के साथ.

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## चरण 4: HTML नियंत्रक बनाएँ

हम एक बनाएंगे `VideoPlayerHtmlController` रूपांतरण प्रक्रिया को संभालने के लिए। URL को अपने इच्छित वेब पते से बदलें।

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.example.com/");
```

## चरण 5: HTML और SVG विकल्प कॉन्फ़िगर करें

रूपांतरण के लिए HTML और SVG विकल्प सेट करें। यह वह जगह है जहाँ आप आवश्यकतानुसार स्वरूपण को अनुकूलित कर सकते हैं।

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## चरण 6: प्रस्तुति को HTML के रूप में सहेजें

अब, प्रस्तुति को मीडिया फ़ाइलों सहित HTML फ़ाइल के रूप में सहेजने का समय आ गया है।

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## जावा स्लाइड्स में मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में परिवर्तित करने के लिए पूर्ण स्रोत कोड

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

इस ट्यूटोरियल में, हमने Java Slides और Aspose.Slides for Java API का उपयोग करके मीडिया फ़ाइलों के साथ संपूर्ण प्रस्तुति को HTML में बदलने की प्रक्रिया को देखा है। इन चरणों का पालन करके, आप अपनी प्रस्तुतियों को कुशलतापूर्वक वेब-अनुकूल प्रारूप में बदल सकते हैं, सभी आवश्यक मीडिया तत्वों को संरक्षित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides कैसे स्थापित कर सकता हूँ?

Java के लिए Aspose.Slides को स्थापित करने के लिए, डाउनलोड पृष्ठ पर जाएँ [यहाँ](https://releases.aspose.com/slides/java/) और दिए गए स्थापना निर्देशों का पालन करें।

### क्या मैं HTML आउटपुट को और अधिक अनुकूलित कर सकता हूँ?

हां, आप अपनी आवश्यकताओं के अनुसार HTML आउटपुट को अनुकूलित कर सकते हैं। `HtmlOptions` क्लास रूपांतरण प्रक्रिया को नियंत्रित करने के लिए विभिन्न सेटिंग्स प्रदान करता है, जिसमें स्वरूपण और लेआउट विकल्प शामिल हैं।

### क्या Aspose.Slides for Java अन्य आउटपुट प्रारूपों का समर्थन करता है?

हां, Aspose.Slides for Java विभिन्न आउटपुट प्रारूपों का समर्थन करता है, जिसमें PDF, PPTX, और बहुत कुछ शामिल है। आप इन विकल्पों को दस्तावेज़ में देख सकते हैं।

### क्या Aspose.Slides for Java व्यावसायिक परियोजनाओं के लिए उपयुक्त है?

हां, Aspose.Slides for Java, Java अनुप्रयोगों में प्रस्तुति-संबंधी कार्यों को संभालने के लिए एक मजबूत और व्यावसायिक रूप से व्यवहार्य समाधान है। इसका व्यापक रूप से एंटरप्राइज़-स्तरीय परियोजनाओं में उपयोग किया जाता है।

### मैं परिवर्तित HTML प्रस्तुति तक कैसे पहुंच सकता हूं?

एक बार जब आप रूपांतरण पूरा कर लेते हैं, तो आप निर्दिष्ट फ़ाइल का पता लगाकर HTML प्रस्तुति तक पहुँच सकते हैं `htmlDocumentFileName` चर।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}