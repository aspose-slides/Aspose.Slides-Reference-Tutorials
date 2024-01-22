---
title: जावा स्लाइड्स में टेम्पलेट के रूप में किसी अन्य प्रस्तुति का उपयोग करके प्रस्तुति गुणों को अपडेट करें
linktitle: जावा स्लाइड्स में टेम्पलेट के रूप में किसी अन्य प्रस्तुति का उपयोग करके प्रस्तुति गुणों को अपडेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके अद्यतन मेटाडेटा के साथ PowerPoint प्रस्तुतियों को बढ़ाएं। जावा स्लाइड्स में टेम्प्लेट का उपयोग करके लेखक, शीर्षक और कीवर्ड जैसी संपत्तियों को अपडेट करना सीखें।
type: docs
weight: 14
url: /hi/java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/
---

## जावा स्लाइड्स में टेम्पलेट के रूप में किसी अन्य प्रस्तुति का उपयोग करके प्रस्तुति गुणों को अद्यतन करने का परिचय

इस ट्यूटोरियल में, हम आपको जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों के लिए प्रस्तुति गुणों (मेटाडेटा) को अपडेट करने की प्रक्रिया के बारे में बताएंगे। आप लेखक, शीर्षक, कीवर्ड और अन्य गुणों को अपडेट करने के लिए टेम्पलेट के रूप में किसी अन्य प्रस्तुति का उपयोग कर सकते हैं। हम आपको चरण-दर-चरण निर्देश और स्रोत कोड उदाहरण प्रदान करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी एकीकृत है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: अपना प्रोजेक्ट सेट करें

सुनिश्चित करें कि आपने एक जावा प्रोजेक्ट बनाया है और अपने प्रोजेक्ट की निर्भरता में जावा लाइब्रेरी के लिए Aspose.Slides को जोड़ा है।

## चरण 2: आवश्यक पैकेज आयात करें

प्रस्तुति गुणों के साथ काम करने के लिए आपको आवश्यक Aspose.Slides पैकेज आयात करने की आवश्यकता होगी। अपने जावा क्लास की शुरुआत में निम्नलिखित आयात विवरण शामिल करें:

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## चरण 3: प्रस्तुति गुण अद्यतन करें

अब, टेम्पलेट के रूप में किसी अन्य प्रेजेंटेशन का उपयोग करके प्रेजेंटेशन गुणों को अपडेट करें। इस उदाहरण में, हम एकाधिक प्रस्तुतियों के लिए गुणों को अपडेट करेंगे, लेकिन आप इस कोड को अपने विशिष्ट उपयोग के मामले में अनुकूलित कर सकते हैं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// वह टेम्प्लेट प्रस्तुति लोड करें जिससे आप गुणों की प्रतिलिपि बनाना चाहते हैं
DocumentProperties template;
IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
template = (DocumentProperties) info.readDocumentProperties();

// वे गुण सेट करें जिन्हें आप अद्यतन करना चाहते हैं
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

आइए टेम्पलेट का उपयोग करके व्यक्तिगत प्रस्तुतियों के गुणों को अपडेट करने की एक विधि परिभाषित करें। यह विधि अद्यतन किए जाने वाले प्रेजेंटेशन का पथ और पैरामीटर के रूप में टेम्प्लेट गुणों का उपयोग करेगी।

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // अद्यतन करने के लिए प्रस्तुतिकरण लोड करें
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // टेम्पलेट का उपयोग करके दस्तावेज़ गुणों को अद्यतन करें
    toUpdate.updateDocumentProperties(template);
    
    // अद्यतन प्रस्तुति सहेजें
    toUpdate.writeBindedPresentation(path);
}
```

## जावा स्लाइड्स में टेम्पलेट के रूप में किसी अन्य प्रस्तुति का उपयोग करके अद्यतन प्रस्तुति गुणों के लिए पूर्ण स्रोत कोड

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

इस व्यापक ट्यूटोरियल में, हमने पता लगाया है कि जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में प्रस्तुति गुणों को कैसे अपडेट किया जाए। हमने विशेष रूप से लेखक के नाम, शीर्षक, कीवर्ड और बहुत कुछ जैसे मेटाडेटा को कुशलतापूर्वक अपडेट करने के लिए एक अन्य प्रस्तुति को टेम्पलेट के रूप में उपयोग करने पर ध्यान केंद्रित किया है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं और अधिक प्रस्तुतियों के लिए गुणों को कैसे अद्यतन कर सकता हूँ?

 आप कॉल करके एकाधिक प्रस्तुतियों के लिए गुणों को अपडेट कर सकते हैं`updateByTemplate` वांछित पथ के साथ प्रत्येक प्रस्तुति के लिए विधि।

### क्या मैं इस कोड को विभिन्न संपत्तियों के लिए अनुकूलित कर सकता हूँ?

हाँ, आप अपनी आवश्यकताओं के आधार पर विशिष्ट गुणों को अद्यतन करने के लिए कोड को अनुकूलित कर सकते हैं। बस संशोधित करें`template` वांछित संपत्ति मूल्यों के साथ वस्तु।

### क्या प्रस्तुतियों के प्रकार पर कोई सीमा है जिसे अद्यतन किया जा सकता है?

नहीं, आप पीपीटीएक्स, ओडीपी और पीपीटी सहित विभिन्न प्रारूपों में प्रस्तुतियों के लिए गुणों को अपडेट कर सकते हैं।