---
title: .NET के लिए Aspose.Slides के साथ प्रस्तुतियों में 3D रोटेशन में महारत हासिल करें
linktitle: प्रेजेंटेशन स्लाइड्स में आकृतियों पर 3D रोटेशन प्रभाव लागू करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ! इस ट्यूटोरियल में आकृतियों पर 3D रोटेशन प्रभाव लागू करना सीखें। गतिशील और दिखने में शानदार प्रस्तुति बनाएँ।
weight: 23
url: /hi/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
आकर्षक और गतिशील प्रस्तुति स्लाइड बनाना प्रभावी संचार का एक महत्वपूर्ण पहलू है। Aspose.Slides for .NET आपके प्रस्तुतियों को बेहतर बनाने के लिए उपकरणों का एक शक्तिशाली सेट प्रदान करता है, जिसमें आकृतियों पर 3D रोटेशन प्रभाव लागू करने की क्षमता भी शामिल है। इस ट्यूटोरियल में, हम Aspose.Slides for .NET का उपयोग करके प्रस्तुति स्लाइड में आकृतियों पर 3D रोटेशन प्रभाव लागू करने की प्रक्रिया के बारे में जानेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास .NET के लिए Aspose.Slides लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/slides/net/).
- विकास परिवेश: अपना कोड लिखने और चलाने के लिए Visual Studio जैसे .NET विकास परिवेश को सेट करें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.Slides की कार्यक्षमता का लाभ उठाने के लिए आवश्यक नेमस्पेस आयात करें। अपने कोड की शुरुआत में निम्नलिखित नेमस्पेस शामिल करें:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा .NET डेवलपमेंट वातावरण में एक नया प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपने अपने प्रोजेक्ट में Aspose.Slides संदर्भ जोड़ा है।
## चरण 2: प्रस्तुति आरंभ करें
स्लाइडों के साथ काम करना शुरू करने के लिए प्रेजेंटेशन क्लास को इंस्टैंसिएट करें:
```csharp
Presentation pres = new Presentation();
```
## चरण 3: ऑटोशेप जोड़ें
स्लाइड में ऑटोशेप जोड़ें, उसका प्रकार, स्थिति और आयाम निर्दिष्ट करें:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## चरण 4: 3D रोटेशन प्रभाव सेट करें
ऑटोशेप के लिए 3D रोटेशन प्रभाव कॉन्फ़िगर करें:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## चरण 5: प्रस्तुति सहेजें
लागू 3D रोटेशन प्रभाव के साथ संशोधित प्रस्तुति को सहेजें:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## चरण 6: अन्य आकृतियों के लिए दोहराएं
यदि आपके पास अतिरिक्त आकृतियाँ हैं, तो प्रत्येक आकृति के लिए चरण 3 से 5 दोहराएँ।
## निष्कर्ष
अपनी प्रेजेंटेशन स्लाइड्स में आकृतियों में 3D रोटेशन इफ़ेक्ट जोड़ने से उनकी दृश्य अपील में उल्लेखनीय वृद्धि हो सकती है। Aspose.Slides for .NET के साथ, यह प्रक्रिया सरल हो जाती है, जिससे आप आकर्षक प्रेजेंटेशन बना सकते हैं।
## पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides for .NET में टेक्स्ट बॉक्स पर 3D रोटेशन लागू कर सकता हूँ?
हां, आप Aspose.Slides का उपयोग करके टेक्स्ट बॉक्स सहित विभिन्न आकृतियों पर 3D रोटेशन प्रभाव लागू कर सकते हैं।
### क्या .NET के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप परीक्षण संस्करण तक पहुंच सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Slides का समर्थन कैसे प्राप्त कर सकता हूं?
 दौरा करना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन और चर्चा के लिए।
### क्या मैं Aspose.Slides for .NET के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides for .NET के लिए विस्तृत दस्तावेज़ कहां पा सकता हूं?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
