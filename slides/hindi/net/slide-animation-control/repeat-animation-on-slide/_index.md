---
title: Aspose.Slides .NET के साथ पावरपॉइंट एनिमेशन में महारत हासिल करें
linktitle: स्लाइड पर एनिमेशन दोहराएँ
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: .NET के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों को बेहतर बनाएँ। एनिमेशन को आसानी से नियंत्रित करें, अपने दर्शकों को आकर्षित करें और एक स्थायी छाप छोड़ें।
weight: 12
url: /hi/net/slide-animation-control/repeat-animation-on-slide/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
प्रस्तुतियों की गतिशील दुनिया में, एनिमेशन को नियंत्रित करने की क्षमता दर्शकों का ध्यान आकर्षित करने और उन्हें आकर्षित करने में महत्वपूर्ण भूमिका निभाती है। Aspose.Slides for .NET डेवलपर्स को स्लाइड के भीतर एनिमेशन प्रकारों को नियंत्रित करने की शक्ति देता है, जिससे अधिक इंटरैक्टिव और नेत्रहीन आकर्षक प्रस्तुतिकरण की अनुमति मिलती है। इस ट्यूटोरियल में, हम चरण दर चरण Aspose.Slides for .NET का उपयोग करके स्लाइड पर एनिमेशन प्रकारों को नियंत्रित करने का तरीका जानेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1.  Aspose.Slides for .NET लाइब्रेरी: लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/slides/net/).
2. .NET विकास वातावरण: अपनी मशीन पर .NET विकास वातावरण सेट करें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.Slides द्वारा प्रदान की गई कार्यक्षमताओं का लाभ उठाने के लिए आवश्यक नामस्थानों को आयात करके शुरू करें:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## चरण 1: प्रोजेक्ट सेट अप करें
अपने प्रोजेक्ट के लिए एक नई निर्देशिका बनाएं और प्रेजेंटेशन फ़ाइल को दर्शाने के लिए प्रेजेंटेशन क्लास को इंस्टैंसिएट करें।
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // आपका कोड यहां जाएगा
}
```
## चरण 2: प्रभाव अनुक्रम तक पहुँचें
MainSequence गुण का उपयोग करके पहली स्लाइड के लिए प्रभाव अनुक्रम पुनर्प्राप्त करें।
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## चरण 3: पहले प्रभाव तक पहुँचें
मुख्य अनुक्रम के गुणों में परिवर्तन करने के लिए उसका पहला प्रभाव प्राप्त करें।
```csharp
IEffect effect = effectsSequence[0];
```
## चरण 4: दोहराएँ सेटिंग संशोधित करें
प्रभाव के टाइमिंग/रिपीट गुण को "स्लाइड के अंत तक" में बदलें।
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## चरण 5: प्रस्तुति सहेजें
परिवर्तनों को देखने के लिए संशोधित प्रस्तुति को सहेजें.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
अतिरिक्त प्रभावों के लिए इन चरणों को दोहराएं या अपनी प्रस्तुति आवश्यकताओं के अनुसार इन्हें अनुकूलित करें।
## निष्कर्ष
Aspose.Slides for .NET के साथ अपने PowerPoint प्रेजेंटेशन में डायनेमिक एनिमेशन शामिल करना पहले कभी इतना आसान नहीं रहा। यह चरण-दर-चरण मार्गदर्शिका आपको एनिमेशन प्रकारों को नियंत्रित करने के ज्ञान से लैस करती है, जिससे यह सुनिश्चित होता है कि आपकी स्लाइड आपके दर्शकों पर एक स्थायी प्रभाव छोड़ें।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं इन एनिमेशन को स्लाइड के भीतर विशिष्ट ऑब्जेक्ट्स पर लागू कर सकता हूं?
हां, आप अनुक्रम के भीतर उनके व्यक्तिगत प्रभावों तक पहुंच कर विशिष्ट वस्तुओं को लक्षित कर सकते हैं।
### क्या Aspose.Slides नवीनतम PowerPoint संस्करणों के साथ संगत है?
Aspose.Slides PowerPoint के विभिन्न संस्करणों के लिए समर्थन प्रदान करता है, तथा पुराने और नए दोनों संस्करणों के साथ संगतता सुनिश्चित करता है।
### मैं अतिरिक्त उदाहरण और संसाधन कहां पा सकता हूं?
 पता लगाएं[प्रलेखन](https://reference.aspose.com/slides/net/) व्यापक उदाहरण और विस्तृत स्पष्टीकरण के लिए.
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 मिलने जाना[यहाँ](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंस प्राप्त करने के बारे में जानकारी के लिए कृपया यहां क्लिक करें।
### क्या आपको सहायता चाहिए या आपके पास और प्रश्न हैं?
 Aspose.Slides समुदाय के साथ जुड़ें[सहयता मंच](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
