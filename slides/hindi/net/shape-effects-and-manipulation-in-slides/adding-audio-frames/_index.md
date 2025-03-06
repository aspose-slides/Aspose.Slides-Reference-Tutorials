---
title: Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में ऑडियो फ़्रेम जोड़ना
linktitle: Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में ऑडियो फ़्रेम जोड़ना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET के साथ प्रस्तुतियाँ बढ़ाएँ! ऑडियो फ़्रेम जोड़ना सीखें, अपने दर्शकों को पहले से कहीं ज़्यादा आकर्षित करें।
weight: 14
url: /hi/net/shape-effects-and-manipulation-in-slides/adding-audio-frames/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
प्रस्तुतियों की गतिशील दुनिया में, ऑडियो तत्वों को शामिल करना आपके दर्शकों के लिए समग्र अनुभव को महत्वपूर्ण रूप से बढ़ा सकता है। Aspose.Slides for .NET डेवलपर्स को प्रस्तुति स्लाइड में ऑडियो फ़्रेम को सहजता से एकीकृत करने में सक्षम बनाता है, जिससे जुड़ाव और अन्तरक्रियाशीलता की एक नई परत जुड़ती है। यह चरण-दर-चरण मार्गदर्शिका आपको Aspose.Slides for .NET का उपयोग करके प्रस्तुति स्लाइड में ऑडियो फ़्रेम जोड़ने की प्रक्रिया से परिचित कराएगी।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1.  Aspose.Slides for .NET लाइब्रेरी: Aspose.Slides for .NET लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/slides/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास .NET के लिए कार्यशील विकास परिवेश है, जैसे कि Visual Studio.
3. दस्तावेज़ निर्देशिका: एक निर्देशिका बनाएं जहां आप अपने दस्तावेज़ संग्रहीत करेंगे, और पथ नोट कर लें।
## नामस्थान आयात करें
अपने .NET अनुप्रयोग में, Aspose.Slides कार्यक्षमता तक पहुंचने के लिए आवश्यक नामस्थानों को आयात करके प्रारंभ करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## चरण 1: प्रस्तुति और स्लाइड बनाएँ
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    ISlide sld = pres.Slides[0];
    // स्लाइड निर्माण के लिए आपका कोड यहां है
}
```
## चरण 2: ऑडियो फ़ाइल लोड करें
```csharp
FileStream fstr = new FileStream(dataDir + "sampleaudio.wav", FileMode.Open, FileAccess.Read);
```
## चरण 3: ऑडियो फ़्रेम जोड़ें
```csharp
IAudioFrame audioFrame = sld.Shapes.AddAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## चरण 4: ऑडियो गुण कॉन्फ़िगर करें
```csharp
audioFrame.PlayAcrossSlides = true;
audioFrame.RewindAudio = true;
audioFrame.PlayMode = AudioPlayModePreset.Auto;
audioFrame.Volume = AudioVolumeMode.Loud;
```
## चरण 5: प्रस्तुति सहेजें
```csharp
pres.Save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```
इन चरणों का पालन करके, आपने .NET के लिए Aspose.Slides का उपयोग करके अपनी प्रस्तुति में ऑडियो फ़्रेम को सफलतापूर्वक एकीकृत कर लिया है।
## निष्कर्ष
अपनी प्रस्तुतियों में ऑडियो तत्वों को शामिल करने से समग्र दर्शक अनुभव में वृद्धि होती है, जिससे आपकी सामग्री अधिक गतिशील और आकर्षक बनती है। .NET के लिए Aspose.Slides इस प्रक्रिया को सरल बनाता है, जिससे डेवलपर्स को कोड की कुछ पंक्तियों के साथ ऑडियो फ़्रेम को सहजता से एकीकृत करने की अनुमति मिलती है।
## पूछे जाने वाले प्रश्न
### क्या Aspose.Slides for .NET विभिन्न ऑडियो प्रारूपों के साथ संगत है?
Aspose.Slides for .NET विभिन्न ऑडियो प्रारूपों का समर्थन करता है, जिसमें WAV, MP3, और बहुत कुछ शामिल है। विस्तृत सूची के लिए दस्तावेज़ देखें।
### क्या मैं जोड़े गए ऑडियो फ्रेम की प्लेबैक सेटिंग्स को नियंत्रित कर सकता हूं?
हां, Aspose.Slides वॉल्यूम, प्ले मोड और अन्य जैसी प्लेबैक सेटिंग्स को कॉन्फ़िगर करने में लचीलापन प्रदान करता है।
### क्या .NET के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप .NET के लिए Aspose.Slides की सुविधाओं का पता लगा सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Slides का समर्थन कहां पा सकता हूं?
 दौरा करना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सहायता प्राप्त करना और समुदाय के साथ जुड़ना।
### मैं .NET के लिए Aspose.Slides कैसे खरीदूं?
 आप लाइब्रेरी को यहां से खरीद सकते हैं[एस्पोज स्टोर](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
