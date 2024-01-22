---
title: जावा स्लाइड्स में HTML एम्बेडिंग छवियाँ कनवर्ट करें
linktitle: जावा स्लाइड्स में HTML एम्बेडिंग छवियाँ कनवर्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: एम्बेडेड छवियों के साथ PowerPoint को HTML में कनवर्ट करें। जावा के लिए Aspose.Slides का उपयोग करके चरण-दर-चरण मार्गदर्शिका। जावा में प्रस्तुति रूपांतरणों को सहजता से स्वचालित करना सीखें।
type: docs
weight: 11
url: /hi/java/presentation-conversion/convert-html-embedding-images-java-slides/
---

## जावा स्लाइड्स में HTML एम्बेडिंग छवियों को कनवर्ट करने का परिचय

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको जावा के लिए Aspose.Slides का उपयोग करके छवियों को एम्बेड करते समय एक PowerPoint प्रस्तुति को HTML दस्तावेज़ में परिवर्तित करने की प्रक्रिया के बारे में बताएंगे। यह ट्यूटोरियल मानता है कि आपने पहले ही अपना विकास परिवेश स्थापित कर लिया है और जावा लाइब्रेरी के लिए Aspose.Slides स्थापित कर लिया है।

## आवश्यकताएं

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1.  जावा लाइब्रेरी के लिए Aspose.Slides स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://downloads.aspose.com/slides/java).

2. एक पावरपॉइंट प्रेजेंटेशन फ़ाइल (पीपीटीएक्स प्रारूप) जिसे आप HTML में कनवर्ट करना चाहते हैं।

3. एक जावा विकास वातावरण स्थापित किया गया।

## चरण 1: आवश्यक पुस्तकालय आयात करें

सबसे पहले, आपको अपने जावा प्रोजेक्ट के लिए आवश्यक लाइब्रेरी और कक्षाएं आयात करनी होंगी।

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन लोड करें

 इसके बाद, आप पावरपॉइंट प्रेजेंटेशन लोड करेंगे जिसे आप HTML में कनवर्ट करना चाहते हैं। प्रतिस्थापित करना सुनिश्चित करें`presentationName` आपकी प्रस्तुति फ़ाइल के वास्तविक पथ के साथ।

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## चरण 3: HTML रूपांतरण विकल्प कॉन्फ़िगर करें

अब, आप HTML रूपांतरण विकल्पों को कॉन्फ़िगर करेंगे। इस उदाहरण में, हम HTML दस्तावेज़ में छवियां एम्बेड करेंगे और बाहरी छवियों के लिए आउटपुट निर्देशिका निर्दिष्ट करेंगे।

```java
Html5Options options = new Html5Options();
//HTML5 दस्तावेज़ में छवियों को जबरदस्ती न सहेजें
options.setEmbedImages(true); // छवियाँ एम्बेड करने के लिए सत्य पर सेट करें
// बाहरी छवियों के लिए पथ सेट करें (यदि आवश्यक हो)
options.setOutputPath("path/to/output/directory/");
```

## चरण 4: आउटपुट डायरेक्टरी बनाएं

HTML दस्तावेज़ को सहेजने से पहले, यदि यह मौजूद नहीं है तो आउटपुट निर्देशिका बनाएं।

```java
File outputDirectory = new File(options.getOutputPath());
if (!outputDirectory.exists()) {
    outputDirectory.mkdirs();
}
```

## चरण 5: प्रेजेंटेशन को HTML के रूप में सहेजें

अब, प्रेजेंटेशन को निर्दिष्ट विकल्पों के साथ HTML5 फॉर्मेट में सेव करें।

```java
pres.save(options.getOutputPath() + "output.html", SaveFormat.Html5, options);
```

## चरण 6: संसाधनों को साफ़ करें

किसी भी आवंटित संसाधन को जारी करने के लिए प्रेजेंटेशन ऑब्जेक्ट का निपटान करना न भूलें।

```java
if (pres != null) {
    pres.dispose();
}
```

## जावा स्लाइड्स में HTML एम्बेडिंग छवियों को परिवर्तित करने के लिए पूर्ण स्रोत कोड

```java
// स्रोत प्रस्तुति का पथ
String presentationName = RunExamples.getDataDir_Conversion() + "PresentationDemo.pptx";
// HTML दस्तावेज़ का पथ
String outFilePath = RunExamples.getOutPath() + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	//HTML5 दस्तावेज़ में छवियों को जबरदस्ती न सहेजें
	options.setEmbedImages(false);
	// बाहरी छवियों के लिए पथ सेट करें
	options.setOutputPath(outFilePath);
	// आउटपुट HTML दस्तावेज़ के लिए निर्देशिका बनाएं
	File f = new File(outFilePath);
	if (!f.exists())
		f.mkdir();
	// प्रेजेंटेशन को HTML5 फॉर्मेट में सेव करें।
	pres.save(outFilePath + "pres.html", SaveFormat.Html5, options);
} finally {
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस व्यापक गाइड में, हमने सीखा है कि जावा के लिए Aspose.Slides का उपयोग करके छवियों को एम्बेड करते समय PowerPoint प्रेजेंटेशन को HTML दस्तावेज़ में कैसे परिवर्तित किया जाए। चरण-दर-चरण निर्देशों का पालन करके, आप इस कार्यक्षमता को अपने जावा अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं और अपनी दस्तावेज़ रूपांतरण प्रक्रियाओं को बढ़ा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं आउटपुट फ़ाइल नाम कैसे बदलूं?

 आप तर्क को संशोधित करके आउटपुट फ़ाइल नाम बदल सकते हैं`pres.save()` तरीका।

### क्या मैं HTML टेम्पलेट को अनुकूलित कर सकता हूँ?

हाँ, आप Aspose.Slides द्वारा उत्पन्न HTML और CSS फ़ाइलों को संशोधित करके HTML टेम्पलेट को अनुकूलित कर सकते हैं। आप उन्हें आउटपुट निर्देशिका में पाएंगे।

### मैं रूपांतरण के दौरान त्रुटियों से कैसे निपटूँ?

रूपांतरण प्रक्रिया के दौरान होने वाले अपवादों को संभालने के लिए आप रूपांतरण कोड को ट्राई-कैच ब्लॉक में लपेट सकते हैं।
