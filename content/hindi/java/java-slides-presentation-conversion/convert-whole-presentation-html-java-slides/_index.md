---
title: जावा स्लाइड्स में संपूर्ण प्रेजेंटेशन को HTML में कनवर्ट करें
linktitle: जावा स्लाइड्स में संपूर्ण प्रेजेंटेशन को HTML में कनवर्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके जावा में PowerPoint प्रस्तुतियों को HTML में परिवर्तित करना सीखें। कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 29
url: /hi/java/presentation-conversion/convert-whole-presentation-html-java-slides/
---

## जावा स्लाइड्स में संपूर्ण प्रेजेंटेशन को HTML में बदलने का परिचय

आज के डिजिटल युग में, प्रस्तुतियों को HTML में परिवर्तित करना एक सामान्य आवश्यकता है, खासकर जब आप अपनी प्रस्तुतियों को ऑनलाइन साझा करना चाहते हैं या उन्हें किसी वेबसाइट में एम्बेड करना चाहते हैं। यदि आप जावा स्लाइड्स के साथ काम कर रहे हैं और संपूर्ण प्रेजेंटेशन को HTML में बदलने की आवश्यकता है, तो आप सही जगह पर हैं। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको जावा एपीआई के लिए Aspose.Slides का उपयोग करके प्रक्रिया के बारे में बताएंगे।

## आवश्यक शर्तें

इससे पहले कि हम रूपांतरण प्रक्रिया में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
2. जावा के लिए Aspose.Slides: जावा लाइब्रेरी के लिए Aspose.Slides को डाउनलोड करें और सेट करें।
3. एक प्रेजेंटेशन: आपको एक पावरपॉइंट प्रेजेंटेशन की आवश्यकता होगी जिसे आप HTML में कनवर्ट करना चाहते हैं।

अब जबकि हमारी पूर्वापेक्षाएँ तैयार हैं, आइए रूपांतरण प्रक्रिया शुरू करें।

## चरण 1: आवश्यक पुस्तकालय आयात करें

अपने जावा प्रोजेक्ट में, आवश्यक लाइब्रेरी आयात करके प्रारंभ करें। प्रस्तुतियों के साथ काम करने के लिए आपको Aspose.Slides की आवश्यकता होगी।

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## चरण 2: प्रस्तुति लोड करें

इसके बाद, आपको पावरपॉइंट प्रेजेंटेशन लोड करना चाहिए जिसे आप HTML में कनवर्ट करना चाहते हैं। सुनिश्चित करें कि आपने अपनी प्रस्तुति फ़ाइल के लिए सही पथ निर्दिष्ट किया है।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रेजेंटेशन ऑब्जेक्ट को इंस्टेंट करें जो एक प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation(dataDir + "Convert_HTML.pptx");
```

## चरण 3: HTML रूपांतरण विकल्प सेट करें

HTML रूपांतरण को अनुकूलित करने के लिए, आप विभिन्न विकल्प सेट कर सकते हैं। उदाहरण के लिए, आप HTML फ़ॉर्मेटर और HTML में नोट्स और टिप्पणियों की स्थिति निर्दिष्ट कर सकते हैं।

```java
HtmlOptions htmlOpt = new HtmlOptions();
htmlOpt.setHtmlFormatter(HtmlFormatter.createDocumentFormatter("", false));
INotesCommentsLayoutingOptions notesOptions = htmlOpt.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## चरण 4: HTML में कनवर्ट करें

अब, हमारे द्वारा निर्धारित विकल्पों का उपयोग करके प्रेजेंटेशन को HTML में बदलने का समय आ गया है।

```java
// प्रस्तुतिकरण को HTML में सहेजा जा रहा है
presentation.save(dataDir + "ConvertWholePresentationToHTML_out.html", SaveFormat.Html, htmlOpt);
```

## चरण 5: सफ़ाई

अंत में, संसाधनों को खाली करने के लिए प्रेजेंटेशन ऑब्जेक्ट का निपटान करना न भूलें।

```java
if (presentation != null) presentation.dispose();
```

## जावा स्लाइड्स में संपूर्ण प्रेजेंटेशन को HTML में बदलने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रेजेंटेशन ऑब्जेक्ट को इंस्टेंट करें जो एक प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation(dataDir + "Convert_HTML.pptx");
try
{
	HtmlOptions htmlOpt = new HtmlOptions();
	htmlOpt.setHtmlFormatter(HtmlFormatter.createDocumentFormatter("", false));
	INotesCommentsLayoutingOptions notesOptions = htmlOpt.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// प्रस्तुतिकरण को HTML में सहेजा जा रहा है
	presentation.save(dataDir + "ConvertWholePresentationToHTML_out.html", SaveFormat.Html, htmlOpt);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

बधाई हो! आपने जावा एपीआई के लिए Aspose.Slides का उपयोग करके एक संपूर्ण प्रस्तुति को जावा स्लाइड्स में सफलतापूर्वक HTML में परिवर्तित कर दिया है। यह अविश्वसनीय रूप से उपयोगी हो सकता है जब आप अपनी प्रस्तुतियों को ऑनलाइन पहुंच योग्य बनाना चाहते हैं या उन्हें वेब अनुप्रयोगों में एकीकृत करना चाहते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं HTML आउटपुट को और अधिक अनुकूलित कर सकता हूँ?

हाँ, आप कोड में HTML रूपांतरण विकल्पों को समायोजित करके HTML आउटपुट को अनुकूलित कर सकते हैं। आप अपनी आवश्यकताओं के अनुरूप फ़ॉर्मेटिंग, लेआउट और बहुत कुछ संशोधित कर सकते हैं।

### क्या जावा के लिए Aspose.Slides एक सशुल्क लाइब्रेरी है?

हां, जावा के लिए Aspose.Slides एक व्यावसायिक लाइब्रेरी है, लेकिन यह एक निःशुल्क परीक्षण संस्करण प्रदान करता है। लाइसेंस खरीदने का निर्णय लेने से पहले आप इसकी विशेषताओं और कार्यक्षमता का पता लगा सकते हैं।

### क्या कोई अन्य आउटपुट स्वरूप समर्थित है?

हाँ, Java के लिए Aspose.Slides PDF, PPTX और छवियों सहित विभिन्न आउटपुट स्वरूपों का समर्थन करता है। आप वह प्रारूप चुन सकते हैं जो आपकी आवश्यकताओं के लिए सबसे उपयुक्त हो।

### क्या मैं संपूर्ण प्रस्तुतीकरण के बजाय विशिष्ट स्लाइडों को परिवर्तित कर सकता हूँ?

हां, आप प्रेजेंटेशन को सेव करने से पहले विशिष्ट स्लाइड्स को कोड में चुनकर उन्हें परिवर्तित कर सकते हैं। यह आपको नियंत्रण देता है कि कौन सी स्लाइड HTML में परिवर्तित हो जाती है।