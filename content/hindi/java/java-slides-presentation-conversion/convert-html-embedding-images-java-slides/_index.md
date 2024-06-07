---
title: HTML एम्बेडिंग छवियों को जावा स्लाइड्स में परिवर्तित करें
linktitle: HTML एम्बेडिंग छवियों को जावा स्लाइड्स में परिवर्तित करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: एम्बेडेड इमेज के साथ PowerPoint को HTML में बदलें। Java के लिए Aspose.Slides का उपयोग करके चरण-दर-चरण मार्गदर्शिका। Java में प्रेजेंटेशन रूपांतरण को आसानी से स्वचालित करना सीखें।
type: docs
weight: 11
url: /hi/java/presentation-conversion/convert-html-embedding-images-java-slides/
---

## HTML एम्बेडिंग छवियों को जावा स्लाइड्स में परिवर्तित करने का परिचय

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको Aspose.Slides for Java का उपयोग करके छवियों को एम्बेड करते हुए PowerPoint प्रस्तुति को HTML दस्तावेज़ में परिवर्तित करने की प्रक्रिया से परिचित कराएँगे। यह ट्यूटोरियल मानता है कि आपने पहले ही अपना विकास वातावरण सेट कर लिया है और Aspose.Slides for Java लाइब्रेरी स्थापित कर ली है।

## आवश्यकताएं

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1.  Aspose.Slides for Java लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://downloads.aspose.com/slides/java).

2. एक पावरपॉइंट प्रस्तुति फ़ाइल (PPTX प्रारूप) जिसे आप HTML में परिवर्तित करना चाहते हैं।

3. एक जावा विकास वातावरण स्थापित किया गया।

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

सबसे पहले, आपको अपने जावा प्रोजेक्ट के लिए आवश्यक लाइब्रेरीज़ और क्लासेज़ आयात करने की आवश्यकता है।

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन लोड करें

 इसके बाद, आप उस PowerPoint प्रेजेंटेशन को लोड करेंगे जिसे आप HTML में बदलना चाहते हैं।`presentationName` अपनी प्रस्तुति फ़ाइल के वास्तविक पथ के साथ.

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## चरण 3: HTML रूपांतरण विकल्प कॉन्फ़िगर करें

अब, आप HTML रूपांतरण विकल्पों को कॉन्फ़िगर करेंगे। इस उदाहरण में, हम HTML दस्तावेज़ में छवियाँ एम्बेड करेंगे और बाहरी छवियों के लिए आउटपुट निर्देशिका निर्दिष्ट करेंगे।

```java
Html5Options options = new Html5Options();
//HTML5 दस्तावेज़ में छवियों को बलपूर्वक न सहेजें
options.setEmbedImages(true); // छवियाँ एम्बेड करने के लिए true पर सेट करें
// बाह्य छवियों के लिए पथ सेट करें (यदि आवश्यक हो)
options.setOutputPath("path/to/output/directory/");
```

## चरण 4: आउटपुट निर्देशिका बनाएँ

HTML दस्तावेज़ को सहेजने से पहले, यदि आउटपुट निर्देशिका मौजूद नहीं है तो उसे बनाएं।

```java
File outputDirectory = new File(options.getOutputPath());
if (!outputDirectory.exists()) {
    outputDirectory.mkdirs();
}
```

## चरण 5: प्रस्तुति को HTML के रूप में सहेजें

अब, निर्दिष्ट विकल्पों के साथ प्रस्तुति को HTML5 प्रारूप में सहेजें।

```java
pres.save(options.getOutputPath() + "output.html", SaveFormat.Html5, options);
```

## चरण 6: संसाधनों को साफ करें

किसी भी आवंटित संसाधन को जारी करने के लिए प्रेजेंटेशन ऑब्जेक्ट को हटाना न भूलें।

```java
if (pres != null) {
    pres.dispose();
}
```

## HTML को जावा स्लाइड में एम्बेड करने वाली छवियों में बदलने के लिए पूरा स्रोत कोड

```java
// स्रोत तक पथ प्रस्तुति
String presentationName = RunExamples.getDataDir_Conversion() + "PresentationDemo.pptx";
// HTML दस्तावेज़ का पथ
String outFilePath = RunExamples.getOutPath() + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	//HTML5 दस्तावेज़ में छवियों को बलपूर्वक न सहेजें
	options.setEmbedImages(false);
	// बाह्य छवियों के लिए पथ सेट करें
	options.setOutputPath(outFilePath);
	// आउटपुट HTML दस्तावेज़ के लिए निर्देशिका बनाएँ
	File f = new File(outFilePath);
	if (!f.exists())
		f.mkdir();
	// प्रस्तुति को HTML5 प्रारूप में सहेजें.
	pres.save(outFilePath + "pres.html", SaveFormat.Html5, options);
} finally {
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस व्यापक गाइड में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके छवियों को एम्बेड करते समय PowerPoint प्रस्तुति को HTML दस्तावेज़ में कैसे परिवर्तित किया जाए। चरण-दर-चरण निर्देशों का पालन करके, आप इस कार्यक्षमता को अपने Java अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं और अपने दस्तावेज़ रूपांतरण प्रक्रियाओं को बढ़ा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं आउटपुट फ़ाइल नाम कैसे बदलूं?

 आप आउटपुट फ़ाइल नाम को तर्क में संशोधन करके बदल सकते हैं`pres.save()` तरीका।

### क्या मैं HTML टेम्पलेट को अनुकूलित कर सकता हूँ?

हां, आप Aspose.Slides द्वारा जेनरेट की गई HTML और CSS फ़ाइलों को संशोधित करके HTML टेम्पलेट को कस्टमाइज़ कर सकते हैं। आप उन्हें आउटपुट डायरेक्टरी में पाएंगे।

### मैं रूपांतरण के दौरान त्रुटियों को कैसे संभालूँ?

रूपांतरण प्रक्रिया के दौरान होने वाले अपवादों को संभालने के लिए आप रूपांतरण कोड को try-catch ब्लॉक में लपेट सकते हैं।
