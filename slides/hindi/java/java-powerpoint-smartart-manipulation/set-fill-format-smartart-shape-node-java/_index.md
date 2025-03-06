---
title: जावा में स्मार्टआर्ट आकार नोड के लिए भरण प्रारूप सेट करें
linktitle: जावा में स्मार्टआर्ट आकार नोड के लिए भरण प्रारूप सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java में SmartArt शेप नोड्स के लिए भरण प्रारूप सेट करना सीखें। जीवंत रंगों और आकर्षक दृश्यों के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।
weight: 12
url: /hi/java/java-powerpoint-smartart-manipulation/set-fill-format-smartart-shape-node-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
डिजिटल सामग्री निर्माण के गतिशील परिदृश्य में, Aspose.Slides for Java आसानी और दक्षता के साथ नेत्रहीन आश्चर्यजनक प्रस्तुतियाँ तैयार करने के लिए एक शक्तिशाली उपकरण के रूप में सामने आता है। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, स्लाइड्स के भीतर आकृतियों में हेरफेर करने की कला में महारत हासिल करना आकर्षक प्रस्तुतियाँ बनाने के लिए महत्वपूर्ण है जो आपके दर्शकों पर एक स्थायी छाप छोड़ती हैं।
## आवश्यक शर्तें
Aspose.Slides का उपयोग करके जावा में स्मार्टआर्ट आकार नोड्स के लिए भरण प्रारूप सेट करने की दुनिया में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर जावा इंस्टॉल है। आप Oracle से JDK का नवीनतम संस्करण डाउनलोड और इंस्टॉल कर सकते हैं[वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java लाइब्रेरी: Aspose वेबसाइट से Aspose.Slides for Java लाइब्रेरी प्राप्त करें। आप इसे ट्यूटोरियल में दिए गए लिंक से डाउनलोड कर सकते हैं[लिंक को डाउनलोड करें](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): जावा विकास के लिए अपना पसंदीदा IDE चुनें। लोकप्रिय विकल्पों में IntelliJ IDEA, Eclipse और NetBeans शामिल हैं।

## पैकेज आयात करें
इस ट्यूटोरियल में, हम SmartArt आकृतियों और उनके नोड्स में हेरफेर करने के लिए Aspose.Slides लाइब्रेरी से कई पैकेजों का उपयोग करेंगे। शुरू करने से पहले, आइए इन पैकेजों को अपने जावा प्रोजेक्ट में आयात करें:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: एक प्रेजेंटेशन ऑब्जेक्ट बनाएँ
स्लाइडों के साथ काम करना शुरू करने के लिए एक प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें:
```java
Presentation presentation = new Presentation();
```
## चरण 2: स्लाइड तक पहुंचें
वह स्लाइड पुनः प्राप्त करें जहां आप स्मार्टआर्ट आकार जोड़ना चाहते हैं:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 3: स्मार्टआर्ट आकार और नोड्स जोड़ें
स्लाइड में स्मार्टआर्ट आकृति जोड़ें और उसमें नोड्स डालें:
```java
ISmartArt chevron = slide.getShapes().addSmartArt(10, 10, 800, 60, SmartArtLayoutType.ClosedChevronProcess);
ISmartArtNode node = chevron.getAllNodes().addNode();
node.getTextFrame().setText("Some text");
```
## चरण 4: नोड भरण रंग सेट करें
स्मार्टआर्ट नोड के भीतर प्रत्येक आकृति के लिए भरण रंग सेट करें:
```java
for (ISmartArtShape item : node.getShapes()) {
    item.getFillFormat().setFillType(FillType.Solid);
    item.getFillFormat().getSolidFillColor().setColor(Color.RED);
}
```
## चरण 5: प्रस्तुति सहेजें
सभी संशोधन करने के बाद प्रस्तुति को सहेजें:
```java
presentation.save(dataDir + "FillFormat_SmartArt_ShapeNode_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
Aspose.Slides का उपयोग करके जावा में स्मार्टआर्ट शेप नोड्स के लिए फिल फ़ॉर्मेट सेट करने की कला में महारत हासिल करने से आप अपने दर्शकों के साथ प्रतिध्वनित होने वाले आकर्षक प्रस्तुतिकरण बनाने में सक्षम हो जाते हैं। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और Aspose.Slides की शक्तिशाली सुविधाओं का लाभ उठाकर, आप आकर्षक प्रस्तुतिकरण तैयार करने की अनंत संभावनाओं को अनलॉक कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अन्य Java लाइब्रेरीज़ के साथ Aspose.Slides for Java का उपयोग कर सकता हूँ?
हां, Aspose.Slides for Java को आपकी प्रस्तुति निर्माण प्रक्रिया को बढ़ाने के लिए अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत किया जा सकता है।
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
हां, आप ट्यूटोरियल में दिए गए लिंक से Java के लिए Aspose.Slides का निःशुल्क परीक्षण प्राप्त कर सकते हैं।
### मैं Aspose.Slides for Java के लिए समर्थन कहां पा सकता हूं?
आप Aspose वेबसाइट पर फ़ोरम और दस्तावेज़ सहित व्यापक समर्थन संसाधन पा सकते हैं।
### क्या मैं स्मार्टआर्ट आकृतियों के स्वरूप को और अधिक अनुकूलित कर सकता हूँ?
बिल्कुल! Aspose.Slides for Java आपके पसंद के अनुसार स्मार्टआर्ट आकृतियों के स्वरूप को अनुकूलित करने के लिए अनुकूलन विकल्पों की एक विस्तृत श्रृंखला प्रदान करता है।
### क्या Aspose.Slides for Java शुरुआती और अनुभवी डेवलपर्स दोनों के लिए उपयुक्त है?
हां, Aspose.Slides for Java सभी कौशल स्तरों के डेवलपर्स की जरूरतों को पूरा करता है, तथा आसान एकीकरण और उपयोग की सुविधा के लिए सहज API और व्यापक प्रलेखन प्रदान करता है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
