---
title: जावा स्लाइड्स में नोट के साथ टीआईएफएफ में कनवर्ट करें
linktitle: जावा स्लाइड्स में नोट के साथ टीआईएफएफ में कनवर्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके आसानी से जावा में स्पीकर नोट्स के साथ PowerPoint प्रस्तुतियों को TIFF प्रारूप में परिवर्तित करें। निर्बाध दस्तावेज़ रूपांतरण के लिए स्रोत कोड के साथ हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 32
url: /hi/java/presentation-conversion/convert-note-tiff-java-slides/
---

## जावा स्लाइड्स में नोट से टीआईएफएफ में कनवर्ट करने का परिचय

इस ट्यूटोरियल में, हम दिखाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके स्पीकर नोट्स के साथ पावरपॉइंट प्रेजेंटेशन को TIFF प्रारूप में कैसे परिवर्तित किया जाए। यह लाइब्रेरी PowerPoint फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने के लिए शक्तिशाली सुविधाएँ प्रदान करती है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1.  जावा लाइब्रेरी के लिए Aspose.Slides: आपके पास जावा लाइब्रेरी के लिए Aspose.Slides इंस्टॉल होना चाहिए। आप इसे वेबसाइट से डाउनलोड कर सकते हैं[यहाँ](https://downloads.aspose.com/slides/java).

2. जावा विकास वातावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा विकास वातावरण स्थापित है।

3. एक पावरपॉइंट प्रेजेंटेशन: एक पावरपॉइंट प्रेजेंटेशन तैयार करें (`ConvertWithNoteToTiff.pptx`) जिसमें स्पीकर नोट्स शामिल हैं।

## चरण 1: Aspose.Slides लाइब्रेरी आयात करें

अपने जावा कोड की शुरुआत में Aspose.Slides लाइब्रेरी से आवश्यक कक्षाएं आयात करें।

```java
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.TiffOptions;
```

## चरण 2: प्रस्तुतिकरण और TIFF विकल्प सेट करें

अपनी प्रस्तुति फ़ाइल का पथ परिभाषित करें (`ConvertWithNoteToTiff.pptx` ) और एक बनाएं`Presentation` वस्तु। फिर, कॉन्फ़िगर करें`TiffOptions` रूपांतरण के लिए.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConvertWithNoteToTiff.pptx");

try {
    TiffOptions opts = new TiffOptions();
    INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
    notesOptions.setNotesPosition(NotesPositions.BottomFull);
    // जरूरत पड़ने पर अतिरिक्त TIFF विकल्प यहां सेट किए जा सकते हैं

    // चरण 3: प्रेजेंटेशन को स्पीकर नोट्स के साथ TIFF में सेव करें
    pres.save(dataDir + "TestNotes_out.tiff", SaveFormat.Tiff, opts);
} finally {
    if (pres != null) pres.dispose();
}
```

## चरण 3: प्रेजेंटेशन को स्पीकर नोट्स के साथ TIFF में सेव करें

 के अंदर`try` ब्लॉक करें, उपयोग करें`pres.save` प्रेजेंटेशन को स्पीकर नोट्स के साथ TIFF फ़ाइल में सहेजने की विधि।`SaveFormat.Tiff` पैरामीटर आउटपुट स्वरूप निर्दिष्ट करता है।

## चरण 4: संसाधनों को साफ़ करें

 में`finally` ब्लॉक करें, सुनिश्चित करें कि आप इसका निपटान करें`Presentation` किसी भी आवंटित संसाधन को जारी करने पर आपत्ति।

इतना ही! आपने Java के लिए Aspose.Slides का उपयोग करके स्पीकर नोट्स के साथ एक PowerPoint प्रस्तुति को TIFF प्रारूप में सफलतापूर्वक परिवर्तित कर लिया है।

## जावा स्लाइड्स में नोट को टीआईएफएफ में बदलने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रेजेंटेशन ऑब्जेक्ट को इंस्टेंट करें जो एक प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation(dataDir + "ConvertWithNoteToTiff.pptx");
try
{
	TiffOptions opts = new TiffOptions();
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// प्रस्तुतिकरण को TIFF नोट्स में सहेजा जा रहा है
	pres.save(dataDir + "TestNotes_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि जावा लाइब्रेरी के लिए Aspose.Slides का उपयोग करके नोट्स के साथ PowerPoint प्रेजेंटेशन को जावा में TIFF में कैसे परिवर्तित किया जाए। यह उन डेवलपर्स के लिए एक मूल्यवान उपकरण हो सकता है जिन्हें दस्तावेज़ रूपांतरण स्वचालित करने और अपनी प्रस्तुतियों में महत्वपूर्ण नोट्स बनाए रखने की आवश्यकता होती है।

## पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे स्थापित करूं?

 आप जावा के लिए Aspose.Slides डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/)और दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

### क्या मैं PowerPoint प्रस्तुतियों को अन्य प्रारूपों में भी परिवर्तित कर सकता हूँ?

हां, जावा के लिए Aspose.Slides पीडीएफ, HTML और TIFF और PNG जैसे छवि प्रारूपों सहित आउटपुट स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है।

### यदि मेरी पावरपॉइंट प्रेजेंटेशन में नोट्स नहीं हैं तो क्या होगा?

यदि आपकी प्रस्तुति में नोट्स नहीं हैं, तो रूपांतरण प्रक्रिया अभी भी काम करेगी, और आपको नोट्स के बिना स्लाइड की एक TIFF छवि मिलेगी।

### क्या जावा के लिए Aspose.Slides व्यावसायिक परियोजनाओं के लिए उपयुक्त है?

हाँ, Aspose.Slides for Java एक मजबूत और विश्वसनीय लाइब्रेरी है जिसका उपयोग कई व्यवसाय अपने जावा अनुप्रयोगों में दस्तावेज़ प्रसंस्करण और हेरफेर के लिए करते हैं।

### क्या मेरे प्रोजेक्ट में जावा के लिए Aspose.Slides का उपयोग करने के लिए कोई लाइसेंस संबंधी विचार हैं?

हां, जावा के लिए Aspose.Slides को व्यावसायिक उपयोग के लिए वैध लाइसेंस की आवश्यकता होती है। आप Aspose वेबसाइट पर लाइसेंसिंग विवरण पा सकते हैं।