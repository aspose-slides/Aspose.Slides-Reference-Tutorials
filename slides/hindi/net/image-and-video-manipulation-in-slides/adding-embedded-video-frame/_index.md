---
title: Aspose.Slides - .NET प्रस्तुतियों में एम्बेडेड वीडियो जोड़ना
linktitle: Aspose.Slides - .NET प्रस्तुतियों में एम्बेडेड वीडियो जोड़ना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: .NET के लिए Aspose.Slides का उपयोग करके एम्बेडेड वीडियो के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ। सहज एकीकरण के लिए हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 19
url: /hi/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - .NET प्रस्तुतियों में एम्बेडेड वीडियो जोड़ना

## परिचय
प्रस्तुतियों की गतिशील दुनिया में, मल्टीमीडिया तत्वों को एकीकृत करने से जुड़ाव में उल्लेखनीय वृद्धि हो सकती है। Aspose.Slides for .NET आपके प्रस्तुति स्लाइड में एम्बेडेड वीडियो फ़्रेम को शामिल करने के लिए एक शक्तिशाली समाधान प्रदान करता है। यह ट्यूटोरियल आपको प्रक्रिया के माध्यम से मार्गदर्शन करेगा, एक सहज अनुभव सुनिश्चित करने के लिए प्रत्येक चरण को तोड़ देगा।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
-  Aspose.Slides for .NET लाइब्रेरी: लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[रिलीज़ पेज](https://releases.aspose.com/slides/net/).
- मीडिया सामग्री: एक वीडियो फ़ाइल (जैसे, "Wildlife.mp4") जिसे आप अपनी प्रस्तुति में एम्बेड करना चाहते हैं।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में आवश्यक नामस्थानों को आयात करके आरंभ करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## चरण 1: निर्देशिकाएँ सेट करें
सुनिश्चित करें कि आपके प्रोजेक्ट में दस्तावेज़ और मीडिया फ़ाइलों के लिए आवश्यक निर्देशिकाएँ हैं:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## चरण 2: प्रेजेंटेशन क्लास को इंस्टैंशिएट करें
PPTX फ़ाइल को दर्शाने के लिए प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ:
```csharp
using (Presentation pres = new Presentation())
{
    // पहली स्लाइड प्राप्त करें
    ISlide sld = pres.Slides[0];
```
## चरण 3: प्रस्तुति के अंदर वीडियो एम्बेड करें
प्रस्तुति के अंदर वीडियो एम्बेड करने के लिए निम्नलिखित कोड का उपयोग करें:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## चरण 4: वीडियो फ़्रेम जोड़ें
अब, स्लाइड में एक वीडियो फ्रेम जोड़ें:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## चरण 5: वीडियो गुण सेट करें
वीडियो को वीडियो फ्रेम पर सेट करें और प्ले मोड और वॉल्यूम कॉन्फ़िगर करें:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## चरण 6: प्रेजेंटेशन सहेजें
अंत में, PPTX फ़ाइल को डिस्क पर सेव करें:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
प्रत्येक वीडियो के लिए इन चरणों को दोहराएं जिसे आप अपनी प्रस्तुति में एम्बेड करना चाहते हैं।
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके अपनी प्रस्तुति में सफलतापूर्वक एक एम्बेडेड वीडियो फ़्रेम जोड़ लिया है। यह गतिशील सुविधा आपकी प्रस्तुति को नई ऊंचाइयों तक ले जा सकती है, जो आपके स्लाइड में सहज रूप से एकीकृत मल्टीमीडिया तत्वों के साथ आपके दर्शकों को आकर्षित करती है।
## पूछे जाने वाले प्रश्न
### क्या मैं प्रस्तुति की किसी भी स्लाइड में वीडियो एम्बेड कर सकता हूँ?
 हां, आप इंडेक्स को संशोधित करके कोई भी स्लाइड चुन सकते हैं`pres.Slides[index]`.
### कौन से वीडियो प्रारूप समर्थित हैं?
Aspose.Slides विभिन्न प्रकार के वीडियो प्रारूपों का समर्थन करता है, जिनमें MP4, AVI और WMV शामिल हैं।
### क्या मैं वीडियो फ्रेम का आकार और स्थिति अनुकूलित कर सकता हूँ?
 बिलकुल! पैरामीटर समायोजित करें`AddVideoFrame(x, y, width, height, video)` जरुरत के अनुसार।
### क्या मेरे द्वारा एम्बेड किये जा सकने वाले वीडियो की संख्या की कोई सीमा है?
एम्बेड किए गए वीडियो की संख्या आमतौर पर आपके प्रेजेंटेशन सॉफ्टवेयर की क्षमता द्वारा सीमित होती है।
### मैं आगे की सहायता कैसे प्राप्त कर सकता हूं या अपना अनुभव कैसे साझा कर सकता हूं?
 दौरा करना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन और चर्चा के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
