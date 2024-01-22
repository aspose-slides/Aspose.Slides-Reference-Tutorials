---
title: Aspose.Slides के साथ PowerPoint में एनीमेशन के बाद के प्रभावों में महारत हासिल करना
linktitle: स्लाइड में एनीमेशन प्रकार के बाद नियंत्रण
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड में एनीमेशन के बाद के प्रभावों को नियंत्रित करना सीखें। गतिशील दृश्य तत्वों के साथ अपनी प्रस्तुतियों को बेहतर बनाएं।
type: docs
weight: 11
url: /hi/net/slide-animation-control/control-after-animation-type/
---
## परिचय
गतिशील एनिमेशन के साथ अपनी प्रस्तुतियों को बेहतर बनाना आपके दर्शकों को आकर्षित करने का एक महत्वपूर्ण पहलू है। .NET के लिए Aspose.Slides स्लाइडों में एनीमेशन के बाद के प्रभावों को नियंत्रित करने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम स्लाइड्स पर आफ्टर-एनीमेशन प्रकार में हेरफेर करने के लिए .NET के लिए Aspose.Slides का उपयोग करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करेंगे। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अधिक इंटरैक्टिव और दृश्य रूप से आकर्षक प्रस्तुतियाँ बनाने में सक्षम होंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित स्थान हैं:
- C# और .NET प्रोग्रामिंग का बुनियादी ज्ञान।
-  .NET लाइब्रेरी के लिए Aspose.Slides स्थापित। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- एक एकीकृत विकास वातावरण (आईडीई) जैसे विजुअल स्टूडियो।
## नामस्थान आयात करें
Aspose.Slides कार्यात्मकताओं तक पहुँचने के लिए आवश्यक नामस्थान आयात करके प्रारंभ करें। अपने कोड में निम्नलिखित पंक्तियाँ जोड़ें:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
अब, आइए बेहतर समझ के लिए दिए गए कोड को कई चरणों में विभाजित करें:
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
सुनिश्चित करें कि निर्दिष्ट निर्देशिका मौजूद है, या यदि नहीं है तो इसे बनाएं।
## चरण 2: आउटपुट फ़ाइल पथ को परिभाषित करें
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
संशोधित प्रस्तुति के लिए आउटपुट फ़ाइल पथ निर्दिष्ट करें।
## चरण 3: प्रस्तुति लोड करें
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
प्रेजेंटेशन क्लास को इंस्टेंट करें और मौजूदा प्रेजेंटेशन को लोड करें।
## चरण 4: स्लाइड 1 पर एनिमेशन प्रभावों के बाद संशोधित करें
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
पहली स्लाइड को क्लोन करें, उसके टाइमलाइन अनुक्रम तक पहुंचें, और एनीमेशन के बाद के प्रभाव को "अगले माउस क्लिक पर छिपाएं" पर सेट करें।
## चरण 5: स्लाइड 2 पर एनिमेशन प्रभावों के बाद संशोधित करें
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
पहली स्लाइड को फिर से क्लोन करें, इस बार एनीमेशन के बाद के प्रभाव को हरे रंग से "रंग" में बदलें।
## चरण 6: स्लाइड 3 पर एनिमेशन प्रभावों के बाद संशोधित करें
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
पहली स्लाइड को एक बार फिर क्लोन करें, एनीमेशन के बाद के प्रभाव को "एनीमेशन के बाद छुपाएं" पर सेट करें।
## चरण 7: संशोधित प्रस्तुति सहेजें
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
संशोधित प्रस्तुति को निर्दिष्ट आउटपुट फ़ाइल पथ के साथ सहेजें।
## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.Slides का उपयोग करके स्लाइड पर एनीमेशन के बाद के प्रभावों को कैसे नियंत्रित किया जाए। अधिक गतिशील और आकर्षक प्रस्तुतियाँ बनाने के लिए एनीमेशन के बाद के विभिन्न प्रकारों के साथ प्रयोग करें।
## पूछे जाने वाले प्रश्न
### क्या मैं एक स्लाइड के भीतर अलग-अलग तत्वों पर अलग-अलग एनीमेशन-पश्चात प्रभाव लागू कर सकता हूँ?
हाँ तुम कर सकते हो। तत्वों के माध्यम से पुनरावृत्ति करें और उनके एनीमेशन के बाद के प्रभावों को तदनुसार समायोजित करें।
### क्या Aspose.Slides .NET के नवीनतम संस्करणों के साथ संगत है?
हां, नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगतता सुनिश्चित करने के लिए Aspose.Slides को नियमित रूप से अपडेट किया जाता है।
### मैं Aspose.Slides का उपयोग करके स्लाइडों में कस्टम एनिमेशन कैसे जोड़ सकता हूँ?
 दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/slides/net/) कस्टम एनिमेशन जोड़ने पर विस्तृत जानकारी के लिए।
### प्रस्तुतियों को सहेजने के लिए Aspose.Slides किस फ़ाइल स्वरूप का समर्थन करता है?
Aspose.Slides पीपीटीएक्स, पीपीटी, पीडीएफ और अन्य सहित विभिन्न प्रारूपों का समर्थन करता है। पूरी सूची के लिए दस्तावेज़ की जाँच करें.
### मैं Aspose.Slides से संबंधित सहायता कहां से प्राप्त कर सकता हूं या प्रश्न पूछ सकता हूं?
 दौरा करना[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11) समर्थन और सामुदायिक सहभागिता के लिए।