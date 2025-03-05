---
title: Aspose.Slides के साथ PowerPoint में कनेक्टर लाइन कोण समायोजित करें
linktitle: Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में कनेक्टर लाइन कोण समायोजित करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET का उपयोग करके PowerPoint स्लाइड में कनेक्टर लाइन कोण को समायोजित करना सीखें। सटीकता और आसानी से अपनी प्रस्तुतियों को बेहतर बनाएँ।
type: docs
weight: 28
url: /hi/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---
## परिचय
दृश्य रूप से आकर्षक प्रस्तुतिकरण स्लाइड बनाने में अक्सर कनेक्टर लाइनों में सटीक समायोजन शामिल होता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुतिकरण स्लाइड में कनेक्टर लाइन कोणों को समायोजित करने का तरीका जानेंगे। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को PowerPoint फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है, जो प्रस्तुतिकरण बनाने, संशोधित करने और हेरफेर करने के लिए व्यापक क्षमताएँ प्रदान करती है।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- विजुअल स्टूडियो या कोई अन्य C# विकास वातावरण स्थापित होना चाहिए।
-  Aspose.Slides for .NET लाइब्रेरी। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- कनेक्टर लाइनों वाली एक पावरपॉइंट प्रस्तुति फ़ाइल जिसे आप समायोजित करना चाहते हैं।
## नामस्थान आयात करें
आरंभ करने के लिए, अपने C# कोड में आवश्यक नामस्थान शामिल करना सुनिश्चित करें:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
Visual Studio में एक नया C# प्रोजेक्ट बनाएँ और Aspose.Slides NuGet पैकेज स्थापित करें। Aspose.Slides लाइब्रेरी के संदर्भ के साथ प्रोजेक्ट संरचना सेट करें।
## चरण 2: प्रस्तुति लोड करें
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 अपनी पावरपॉइंट प्रेजेंटेशन फ़ाइल को इसमें लोड करें`Presentation`ऑब्जेक्ट. "आपकी दस्तावेज़ निर्देशिका" को अपनी फ़ाइल के वास्तविक पथ से बदलें.
## चरण 3: स्लाइड और आकृतियों तक पहुँचें
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
प्रस्तुति में पहली स्लाइड तक पहुँचें और स्लाइड पर आकृतियों को दर्शाने के लिए एक चर को आरंभीकृत करें।
## चरण 4: आकृतियों के माध्यम से पुनरावृति करें
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // कनेक्टर लाइनों को संभालने के लिए कोड
}
```
कनेक्टर लाइनों की पहचान करने और उन्हें संसाधित करने के लिए स्लाइड पर प्रत्येक आकृति को लूप करें।
## चरण 5: कनेक्टर लाइन कोण समायोजित करें
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // ऑटोशेप्स को संभालने के लिए कोड
}
else if (shape is Connector)
{
    // कनेक्टर्स को संभालने के लिए कोड
}
Console.WriteLine(dir);
```
 पहचान करें कि आकृति ऑटोशेप है या कनेक्टर, तथा दिए गए निर्देशों का उपयोग करके कनेक्टर लाइन कोण समायोजित करें।`getDirection` तरीका।
##  चरण 6: परिभाषित करें`getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // दिशा की गणना के लिए कोड
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
 कार्यान्वयन`getDirection` कनेक्टर लाइन के आयाम और अभिविन्यास के आधार पर उसके कोण की गणना करने की विधि।
## निष्कर्ष
इन चरणों के साथ, आप Aspose.Slides for .NET का उपयोग करके अपने PowerPoint प्रेजेंटेशन में कनेक्टर लाइन कोणों को प्रोग्रामेटिक रूप से समायोजित कर सकते हैं। यह ट्यूटोरियल आपकी स्लाइड्स की दृश्य अपील को बढ़ाने के लिए एक आधार प्रदान करता है।
## पूछे जाने वाले प्रश्न
### क्या Aspose.Slides विंडोज़ और वेब अनुप्रयोगों दोनों के लिए उपयुक्त है?
हां, Aspose.Slides का उपयोग विंडोज़ और वेब अनुप्रयोगों दोनों में किया जा सकता है।
### क्या मैं खरीदने से पहले Aspose.Slides का निःशुल्क परीक्षण डाउनलोड कर सकता हूँ?
 हां, आप एक निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for .NET के लिए व्यापक दस्तावेज़ कहां पा सकता हूं?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/slides/net/).
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या Aspose.Slides के लिए कोई सहायता मंच है?
 हां, आप सहायता फ़ोरम पर जा सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).