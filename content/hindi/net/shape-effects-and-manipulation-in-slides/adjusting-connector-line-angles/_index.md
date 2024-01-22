---
title: Aspose.Slides के साथ PowerPoint में कनेक्टर लाइन कोण समायोजित करें
linktitle: Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में कनेक्टर लाइन कोणों को समायोजित करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड में कनेक्टर लाइन कोणों को समायोजित करना सीखें। अपनी प्रस्तुतियों को सटीकता और सहजता से बढ़ाएं।
type: docs
weight: 28
url: /hi/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---
## परिचय
देखने में आकर्षक प्रेजेंटेशन स्लाइड बनाने में अक्सर कनेक्टर लाइनों का सटीक समायोजन शामिल होता है। इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में कनेक्टर लाइन कोणों को कैसे समायोजित किया जाए। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को PowerPoint फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है, प्रस्तुतियों को बनाने, संशोधित करने और हेरफेर करने के लिए व्यापक क्षमताएं प्रदान करती है।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- विज़ुअल स्टूडियो या कोई अन्य C# विकास वातावरण स्थापित।
-  .NET लाइब्रेरी के लिए Aspose.Slides। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- कनेक्टर लाइनों के साथ एक PowerPoint प्रस्तुति फ़ाइल जिसे आप समायोजित करना चाहते हैं।
## नामस्थान आयात करें
आरंभ करने के लिए, अपने C# कोड में आवश्यक नामस्थान शामिल करना सुनिश्चित करें:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
विजुअल स्टूडियो में एक नया C# प्रोजेक्ट बनाएं और Aspose.Slides NuGet पैकेज इंस्टॉल करें। Aspose.Slides लाइब्रेरी के संदर्भ में प्रोजेक्ट संरचना सेट करें।
## चरण 2: प्रस्तुति लोड करें
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 अपनी पावरपॉइंट प्रेजेंटेशन फ़ाइल को इसमें लोड करें`Presentation`वस्तु। "आपकी दस्तावेज़ निर्देशिका" को अपनी फ़ाइल के वास्तविक पथ से बदलें।
## चरण 3: स्लाइड और आकृतियों तक पहुंचें
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
प्रेजेंटेशन में पहली स्लाइड तक पहुंचें और स्लाइड पर आकृतियों को दर्शाने के लिए एक वेरिएबल को इनिशियलाइज़ करें।
## चरण 4: आकृतियों के माध्यम से पुनरावृति करें
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // कनेक्टर लाइनों को संभालने के लिए कोड
}
```
कनेक्टर लाइनों को पहचानने और संसाधित करने के लिए स्लाइड पर प्रत्येक आकृति के माध्यम से लूप करें।
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
 पहचानें कि आकार ऑटोशेप है या कनेक्टर, और दिए गए का उपयोग करके कनेक्टर लाइन कोणों को समायोजित करें`getDirection` तरीका।
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
 लागू करें`getDirection` इसके आयामों और अभिविन्यास के आधार पर कनेक्टर लाइन के कोण की गणना करने की विधि।
## निष्कर्ष
इन चरणों के साथ, आप .NET के लिए Aspose.Slides का उपयोग करके अपने PowerPoint प्रस्तुति में कनेक्टर लाइन कोणों को प्रोग्रामेटिक रूप से समायोजित कर सकते हैं। यह ट्यूटोरियल आपकी स्लाइड की दृश्य अपील को बढ़ाने के लिए आधार प्रदान करता है।
## पूछे जाने वाले प्रश्न
### क्या Aspose.Slides विंडोज़ और वेब एप्लिकेशन दोनों के लिए उपयुक्त है?
हां, Aspose.Slides का उपयोग विंडोज़ और वेब एप्लिकेशन दोनों में किया जा सकता है।
### क्या मैं खरीदने से पहले Aspose.Slides का निःशुल्क परीक्षण डाउनलोड कर सकता हूँ?
 हाँ, आप निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे .NET के लिए Aspose.Slides के लिए व्यापक दस्तावेज़ कहाँ मिल सकते हैं?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/slides/net/).
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आपको अस्थायी लाइसेंस मिल सकता है[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या Aspose.Slides के लिए कोई सहायता मंच है?
 हाँ, आप सहायता फ़ोरम पर जा सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).