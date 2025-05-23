---
"description": "Aspose.Slides for .NET में सापेक्ष स्केल ऊंचाई के साथ पिक्चर फ़्रेम जोड़ना सीखें। निर्बाध प्रस्तुतियों के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"linktitle": "Aspose.Slides में सापेक्ष स्केल ऊंचाई के साथ चित्र फ़्रेम जोड़ना"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "Aspose.Slides .NET के साथ पिक्चर फ्रेम्स जोड़ना ट्यूटोरियल"
"url": "/hi/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET के साथ पिक्चर फ्रेम्स जोड़ना ट्यूटोरियल

## परिचय
Aspose.Slides for .NET एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को अपने .NET अनुप्रयोगों में आसानी से PowerPoint प्रस्तुतियाँ बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। इस ट्यूटोरियल में, हम Aspose.Slides for .NET का उपयोग करके सापेक्ष स्केल ऊँचाई के साथ चित्र फ़्रेम जोड़ने की प्रक्रिया में गोता लगाएँगे। अपने प्रस्तुति-निर्माण कौशल को बढ़ाने के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- विजुअल स्टूडियो या कोई अन्य पसंदीदा C# विकास वातावरण स्थापित होना चाहिए।
- Aspose.Slides for .NET लाइब्रेरी आपके प्रोजेक्ट में जोड़ दी गई।
## नामस्थान आयात करें
अपने C# कोड में आवश्यक नेमस्पेस को आयात करके शुरू करें। यह चरण सुनिश्चित करता है कि आपके पास Aspose.Slides लाइब्रेरी द्वारा प्रदान की गई कक्षाओं और कार्यक्षमताओं तक पहुँच है।
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा डेवलपमेंट एनवायरनमेंट में एक नया C# प्रोजेक्ट बनाकर शुरुआत करें। अपने प्रोजेक्ट में Aspose.Slides for .NET लाइब्रेरी को संदर्भित करके जोड़ना सुनिश्चित करें।
## चरण 2: प्रस्तुति और छवि लोड करें
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // प्रस्तुति छवि संग्रह में जोड़ने के लिए छवि लोड करें
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
इस चरण में, हम एक नया प्रेजेंटेशन ऑब्जेक्ट बनाते हैं और उस छवि को लोड करते हैं जिसे हम प्रेजेंटेशन में जोड़ना चाहते हैं।
## चरण 3: स्लाइड में चित्र फ़्रेम जोड़ें
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
अब, प्रेजेंटेशन की पहली स्लाइड में एक पिक्चर फ्रेम जोड़ें। अपनी आवश्यकताओं के अनुसार आकार प्रकार, स्थिति और आयाम जैसे मापदंडों को समायोजित करें।
## चरण 4: सापेक्ष स्केल चौड़ाई और ऊंचाई सेट करें
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
वांछित स्केलिंग प्रभाव प्राप्त करने के लिए चित्र फ़्रेम के लिए सापेक्ष स्केल ऊंचाई और चौड़ाई सेट करें।
## चरण 5: प्रस्तुति सहेजें
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
अंत में, निर्दिष्ट आउटपुट प्रारूप में जोड़े गए चित्र फ़्रेम के साथ प्रस्तुति को सहेजें।
## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि Aspose.Slides for .NET का उपयोग करके सापेक्ष स्केल ऊंचाई के साथ चित्र फ़्रेम कैसे जोड़ें। अपनी ज़रूरतों के अनुसार आकर्षक प्रस्तुतिकरण बनाने के लिए अलग-अलग छवियों, स्थितियों और स्केल के साथ प्रयोग करें।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
Aspose.Slides मुख्य रूप से .NET भाषाओं का समर्थन करता है, लेकिन आप विभिन्न प्लेटफार्मों के साथ संगतता के लिए अन्य Aspose उत्पादों का पता लगा सकते हैं।
### मैं Aspose.Slides for .NET के लिए विस्तृत दस्तावेज़ कहां पा सकता हूं?
देखें [प्रलेखन](https://reference.aspose.com/slides/net/) विस्तृत जानकारी और उदाहरण के लिए.
### क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
हाँ, आप प्राप्त कर सकते हैं [मुफ्त परीक्षण](https://releases.aspose.com/) पुस्तकालय की क्षमताओं का मूल्यांकन करने के लिए।
### मैं .NET के लिए Aspose.Slides का समर्थन कैसे प्राप्त कर सकता हूं?
दौरा करना [Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) समुदाय और Aspose विशेषज्ञों से सहायता प्राप्त करने के लिए।
### मैं .NET के लिए Aspose.Slides कहां से खरीद सकता हूं?
आप .NET के लिए Aspose.Slides यहाँ से खरीद सकते हैं। [खरीद पृष्ठ](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}