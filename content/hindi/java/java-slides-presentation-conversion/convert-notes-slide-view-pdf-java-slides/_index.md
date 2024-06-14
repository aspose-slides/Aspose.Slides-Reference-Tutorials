---
title: जावा स्लाइड्स में नोट्स स्लाइड दृश्य को पीडीएफ में बदलें
linktitle: जावा स्लाइड्स में नोट्स स्लाइड दृश्य को पीडीएफ में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके नोट्स के साथ PowerPoint प्रस्तुतियों को PDF में परिवर्तित करना सीखें। स्रोत कोड के साथ हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 16
url: /hi/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

## जावा स्लाइड्स में नोट्स स्लाइड दृश्य को पीडीएफ में परिवर्तित करने का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java लाइब्रेरी का उपयोग करके नोट्स स्लाइड दृश्य वाले PowerPoint प्रेजेंटेशन को PDF में बदलने की प्रक्रिया के बारे में बताएंगे। यह लाइब्रेरी Java में PowerPoint प्रेजेंटेशन के साथ काम करने के लिए शक्तिशाली सुविधाएँ प्रदान करती है।

## आवश्यक शर्तें
1. जावा डेवलपमेंट किट (JDK) स्थापित.
2. Aspose.Slides for Java लाइब्रेरी आपके प्रोजेक्ट में जोड़ दी गई।

## चरण 1: आवश्यक कक्षाएं आयात करें
आरंभ करने के लिए, आपको Aspose.Slides लाइब्रेरी से आवश्यक क्लासेस आयात करने की आवश्यकता होगी। ऐसा करने के लिए कोड यहां दिया गया है:

```java
import com.aspose.slides.*;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन लोड करें
 आपकी पावरपॉइंट प्रेजेंटेशन फ़ाइल तैयार होनी चाहिए।`"Your Document Directory"` उस निर्देशिका का पथ जहाँ आपकी प्रस्तुति फ़ाइल स्थित है। प्रस्तुति लोड करने के लिए कोड यहाँ दिया गया है:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## चरण 3: PDF विकल्प कॉन्फ़िगर करें
अब, आइए PDF एक्सपोर्ट विकल्पों को कॉन्फ़िगर करें। विशेष रूप से, हम PDF में स्लाइड के नीचे नोट्स शामिल करने के लिए नोट्स की स्थिति को "बॉटमफुल" पर सेट करेंगे। यहाँ कोड है:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

आप अपनी आवश्यकताओं के अनुसार अन्य पीडीएफ विकल्पों को अनुकूलित कर सकते हैं।

## चरण 4: प्रेजेंटेशन को नोट्स के साथ PDF के रूप में सहेजें
 अंत में, आइए प्रेजेंटेशन को नोट्स सहित PDF फ़ाइल के रूप में सेव करें। आप आउटपुट फ़ाइल का नाम निर्दिष्ट कर सकते हैं (उदाहरण के लिए,`"Pdf_Notes_out.pdf"`) और प्रारूप चुनें (`SaveFormat.Pdf`) ऐसा करने के लिए कोड यहां दिया गया है:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## चरण 5: संसाधनों को साफ़ करें
प्रस्तुतिकरण पूरा हो जाने पर संसाधन जारी करना न भूलें:

```java
if (presentation != null) presentation.dispose();
```

## जावा स्लाइड्स में नोट्स स्लाइड दृश्य को पीडीएफ में परिवर्तित करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// प्रस्तुति को PDF नोट्स में सहेजना
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Slides for Java लाइब्रेरी का उपयोग करके नोट्स स्लाइड व्यू वाले PowerPoint प्रेजेंटेशन को PDF में बदलने का तरीका खोजा है। हमने इस रूपांतरण को प्राप्त करने के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका का पालन किया। यहाँ मुख्य बातें दी गई हैं:

## अक्सर पूछे जाने वाले प्रश्न

### मैं पीडीएफ में नोट्स की स्थिति कैसे बदलूं?

 आप पीडीएफ में नोट्स की स्थिति को संशोधित करके बदल सकते हैं`setNotesPosition` विधि तर्क। उदाहरण के लिए, आप इसे सेट कर सकते हैं`NotesPositions.RightFull` नोट्स को स्लाइड के दाईं ओर रखने के लिए.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### क्या मैं पीडीएफ निर्यात को और अधिक अनुकूलित कर सकता हूं?

 हां, आप विभिन्न विकल्पों को समायोजित करके पीडीएफ निर्यात को अनुकूलित कर सकते हैं`PdfOptions` उदाहरण के लिए, आप अपनी आवश्यकताओं के अनुसार गुणवत्ता, संपीड़न और अन्य पैरामीटर सेट कर सकते हैं।

### मैं Java के लिए Aspose.Slides कैसे प्राप्त कर सकता हूँ?

 आप वेबसाइट से Java के लिए Aspose.Slides डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

### क्या Aspose.Slides का उपयोग करने के लिए कोई लाइसेंसिंग आवश्यकताएं हैं?

हां, Aspose.Slides को व्यावसायिक उपयोग के लिए वैध लाइसेंस की आवश्यकता होती है। आप Aspose वेबसाइट से लाइसेंस प्राप्त कर सकते हैं।

### मैं अधिक दस्तावेज और उदाहरण कहां पा सकता हूं?

 आप Aspose.Slides for Java के लिए विस्तृत दस्तावेज़ और उदाहरण यहां पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).