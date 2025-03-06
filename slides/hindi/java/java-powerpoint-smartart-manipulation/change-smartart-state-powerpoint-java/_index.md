---
title: जावा के साथ PowerPoint में स्मार्टआर्ट स्थिति बदलें
linktitle: जावा के साथ PowerPoint में स्मार्टआर्ट स्थिति बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा और Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt की स्थिति को बदलना सीखें। अपनी प्रस्तुति स्वचालन कौशल को बढ़ाएँ।
weight: 21
url: /hi/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा के साथ PowerPoint में स्मार्टआर्ट स्थिति बदलें

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Slides लाइब्रेरी के साथ Java का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt ऑब्जेक्ट्स को कैसे मैनिपुलेट किया जाए। SmartArt PowerPoint में एक शक्तिशाली सुविधा है जो आपको आकर्षक आरेख और ग्राफ़िक्स बनाने की अनुमति देती है।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर जावा इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं।[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[वेबसाइट](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
अपने जावा प्रोजेक्ट में Aspose.Slides के साथ काम करना शुरू करने के लिए, आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
अब आइए दिए गए उदाहरण कोड को कई चरणों में विभाजित करें:
## चरण 1: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
```java
Presentation presentation = new Presentation();
```
 यहाँ, हम एक नया निर्माण करते हैं`Presentation` ऑब्जेक्ट, जो एक पावरपॉइंट प्रस्तुति का प्रतिनिधित्व करता है।
## चरण 2: स्मार्टआर्ट ऑब्जेक्ट जोड़ें
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
 यह चरण प्रस्तुति की पहली स्लाइड में एक स्मार्टआर्ट ऑब्जेक्ट जोड़ता है। हम स्मार्टआर्ट ऑब्जेक्ट की स्थिति और आयाम, साथ ही लेआउट प्रकार (इस मामले में,) निर्दिष्ट करते हैं।`BasicProcess`).
## चरण 3: स्मार्टआर्ट स्थिति सेट करें
```java
smart.setReversed(true);
```
यहाँ, हम SmartArt ऑब्जेक्ट की स्थिति निर्धारित करते हैं। इस उदाहरण में, हम SmartArt की दिशा को उलट रहे हैं।
## चरण 4: स्मार्टआर्ट स्थिति की जाँच करें
```java
boolean flag = smart.isReversed();
```
 हम स्मार्टआर्ट ऑब्जेक्ट की वर्तमान स्थिति भी जाँच सकते हैं। यह लाइन यह पता लगाती है कि स्मार्टआर्ट उल्टा है या नहीं और इसे स्टोर करती है`flag` चर।
## चरण 5: प्रस्तुति सहेजें
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
अंत में, हम संशोधित प्रस्तुति को डिस्क पर निर्दिष्ट स्थान पर सहेज लेते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि जावा और Aspose.Slides लाइब्रेरी का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt ऑब्जेक्ट की स्थिति कैसे बदलें। इस ज्ञान के साथ, आप प्रोग्रामेटिक रूप से गतिशील और आकर्षक प्रस्तुतियाँ बना सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Java के लिए Aspose.Slides का उपयोग करके SmartArt के अन्य गुणों को संशोधित कर सकता हूँ?
हां, आप Aspose.Slides का उपयोग करके SmartArt ऑब्जेक्ट्स के विभिन्न पहलुओं, जैसे रंग, शैली और लेआउट को संशोधित कर सकते हैं।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
हां, Aspose.Slides विभिन्न संस्करणों में पावरपॉइंट प्रस्तुतियों का समर्थन करता है, जिससे संगतता और निर्बाध एकीकरण सुनिश्चित होता है।
### क्या मैं Aspose.Slides के साथ कस्टम स्मार्टआर्ट लेआउट बना सकता हूँ?
बिल्कुल! Aspose.Slides आपकी विशिष्ट आवश्यकताओं के अनुरूप कस्टम स्मार्टआर्ट लेआउट बनाने के लिए API प्रदान करता है।
### क्या Aspose.Slides PowerPoint के अलावा अन्य फ़ाइल स्वरूपों के लिए समर्थन प्रदान करता है?
हां, Aspose.Slides फ़ाइल स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है, जिसमें PPTX, PPT, PDF, और बहुत कुछ शामिल है।
### क्या कोई सामुदायिक मंच है जहां मैं Aspose.Slides से संबंधित प्रश्नों में सहायता प्राप्त कर सकता हूं?
 हां, आप Aspose.Slides फोरम पर जा सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11) सहायता और चर्चा के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
