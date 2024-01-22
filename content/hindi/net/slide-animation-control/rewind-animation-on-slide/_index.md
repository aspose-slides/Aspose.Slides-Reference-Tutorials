---
title: Aspose.Slides के साथ प्रस्तुतियों में रिवाइंड एनिमेशन में महारत हासिल करना
linktitle: स्लाइड पर एनीमेशन को रिवाइंड करें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड पर एनिमेशन को रिवाइंड करना सीखें। संपूर्ण स्रोत कोड उदाहरणों के साथ इस चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 13
url: /hi/net/slide-animation-control/rewind-animation-on-slide/
---
## परिचय
प्रस्तुतियों की गतिशील दुनिया में, मनोरम एनिमेशन को शामिल करने से जुड़ाव में उल्लेखनीय वृद्धि हो सकती है। .NET के लिए Aspose.Slides आपकी प्रस्तुतियों में जान फूंकने के लिए एक शक्तिशाली टूलसेट प्रदान करता है। एक दिलचस्प विशेषता स्लाइड पर एनिमेशन को रिवाइंड करने की क्षमता है। इस व्यापक गाइड में, हम आपको चरण दर चरण प्रक्रिया के बारे में बताएंगे, जिससे आप .NET के लिए Aspose.Slides का उपयोग करके एनीमेशन रिवाइंड की पूरी क्षमता का उपयोग कर सकेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
-  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास लाइब्रेरी स्थापित है। यदि नहीं, तो इसे यहां से डाउनलोड करें[.NET दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/net/).
- .NET विकास वातावरण: सुनिश्चित करें कि आपके पास एक कार्यशील .NET विकास वातावरण स्थापित है।
- बुनियादी सी# ज्ञान: सी# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें।
## नामस्थान आयात करें
अपने C# कोड में, आपको .NET के लिए Aspose.Slides द्वारा प्रदान की गई कार्यक्षमता का लाभ उठाने के लिए आवश्यक नेमस्पेस आयात करने की आवश्यकता होगी। आपका मार्गदर्शन करने के लिए यहां एक स्निपेट दिया गया है:
```csharp
using System;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा .NET विकास परिवेश में एक नया प्रोजेक्ट बनाएं। यदि आपके दस्तावेज़ मौजूद नहीं हैं तो उनके लिए एक निर्देशिका सेट करें।
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## चरण 2: प्रस्तुति लोड करें
 त्वरित करें`Presentation` आपकी प्रस्तुति फ़ाइल का प्रतिनिधित्व करने के लिए क्लास।
```csharp
using (Presentation presentation = new Presentation(dataDir + "AnimationRewind.pptx"))
{
    // अगले चरणों के लिए आपका कोड यहां दिया गया है
}
```
## चरण 3: पहुँच प्रभाव अनुक्रम
पहली स्लाइड के लिए प्रभाव अनुक्रम पुनः प्राप्त करें।
```csharp
ISequence effectsSequence = presentation.Slides[0].Timeline.MainSequence;
```
## चरण 4: प्रभाव समय को संशोधित करें
मुख्य अनुक्रम के पहले प्रभाव तक पहुंचें और रिवाइंड को सक्षम करने के लिए इसके समय को संशोधित करें।
```csharp
IEffect effect = effectsSequence[0];
Console.WriteLine("\nEffect Timing/Rewind in source presentation is {0}", effect.Timing.Rewind);
effect.Timing.Rewind = true;
```
## चरण 5: प्रस्तुति सहेजें
संशोधित प्रस्तुति सहेजें.
```csharp
presentation.Save(RunExamples.OutPath + "AnimationRewind-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
## चरण 6: गंतव्य प्रस्तुति में रिवाइंड प्रभाव की जाँच करें
संशोधित प्रस्तुति लोड करें और जांचें कि रिवाइंड प्रभाव लागू है या नहीं।
```csharp
using (Presentation pres = new Presentation(RunExamples.OutPath + "AnimationRewind-out.pptx"))
{
    effectsSequence = pres.Slides[0].Timeline.MainSequence;
    effect = effectsSequence[0];
    Console.WriteLine("Effect Timing/Rewind in destination presentation is {0}\n", effect.Timing.Rewind);
}
```
अतिरिक्त स्लाइडों के लिए इन चरणों को दोहराएं या अपनी प्रस्तुति की संरचना के अनुसार प्रक्रिया को अनुकूलित करें।
## निष्कर्ष
Unlocking the rewind animation feature in Aspose.Slides for .NET opens up exciting possibilities for creating dynamic and engaging presentations. By following this step-by-step guide, you can seamlessly integrate animation rewind into your projects, enhancing the visual appeal of your slides.
---
## पूछे जाने वाले प्रश्न
### क्या .NET के लिए Aspose.Slides नवीनतम .NET फ्रेमवर्क संस्करण के साथ संगत है?
 नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगतता सुनिश्चित करने के लिए .NET के लिए Aspose.Slides को नियमित रूप से अद्यतन किया जाता है। जाँचें[प्रलेखन](https://reference.aspose.com/slides/net/) अनुकूलता विवरण के लिए.
### क्या मैं किसी स्लाइड के भीतर विशिष्ट ऑब्जेक्ट पर रिवाइंड एनीमेशन लागू कर सकता हूँ?
हां, आप स्लाइड के भीतर विशिष्ट ऑब्जेक्ट या तत्वों पर चुनिंदा रूप से रिवाइंड एनीमेशन लागू करने के लिए कोड को कस्टमाइज़ कर सकते हैं।
### क्या .NET के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण प्राप्त करके सुविधाओं का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 दौरा करना[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11) सहायता प्राप्त करना और समुदाय के साथ जुड़ना।
### क्या मैं .NET के लिए Aspose.Slides के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).