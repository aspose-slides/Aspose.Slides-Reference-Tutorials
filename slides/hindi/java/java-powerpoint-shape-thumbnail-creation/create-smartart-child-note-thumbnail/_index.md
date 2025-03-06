---
title: स्मार्टआर्ट चाइल्ड नोट थंबनेल बनाएं
linktitle: स्मार्टआर्ट चाइल्ड नोट थंबनेल बनाएं
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ जावा में स्मार्टआर्ट चाइल्ड नोट थंबनेल बनाना सीखें, जिससे आपकी पावरपॉइंट प्रस्तुतियाँ आसानी से बेहतर बन सकें।
weight: 15
url: /hi/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके जावा में स्मार्टआर्ट चाइल्ड नोट थंबनेल बनाने का तरीका जानेंगे। Aspose.Slides एक शक्तिशाली जावा API है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों के साथ काम करने की अनुमति देता है, जिससे वे आसानी से स्लाइड बना, संशोधित और हेरफेर कर सकते हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2.  Aspose.Slides for Java लाइब्रेरी को आपके प्रोजेक्ट में डाउनलोड और कॉन्फ़िगर किया गया है। आप लाइब्रेरी को यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
अपने जावा क्लास में आवश्यक पैकेज आयात करना सुनिश्चित करें:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
सुनिश्चित करें कि आपके पास Aspose.Slides लाइब्रेरी के साथ एक Java प्रोजेक्ट सेटअप और कॉन्फ़िगर किया गया है।
## चरण 2: एक प्रस्तुति बनाएं
 उदाहरण प्रस्तुत करें`Presentation` PPTX फ़ाइल को दर्शाने के लिए क्लास:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## चरण 3: स्मार्टआर्ट जोड़ें
अपनी प्रस्तुति स्लाइड में स्मार्टआर्ट जोड़ें:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## चरण 4: नोड संदर्भ प्राप्त करें
किसी नोड का संदर्भ उसके सूचकांक का उपयोग करके प्राप्त करें:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## चरण 5: थंबनेल प्राप्त करें
स्मार्टआर्ट नोड की थंबनेल छवि प्राप्त करें:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## चरण 6: थंबनेल सहेजें
थम्बनेल छवि को फ़ाइल में सहेजें:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
अपनी प्रस्तुति में आवश्यकतानुसार प्रत्येक स्मार्टआर्ट नोड के लिए इन चरणों को दोहराएं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides का उपयोग करके जावा में स्मार्टआर्ट चाइल्ड नोट थंबनेल कैसे बनाएं। इस ज्ञान के साथ, आप अपने पावरपॉइंट प्रेजेंटेशन को प्रोग्रामेटिक रूप से बढ़ा सकते हैं, आसानी से आकर्षक तत्वों को जोड़ सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं मौजूदा PowerPoint फ़ाइलों में बदलाव करने के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, Aspose.Slides आपको मौजूदा PowerPoint फ़ाइलों को संशोधित करने की अनुमति देता है, जिसमें स्लाइड्स और उनकी सामग्री को जोड़ना, हटाना या संपादित करना शामिल है।
### क्या Aspose.Slides स्लाइडों को विभिन्न फ़ाइल स्वरूपों में निर्यात करने का समर्थन करता है?
बिल्कुल! Aspose.Slides स्लाइड्स को विभिन्न प्रारूपों में निर्यात करने का समर्थन करता है, जिसमें पीडीएफ, चित्र और HTML आदि शामिल हैं।
### क्या Aspose.Slides एंटरप्राइज़-स्तरीय पावरपॉइंट स्वचालन के लिए उपयुक्त है?
हां, Aspose.Slides को एंटरप्राइज़-स्तरीय पावरपॉइंट स्वचालन कार्यों को कुशलतापूर्वक और विश्वसनीय रूप से संभालने के लिए डिज़ाइन किया गया है।
### क्या मैं Aspose.Slides के साथ प्रोग्रामेटिक रूप से जटिल स्मार्टआर्ट आरेख बना सकता हूँ?
निश्चित रूप से! Aspose.Slides विभिन्न जटिलताओं के स्मार्टआर्ट आरेखों को बनाने और उनमें हेरफेर करने के लिए व्यापक समर्थन प्रदान करता है।
### क्या Aspose.Slides डेवलपर्स के लिए तकनीकी सहायता प्रदान करता है?
 हां, Aspose.Slides अपने माध्यम से डेवलपर्स के लिए समर्पित तकनीकी सहायता प्रदान करता है[मंच](https://forum.aspose.com/c/slides/11) और अन्य चैनल.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
