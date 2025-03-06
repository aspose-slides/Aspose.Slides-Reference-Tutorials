---
title: Aspose.Slides के साथ आश्चर्यजनक स्केच्ड आकृतियाँ बनाएँ
linktitle: Aspose.Slides के साथ प्रेजेंटेशन स्लाइड में स्केच्ड आकृतियाँ बनाना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET का उपयोग करके अपनी प्रस्तुति स्लाइड में रचनात्मक स्केच किए गए आकार जोड़ना सीखें। दृश्य अपील को सहजता से बढ़ाएँ!
weight: 13
url: /hi/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides के साथ आश्चर्यजनक स्केच्ड आकृतियाँ बनाएँ

## परिचय
Aspose.Slides for .NET का उपयोग करके प्रेजेंटेशन स्लाइड में स्केच किए गए आकार बनाने के बारे में हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। यदि आप अपनी प्रस्तुतियों में रचनात्मकता का स्पर्श जोड़ना चाहते हैं, तो स्केच किए गए आकार एक अद्वितीय और हाथ से तैयार किए गए सौंदर्य प्रदान करते हैं। इस ट्यूटोरियल में, हम आपको प्रक्रिया के माध्यम से चलेंगे, इसे एक सहज अनुभव सुनिश्चित करने के लिए सरल चरणों में विभाजित करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
-  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास .NET के लिए Aspose.Slides लाइब्रेरी स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- विकास वातावरण: अपने पसंदीदा IDE के साथ .NET विकास वातावरण सेट करें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में आवश्यक नेमस्पेस आयात करके शुरू करें। यह चरण सुनिश्चित करता है कि आपके पास Aspose.Slides के साथ काम करने के लिए आवश्यक क्लासेस और कार्यक्षमताओं तक पहुँच है।
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
## चरण 1: प्रोजेक्ट सेट अप करें
एक नया .NET प्रोजेक्ट बनाकर या किसी मौजूदा प्रोजेक्ट को खोलकर शुरुआत करें। अपने प्रोजेक्ट संदर्भों में Aspose.Slides को शामिल करना सुनिश्चित करें।
## चरण 2: Aspose.Slides को आरंभ करें
निम्नलिखित कोड स्निपेट जोड़कर Aspose.Slides को आरंभ करें। यह प्रेजेंटेशन सेट करता है और प्रेजेंटेशन फ़ाइल और थंबनेल इमेज के लिए आउटपुट पथ निर्दिष्ट करता है।
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // अगले चरण पर आगे बढ़ें...
}
```
## चरण 3: स्केच की गई आकृति जोड़ें
अब, आइए स्लाइड में एक स्केच की गई आकृति जोड़ें। इस उदाहरण में, हम एक फ्रीहैंड स्केच प्रभाव के साथ एक आयत जोड़ेंगे।
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// आकृति को मुक्तहस्त शैली के रेखाचित्र में बदलें
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## चरण 4: थंबनेल उत्पन्न करें
स्केच की गई आकृति को देखने के लिए स्लाइड का थंबनेल बनाएं। थंबनेल को PNG फ़ाइल के रूप में सेव करें।
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## चरण 5: प्रस्तुति सहेजें
प्रस्तुतीकरण फ़ाइल को रेखाचित्रित आकृति के साथ सहेजें।
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
बस! आपने Aspose.Slides for .NET का उपयोग करके स्केच की गई आकृतियों के साथ सफलतापूर्वक एक प्रस्तुति बना ली है।
## निष्कर्ष
अपनी प्रस्तुति स्लाइड में स्केच किए गए आकार जोड़ने से दृश्य अपील बढ़ सकती है और आपके दर्शकों को आकर्षित कर सकती है। .NET के लिए Aspose.Slides के साथ, प्रक्रिया सरल हो जाती है, जिससे आप अपनी रचनात्मकता को सहजता से उजागर कर सकते हैं।
## पूछे जाने वाले प्रश्न
### 1. क्या मैं स्केच किए गए प्रभाव को अनुकूलित कर सकता हूँ?
 हां, Aspose.Slides for .NET स्केच किए गए प्रभावों के लिए विभिन्न अनुकूलन विकल्प प्रदान करता है।[प्रलेखन](https://reference.aspose.com/slides/net/) विस्तृत जानकारी के लिए.
### 2. क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 ज़रूर! आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण आज़मा सकते हैं[यहाँ](https://releases.aspose.com/).
### 3. मुझे सहायता कहां मिल सकती है?
 किसी भी सहायता या प्रश्न के लिए, कृपया यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### 4. मैं .NET के लिए Aspose.Slides कैसे खरीद सकता हूँ?
 .NET के लिए Aspose.Slides खरीदने के लिए, यहां जाएं[खरीद पृष्ठ](https://purchase.aspose.com/buy).
### 5. क्या आप अस्थायी लाइसेंस प्रदान करते हैं?
 हां, अस्थायी लाइसेंस उपलब्ध हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
