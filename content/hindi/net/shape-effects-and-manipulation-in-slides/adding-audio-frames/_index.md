---
title: Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में ऑडियो फ़्रेम जोड़ना
linktitle: Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में ऑडियो फ़्रेम जोड़ना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides के साथ प्रस्तुतियाँ बढ़ाएँ! ऑडियो फ़्रेम को निर्बाध रूप से जोड़ना सीखें, अपने दर्शकों को पहले की तरह आकर्षित करें।
type: docs
weight: 14
url: /hi/net/shape-effects-and-manipulation-in-slides/adding-audio-frames/
---
## परिचय
प्रस्तुतियों की गतिशील दुनिया में, ऑडियो तत्वों को शामिल करने से आपके दर्शकों के समग्र अनुभव में उल्लेखनीय वृद्धि हो सकती है। .NET के लिए Aspose.Slides डेवलपर्स को जुड़ाव और अन्तरक्रियाशीलता की एक नई परत जोड़कर, प्रेजेंटेशन स्लाइड्स में ऑडियो फ्रेम को सहजता से एकीकृत करने का अधिकार देता है। यह चरण-दर-चरण मार्गदर्शिका आपको .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में ऑडियो फ़्रेम जोड़ने की प्रक्रिया के बारे में बताएगी।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET लाइब्रेरी के लिए Aspose.Slides: .NET लाइब्रेरी के लिए Aspose.Slides को डाउनलोड और इंस्टॉल करें।[लिंक को डाउनलोड करें](https://releases.aspose.com/slides/net/).
2. विकास वातावरण: सुनिश्चित करें कि आपके पास .NET के लिए विजुअल स्टूडियो जैसा कार्यशील विकास वातावरण है।
3. दस्तावेज़ निर्देशिका: एक निर्देशिका बनाएं जहां आप अपने दस्तावेज़ संग्रहीत करेंगे, और पथ नोट कर लेंगे।
## नामस्थान आयात करें
अपने .NET एप्लिकेशन में, Aspose.Slides कार्यक्षमता तक पहुंचने के लिए आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## चरण 1: प्रेजेंटेशन और स्लाइड बनाएं
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    ISlide sld = pres.Slides[0];
    // स्लाइड निर्माण के लिए आपका कोड यहां जाता है
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
इन चरणों का पालन करके, आपने .NET के लिए Aspose.Slides का उपयोग करके ऑडियो फ़्रेम को अपनी प्रस्तुति में सफलतापूर्वक एकीकृत कर लिया है।
## निष्कर्ष
अपनी प्रस्तुतियों में ऑडियो तत्वों को शामिल करने से समग्र दर्शक अनुभव में वृद्धि होती है, जिससे आपकी सामग्री अधिक गतिशील और आकर्षक बन जाती है। .NET के लिए Aspose.Slides इस प्रक्रिया को सरल बनाता है, जिससे डेवलपर्स को कोड की कुछ पंक्तियों के साथ ऑडियो फ्रेम को सहजता से एकीकृत करने की अनुमति मिलती है।
## पूछे जाने वाले प्रश्न
### क्या .NET के लिए Aspose.Slides विभिन्न ऑडियो प्रारूपों के साथ संगत है?
.NET के लिए Aspose.Slides WAV, MP3 और अन्य सहित विभिन्न ऑडियो प्रारूपों का समर्थन करता है। विस्तृत सूची के लिए दस्तावेज़ की जाँच करें।
### क्या मैं जोड़े गए ऑडियो फ़्रेम की प्लेबैक सेटिंग्स को नियंत्रित कर सकता हूँ?
हां, Aspose.Slides प्लेबैक सेटिंग्स जैसे वॉल्यूम, प्ले मोड और बहुत कुछ कॉन्फ़िगर करने में लचीलापन प्रदान करता है।
### क्या .NET के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप .NET के लिए Aspose.Slides की सुविधाओं का पता लगा सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/).
### मुझे .NET के लिए Aspose.Slides के लिए समर्थन कहां मिल सकता है?
 दौरा करना[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11) सहायता प्राप्त करना और समुदाय के साथ जुड़ना।
### मैं .NET के लिए Aspose.Slides कैसे खरीदूं?
 आप लाइब्रेरी यहां से खरीद सकते हैं[असपोज़ स्टोर](https://purchase.aspose.com/buy).