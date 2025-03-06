---
title: जावा स्लाइड्स में नोट को TIFF में बदलें
linktitle: जावा स्लाइड्स में नोट को TIFF में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके स्पीकर नोट्स के साथ PowerPoint प्रस्तुतियों को जावा में TIFF प्रारूप में आसानी से परिवर्तित करें। निर्बाध दस्तावेज़ रूपांतरण के लिए स्रोत कोड के साथ हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 32
url: /hi/java/presentation-conversion/convert-note-tiff-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में नोट को TIFF में बदलने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके स्पीकर नोट्स के साथ PowerPoint प्रेजेंटेशन को TIFF प्रारूप में बदलने का तरीका दिखाएंगे। यह लाइब्रेरी प्रोग्रामेटिक रूप से PowerPoint फ़ाइलों के साथ काम करने के लिए शक्तिशाली सुविधाएँ प्रदान करती है।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

1.  Aspose.Slides for Java लाइब्रेरी: आपके पास Aspose.Slides for Java लाइब्रेरी इंस्टॉल होनी चाहिए। आप इसे वेबसाइट से डाउनलोड कर सकते हैं[यहाँ](https://downloads.aspose.com/slides/java).

2. जावा विकास वातावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा विकास वातावरण स्थापित है।

3. एक पावरपॉइंट प्रेजेंटेशन: एक पावरपॉइंट प्रेजेंटेशन तैयार करें (`ConvertWithNoteToTiff.pptx`) जिसमें स्पीकर नोट्स शामिल हैं।

## चरण 1: Aspose.Slides लाइब्रेरी आयात करें

अपने जावा कोड के आरंभ में Aspose.Slides लाइब्रेरी से आवश्यक क्लासेस आयात करें।

```java
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.TiffOptions;
```

## चरण 2: प्रेजेंटेशन और TIFF विकल्प सेट करें

अपनी प्रस्तुति फ़ाइल का पथ निर्धारित करें (`ConvertWithNoteToTiff.pptx` ) और एक बनाएं`Presentation` ऑब्जेक्ट. फिर, कॉन्फ़िगर करें`TiffOptions`रूपांतरण के लिए.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConvertWithNoteToTiff.pptx");

try {
    TiffOptions opts = new TiffOptions();
    INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
    notesOptions.setNotesPosition(NotesPositions.BottomFull);
    // यदि आवश्यक हो तो अतिरिक्त TIFF विकल्प यहां सेट किए जा सकते हैं

    // चरण 3: स्पीकर नोट्स के साथ प्रेजेंटेशन को TIFF में सेव करें
    pres.save(dataDir + "TestNotes_out.tiff", SaveFormat.Tiff, opts);
} finally {
    if (pres != null) pres.dispose();
}
```

## चरण 3: स्पीकर नोट्स के साथ प्रेजेंटेशन को TIFF में सेव करें

 के अंदर`try` ब्लॉक, का उपयोग करें`pres.save` स्पीकर नोट्स के साथ प्रेजेंटेशन को TIFF फ़ाइल में सेव करने की विधि।`SaveFormat.Tiff` पैरामीटर आउटपुट स्वरूप निर्दिष्ट करता है.

## चरण 4: संसाधनों को साफ़ करें

 में`finally` ब्लॉक करें, सुनिश्चित करें कि आप उसका निपटान करें`Presentation` किसी भी आवंटित संसाधन को जारी करने पर आपत्ति।

बस! आपने स्पीकर नोट्स के साथ PowerPoint प्रेजेंटेशन को Aspose.Slides for Java का उपयोग करके TIFF प्रारूप में सफलतापूर्वक परिवर्तित कर लिया है।

## जावा स्लाइड्स में नोट के साथ TIFF में कनवर्ट करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation(dataDir + "ConvertWithNoteToTiff.pptx");
try
{
	TiffOptions opts = new TiffOptions();
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// प्रस्तुति को TIFF नोट्स में सहेजना
	pres.save(dataDir + "TestNotes_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Slides for Java लाइब्रेरी का उपयोग करके जावा में नोट्स के साथ PowerPoint प्रेजेंटेशन को TIFF में कैसे बदला जाए। यह उन डेवलपर्स के लिए एक मूल्यवान उपकरण हो सकता है जिन्हें दस्तावेज़ रूपांतरणों को स्वचालित करने और अपनी प्रस्तुतियों में महत्वपूर्ण नोट्स बनाए रखने की आवश्यकता होती है।

## पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?

 आप Java के लिए Aspose.Slides को यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/) और दस्तावेज़ में दिए गए स्थापना निर्देशों का पालन करें।

### क्या मैं पावरपॉइंट प्रस्तुतियों को अन्य प्रारूपों में भी परिवर्तित कर सकता हूँ?

हां, Java के लिए Aspose.Slides पीडीएफ, HTML, और TIFF और PNG जैसे छवि प्रारूपों सहित आउटपुट प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।

### यदि मेरी पावरपॉइंट प्रस्तुति में नोट्स नहीं हैं तो क्या होगा?

यदि आपकी प्रस्तुति में नोट्स नहीं हैं, तो भी रूपांतरण प्रक्रिया काम करेगी, और आपको नोट्स के बिना स्लाइडों की TIFF छवि प्राप्त होगी।

### क्या Aspose.Slides for Java व्यावसायिक परियोजनाओं के लिए उपयुक्त है?

हां, Aspose.Slides for Java एक मजबूत और विश्वसनीय लाइब्रेरी है जिसका उपयोग कई व्यवसायों द्वारा उनके जावा अनुप्रयोगों में दस्तावेज़ प्रसंस्करण और हेरफेर के लिए किया जाता है।

### क्या मेरे प्रोजेक्ट में Java के लिए Aspose.Slides का उपयोग करने के लिए कोई लाइसेंसिंग संबंधी विचारणीय बातें हैं?

हां, Aspose.Slides for Java को व्यावसायिक उपयोग के लिए वैध लाइसेंस की आवश्यकता होती है। आप Aspose वेबसाइट पर लाइसेंसिंग विवरण पा सकते हैं।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
