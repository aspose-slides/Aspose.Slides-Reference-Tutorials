---
title: पावरपॉइंट प्रस्तुतियों में छवि भरने के लिए स्ट्रेच ऑफसेट जोड़ना
linktitle: स्लाइड्स में छवि भरने के लिए स्ट्रेच ऑफसेट जोड़ना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Slides के साथ PowerPoint प्रस्तुतियों को कैसे बढ़ाया जाए। छवि भरण के लिए स्ट्रेच ऑफसेट जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 18
url: /hi/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---
## परिचय
प्रस्तुतियों की गतिशील दुनिया में, दृश्य दर्शकों का ध्यान खींचने में महत्वपूर्ण भूमिका निभाते हैं। .NET के लिए Aspose.Slides सुविधाओं का एक मजबूत सेट प्रदान करके डेवलपर्स को अपनी PowerPoint प्रस्तुतियों को बढ़ाने का अधिकार देता है। ऐसी एक सुविधा छवि भरण के लिए स्ट्रेच ऑफसेट जोड़ने की क्षमता है, जो रचनात्मक और दृश्यमान रूप से आकर्षक स्लाइड की अनुमति देती है।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET लाइब्रेरी के लिए Aspose.Slides: लाइब्रेरी को डाउनलोड और इंस्टॉल करें[.NET दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास एक कार्यशील .NET विकास परिवेश स्थापित है।
अब, आइए चरण-दर-चरण मार्गदर्शिका के साथ शुरुआत करें।
## नामस्थान आयात करें
सबसे पहले, अपने .NET एप्लिकेशन के भीतर Aspose.Slides कार्यक्षमता का लाभ उठाने के लिए आवश्यक नामस्थान आयात करें।
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा विकास परिवेश में एक नया .NET प्रोजेक्ट बनाएं। सुनिश्चित करें कि .NET के लिए Aspose.Slides उचित रूप से संदर्भित है।
## चरण 2: प्रेजेंटेशन क्लास आरंभ करें
 त्वरित करें`Presentation` PowerPoint फ़ाइल का प्रतिनिधित्व करने के लिए क्लास।
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // आपका कोड यहां जाता है
}
```
## चरण 3: पहली स्लाइड प्राप्त करें
काम करने के लिए प्रेजेंटेशन से पहली स्लाइड पुनः प्राप्त करें।
```csharp
ISlide sld = pres.Slides[0];
```
## चरण 4: ImageEx क्लास को त्वरित करें
 का एक उदाहरण बनाएं`ImageEx` उस छवि को संभालने के लिए क्लास जिसे आप स्लाइड में जोड़ना चाहते हैं।
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## चरण 5: चित्र फ़्रेम जोड़ें
 का उपयोग करें`AddPictureFrame` स्लाइड में चित्र फ़्रेम जोड़ने की विधि। फ़्रेम के आयाम और स्थिति निर्दिष्ट करें.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## चरण 6: प्रस्तुति सहेजें
संशोधित प्रस्तुति को डिस्क पर सहेजें।
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
इतना ही! आपने .NET के लिए Aspose.Slides का उपयोग करके स्लाइड्स में छवि भरने के लिए एक स्ट्रेच ऑफसेट सफलतापूर्वक जोड़ा है।
## निष्कर्ष
.NET के लिए Aspose.Slides के साथ अपनी PowerPoint प्रस्तुतियों को बढ़ाना अब पहले से कहीं अधिक आसान है। इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि छवि भरण के लिए स्ट्रेच ऑफसेट को कैसे शामिल किया जाए, जिससे आपकी स्लाइड में रचनात्मकता का एक नया स्तर आए।
## पूछे जाने वाले प्रश्न
### क्या मैं अपने वेब अनुप्रयोगों में .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हाँ, .NET के लिए Aspose.Slides डेस्कटॉप और वेब अनुप्रयोगों दोनों के लिए उपयुक्त है।
### क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 दौरा करना[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन के लिए.
### मुझे .NET के लिए Aspose.Slides का संपूर्ण दस्तावेज़ कहां मिल सकता है?
 को देखें[प्रलेखन](https://reference.aspose.com/slides/net/) विस्तृत जानकारी के लिए.
### क्या मैं .NET के लिए Aspose.Slides खरीद सकता हूँ?
 हां, आप उत्पाद खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).