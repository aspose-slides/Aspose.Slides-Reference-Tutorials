---
title: जावा स्लाइड में नोट्स स्लाइड व्यू को पीडीएफ में बदलें
linktitle: जावा स्लाइड में नोट्स स्लाइड व्यू को पीडीएफ में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके नोट्स के साथ PowerPoint प्रस्तुतियों को PDF में परिवर्तित करना सीखें। स्रोत कोड के साथ हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 16
url: /hi/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

## जावा स्लाइड में नोट्स स्लाइड व्यू को पीडीएफ में बदलने का परिचय

इस ट्यूटोरियल में, हम जावा लाइब्रेरी के लिए Aspose.Slides का उपयोग करके नोट्स स्लाइड व्यू के साथ एक पावरपॉइंट प्रेजेंटेशन को पीडीएफ में परिवर्तित करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करेंगे। यह लाइब्रेरी जावा में पावरपॉइंट प्रस्तुतियों के साथ काम करने के लिए शक्तिशाली सुविधाएँ प्रदान करती है।

## आवश्यक शर्तें
1. जावा डेवलपमेंट किट (जेडीके) स्थापित किया गया।
2. जावा लाइब्रेरी के लिए Aspose.Slides आपके प्रोजेक्ट में जोड़ा गया।

## चरण 1: आवश्यक कक्षाएं आयात करें
आरंभ करने के लिए, आपको Aspose.Slides लाइब्रेरी से आवश्यक कक्षाएं आयात करनी होंगी। ऐसा करने के लिए कोड यहां दिया गया है:

```java
import com.aspose.slides.*;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन लोड करें
 आपकी पॉवरपॉइंट प्रेजेंटेशन फ़ाइल तैयार होनी चाहिए। प्रतिस्थापित करें`"Your Document Directory"` उस निर्देशिका के पथ के साथ जहां आपकी प्रस्तुति फ़ाइल स्थित है। प्रेजेंटेशन लोड करने के लिए कोड यहां दिया गया है:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## चरण 3: पीडीएफ विकल्प कॉन्फ़िगर करें
अब, पीडीएफ निर्यात विकल्पों को कॉन्फ़िगर करें। विशेष रूप से, हम पीडीएफ में स्लाइड के नीचे नोट्स को शामिल करने के लिए नोट्स की स्थिति को "बॉटमफुल" पर सेट करेंगे। यहाँ कोड है:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

आप अपनी आवश्यकताओं के अनुसार अन्य पीडीएफ विकल्पों को अनुकूलित कर सकते हैं।

## चरण 4: प्रेजेंटेशन को नोट्स के साथ पीडीएफ के रूप में सहेजें
अंत में, आइए प्रेजेंटेशन को नोट्स सहित एक पीडीएफ फाइल के रूप में सहेजें। आप आउटपुट फ़ाइल नाम निर्दिष्ट कर सकते हैं (उदाहरण के लिए,`"Pdf_Notes_out.pdf"`) और प्रारूप चुनें (`SaveFormat.Pdf`). ऐसा करने के लिए कोड यहां दिया गया है:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## चरण 5: संसाधनों को साफ़ करें
प्रस्तुतिकरण पूरा करने के बाद संसाधनों को जारी करना न भूलें:

```java
if (presentation != null) presentation.dispose();
```

## जावा स्लाइड में नोट्स स्लाइड व्यू को पीडीएफ में बदलने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रेजेंटेशन ऑब्जेक्ट को इंस्टेंट करें जो एक प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// प्रस्तुतिकरण को पीडीएफ नोट्स में सहेजा जा रहा है
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया है कि जावा लाइब्रेरी के लिए Aspose.Slides का उपयोग करके नोट्स स्लाइड व्यू के साथ PowerPoint प्रस्तुतियों को पीडीएफ में कैसे परिवर्तित किया जाए। इस रूपांतरण को प्राप्त करने के लिए हमने स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका का पालन किया। यहां मुख्य बातें दी गई हैं:

## अक्सर पूछे जाने वाले प्रश्न

### मैं पीडीएफ में नोट्स की स्थिति कैसे बदलूं?

 आप संशोधित करके पीडीएफ में नोट्स की स्थिति बदल सकते हैं`setNotesPosition` विधि तर्क. उदाहरण के लिए, आप इसे सेट कर सकते हैं`NotesPositions.RightFull` नोट्स को स्लाइड के दाईं ओर रखने के लिए।

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### क्या मैं पीडीएफ निर्यात को और अधिक अनुकूलित कर सकता हूँ?

हां, आप विभिन्न विकल्पों को समायोजित करके पीडीएफ निर्यात को अनुकूलित कर सकते हैं`PdfOptions` वस्तु। उदाहरण के लिए, आप अपनी आवश्यकताओं के अनुसार गुणवत्ता, संपीड़न और अन्य पैरामीटर सेट कर सकते हैं।

### मैं जावा के लिए Aspose.Slides कैसे प्राप्त कर सकता हूँ?

 आप जावा के लिए Aspose.Slides को वेबसाइट से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

### क्या Aspose.Slides का उपयोग करने के लिए कोई लाइसेंसिंग आवश्यकताएं हैं?

हाँ, Aspose.Slides को व्यावसायिक उपयोग के लिए वैध लाइसेंस की आवश्यकता होती है। आप Aspose वेबसाइट से लाइसेंस प्राप्त कर सकते हैं।

### मुझे और अधिक दस्तावेज़ और उदाहरण कहां मिल सकते हैं?

 आप जावा के लिए Aspose.Slides के लिए व्यापक दस्तावेज़ और उदाहरण यहां पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).