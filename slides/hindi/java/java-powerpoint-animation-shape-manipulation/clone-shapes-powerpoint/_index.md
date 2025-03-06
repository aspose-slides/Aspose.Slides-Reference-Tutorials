---
title: पावरपॉइंट में आकृतियाँ क्लोन करें
linktitle: पावरपॉइंट में आकृतियाँ क्लोन करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में आकृतियों को क्लोन करना सीखें। इस आसान-से-अनुसरण ट्यूटोरियल के साथ अपने वर्कफ़्लो को सुव्यवस्थित करें।
weight: 16
url: /hi/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# पावरपॉइंट में आकृतियाँ क्लोन करें

## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में आकृतियों को कैसे क्लोन किया जाए। आकृतियों को क्लोन करने से आप किसी प्रस्तुति में मौजूदा आकृतियों को डुप्लिकेट कर सकते हैं, जो स्लाइड में सुसंगत लेआउट या दोहराए जाने वाले तत्वों को बनाने के लिए विशेष रूप से उपयोगी हो सकता है।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट स्थापित है। आप नवीनतम संस्करण को डाउनलोड करके इंस्टॉल कर सकते हैं।[वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java लाइब्रेरी: अपने Java प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी डाउनलोड करें और शामिल करें। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
आरंभ करने के लिए, आपको अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करने होंगे। ये पैकेज Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों के साथ काम करने के लिए आवश्यक कार्यक्षमताएँ प्रदान करते हैं।
```java
import com.aspose.slides.*;

```
## चरण 1: प्रस्तुति लोड करें
 सबसे पहले, आपको उन आकृतियों वाली पावरपॉइंट प्रस्तुति को लोड करना होगा जिन्हें आप क्लोन करना चाहते हैं।`Presentation` स्रोत प्रस्तुति को लोड करने के लिए क्लास का उपयोग करें।
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## चरण 2: आकृतियों का क्लोन बनाएं
इसके बाद, आप स्रोत प्रस्तुति से आकृतियों को क्लोन करेंगे और उन्हें उसी प्रस्तुति में एक नई स्लाइड में जोड़ेंगे। इसमें स्रोत आकृतियों तक पहुँचना, एक नई स्लाइड बनाना और फिर क्लोन की गई आकृतियों को नई स्लाइड में जोड़ना शामिल है।
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## चरण 3: प्रस्तुति सहेजें
अंत में, क्लोन आकृतियों के साथ संशोधित प्रस्तुति को एक नई फ़ाइल में सहेजें।
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में आकृतियों को क्लोन करना एक सरल प्रक्रिया है जो आपके प्रस्तुति निर्माण वर्कफ़्लो को सुव्यवस्थित करने में मदद कर सकती है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप आसानी से मौजूदा आकृतियों की नकल कर सकते हैं और उन्हें आवश्यकतानुसार अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं विभिन्न स्लाइडों में आकृतियों का क्लोन बना सकता हूँ?
हां, आप प्रस्तुति में किसी भी स्लाइड से आकृतियों को क्लोन कर सकते हैं और उन्हें Aspose.Slides for Java का उपयोग करके किसी अन्य स्लाइड में जोड़ सकते हैं।
### क्या आकृतियों की क्लोनिंग की कोई सीमाएं हैं?
यद्यपि Aspose.Slides for Java मजबूत क्लोनिंग क्षमताएं प्रदान करता है, फिर भी जटिल आकृतियों या एनिमेशन को पूरी तरह से दोहराया नहीं जा सकता है।
### क्या मैं क्लोन आकृतियों को स्लाइड में जोड़ने के बाद उन्हें संशोधित कर सकता हूँ?
बिल्कुल, एक बार जब आकृतियों को क्लोन कर लिया जाता है और स्लाइड में जोड़ दिया जाता है, तो आप आवश्यकतानुसार उनके गुणों, स्टाइलिंग और सामग्री को संशोधित कर सकते हैं।
### क्या Java के लिए Aspose.Slides आकृतियों के अलावा अन्य तत्वों की क्लोनिंग का समर्थन करता है?
हां, आप Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुति के भीतर स्लाइड, पाठ, चित्र और अन्य तत्वों को क्लोन कर सकते हैं।
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप जावा के लिए Aspose.Slides का एक निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
