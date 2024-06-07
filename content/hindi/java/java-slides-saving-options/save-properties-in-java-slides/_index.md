---
title: जावा स्लाइड्स में गुण सहेजें
linktitle: जावा स्लाइड्स में गुण सहेजें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ अपने PowerPoint प्रेजेंटेशन को ऑप्टिमाइज़ करें। गुण सेट करना, एन्क्रिप्शन अक्षम करना, पासवर्ड सुरक्षा जोड़ना और आसानी से सहेजना सीखें।
type: docs
weight: 12
url: /hi/java/saving-options/save-properties-in-java-slides/
---

## जावा स्लाइड्स में गुण सहेजने का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में प्रॉपर्टीज़ को सहेजने की प्रक्रिया के बारे में बताएँगे। आप सीखेंगे कि डॉक्यूमेंट प्रॉपर्टीज़ को कैसे सेट करें, डॉक्यूमेंट प्रॉपर्टीज़ के लिए एन्क्रिप्शन को कैसे अक्षम करें, अपनी प्रेजेंटेशन को सुरक्षित रखने के लिए पासवर्ड कैसे सेट करें और इसे फ़ाइल में कैसे सेव करें। हम आपको चरण-दर-चरण निर्देश और सोर्स कोड उदाहरण प्रदान करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी आपके Java प्रोजेक्ट में एकीकृत है। आप लाइब्रेरी को Aspose वेबसाइट से डाउनलोड कर सकते हैं[यहाँ](https://downloads.aspose.com/slides/java).

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

आरंभ करने के लिए, आवश्यक कक्षाएं और लाइब्रेरीज़ आयात करें:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## चरण 2: एक प्रेजेंटेशन ऑब्जेक्ट बनाएँ

अपने PowerPoint प्रेजेंटेशन को दर्शाने के लिए प्रेजेंटेशन ऑब्जेक्ट को इंस्टेंटिएट करें। आप या तो एक नया प्रेजेंटेशन बना सकते हैं या मौजूदा प्रेजेंटेशन लोड कर सकते हैं। इस उदाहरण में, हम एक नया प्रेजेंटेशन बनाएंगे।

```java
// उस निर्देशिका का पथ जहाँ आप प्रस्तुति को सहेजना चाहते हैं
String dataDir = "Your Document Directory";

// प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंसिएट करें
Presentation presentation = new Presentation();
```

## चरण 3: दस्तावेज़ गुण सेट करें

आप विभिन्न दस्तावेज़ गुण सेट कर सकते हैं जैसे शीर्षक, लेखक, कीवर्ड, और बहुत कुछ। यहाँ, हम कुछ सामान्य गुण सेट करेंगे:

```java
// प्रस्तुति का शीर्षक निर्धारित करें
presentation.getDocumentProperties().setTitle("My Presentation");

// प्रस्तुति का लेखक निर्धारित करें
presentation.getDocumentProperties().setAuthor("John Doe");

// प्रस्तुति के लिए कीवर्ड सेट करें
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

## चरण 4: दस्तावेज़ गुणों के लिए एन्क्रिप्शन अक्षम करें

डिफ़ॉल्ट रूप से, Aspose.Slides दस्तावेज़ गुणों को एन्क्रिप्ट करता है। यदि आप दस्तावेज़ गुणों के लिए एन्क्रिप्शन अक्षम करना चाहते हैं, तो निम्न कोड का उपयोग करें:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

## चरण 5: प्रस्तुति की सुरक्षा के लिए पासवर्ड सेट करें

 आप अपनी प्रस्तुति तक पहुंच को प्रतिबंधित करने के लिए पासवर्ड से उसे सुरक्षित कर सकते हैं।`encrypt` पासवर्ड सेट करने की विधि:

```java
// प्रस्तुति की सुरक्षा के लिए पासवर्ड सेट करें
presentation.getProtectionManager().encrypt("your_password");
```

 प्रतिस्थापित करें`"your_password"` अपने इच्छित पासवर्ड के साथ.

## चरण 6: प्रेजेंटेशन सहेजें

अंत में, प्रस्तुति को एक फ़ाइल में सहेजें। इस उदाहरण में, हम इसे PPTX फ़ाइल के रूप में सहेजेंगे:

```java
// प्रस्तुति को फ़ाइल में सहेजें
presentation.save(dataDir + "Password_Protected_Presentation_out.pptx", SaveFormat.Pptx);
```

 प्रतिस्थापित करें`"Password_Protected_Presentation_out.pptx"` अपने इच्छित फ़ाइल नाम और पथ के साथ.

## जावा स्लाइड्स में सेव प्रॉपर्टीज़ के लिए पूरा सोर्स कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
//एक प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंसिएट करें जो एक PPT फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation();
try
{
	//....यहाँ कुछ काम करो.....
	// पासवर्ड संरक्षित मोड में दस्तावेज़ गुणों तक पहुंच सेट करना
	presentation.getProtectionManager().setEncryptDocumentProperties(false);
	// पासवर्ड सेट करना
	presentation.getProtectionManager().encrypt("pass");
	// अपनी प्रस्तुति को फ़ाइल में सहेजें
	presentation.save(dataDir + "Password Protected Presentation_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में दस्तावेज़ गुणों को कैसे सहेजा जाए। आप विभिन्न गुण सेट कर सकते हैं, दस्तावेज़ गुणों के लिए एन्क्रिप्शन अक्षम कर सकते हैं, सुरक्षा के लिए पासवर्ड सेट कर सकते हैं, और प्रस्तुति को अपने इच्छित प्रारूप में सहेज सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides में दस्तावेज़ गुण कैसे सेट कर सकता हूँ?

 Aspose.Slides for Java में दस्तावेज़ गुण सेट करने के लिए, आप इसका उपयोग कर सकते हैं`DocumentProperties` क्लास। शीर्षक, लेखक और कीवर्ड जैसे गुण सेट करने का एक उदाहरण यहां दिया गया है:

```java
// प्रस्तुति का शीर्षक निर्धारित करें
presentation.getDocumentProperties().setTitle("My Presentation");

