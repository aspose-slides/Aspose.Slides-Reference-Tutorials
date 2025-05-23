---
"description": "जानें कि Aspose.Slides for .NET का उपयोग करके PowerPoint प्रस्तुतियों को कैसे बेहतर बनाया जाए। पिक्चर फ्रेम के लिए बाईं ओर स्ट्रेच ऑफ़सेट जोड़ने के लिए हमारे चरण-दर-चरण गाइड का पालन करें।"
"linktitle": "Aspose.Slides में पिक्चर फ्रेम के लिए बाईं ओर स्ट्रेच ऑफसेट जोड़ना"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "Aspose.Slide के साथ PowerPoint में बाईं ओर स्ट्रेच ऑफसेट जोड़ना"
"url": "/hi/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slide के साथ PowerPoint में बाईं ओर स्ट्रेच ऑफसेट जोड़ना

## परिचय
Aspose.Slides for .NET एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को PowerPoint प्रस्तुतियों को आसानी से हेरफेर करने में सक्षम बनाती है। इस ट्यूटोरियल में, हम Aspose.Slides for .NET का उपयोग करके चित्र फ़्रेम के लिए बाईं ओर एक स्ट्रेच ऑफ़सेट जोड़ने की प्रक्रिया का पता लगाएंगे। PowerPoint प्रस्तुतियों के भीतर छवियों और आकृतियों के साथ काम करने में अपने कौशल को बढ़ाने के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- Aspose.Slides for .NET: सुनिश्चित करें कि आपके पास लाइब्रेरी स्थापित है। यदि नहीं, तो इसे यहाँ से डाउनलोड करें [.NET दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/net/).
- विकास परिवेश: .NET क्षमताओं के साथ कार्यशील विकास परिवेश रखें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में आवश्यक नामस्थानों को आयात करके आरंभ करें:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
एक नया प्रोजेक्ट बनाएँ या मौजूदा प्रोजेक्ट खोलें। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides लाइब्रेरी का संदर्भ दिया गया है।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट बनाएँ
उदाहरण प्रस्तुत करें `Presentation` क्लास, जो PPTX फ़ाइल का प्रतिनिधित्व करता है:
```csharp
using (Presentation pres = new Presentation())
{
    // अगले चरणों के लिए आपका कोड यहां जाएगा।
}
```
## चरण 3: पहली स्लाइड प्राप्त करें
प्रस्तुति से पहली स्लाइड प्राप्त करें:
```csharp
ISlide slide = pres.Slides[0];
```
## चरण 4: छवि को तत्कालित करें
वह छवि लोड करें जिसका आप उपयोग करना चाहते हैं:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## चरण 5: आयत ऑटोशेप जोड़ें
आयत प्रकार का एक ऑटोशेप बनाएँ:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## चरण 6: भरण प्रकार और चित्र भरण मोड सेट करें
आकृति का भरण प्रकार और चित्र भरण मोड कॉन्फ़िगर करें:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## चरण 7: आकृति को भरने के लिए छवि सेट करें
आकृति को भरने के लिए छवि निर्दिष्ट करें:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## चरण 8: स्ट्रेच ऑफसेट निर्दिष्ट करें
आकृति के बाउंडिंग बॉक्स के संगत किनारों से छवि ऑफसेट को परिभाषित करें:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## चरण 9: प्रस्तुति सहेजें
PPTX फ़ाइल को डिस्क पर लिखें:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके चित्र फ़्रेम के लिए बाईं ओर एक स्ट्रेच ऑफ़सेट सफलतापूर्वक जोड़ लिया है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में पिक्चर फ़्रेम में हेरफेर करने की प्रक्रिया का पता लगाया। चरण-दर-चरण मार्गदर्शिका का पालन करके, आपने छवियों, आकृतियों और ऑफ़सेट के साथ काम करने में अंतर्दृष्टि प्राप्त की है।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं आयतों के अलावा अन्य आकृतियों पर भी स्ट्रेच ऑफसेट लागू कर सकता हूँ?
उत्तर: जबकि यह ट्यूटोरियल आयतों पर केंद्रित है, स्ट्रेच ऑफसेट को Aspose.Slides द्वारा समर्थित विभिन्न आकृतियों पर लागू किया जा सकता है।
### प्रश्न: मैं विभिन्न प्रभावों के लिए स्ट्रेच ऑफसेट को कैसे समायोजित कर सकता हूं?
उत्तर: वांछित दृश्य प्रभाव प्राप्त करने के लिए विभिन्न ऑफसेट मानों के साथ प्रयोग करें। अपनी विशिष्ट आवश्यकताओं के अनुरूप मानों को ठीक करें।
### प्रश्न: क्या Aspose.Slides नवीनतम .NET फ्रेमवर्क के साथ संगत है?
उत्तर: Aspose.Slides को नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगतता सुनिश्चित करने के लिए नियमित रूप से अपडेट किया जाता है।
### प्रश्न: मैं Aspose.Slides के लिए अतिरिक्त उदाहरण और संसाधन कहां पा सकता हूं?
उत्तर: अन्वेषण करें [Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/) विस्तृत उदाहरण और मार्गदर्शन के लिए.
### प्रश्न: क्या मैं एक ही आकृति पर एकाधिक स्ट्रेच ऑफसेट लागू कर सकता हूँ?
उत्तर: हां, आप जटिल और अनुकूलित दृश्य प्रभाव प्राप्त करने के लिए कई स्ट्रेच ऑफसेट को संयोजित कर सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}