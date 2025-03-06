---
title: पावरपॉइंट प्रेजेंटेशन में इमेज भरने के लिए स्ट्रेच ऑफसेट जोड़ना
linktitle: स्लाइड्स में छवि भरने के लिए स्ट्रेच ऑफ़सेट जोड़ना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: जानें कि Aspose.Slides for .NET के साथ PowerPoint प्रेजेंटेशन को कैसे बेहतर बनाया जाए। इमेज फ़िल के लिए स्ट्रेच ऑफ़सेट जोड़ने के लिए चरण-दर-चरण गाइड का पालन करें।
weight: 18
url: /hi/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# पावरपॉइंट प्रेजेंटेशन में इमेज भरने के लिए स्ट्रेच ऑफसेट जोड़ना

## परिचय
प्रस्तुतियों की गतिशील दुनिया में, दृश्य दर्शकों का ध्यान आकर्षित करने में महत्वपूर्ण भूमिका निभाते हैं। Aspose.Slides for .NET डेवलपर्स को कई बेहतरीन सुविधाएँ प्रदान करके अपने PowerPoint प्रस्तुतियों को बेहतर बनाने में सक्षम बनाता है। ऐसी ही एक विशेषता है छवि भरने के लिए स्ट्रेच ऑफ़सेट जोड़ने की क्षमता, जो रचनात्मक और आकर्षक स्लाइड बनाने की अनुमति देती है।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1.  Aspose.Slides for .NET लाइब्रेरी: लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[.NET दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास एक कार्यशील .NET विकास परिवेश स्थापित है।
अब, आइए चरण-दर-चरण मार्गदर्शिका से शुरुआत करें।
## नामस्थान आयात करें
सबसे पहले, अपने .NET अनुप्रयोग के भीतर Aspose.Slides कार्यक्षमता का लाभ उठाने के लिए आवश्यक नामस्थान आयात करें।
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा डेवलपमेंट एनवायरनमेंट में एक नया .NET प्रोजेक्ट बनाएँ। सुनिश्चित करें कि Aspose.Slides for .NET का संदर्भ ठीक से दिया गया है।
## चरण 2: प्रेजेंटेशन क्लास आरंभ करें
 उदाहरण प्रस्तुत करें`Presentation` PowerPoint फ़ाइल का प्रतिनिधित्व करने के लिए क्लास का उपयोग करें।
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // आपका कोड यहां जाएगा
}
```
## चरण 3: पहली स्लाइड प्राप्त करें
कार्य करने के लिए प्रस्तुति से पहली स्लाइड प्राप्त करें।
```csharp
ISlide sld = pres.Slides[0];
```
## चरण 4: ImageEx क्लास को तत्कालित करें
 इसका एक उदाहरण बनाएं`ImageEx`उस छवि को संभालने के लिए क्लास का उपयोग करें जिसे आप स्लाइड में जोड़ना चाहते हैं।
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## चरण 5: चित्र फ़्रेम जोड़ें
 उपयोग करें`AddPictureFrame` स्लाइड में पिक्चर फ्रेम जोड़ने की विधि। फ्रेम के आयाम और स्थिति निर्दिष्ट करें।
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## चरण 6: प्रेजेंटेशन सहेजें
संशोधित प्रस्तुति को डिस्क पर सहेजें.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
बस! आपने Aspose.Slides for .NET का उपयोग करके स्लाइड्स में छवि भरने के लिए स्ट्रेच ऑफ़सेट सफलतापूर्वक जोड़ लिया है।
## निष्कर्ष
Aspose.Slides for .NET के साथ अपने PowerPoint प्रेजेंटेशन को बेहतर बनाना अब पहले से कहीं ज़्यादा आसान हो गया है। इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि इमेज फ़िल के लिए स्ट्रेच ऑफ़सेट को कैसे शामिल किया जाए, जिससे आपकी स्लाइड्स में रचनात्मकता का एक नया स्तर आए।
## पूछे जाने वाले प्रश्न
### क्या मैं अपने वेब अनुप्रयोगों में .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, Aspose.Slides for .NET डेस्कटॉप और वेब अनुप्रयोगों दोनों के लिए उपयुक्त है।
### क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Slides का समर्थन कैसे प्राप्त कर सकता हूं?
 दौरा करना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन के लिए.
### मैं Aspose.Slides for .NET का संपूर्ण दस्तावेज़ कहां पा सकता हूं?
 को देखें[प्रलेखन](https://reference.aspose.com/slides/net/) विस्तृत जानकारी के लिए.
### क्या मैं .NET के लिए Aspose.Slides खरीद सकता हूँ?
 हां, आप उत्पाद खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
