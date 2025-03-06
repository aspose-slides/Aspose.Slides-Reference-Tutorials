---
title: स्लाइड में सादी लाइन जोड़ें
linktitle: स्लाइड में सादी लाइन जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके प्रोग्रामेटिक रूप से PowerPoint स्लाइड में एक सादी लाइन जोड़ना सीखें। इस चरण-दर-चरण मार्गदर्शिका के साथ अपनी उत्पादकता बढ़ाएँ।
weight: 14
url: /hi/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो Java डेवलपर्स को PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है। Aspose.Slides के साथ, आप आसानी से PowerPoint फ़ाइलें बना सकते हैं, संशोधित कर सकते हैं और परिवर्तित कर सकते हैं, जिससे आपका समय और प्रयास बचता है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में स्लाइड में एक सादी रेखा जोड़ने की प्रक्रिया से परिचित कराएँगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है
- Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके Java प्रोजेक्ट में जोड़ी गई
- जावा प्रोग्रामिंग भाषा का बुनियादी ज्ञान

## पैकेज आयात करें
शुरू करने के लिए, आपको अपने जावा कोड में आवश्यक पैकेज आयात करने होंगे। आप यह कैसे कर सकते हैं:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## चरण 1: वातावरण सेट करें
 सबसे पहले, एक नया जावा प्रोजेक्ट बनाएं और अपने प्रोजेक्ट के क्लासपाथ में Aspose.Slides for Java लाइब्रेरी जोड़ें। आप लाइब्रेरी को यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
## चरण 2: एक नई प्रस्तुति बनाएँ
 इसके बाद, उदाहरण बनाएं`Presentation` एक नया पावरपॉइंट प्रेजेंटेशन बनाने के लिए क्लास का उपयोग करें।
```java
Presentation pres = new Presentation();
```
## चरण 3: स्लाइड जोड़ें
प्रस्तुति की पहली स्लाइड प्राप्त करें और उसे एक चर में संग्रहीत करें।
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## चरण 4: एक रेखा आकार जोड़ें
अब, स्लाइड में ऑटोशेप प्रकार की लाइन जोड़ें।
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## चरण 5: प्रस्तुति सहेजें
अंत में, प्रस्तुति को डिस्क पर सहेजें।
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में स्लाइड में सफलतापूर्वक एक प्लेन लाइन जोड़ दी है। Aspose.Slides के साथ, आप आसानी से PowerPoint फ़ाइलों को प्रोग्रामेटिक रूप से मैनिपुलेट कर सकते हैं, जिससे आपके Java अनुप्रयोगों के लिए संभावनाओं की दुनिया खुल जाती है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं रेखा आकार के गुणों को अनुकूलित कर सकता हूँ?
हां, आप Aspose.Slides API का उपयोग करके विभिन्न गुणों जैसे लाइन रंग, चौड़ाई, शैली आदि को अनुकूलित कर सकते हैं।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
हां, Aspose.Slides विभिन्न PowerPoint प्रारूपों का समर्थन करता है, जिसमें PPT, PPTX और अन्य शामिल हैं, जो विभिन्न संस्करणों में संगतता सुनिश्चित करता है।
### क्या Aspose.Slides लाइनों के अलावा अन्य आकृतियाँ जोड़ने के लिए समर्थन प्रदान करता है?
बिल्कुल! Aspose.Slides आकार प्रकारों की एक विस्तृत श्रृंखला प्रदान करता है, जिसमें आयताकार, वृत्त, तीर और बहुत कुछ शामिल है।
### क्या मैं लाइन आकार के साथ स्लाइड में पाठ भी जोड़ सकता हूँ?
हां, आप Aspose.Slides API का उपयोग करके स्लाइड में टेक्स्ट, चित्र और अन्य सामग्री जोड़ सकते हैं।
### क्या Aspose.Slides के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप Aspose.Slides का निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
