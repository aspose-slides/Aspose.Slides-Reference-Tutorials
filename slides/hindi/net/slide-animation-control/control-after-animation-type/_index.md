---
title: Aspose.Slides के साथ PowerPoint में एनीमेशन के बाद के प्रभावों में महारत हासिल करें
linktitle: स्लाइड में एनीमेशन टाइप के बाद नियंत्रण
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET का उपयोग करके PowerPoint स्लाइड में एनीमेशन के बाद के प्रभावों को नियंत्रित करना सीखें। गतिशील दृश्य तत्वों के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।
weight: 11
url: /hi/net/slide-animation-control/control-after-animation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
गतिशील एनिमेशन के साथ अपनी प्रस्तुतियों को बेहतर बनाना आपके दर्शकों को आकर्षित करने का एक महत्वपूर्ण पहलू है। Aspose.Slides for .NET स्लाइड्स में आफ्टर-एनीमेशन प्रभावों को नियंत्रित करने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम आपको स्लाइड्स पर आफ्टर-एनीमेशन प्रकार में हेरफेर करने के लिए Aspose.Slides for .NET का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अधिक इंटरैक्टिव और नेत्रहीन आकर्षक प्रस्तुतियाँ बनाने में सक्षम होंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित चीजें मौजूद हैं:
- C# और .NET प्रोग्रामिंग का बुनियादी ज्ञान।
-  Aspose.Slides for .NET लाइब्रेरी स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- एक एकीकृत विकास वातावरण (IDE) जैसे कि विजुअल स्टूडियो.
## नामस्थान आयात करें
Aspose.Slides कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नामस्थानों को आयात करके शुरू करें। अपने कोड में निम्न पंक्तियाँ जोड़ें:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
अब, बेहतर समझ के लिए दिए गए कोड को कई चरणों में विभाजित करें:
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
सुनिश्चित करें कि निर्दिष्ट निर्देशिका मौजूद है, या यदि नहीं है तो उसे बनाएं।
## चरण 2: आउटपुट फ़ाइल पथ निर्धारित करें
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
संशोधित प्रस्तुति के लिए आउटपुट फ़ाइल पथ निर्दिष्ट करें.
## चरण 3: प्रस्तुति लोड करें
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
प्रेजेंटेशन क्लास को इन्स्टेन्सिएट करें और मौजूदा प्रेजेंटेशन को लोड करें।
## चरण 4: स्लाइड 1 पर एनीमेशन प्रभाव के बाद संशोधन करें
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
पहली स्लाइड को क्लोन करें, इसके टाइमलाइन अनुक्रम तक पहुंचें, और एनीमेशन के बाद के प्रभाव को "अगले माउस क्लिक पर छिपाएं" पर सेट करें।
## चरण 5: स्लाइड 2 पर एनीमेशन प्रभाव के बाद संशोधन करें
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
पहली स्लाइड को पुनः क्लोन करें, इस बार एनीमेशन के बाद के प्रभाव को हरे रंग के साथ "रंग" में बदलें।
## चरण 6: स्लाइड 3 पर एनीमेशन प्रभाव के बाद संशोधन करें
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
पहली स्लाइड को एक बार फिर क्लोन करें, तथा आफ्टर-एनीमेशन प्रभाव को "एनीमेशन के बाद छिपाएं" पर सेट करें।
## चरण 7: संशोधित प्रस्तुति को सहेजें
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
संशोधित प्रस्तुति को निर्दिष्ट आउटपुट फ़ाइल पथ के साथ सहेजें.
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके स्लाइड पर आफ्टर-एनीमेशन प्रभाव को नियंत्रित करना सफलतापूर्वक सीख लिया है। अधिक गतिशील और आकर्षक प्रस्तुतियाँ बनाने के लिए विभिन्न आफ्टर-एनीमेशन प्रकारों के साथ प्रयोग करें।
## पूछे जाने वाले प्रश्न
### क्या मैं स्लाइड के अलग-अलग तत्वों पर अलग-अलग आफ्टर-एनीमेशन प्रभाव लागू कर सकता हूँ?
हां, आप ऐसा कर सकते हैं। तत्वों के माध्यम से पुनरावृत्ति करें और उनके एनीमेशन के बाद के प्रभावों को तदनुसार समायोजित करें।
### क्या Aspose.Slides .NET के नवीनतम संस्करणों के साथ संगत है?
हां, नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगतता सुनिश्चित करने के लिए Aspose.Slides को नियमित रूप से अपडेट किया जाता है।
### मैं Aspose.Slides का उपयोग करके स्लाइड्स में कस्टम एनिमेशन कैसे जोड़ सकता हूँ?
 दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/slides/net/) कस्टम एनिमेशन जोड़ने के बारे में विस्तृत जानकारी के लिए.
### प्रस्तुतियों को सहेजने के लिए Aspose.Slides किस फ़ाइल स्वरूप का समर्थन करता है?
Aspose.Slides विभिन्न प्रारूपों का समर्थन करता है, जिसमें PPTX, PPT, PDF, और बहुत कुछ शामिल है। पूरी सूची के लिए दस्तावेज़ देखें।
### मैं Aspose.Slides से संबंधित सहायता कहां से प्राप्त कर सकता हूं या प्रश्न कहां पूछ सकता हूं?
 दौरा करना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) समर्थन और सामुदायिक संपर्क के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
