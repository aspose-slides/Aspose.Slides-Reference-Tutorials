---
title: जावा पावरपॉइंट में कस्टम बुलेट नंबर सेट करें
linktitle: जावा पावरपॉइंट में कस्टम बुलेट नंबर सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ Java PowerPoint में कस्टम बुलेट नंबर सेट करना सीखें, जिससे प्रोग्रामेटिक रूप से प्रस्तुति स्पष्टता और संरचना में वृद्धि हो।
type: docs
weight: 15
url: /hi/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---
## परिचय
आज के डिजिटल युग में, विचारों और डेटा को प्रभावी ढंग से संप्रेषित करने के लिए गतिशील प्रस्तुतियाँ बनाना महत्वपूर्ण है। जावा के लिए Aspose.Slides प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों में हेरफेर करने के लिए एक शक्तिशाली टूलकिट प्रदान करता है, जो आपकी प्रस्तुति-निर्माण प्रक्रिया को बढ़ाने के लिए व्यापक सुविधाएँ प्रदान करता है। यह लेख Aspose.Slides का उपयोग करके जावा पावरपॉइंट प्रस्तुतियों में कस्टम बुलेट नंबर सेट करने के बारे में बताता है। चाहे आप एक अनुभवी डेवलपर हों या एक नए व्यक्ति, यह ट्यूटोरियल आपको प्रक्रिया के माध्यम से चरण-दर-चरण मार्गदर्शन करेगा, यह सुनिश्चित करते हुए कि आप इस क्षमता का कुशलतापूर्वक लाभ उठा सकते हैं।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके विकास परिवेश में निम्नलिखित पूर्वापेक्षाएँ स्थापित हैं:
- जावा डेवलपमेंट किट (JDK) स्थापित
- एकीकृत विकास वातावरण (IDE) जैसे कि IntelliJ IDEA या Eclipse
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/)
- जावा प्रोग्रामिंग भाषा और ऑब्जेक्ट-ओरिएंटेड अवधारणाओं की बुनियादी समझ

## पैकेज आयात करें
सबसे पहले, आवश्यक Aspose.Slides क्लासेस और अन्य जावा मानक लाइब्रेरीज़ को आयात करें:
```java
import com.aspose.slides.*;
```
## चरण 1: एक प्रेजेंटेशन ऑब्जेक्ट बनाएँ
Aspose.Slides का उपयोग करके एक नया पावरपॉइंट प्रेजेंटेशन बनाकर शुरुआत करें।
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## चरण 2: टेक्स्ट के साथ ऑटोशेप जोड़ें
स्लाइड पर एक ऑटोशेप (आयत) डालें और उसके टेक्स्ट फ्रेम तक पहुँचें।
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## चरण 3: डिफ़ॉल्ट पैराग्राफ़ हटाएं
टेक्स्ट फ़्रेम से डिफ़ॉल्ट मौजूदा पैराग्राफ़ को हटाएँ.
```java
textFrame.getParagraphs().removeAt(0);
```
## चरण 4: क्रमांकित बुलेट्स जोड़ें
विशिष्ट संख्याओं से शुरू करते हुए कस्टम क्रमांकित बुलेट्स के साथ पैराग्राफ जोड़ें।
```java
// 2 से शुरू होने वाले बुलेट के साथ उदाहरण पैराग्राफ
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// 3 से शुरू होने वाले बुलेट के साथ उदाहरण पैराग्राफ
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// 7 से शुरू होने वाले बुलेट के साथ उदाहरण पैराग्राफ
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## चरण 5: प्रस्तुति सहेजें
अंत में, संशोधित प्रस्तुति को अपने इच्छित स्थान पर सहेजें।
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
निष्कर्ष में, Aspose.Slides for Java प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों में कस्टम बुलेट नंबर सेट करने की प्रक्रिया को सरल बनाता है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपनी प्रस्तुतियों की दृश्य स्पष्टता और संरचना को कुशलतापूर्वक बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं बुलेट्स के स्वरूप को और अधिक अनुकूलित कर सकता हूँ?
हां, Aspose.Slides बुलेट प्रकार, आकार, रंग और अधिक को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### क्या Aspose.Slides PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides 97-2003 से लेकर नवीनतम संस्करणों तक PowerPoint प्रारूपों का समर्थन करता है।
### मैं Aspose.Slides के लिए तकनीकी सहायता कैसे प्राप्त कर सकता हूं?
 मिलने जाना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) तकनीकी सहायता के लिए संपर्क करें।
### क्या मैं खरीदने से पहले Aspose.Slides आज़मा सकता हूँ?
 हां, आप यहां से निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides कहां से खरीद सकता हूं?
 आप Aspose.Slides यहाँ से खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).