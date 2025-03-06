---
title: Aspose.Slides के साथ आकार एनिमेशन आसान बना दिया गया
linktitle: Aspose.Slides के साथ प्रस्तुति स्लाइडों में आकृतियों पर एनिमेशन लागू करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: .NET के लिए Aspose.Slides के साथ शानदार प्रस्तुतिकरण बनाएँ। इस चरण-दर-चरण मार्गदर्शिका में आकृतियों पर एनिमेशन लागू करना सीखें। अपनी स्लाइड्स को अभी बेहतर बनाएँ!
weight: 21
url: /hi/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
गतिशील प्रस्तुतियों की दुनिया में, आकृतियों में एनिमेशन जोड़ने से आपकी स्लाइड्स की दृश्य अपील और जुड़ाव में उल्लेखनीय वृद्धि हो सकती है। .NET के लिए Aspose.Slides इसे सहजता से प्राप्त करने के लिए एक शक्तिशाली टूलकिट प्रदान करता है। इस ट्यूटोरियल में, हम आपको Aspose.Slides का उपयोग करके आकृतियों में एनिमेशन लागू करने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे, जिससे आप आकर्षक प्रस्तुतियाँ बना सकेंगे जो एक स्थायी छाप छोड़ती हैं।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित चीजें मौजूद हैं:
1.  Aspose.Slides for .NET: सुनिश्चित करें कि आपके पास लाइब्रेरी स्थापित है और उपयोग के लिए तैयार है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
2. विकास वातावरण: आवश्यक कॉन्फ़िगरेशन के साथ अपना पसंदीदा विकास वातावरण सेट करें।
3. दस्तावेज़ निर्देशिका: अपनी प्रस्तुति फ़ाइलों को संग्रहीत करने के लिए एक निर्देशिका बनाएँ।
## नामस्थान आयात करें
अपने .NET अनुप्रयोग में, आवश्यक नामस्थानों को आयात करके प्रारंभ करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## चरण 1: एक प्रस्तुति बनाएं
 का उपयोग करके एक नई प्रस्तुति बनाकर आरंभ करें`Presentation` कक्षा:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // प्रस्तुतिकरण बनाने के लिए आपका कोड यहां है।
}
```
## चरण 2: एनिमेटेड आकार जोड़ें
अब, आइए अपनी प्रस्तुति की पहली स्लाइड में एक एनिमेटेड आकृति जोड़ें:
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## चरण 3: एनीमेशन प्रभाव लागू करें
निर्मित आकृति में 'पथफुटबॉल' एनीमेशन प्रभाव जोड़ें:
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## चरण 4: ट्रिगर बटन बनाएं
एक बटन बनाएं जो एनीमेशन को ट्रिगर करेगा:
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## चरण 5: कस्टम उपयोगकर्ता पथ परिभाषित करें
एनीमेशन के लिए एक कस्टम उपयोगकर्ता पथ परिभाषित करें:
```csharp
ISequence seqInter = pres.Slides[0].Timeline.InteractiveSequences.Add(shapeTrigger);
IEffect fxUserPath = seqInter.AddEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
IMotionEffect motionBhv = ((IMotionEffect)fxUserPath.Behaviors[0]);
PointF[] pts = new PointF[1];
pts[0] = new PointF(0.076f, 0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new PointF(-0.076f, -0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.Path.Add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
// प्रस्तुति को PPTX के रूप में डिस्क पर सहेजें
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
यह .NET के लिए Aspose.Slides का उपयोग करके आकृतियों पर एनिमेशन लागू करने के लिए चरण-दर-चरण मार्गदर्शिका को पूरा करता है।
## निष्कर्ष
अपनी प्रस्तुतियों में एनिमेशन शामिल करने से एक गतिशील तत्व जुड़ता है जो आपके दर्शकों का ध्यान आकर्षित करता है। Aspose.Slides के साथ, आपके पास इन प्रभावों को सहजता से एकीकृत करने और अपनी प्रस्तुतियों को अगले स्तर तक बढ़ाने के लिए एक मजबूत उपकरण है।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं एक ही आकृति पर एकाधिक एनिमेशन लागू कर सकता हूँ?
हां, Aspose.Slides आपको एक ही आकृति में एकाधिक एनीमेशन प्रभाव जोड़ने की अनुमति देता है, जिससे जटिल एनिमेशन बनाने में लचीलापन मिलता है।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
Aspose.Slides विभिन्न PowerPoint संस्करणों के साथ संगतता सुनिश्चित करता है, जिससे यह सुनिश्चित होता है कि आपकी प्रस्तुतियाँ विभिन्न प्लेटफार्मों पर निर्बाध रूप से काम करें।
### मैं Aspose.Slides के लिए अतिरिक्त संसाधन और समर्थन कहां पा सकता हूं?
 पता लगाएं[प्रलेखन](https://reference.aspose.com/slides/net/) और सहायता मांगें[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### क्या मुझे Aspose.Slides लाइब्रेरी का उपयोग करने के लिए लाइसेंस की आवश्यकता है?
 हां, आप लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/buy) Aspose.Slides की पूरी क्षमता को अनलॉक करने के लिए.
### क्या मैं खरीदने से पहले Aspose.Slides आज़मा सकता हूँ?
 ज़रूर! इसका उपयोग करें[मुफ्त परीक्षण](https://releases.aspose.com/) प्रतिबद्धता बनाने से पहले Aspose.Slides की क्षमताओं का अनुभव करें।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
