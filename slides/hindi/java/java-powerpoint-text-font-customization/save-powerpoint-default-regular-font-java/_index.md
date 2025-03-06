---
title: जावा का उपयोग करके पावरपॉइंट को डिफ़ॉल्ट नियमित फ़ॉन्ट के साथ सहेजें
linktitle: जावा का उपयोग करके पावरपॉइंट को डिफ़ॉल्ट नियमित फ़ॉन्ट के साथ सहेजें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से मैनिपुलेट करना सीखें। चरण-दर-चरण ट्यूटोरियल के साथ Java PowerPoint हैंडलिंग में महारत हासिल करें।
type: docs
weight: 12
url: /hi/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---
## परिचय
जावा विकास के क्षेत्र में, प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाना और उनमें हेरफेर करना उत्पादकता और अनुकूलन विकल्पों को बहुत बढ़ा सकता है। Aspose.Slides for Java एक मजबूत लाइब्रेरी है जो डेवलपर्स को पावरपॉइंट फ़ाइलों को कुशलतापूर्वक संभालने में सक्षम बनाती है, जो सरल संशोधनों से लेकर जटिल प्रस्तुतियों तक की सुविधाओं का एक व्यापक सेट प्रदान करती है।
## आवश्यक शर्तें
Java के लिए Aspose.Slides का उपयोग करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ सेट अप हैं:
1. जावा डेवलपमेंट किट (JDK): Aspose.Slides for Java को सही ढंग से कार्य करने के लिए JDK 1.8 या उससे ऊपर के संस्करण की आवश्यकता होती है।
2. Aspose.Slides for Java JAR: Aspose.Slides for Java का नवीनतम संस्करण यहाँ से डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): IntelliJ IDEA, Eclipse, या अपनी पसंद का कोई अन्य Java IDE उपयोग करें।
4. जावा की बुनियादी समझ: जावा प्रोग्रामिंग भाषा के मूल सिद्धांतों से परिचित होना आवश्यक है।

## पैकेज आयात करें
Java के लिए Aspose.Slides का उपयोग शुरू करने के लिए, आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
यह सुनिश्चित करता है कि आपके पास Java के लिए Aspose.Slides द्वारा प्रदान की गई सभी कक्षाओं और विधियों तक पहुंच है।
## चरण 1: अपना प्रोजेक्ट सेट करें
सबसे पहले, अपने IDE में एक नया Java प्रोजेक्ट बनाएं और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides for Java JAR फ़ाइल शामिल करें।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
 एक उदाहरण बनाना`Presentation` अपनी स्थानीय निर्देशिका से एक मौजूदा पावरपॉइंट फ़ाइल (.pptx) लोड करके ऑब्जेक्ट को खोलें।
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// प्रस्तुति लोड करें
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 प्रतिस्थापित करें`"Your Document Directory"` और`"Your Output Directory"` अपने वास्तविक फ़ाइल पथ के साथ.
## चरण 3: प्रस्तुति को डिफ़ॉल्ट नियमित फ़ॉन्ट के साथ सहेजें
 आउटपुट प्रारूपों (HTML और PDF) के लिए डिफ़ॉल्ट नियमित फ़ॉन्ट निर्दिष्ट करें`HtmlOptions` और`PdfOptions` क्रमश।
```java
try {
    // HTML सेव विकल्प
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // पीडीएफ सेव विकल्प
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 प्रतिस्थापन सुनिश्चित करें`"Arial Black"` और`"Lucida Console"` अपने इच्छित डिफ़ॉल्ट नियमित फ़ॉन्ट्स के साथ।

## निष्कर्ष
इन चरणों का पालन करके, आपने सीखा है कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों को प्रभावी ढंग से कैसे मैनिपुलेट किया जाए। यह क्षमता आपको कार्यों को स्वचालित करने, प्रस्तुतियों को अनुकूलित करने और उन्नत PowerPoint हैंडलिंग कार्यक्षमताओं के साथ अपने Java अनुप्रयोगों को बढ़ाने की अनुमति देती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Slides for Java JDK के पुराने संस्करणों के साथ काम कर सकता है?
Java के लिए Aspose.Slides को अनुकूलता के लिए JDK 1.8 या उससे ऊपर के संस्करण की आवश्यकता है।
### मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides for Java पर अधिक विस्तृत दस्तावेज़ कहां पा सकता हूं?
 विस्तृत दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/slides/java/).
### क्या Aspose.Slides for Java के लिए सामुदायिक समर्थन उपलब्ध है?
 हां, आप सामुदायिक सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
### क्या मैं Java के लिए Aspose.Slides निःशुल्क आज़मा सकता हूँ?
 हां, निःशुल्क परीक्षण संस्करण डाउनलोड करें[यहाँ](https://releases.aspose.com/).