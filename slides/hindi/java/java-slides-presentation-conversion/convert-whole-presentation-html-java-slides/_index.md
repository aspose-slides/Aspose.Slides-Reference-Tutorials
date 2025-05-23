---
"description": "Aspose.Slides का उपयोग करके जावा में PowerPoint प्रस्तुतियों को HTML में परिवर्तित करना सीखें। कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।"
"linktitle": "जावा स्लाइड्स में संपूर्ण प्रस्तुति को HTML में बदलें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में संपूर्ण प्रस्तुति को HTML में बदलें"
"url": "/hi/java/presentation-conversion/convert-whole-presentation-html-java-slides/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में संपूर्ण प्रस्तुति को HTML में बदलें


## जावा स्लाइड्स में संपूर्ण प्रेजेंटेशन को HTML में बदलने का परिचय

आज के डिजिटल युग में, प्रेजेंटेशन को HTML में बदलना एक आम ज़रूरत है, खासकर तब जब आप अपनी प्रेजेंटेशन को ऑनलाइन शेयर करना चाहते हैं या उन्हें किसी वेबसाइट में एम्बेड करना चाहते हैं। अगर आप Java Slides के साथ काम कर रहे हैं और आपको पूरी प्रेजेंटेशन को HTML में बदलने की ज़रूरत है, तो आप सही जगह पर हैं। इस चरण-दर-चरण गाइड में, हम आपको Aspose.Slides for Java API का उपयोग करके प्रक्रिया के बारे में बताएँगे।

## आवश्यक शर्तें

इससे पहले कि हम रूपांतरण प्रक्रिया में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. जावा डेवलपमेंट एनवायरनमेंट: सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
2. Aspose.Slides for Java: Aspose.Slides for Java लाइब्रेरी को डाउनलोड और सेट अप करें।
3. प्रस्तुति: आपको एक पावरपॉइंट प्रस्तुति की आवश्यकता होगी जिसे आप HTML में परिवर्तित करना चाहते हैं।

अब जबकि हमारी पूर्व-आवश्यकताएं तैयार हैं, तो आइए रूपांतरण प्रक्रिया शुरू करें।

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

अपने जावा प्रोजेक्ट में, आवश्यक लाइब्रेरीज़ को आयात करके शुरू करें। प्रस्तुतियों के साथ काम करने के लिए आपको Aspose.Slides की आवश्यकता होगी।

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## चरण 2: प्रस्तुति लोड करें

इसके बाद, आपको वह PowerPoint प्रेजेंटेशन लोड करना चाहिए जिसे आप HTML में बदलना चाहते हैं। सुनिश्चित करें कि आपने अपनी प्रेजेंटेशन फ़ाइल के लिए सही पथ निर्दिष्ट किया है।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
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

अब, हमारे द्वारा निर्धारित विकल्पों का उपयोग करके प्रस्तुति को HTML में परिवर्तित करने का समय आ गया है।

```java
// प्रस्तुति को HTML में सहेजना
presentation.save(dataDir + "ConvertWholePresentationToHTML_out.html", SaveFormat.Html, htmlOpt);
```

## चरण 5: सफ़ाई

अंत में, संसाधनों को मुक्त करने के लिए प्रेजेंटेशन ऑब्जेक्ट को हटाना न भूलें।

```java
if (presentation != null) presentation.dispose();
```

## जावा स्लाइड्स में संपूर्ण प्रस्तुति को HTML में परिवर्तित करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation(dataDir + "Convert_HTML.pptx");
try
{
	HtmlOptions htmlOpt = new HtmlOptions();
	htmlOpt.setHtmlFormatter(HtmlFormatter.createDocumentFormatter("", false));
	INotesCommentsLayoutingOptions notesOptions = htmlOpt.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// प्रस्तुति को HTML में सहेजना
	presentation.save(dataDir + "ConvertWholePresentationToHTML_out.html", SaveFormat.Html, htmlOpt);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

बधाई हो! आपने Aspose.Slides for Java API का उपयोग करके Java Slides में संपूर्ण प्रस्तुति को HTML में सफलतापूर्वक परिवर्तित कर लिया है। यह तब बहुत उपयोगी हो सकता है जब आप अपनी प्रस्तुतियों को ऑनलाइन सुलभ बनाना चाहते हैं या उन्हें वेब अनुप्रयोगों में एकीकृत करना चाहते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं HTML आउटपुट को और अधिक अनुकूलित कर सकता हूँ?

हां, आप कोड में HTML रूपांतरण विकल्पों को समायोजित करके HTML आउटपुट को कस्टमाइज़ कर सकते हैं। आप अपनी ज़रूरतों के हिसाब से फ़ॉर्मेटिंग, लेआउट और बहुत कुछ संशोधित कर सकते हैं।

### क्या Aspose.Slides for Java एक सशुल्क लाइब्रेरी है?

हां, Aspose.Slides for Java एक व्यावसायिक लाइब्रेरी है, लेकिन यह एक निःशुल्क परीक्षण संस्करण प्रदान करता है। लाइसेंस खरीदने का निर्णय लेने से पहले आप इसकी विशेषताओं और कार्यक्षमता का पता लगा सकते हैं।

### क्या कोई अन्य आउटपुट प्रारूप समर्थित है?

हां, Aspose.Slides for Java विभिन्न आउटपुट प्रारूपों का समर्थन करता है, जिसमें PDF, PPTX और छवियां शामिल हैं। आप अपनी आवश्यकताओं के अनुसार सबसे उपयुक्त प्रारूप चुन सकते हैं।

### क्या मैं संपूर्ण प्रस्तुति के बजाय विशिष्ट स्लाइडों को परिवर्तित कर सकता हूँ?

हां, आप प्रेजेंटेशन को सेव करने से पहले कोड में उन्हें चुनकर विशिष्ट स्लाइड्स को कन्वर्ट कर सकते हैं। इससे आपको यह नियंत्रण मिलता है कि कौन सी स्लाइड्स HTML में कन्वर्ट होंगी।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}