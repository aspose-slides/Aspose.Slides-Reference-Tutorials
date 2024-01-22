---
title: जावा स्लाइड्स में प्रेजेंटेशन प्रोटेक्शन की जाँच करें
linktitle: जावा स्लाइड्स में प्रेजेंटेशन प्रोटेक्शन की जाँच करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में प्रस्तुति सुरक्षा की जांच करना सीखें। यह चरण-दर-चरण मार्गदर्शिका लिखने और खुली सुरक्षा जांच के लिए कोड उदाहरण प्रदान करती है।
type: docs
weight: 15
url: /hi/java/presentation-properties/check-presentation-protection-in-java-slides/
---

## जावा स्लाइड्स में प्रेजेंटेशन प्रोटेक्शन की जाँच का परिचय

इस ट्यूटोरियल में, हम देखेंगे कि जावा के लिए Aspose.Slides का उपयोग करके प्रस्तुति सुरक्षा की जांच कैसे करें। हम दो परिदृश्यों को कवर करेंगे: लेखन सुरक्षा की जाँच करना और प्रस्तुति के लिए खुली सुरक्षा की जाँच करना। हम प्रत्येक परिदृश्य के लिए चरण-दर-चरण कोड उदाहरण प्रदान करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Slides सेटअप है। आप इसे Aspose वेबसाइट से डाउनलोड कर सकते हैं और इसे अपने प्रोजेक्ट की निर्भरता में जोड़ सकते हैं।

### मावेन निर्भरता

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 प्रतिस्थापित करें`your_version_here` जावा के लिए Aspose.Slides के जिस संस्करण का आप उपयोग कर रहे हैं।

## चरण 1: लेखन सुरक्षा की जाँच करें

 यह जांचने के लिए कि क्या कोई प्रेजेंटेशन पासवर्ड द्वारा लिखित-सुरक्षित है, आप इसका उपयोग कर सकते हैं`IPresentationInfo` इंटरफेस। ऐसा करने के लिए कोड यहां दिया गया है:

```java
// स्रोत प्रस्तुति के लिए पथ
String pptxFile = "path_to_presentation.pptx";

// IPresentationInfo इंटरफ़ेस के माध्यम से राइट प्रोटेक्शन पासवर्ड की जाँच करें
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 प्रतिस्थापित करें`"path_to_presentation.pptx"` आपकी प्रस्तुति फ़ाइल के वास्तविक पथ के साथ और`"password_here"` लेखन सुरक्षा पासवर्ड के साथ.

## चरण 2: ओपन प्रोटेक्शन की जाँच करें

 यह जाँचने के लिए कि क्या कोई प्रेजेंटेशन खोलने के लिए पासवर्ड से सुरक्षित है, आप इसका उपयोग कर सकते हैं`IPresentationInfo` इंटरफेस। ऐसा करने के लिए कोड यहां दिया गया है:

```java
// स्रोत प्रस्तुति के लिए पथ
String pptFile = "path_to_presentation.ppt";

// IPresentationInfo इंटरफ़ेस के माध्यम से प्रेजेंटेशन ओपन प्रोटेक्शन की जाँच करें
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 प्रतिस्थापित करें`"path_to_presentation.ppt"` आपकी प्रस्तुति फ़ाइल के वास्तविक पथ के साथ।

## जावा स्लाइड्स में चेक प्रेजेंटेशन सुरक्षा के लिए संपूर्ण स्रोत कोड

```java
//स्रोत प्रस्तुति के लिए पथ
String pptxFile = RunExamples.getDataDir_PresentationProperties() + "modify_pass2.pptx";
String pptFile = RunExamples.getDataDir_PresentationProperties() + "open_pass1.ppt";
// IPresentationInfo इंटरफ़ेस के माध्यम से राइट प्रोटेक्शन पासवर्ड की जाँच करें
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// IProtectionManager इंटरफ़ेस के माध्यम से राइट प्रोटेक्शन पासवर्ड की जाँच करें
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
// IPresentationInfo इंटरफ़ेस के माध्यम से प्रेजेंटेशन ओपन प्रोटेक्शन की जाँच करें
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में प्रस्तुति सुरक्षा की जांच कैसे करें। हमने दो परिदृश्यों को कवर किया: लेखन सुरक्षा की जाँच करना और खुली सुरक्षा की जाँच करना। संरक्षित प्रस्तुतियों को प्रभावी ढंग से संभालने के लिए अब आप इन जांचों को अपने जावा अनुप्रयोगों में एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे प्राप्त करूं?

आप जावा के लिए Aspose.Slides को Aspose वेबसाइट से डाउनलोड कर सकते हैं या इसे अपने प्रोजेक्ट में Maven निर्भरता के रूप में जोड़ सकते हैं, जैसा कि आवश्यक शर्तें अनुभाग में दिखाया गया है।

### क्या मैं प्रस्तुतिकरण के लिए लेखन सुरक्षा और खुली सुरक्षा दोनों की जाँच कर सकता हूँ?

हां, आप दिए गए कोड उदाहरणों का उपयोग करके किसी प्रस्तुति के लिए लेखन सुरक्षा और खुली सुरक्षा दोनों की जांच कर सकते हैं।

### यदि मैं सुरक्षा पासवर्ड भूल जाऊं तो मुझे क्या करना चाहिए?

यदि आप किसी प्रेजेंटेशन के लिए सुरक्षा पासवर्ड भूल जाते हैं, तो इसे पुनर्प्राप्त करने का कोई अंतर्निहित तरीका नहीं है। ऐसी स्थितियों से बचने के लिए अपने पासवर्ड का रिकॉर्ड रखना सुनिश्चित करें।

### क्या Java के लिए Aspose.Slides नवीनतम PowerPoint फ़ाइल स्वरूपों के साथ संगत है?

हाँ, Java के लिए Aspose.Slides .pptx फ़ाइलों सहित नवीनतम PowerPoint फ़ाइल स्वरूपों का समर्थन करता है।