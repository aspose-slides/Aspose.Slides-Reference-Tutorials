---
title: जावा स्लाइड्स में टेम्पलेट के रूप में किसी अन्य प्रेजेंटेशन का उपयोग करके प्रेजेंटेशन गुण अपडेट करें
linktitle: जावा स्लाइड्स में टेम्पलेट के रूप में किसी अन्य प्रेजेंटेशन का उपयोग करके प्रेजेंटेशन गुण अपडेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Java के लिए Aspose.Slides का उपयोग करके अपडेट किए गए मेटाडेटा के साथ PowerPoint प्रस्तुतियों को बेहतर बनाएँ। Java स्लाइड्स में टेम्प्लेट का उपयोग करके लेखक, शीर्षक और कीवर्ड जैसे गुणों को अपडेट करना सीखें।
weight: 14
url: /hi/java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में टेम्पलेट के रूप में किसी अन्य प्रेजेंटेशन का उपयोग करके प्रेजेंटेशन गुण अपडेट करने का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों के लिए प्रस्तुति गुण (मेटाडेटा) को अपडेट करने की प्रक्रिया से परिचित कराएँगे। आप लेखक, शीर्षक, कीवर्ड और अन्य जैसे गुणों को अपडेट करने के लिए टेम्पलेट के रूप में किसी अन्य प्रस्तुति का उपयोग कर सकते हैं। हम आपको चरण-दर-चरण निर्देश और स्रोत कोड उदाहरण प्रदान करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी आपके Java प्रोजेक्ट में एकीकृत है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: अपना प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपने एक Java प्रोजेक्ट बनाया है और अपने प्रोजेक्ट की निर्भरताओं में Aspose.Slides for Java लाइब्रेरी को जोड़ा है।

## चरण 2: आवश्यक पैकेज आयात करें

आपको प्रेजेंटेशन प्रॉपर्टीज़ के साथ काम करने के लिए आवश्यक Aspose.Slides पैकेज आयात करने की आवश्यकता होगी। अपने जावा क्लास की शुरुआत में निम्नलिखित आयात कथन शामिल करें:

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## चरण 3: प्रस्तुति गुण अपडेट करें

अब, आइए टेम्पलेट के रूप में किसी अन्य प्रस्तुति का उपयोग करके प्रस्तुति गुणों को अपडेट करें। इस उदाहरण में, हम कई प्रस्तुतियों के लिए गुणों को अपडेट करेंगे, लेकिन आप इस कोड को अपने विशिष्ट उपयोग के मामले में अनुकूलित कर सकते हैं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// वह टेम्पलेट प्रस्तुति लोड करें जिससे आप गुण कॉपी करना चाहते हैं
DocumentProperties template;
IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
template = (DocumentProperties) info.readDocumentProperties();

// वे गुण सेट करें जिन्हें आप अपडेट करना चाहते हैं
template.setAuthor("Template Author");
template.setTitle("Template Title");
template.setCategory("Template Category");
template.setKeywords("Keyword1, Keyword2, Keyword3");
template.setCompany("Our Company");
template.setComments("Created from template");
template.setContentType("Template Content");
template.setSubject("Template Subject");

// एक ही टेम्पलेट का उपयोग करके एकाधिक प्रस्तुतियाँ अपडेट करें
updateByTemplate(dataDir + "doc1.pptx", template);
updateByTemplate(dataDir + "doc2.odp", template);
updateByTemplate(dataDir + "doc3.ppt", template);
```

##  चरण 4: परिभाषित करें`updateByTemplate` Method

आइए टेम्पलेट का उपयोग करके अलग-अलग प्रस्तुतियों के गुणों को अपडेट करने के लिए एक विधि परिभाषित करें। यह विधि अपडेट की जाने वाली प्रस्तुति का पथ और टेम्पलेट गुणों को पैरामीटर के रूप में लेगी।

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // अद्यतन करने के लिए प्रस्तुति लोड करें
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // टेम्पलेट का उपयोग करके दस्तावेज़ गुण अपडेट करें
    toUpdate.updateDocumentProperties(template);
    
    // अद्यतन प्रस्तुति सहेजें
    toUpdate.writeBindedPresentation(path);
}
```

## जावा स्लाइड्स में टेम्पलेट के रूप में किसी अन्य प्रेजेंटेशन का उपयोग करके प्रेजेंटेशन गुणों को अपडेट करने के लिए पूरा स्रोत कोड

```java
	// दस्तावेज़ निर्देशिका का पथ.
	String dataDir = "Your Document Directory";
	DocumentProperties template;
	IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
	template = (DocumentProperties) info.readDocumentProperties();
	template.setAuthor("Template Author");
	template.setTitle("Template Title");
	template.setCategory("Template Category");
	template.setKeywords("Keyword1, Keyword2, Keyword3");
	template.setCompany("Our Company");
	template.setComments("Created from template");
	template.setContentType("Template Content");
	template.setSubject("Template Subject");
	updateByTemplate(dataDir + "doc1.pptx", template);
	updateByTemplate(dataDir + "doc2.odp", template);
	updateByTemplate(dataDir + "doc3.ppt", template);
}
private static void updateByTemplate(String path, IDocumentProperties template)
{
	IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
	toUpdate.updateDocumentProperties(template);
	toUpdate.writeBindedPresentation(path);
```

## निष्कर्ष

इस व्यापक ट्यूटोरियल में, हमने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में प्रस्तुति गुणों को अपडेट करने का तरीका खोजा है। हमने विशेष रूप से लेखक के नाम, शीर्षक, कीवर्ड और अधिक जैसे मेटाडेटा को कुशलतापूर्वक अपडेट करने के लिए टेम्पलेट के रूप में किसी अन्य प्रस्तुति का उपयोग करने पर ध्यान केंद्रित किया।

## अक्सर पूछे जाने वाले प्रश्न

### मैं अधिक प्रस्तुतियों के लिए गुण कैसे अपडेट कर सकता हूं?

 आप कॉल करके एकाधिक प्रस्तुतियों के लिए गुण अपडेट कर सकते हैं`updateByTemplate` प्रत्येक प्रस्तुति के लिए वांछित पथ के साथ विधि।

### क्या मैं इस कोड को विभिन्न गुणों के लिए अनुकूलित कर सकता हूँ?

हां, आप अपनी आवश्यकताओं के आधार पर विशिष्ट गुणों को अपडेट करने के लिए कोड को कस्टमाइज़ कर सकते हैं। बस संशोधित करें`template` वांछित संपत्ति मूल्यों के साथ ऑब्जेक्ट.

### क्या अद्यतन किये जा सकने वाले प्रस्तुतीकरणों के प्रकार पर कोई सीमा है?

नहीं, आप PPTX, ODP और PPT सहित विभिन्न प्रारूपों में प्रस्तुतियों के लिए गुणधर्मों को अद्यतन कर सकते हैं।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
