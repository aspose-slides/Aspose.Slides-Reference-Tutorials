---
title: जावा के साथ पावरपॉइंट में स्मार्टआर्ट लेआउट बदलें
linktitle: जावा के साथ पावरपॉइंट में स्मार्टआर्ट लेआउट बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ Java का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt लेआउट में परिवर्तन करना सीखें।
weight: 19
url: /hi/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, हम जावा का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt लेआउट में हेरफेर करने का तरीका जानेंगे। SmartArt PowerPoint में एक शक्तिशाली सुविधा है जो उपयोगकर्ताओं को विभिन्न उद्देश्यों के लिए आकर्षक ग्राफिक्स बनाने की अनुमति देती है, जैसे कि प्रक्रियाओं, पदानुक्रमों, संबंधों और बहुत कुछ को चित्रित करना।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा डेवलपमेंट एनवायरनमेंट: सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2.  Aspose.Slides लाइब्रेरी: Aspose.Slides for Java लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/slides/java/).
3. जावा की बुनियादी समझ: जावा प्रोग्रामिंग भाषा के मूल सिद्धांतों से परिचित होना सहायक होगा।
4. एकीकृत विकास वातावरण (IDE): अपनी पसंद का IDE चुनें, जैसे कि Eclipse या IntelliJ IDEA.

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## चरण 1: अपना जावा प्रोजेक्ट वातावरण सेट करें
सुनिश्चित करें कि आपका जावा प्रोजेक्ट आपके चुने हुए IDE में ठीक से सेट अप है। एक नया जावा प्रोजेक्ट बनाएँ और अपने प्रोजेक्ट की निर्भरता में Aspose.Slides लाइब्रेरी शामिल करें।
## चरण 2: एक नई प्रस्तुति बनाएँ
एक नया PowerPoint प्रस्तुतिकरण बनाने के लिए एक नया प्रस्तुतिकरण ऑब्जेक्ट इंस्टैंशिएट करें।
```java
Presentation presentation = new Presentation();
```
## चरण 3: स्मार्टआर्ट ग्राफ़िक जोड़ें
अपनी प्रस्तुति में स्मार्टआर्ट ग्राफ़िक जोड़ें। स्लाइड पर स्मार्टआर्ट ग्राफ़िक की स्थिति और आयाम निर्दिष्ट करें।
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## चरण 4: स्मार्टआर्ट लेआउट बदलें
स्मार्टआर्ट ग्राफ़िक के लेआउट को अपने इच्छित लेआउट प्रकार में बदलें।
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## चरण 5: प्रस्तुति सहेजें
संशोधित प्रस्तुति को अपने सिस्टम पर निर्दिष्ट निर्देशिका में सहेजें।
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
जावा का उपयोग करके पावरपॉइंट प्रेजेंटेशन में स्मार्टआर्ट लेआउट में हेरफेर करना Aspose.Slides for Java के साथ एक सीधी प्रक्रिया है। इस ट्यूटोरियल का पालन करके, आप अपनी प्रेजेंटेशन आवश्यकताओं के अनुरूप स्मार्टआर्ट ग्राफ़िक्स को आसानी से संशोधित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides for Java का उपयोग करके स्मार्टआर्ट ग्राफिक्स के स्वरूप को अनुकूलित कर सकता हूँ?
हां, आप स्मार्टआर्ट ग्राफिक्स के विभिन्न पहलुओं, जैसे रंग, शैली और प्रभाव को अनुकूलित कर सकते हैं।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
Aspose.Slides, PowerPoint के विभिन्न संस्करणों में निर्मित PowerPoint प्रस्तुतियों का समर्थन करता है, तथा विभिन्न प्लेटफार्मों पर संगतता सुनिश्चित करता है।
### क्या Aspose.Slides अन्य प्रोग्रामिंग भाषाओं के लिए समर्थन प्रदान करता है?
हां, Aspose.Slides .NET, Python और JavaScript सहित कई प्रोग्रामिंग भाषाओं के लिए उपलब्ध है।
### क्या मैं Aspose.Slides का उपयोग करके स्क्रैच से स्मार्टआर्ट ग्राफिक्स बना सकता हूँ?
बिल्कुल, आप प्रोग्रामेटिक रूप से स्मार्टआर्ट ग्राफिक्स बना सकते हैं या अपनी आवश्यकताओं के अनुरूप मौजूदा ग्राफिक्स को संशोधित कर सकते हैं।
### क्या कोई सामुदायिक मंच है जहां मैं Aspose.Slides के संबंध में सहायता मांग सकता हूं?
 हां, आप Aspose.Slides फोरम पर जा सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11) प्रश्न पूछने और समुदाय के साथ जुड़ने के लिए।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