// प्रस्तुति का लेखक निर्धारित करें
presentation.getDocumentProperties().setAuthor("John Doe");

// प्रस्तुति के लिए कीवर्ड सेट करें
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

### दस्तावेज़ गुणों के लिए एन्क्रिप्शन अक्षम करने का उद्देश्य क्या है?

दस्तावेज़ गुणों के लिए एन्क्रिप्शन अक्षम करने से आप दस्तावेज़ मेटाडेटा को एन्क्रिप्शन के बिना संग्रहीत कर सकते हैं। यह तब उपयोगी हो सकता है जब आप चाहते हैं कि दस्तावेज़ गुण (जैसे शीर्षक, लेखक, आदि) पासवर्ड दर्ज किए बिना दृश्यमान और सुलभ हों।

आप निम्नलिखित कोड का उपयोग करके एन्क्रिप्शन को अक्षम कर सकते हैं:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

### मैं Aspose.Slides for Java का उपयोग करके अपने PowerPoint प्रेजेंटेशन को पासवर्ड से कैसे सुरक्षित कर सकता हूँ?

अपने पावरपॉइंट प्रेजेंटेशन को पासवर्ड से सुरक्षित करने के लिए, आप इसका उपयोग कर सकते हैं`encrypt` द्वारा प्रदान की गई विधि`ProtectionManager` पासवर्ड सेट करने का तरीका इस प्रकार है:

```java
// प्रस्तुति की सुरक्षा के लिए पासवर्ड सेट करें
presentation.getProtectionManager().encrypt("your_password");
```

 प्रतिस्थापित करें`"your_password"` अपने इच्छित पासवर्ड के साथ.

### क्या मैं प्रस्तुति को PPTX के अलावा किसी अन्य प्रारूप में सहेज सकता हूँ?

 हां, आप प्रस्तुति को Aspose.Slides for Java द्वारा समर्थित विभिन्न प्रारूपों में सहेज सकते हैं, जैसे कि PPT, PDF, और अधिक। किसी भिन्न प्रारूप में सहेजने के लिए, बदलें`SaveFormat` पैरामीटर में`presentation.save` विधि। उदाहरण के लिए, PDF के रूप में सहेजने के लिए:

```java
presentation.save(dataDir + "Presentation.pdf", SaveFormat.Pdf);
```

### क्या प्रेजेंटेशन ऑब्जेक्ट को सेव करने के बाद उसे हटाना आवश्यक है?

 सिस्टम संसाधनों को रिलीज़ करने के लिए प्रेजेंटेशन ऑब्जेक्ट को हटाना एक अच्छा अभ्यास है। आप इसका उपयोग कर सकते हैं`finally` उचित निपटान सुनिश्चित करने के लिए ब्लॉक का उपयोग करें, जैसा कि कोड उदाहरण में दिखाया गया है:

```java
finally {
    if (presentation != null) presentation.dispose();
}
```

यह आपके अनुप्रयोग में मेमोरी लीक को रोकने में मदद करता है।

### मैं Aspose.Slides for Java और इसकी विशेषताओं के बारे में अधिक कैसे जान सकता हूँ?

 आप Aspose.Slides for Java दस्तावेज़न यहाँ देख सकते हैं[यहाँ](https://docs.aspose.com/slides/java/) लाइब्रेरी के उपयोग के बारे में विस्तृत जानकारी, ट्यूटोरियल और उदाहरण के लिए यहां क्लिक करें।