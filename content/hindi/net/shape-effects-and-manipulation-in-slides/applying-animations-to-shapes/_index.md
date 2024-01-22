---
title: Aspose.Slides के साथ आकार एनिमेशन को आसान बनाया गया
linktitle: Aspose.Slides के साथ प्रेजेंटेशन स्लाइड्स में आकृतियों में एनिमेशन लागू करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides के साथ शानदार प्रस्तुतियाँ बनाएँ। इस चरण-दर-चरण मार्गदर्शिका में जानें कि आकृतियों पर एनिमेशन कैसे लागू करें। अब अपनी स्लाइडें उन्नत करें!
type: docs
weight: 21
url: /hi/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---
## परिचय
गतिशील प्रस्तुतियों की दुनिया में, आकृतियों में एनिमेशन जोड़ने से आपकी स्लाइड की दृश्य अपील और जुड़ाव में उल्लेखनीय वृद्धि हो सकती है। .NET के लिए Aspose.Slides इसे निर्बाध रूप से प्राप्त करने के लिए एक शक्तिशाली टूलकिट प्रदान करता है। इस ट्यूटोरियल में, हम आपको Aspose.Slides का उपयोग करके आकृतियों में एनिमेशन लागू करने की प्रक्रिया के बारे में मार्गदर्शन करेंगे, जिससे आप आकर्षक प्रस्तुतियाँ बना सकेंगे जो एक स्थायी प्रभाव छोड़ती हैं।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित स्थान हैं:
1.  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास लाइब्रेरी स्थापित है और उपयोग के लिए तैयार है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
2. विकास परिवेश: आवश्यक कॉन्फ़िगरेशन के साथ अपना पसंदीदा विकास परिवेश स्थापित करें।
3. दस्तावेज़ निर्देशिका: अपनी प्रस्तुति फ़ाइलों को संग्रहीत करने के लिए एक निर्देशिका बनाएं।
## नामस्थान आयात करें
अपने .NET एप्लिकेशन में, आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## चरण 1: एक प्रेजेंटेशन बनाएं
 का उपयोग करके एक नई प्रस्तुति बनाकर शुरुआत करें`Presentation` कक्षा:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    //प्रेजेंटेशन बनाने के लिए आपका कोड यहां जाता है।
}
```
## चरण 2: एनिमेटेड आकृति जोड़ें
अब, आइए अपनी प्रस्तुति की पहली स्लाइड में एक एनिमेटेड आकृति जोड़ें:
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## चरण 3: एनिमेशन प्रभाव लागू करें
निर्मित आकार में 'पाथफुटबॉल' एनीमेशन प्रभाव जोड़ें:
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## चरण 4: ट्रिगर बटन बनाएं
एक बटन बनाएं जो एनीमेशन को ट्रिगर करेगा:
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## चरण 5: कस्टम उपयोगकर्ता पथ को परिभाषित करें
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
// प्रेजेंटेशन को डिस्क पर PPTX के रूप में सेव करें
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
यह .NET के लिए Aspose.Slides का उपयोग करके आकृतियों में एनिमेशन लागू करने के लिए चरण-दर-चरण मार्गदर्शिका को पूरा करता है।
## निष्कर्ष
अपनी प्रस्तुतियों में एनिमेशन शामिल करने से एक गतिशील तत्व जुड़ जाता है जो आपके दर्शकों का ध्यान आकर्षित करता है। Aspose.Slides के साथ, आपके पास इन प्रभावों को सहजता से एकीकृत करने और अपनी प्रस्तुतियों को अगले स्तर तक बढ़ाने के लिए एक मजबूत उपकरण है।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं एक ही आकार में अनेक एनिमेशन लागू कर सकता हूँ?
हां, Aspose.Slides आपको जटिल एनिमेशन बनाने में लचीलापन प्रदान करते हुए, एक ही आकार में कई एनीमेशन प्रभाव जोड़ने की अनुमति देता है।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
Aspose.Slides विभिन्न PowerPoint संस्करणों के साथ संगतता सुनिश्चित करता है, यह सुनिश्चित करते हुए कि आपकी प्रस्तुतियाँ विभिन्न प्लेटफार्मों पर निर्बाध रूप से काम करती हैं।
### मुझे Aspose.Slides के लिए अतिरिक्त संसाधन और समर्थन कहां मिल सकता है?
 पता लगाएं[प्रलेखन](https://reference.aspose.com/slides/net/) और इसमें सहायता मांगें[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11).
### क्या मुझे लाइब्रेरी का उपयोग करने के लिए Aspose.Slides के लाइसेंस की आवश्यकता है?
 हाँ, आप लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/buy) Aspose.Slides की पूरी क्षमता को अनलॉक करने के लिए।
### क्या मैं खरीदने से पहले Aspose.Slides आज़मा सकता हूँ?
 निश्चित रूप से! का उपयोग करें[मुफ्त परीक्षण](https://releases.aspose.com/) प्रतिबद्धता बनाने से पहले Aspose.Slides की क्षमताओं का अनुभव करना।