---
title: Aspose.Slides के साथ आश्चर्यजनक रेखाचित्र आकृतियाँ बनाएँ
linktitle: Aspose.Slides के साथ प्रेजेंटेशन स्लाइड्स में स्केच्ड आकृतियाँ बनाना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके अपनी प्रेजेंटेशन स्लाइड्स में रचनात्मक स्केच किए गए आकार जोड़ने का तरीका जानें। सहजता से दृश्य अपील बढ़ाएँ!
type: docs
weight: 13
url: /hi/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## परिचय
.NET के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में स्केच की गई आकृतियाँ बनाने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। यदि आप अपनी प्रस्तुतियों में रचनात्मकता का स्पर्श जोड़ना चाहते हैं, तो स्केच की गई आकृतियाँ एक अद्वितीय और हाथ से बनाई गई सुंदरता प्रदान करती हैं। इस ट्यूटोरियल में, हम आपको एक सहज अनुभव सुनिश्चित करने के लिए प्रक्रिया के बारे में बताएंगे, इसे सरल चरणों में विभाजित करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास .NET के लिए Aspose.Slides लाइब्रेरी स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- विकास परिवेश: अपने पसंदीदा IDE के साथ एक .NET विकास परिवेश स्थापित करें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में आवश्यक नामस्थान आयात करके प्रारंभ करें। यह चरण सुनिश्चित करता है कि आपके पास Aspose.Slides के साथ काम करने के लिए आवश्यक कक्षाओं और कार्यात्मकताओं तक पहुंच है।
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## चरण 1: प्रोजेक्ट सेट करें
एक नया .NET प्रोजेक्ट बनाकर या किसी मौजूदा को खोलकर शुरुआत करें। अपने प्रोजेक्ट संदर्भों में Aspose.Slides को शामिल करना सुनिश्चित करें।
## चरण 2: Aspose.Slides को आरंभ करें
निम्नलिखित कोड स्निपेट जोड़कर Aspose.Slides को प्रारंभ करें। यह प्रेजेंटेशन सेट करता है और प्रेजेंटेशन फ़ाइल और थंबनेल छवि के लिए आउटपुट पथ निर्दिष्ट करता है।
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // अगले चरणों पर जारी रखें...
}
```
## चरण 3: स्केच्ड आकृति जोड़ें
अब, स्लाइड में एक स्केच की गई आकृति जोड़ें। इस उदाहरण में, हम फ्रीहैंड स्केच प्रभाव के साथ एक आयत जोड़ेंगे।
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// मुक्तहस्त शैली के स्केच में आकार बदलें
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## चरण 4: थंबनेल जनरेट करें
स्केच की गई आकृति को देखने के लिए स्लाइड का एक थंबनेल बनाएं। थंबनेल को पीएनजी फ़ाइल के रूप में सहेजें।
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## चरण 5: प्रस्तुति सहेजें
प्रेजेंटेशन फ़ाइल को स्केच किए गए आकार के साथ सहेजें।
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
इतना ही! आपने .NET के लिए Aspose.Slides का उपयोग करके स्केच की गई आकृतियों के साथ सफलतापूर्वक एक प्रस्तुति बनाई है।
## निष्कर्ष
अपनी प्रेजेंटेशन स्लाइड में स्केच की गई आकृतियाँ जोड़ने से दृश्य अपील बढ़ सकती है और आपके दर्शक आकर्षित हो सकते हैं। .NET के लिए Aspose.Slides के साथ, प्रक्रिया सीधी हो जाती है, जिससे आप अपनी रचनात्मकता को सहजता से उजागर कर सकते हैं।
## पूछे जाने वाले प्रश्न
### 1. क्या मैं स्केच किए गए प्रभाव को अनुकूलित कर सकता हूँ?
हां, .NET के लिए Aspose.Slides स्केच किए गए प्रभावों के लिए विभिन्न अनुकूलन विकल्प प्रदान करता है। को देखें[प्रलेखन](https://reference.aspose.com/slides/net/) विस्तृत जानकारी के लिए.
### 2. क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 निश्चित रूप से! आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण देख सकते हैं[यहाँ](https://releases.aspose.com/).
### 3. मुझे सहायता कहाँ से मिल सकती है?
 किसी भी सहायता या प्रश्न के लिए, पर जाएँ[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11).
### 4. मैं .NET के लिए Aspose.Slides कैसे खरीद सकता हूँ?
 .NET के लिए Aspose.Slides खरीदने के लिए, पर जाएँ[खरीद पृष्ठ](https://purchase.aspose.com/buy).
### 5. क्या आप अस्थायी लाइसेंस प्रदान करते हैं?
 हाँ, अस्थायी लाइसेंस उपलब्ध हैं[यहाँ](https://purchase.aspose.com/temporary-license/).