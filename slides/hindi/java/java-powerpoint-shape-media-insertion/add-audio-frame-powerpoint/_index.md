---
title: PowerPoint में ऑडियो फ़्रेम जोड़ें
linktitle: PowerPoint में ऑडियो फ़्रेम जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में ऑडियो फ़्रेम जोड़ना सीखें। आकर्षक ऑडियो तत्वों के साथ अपनी प्रस्तुतियों को सहजता से बेहतर बनाएँ।
weight: 12
url: /hi/java/java-powerpoint-shape-media-insertion/add-audio-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
ऑडियो तत्वों के साथ प्रस्तुतियों को बेहतर बनाने से उनका प्रभाव और जुड़ाव काफी हद तक बढ़ सकता है। Aspose.Slides for Java के साथ, PowerPoint प्रस्तुतियों में ऑडियो फ़्रेम को एकीकृत करना एक सहज प्रक्रिया बन जाती है। यह ट्यूटोरियल आपको Aspose.Slides for Java का उपयोग करके अपनी प्रस्तुतियों में ऑडियो फ़्रेम जोड़ने की चरण-दर-चरण प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
2.  Aspose.Slides for Java लाइब्रेरी: Aspose.Slides for Java लाइब्रेरी डाउनलोड करें और इंस्टॉल करें। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/).
3. ऑडियो फ़ाइल: वह ऑडियो फ़ाइल (जैसे, WAV प्रारूप) तैयार करें जिसे आप अपनी प्रस्तुति में जोड़ना चाहते हैं।
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## चरण 1: अपनी प्रोजेक्ट निर्देशिका सेट करें
सुनिश्चित करें कि आपके पास अपनी परियोजना के लिए एक निर्देशिका संरचना स्थापित है। यदि नहीं, तो अपनी फ़ाइलों को प्रभावी ढंग से व्यवस्थित करने के लिए एक निर्देशिका संरचना बनाएँ।
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## चरण 2: प्रेजेंटेशन क्लास को इंस्टैंशिएट करें
 उदाहरण प्रस्तुत करें`Presentation` पावरपॉइंट प्रेजेंटेशन को दर्शाने के लिए क्लास का उपयोग करें।
```java
Presentation pres = new Presentation();
```
## चरण 3: स्लाइड प्राप्त करें और ऑडियो फ़ाइल लोड करें
पहली स्लाइड प्राप्त करें और अपनी निर्देशिका से ऑडियो फ़ाइल लोड करें।
```java
ISlide sld = pres.getSlides().get_Item(0);
FileInputStream fstr = new FileInputStream(dataDir + "sampleaudio.wav");
```
## चरण 4: ऑडियो फ़्रेम जोड़ें
स्लाइड में ऑडियो फ़्रेम जोड़ें.
```java
IAudioFrame audioFrame = sld.getShapes().addAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## चरण 5: ऑडियो गुण सेट करें
स्लाइडों पर प्ले, ऑडियो रिवाइंड, प्ले मोड और वॉल्यूम जैसे गुण सेट करें।
```java
audioFrame.setPlayAcrossSlides(true);
audioFrame.setRewindAudio(true);
audioFrame.setPlayMode(AudioPlayModePreset.Auto);
audioFrame.setVolume(AudioVolumeMode.Loud);
```
## चरण 6: प्रेजेंटेशन सहेजें
संशोधित प्रस्तुति को जोड़े गए ऑडियो फ्रेम के साथ सहेजें।
```java
pres.save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
अपने पावरपॉइंट प्रेजेंटेशन में ऑडियो तत्वों को शामिल करने से उनकी प्रभावशीलता बढ़ सकती है और आपके दर्शकों को आकर्षित कर सकते हैं। Aspose.Slides for Java के साथ, ऑडियो फ़्रेम जोड़ने की प्रक्रिया सरल हो जाती है, जिससे आप आसानी से गतिशील और आकर्षक प्रेजेंटेशन बना सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अपनी प्रस्तुति में विभिन्न प्रारूपों की ऑडियो फ़ाइलें जोड़ सकता हूँ?
हां, Aspose.Slides for Java विभिन्न ऑडियो प्रारूपों का समर्थन करता है, जिसमें WAV, MP3 और अन्य शामिल हैं।
### क्या स्लाइडों में ऑडियो प्लेबैक का समय समायोजित करना संभव है?
बिल्कुल। आप Aspose.Slides for Java का उपयोग करके ऑडियो प्लेबैक को विशिष्ट स्लाइड ट्रांज़िशन के साथ सिंक्रनाइज़ कर सकते हैं।
### क्या Java के लिए Aspose.Slides क्रॉस-प्लेटफॉर्म संगतता के लिए समर्थन प्रदान करता है?
हां, आप एम्बेडेड ऑडियो फ्रेम के साथ पावरपॉइंट प्रस्तुतियां बना सकते हैं जो विभिन्न प्लेटफार्मों पर संगत हैं।
### क्या मैं प्रस्तुति में ऑडियो प्लेयर के स्वरूप को अनुकूलित कर सकता हूँ?
Aspose.Slides for Java व्यापक अनुकूलन विकल्प प्रदान करता है, जिससे आप ऑडियो प्लेयर के स्वरूप को अपनी पसंद के अनुसार ढाल सकते हैं।
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप उनके यहां से Aspose.Slides for Java का निःशुल्क परीक्षण प्राप्त कर सकते हैं[वेबसाइट](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
