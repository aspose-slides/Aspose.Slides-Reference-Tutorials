---
title: पावरपॉइंट में वीडियो फ्रेम जोड़ें
linktitle: पावरपॉइंट में वीडियो फ्रेम जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में वीडियो सामग्री को सहजता से एकीकृत करना सीखें। अपने दर्शकों को आकर्षित करने के लिए मल्टीमीडिया तत्वों के साथ आपकी स्लाइड्स।
weight: 17
url: /hi/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में वीडियो फ़्रेम जोड़ने की प्रक्रिया के बारे में बताएँगे। इन चरण-दर-चरण निर्देशों का पालन करके, आप आसानी से अपने प्रेजेंटेशन में वीडियो सामग्री को सहजता से एकीकृत कर पाएँगे।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है
- Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके Java प्रोजेक्ट में सेट अप की गई
## पैकेज आयात करें
सबसे पहले, आपको अपने जावा कोड में Aspose.Slides कार्यक्षमताओं का उपयोग करने के लिए आवश्यक पैकेजों को आयात करना होगा। 
```java
import com.aspose.slides.*;

import java.io.File;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
सुनिश्चित करें कि आपके पास अपनी पावरपॉइंट फ़ाइलों को संग्रहीत करने के लिए एक निर्देशिका स्थापित है।
```java
String dataDir = "Your Document Directory";
```
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट बनाएँ
 उदाहरण प्रस्तुत करें`Presentation` PowerPoint फ़ाइल का प्रतिनिधित्व करने के लिए क्लास का उपयोग करें।
```java
Presentation pres = new Presentation();
```
## चरण 3: स्लाइड में वीडियो फ़्रेम जोड़ें
पहली स्लाइड लें और उसमें एक वीडियो फ्रेम जोड़ें।
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## चरण 4: प्ले मोड और वॉल्यूम सेट करें
वीडियो फ्रेम का प्ले मोड और वॉल्यूम सेट करें।
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## चरण 5: प्रस्तुति सहेजें
संशोधित PowerPoint फ़ाइल को डिस्क पर सहेजें.
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में वीडियो फ़्रेम जोड़ना सफलतापूर्वक सीख लिया है। अपने दर्शकों को प्रभावी ढंग से आकर्षित करने के लिए मल्टीमीडिया तत्वों को शामिल करके अपनी प्रेजेंटेशन को बेहतर बनाएँ।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं पावरपॉइंट प्रेजेंटेशन में किसी भी प्रारूप का वीडियो जोड़ सकता हूँ?
Aspose.Slides विभिन्न वीडियो प्रारूपों जैसे AVI, WMV, MP4, और अधिक का समर्थन करता है। सुनिश्चित करें कि प्रारूप PowerPoint के साथ संगत है।
### क्या Aspose.Slides जावा के विभिन्न संस्करणों के साथ संगत है?
हां, Aspose.Slides for Java JDK संस्करण 6 और उससे ऊपर के साथ संगत है।
### मैं वीडियो फ्रेम का आकार और स्थिति कैसे समायोजित कर सकता हूं?
 आप वीडियो फ्रेम के आयाम और निर्देशांक को पैरामीटर में संशोधन करके अनुकूलित कर सकते हैं`addVideoFrame` तरीका।
### क्या मैं वीडियो की प्लेबैक सेटिंग्स को नियंत्रित कर सकता हूँ?
हां, आप अपनी पसंद के अनुसार वीडियो फ्रेम का प्ले मोड और वॉल्यूम सेट कर सकते हैं।
### मैं Aspose.Slides के लिए अधिक समर्थन और संसाधन कहां पा सकता हूं?
 दौरा करना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सहायता, दस्तावेज़ीकरण और सामुदायिक समर्थन के लिए।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
