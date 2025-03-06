---
title: जावा स्लाइड्स में XPS विकल्प के बिना कनवर्ट करें
linktitle: जावा स्लाइड्स में XPS विकल्प के बिना कनवर्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों को XPS प्रारूप में परिवर्तित करना सीखें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 33
url: /hi/java/presentation-conversion/convert-without-xps-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## परिचय Aspose.Slides for Java में XPS विकल्पों के बिना PowerPoint को XPS में बदलें

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके किसी PowerPoint प्रेजेंटेशन को XPS (XML पेपर स्पेसिफिकेशन) दस्तावेज़ में बदलने की प्रक्रिया के बारे में बताएंगे, बिना किसी XPS विकल्प को निर्दिष्ट किए। हम आपको इस कार्य को पूरा करने के लिए चरण-दर-चरण निर्देश और Java स्रोत कोड प्रदान करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1.  Aspose.Slides for Java: सुनिश्चित करें कि आपके पास अपने Java प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित और कॉन्फ़िगर है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Slides for Java वेबसाइट](https://downloads.aspose.com/slides/java).

2. जावा डेवलपमेंट एनवायरनमेंट: आपके कंप्यूटर पर जावा डेवलपमेंट एनवायरनमेंट स्थापित होना चाहिए।

## चरण 1: Java के लिए Aspose.Slides आयात करें

अपने जावा प्रोजेक्ट में, अपनी जावा फ़ाइल की शुरुआत में आवश्यक Aspose.Slides for Java क्लासेस आयात करें:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन लोड करें

अब, हम उस PowerPoint प्रेजेंटेशन को लोड करेंगे जिसे आप XPS में बदलना चाहते हैं।`"Your Document Directory"` अपनी पावरपॉइंट प्रस्तुति फ़ाइल के वास्तविक पथ के साथ:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

 सुनिश्चित करें कि आप प्रतिस्थापित करें`"Convert_XPS.pptx"` अपनी पावरपॉइंट फ़ाइल के वास्तविक नाम के साथ.

## चरण 3: XPS विकल्प के बिना XPS के रूप में सहेजें

Aspose.Slides for Java के साथ, आप लोड की गई प्रस्तुति को XPS दस्तावेज़ के रूप में आसानी से सहेज सकते हैं, बिना किसी XPS विकल्प को निर्दिष्ट किए। यहाँ बताया गया है कि आप यह कैसे कर सकते हैं:

```java
try {
    // प्रस्तुति को XPS दस्तावेज़ में सहेजना
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

 यह कोड ब्लॉक प्रस्तुति को XPS दस्तावेज़ के रूप में नाम से सहेजता है`"XPS_Output_Without_XPSOption_out.xps"`आप आवश्यकतानुसार आउटपुट फ़ाइल का नाम बदल सकते हैं।

## जावा स्लाइड्स में XPS विकल्प के बिना कन्वर्ट करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	// प्रस्तुति को XPS दस्तावेज़ में सहेजना
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

 इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Slides for Java का उपयोग करके किसी भी XPS विकल्प को निर्दिष्ट किए बिना PowerPoint प्रस्तुति को XPS दस्तावेज़ में कैसे परिवर्तित किया जाए। आप Aspose.Slides for Java द्वारा प्रदान किए गए विकल्पों की खोज करके रूपांतरण प्रक्रिया को और अधिक अनुकूलित कर सकते हैं। अधिक उन्नत सुविधाओं और गहन दस्तावेज़ीकरण के लिए, यहाँ जाएँ[Aspose.Slides for Java दस्तावेज़](https://docs.aspose.com/slides/java/).

## अक्सर पूछे जाने वाले प्रश्न

### रूपांतरण करते समय मैं XPS विकल्प कैसे निर्दिष्ट करूँ?

 पावरपॉइंट प्रेजेंटेशन को परिवर्तित करते समय XPS विकल्प निर्दिष्ट करने के लिए, आप इसका उपयोग कर सकते हैं`XpsOptions` क्लास और इमेज कम्प्रेशन और फॉन्ट एम्बेडिंग जैसे विभिन्न गुण सेट करें। यदि आपके पास XPS रूपांतरण के लिए विशिष्ट आवश्यकताएँ हैं, तो देखें[Aspose.Slides for Java दस्तावेज़](https://docs.aspose.com/slides/java/) अधिक जानकारी के लिए।

### क्या अन्य प्रारूपों में सहेजने के लिए कोई अतिरिक्त विकल्प हैं?

 हां, Aspose.Slides for Java XPS के अलावा विभिन्न आउटपुट फॉर्मेट प्रदान करता है, जैसे PDF, TIFF और HTML। आप वांछित आउटपुट फॉर्मेट को बदलकर निर्दिष्ट कर सकते हैं`SaveFormat` कॉल करते समय पैरामीटर`save` विधि। समर्थित प्रारूपों की पूरी सूची के लिए दस्तावेज़ देखें।

### मैं रूपांतरण प्रक्रिया के दौरान अपवादों को कैसे संभाल सकता हूँ?

 आप रूपांतरण प्रक्रिया के दौरान होने वाली किसी भी त्रुटि को सुचारू रूप से संभालने के लिए अपवाद हैंडलिंग को लागू कर सकते हैं। जैसा कि कोड में दिखाया गया है,`try` और`finally` ब्लॉक का उपयोग उचित संसाधन निपटान सुनिश्चित करने के लिए किया जाता है, भले ही कोई अपवाद उत्पन्न हो।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
