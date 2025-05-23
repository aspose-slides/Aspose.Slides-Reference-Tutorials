---
"description": ".NET के लिए Aspose.Slides का उपयोग करके विशिष्ट सीमाओं के साथ PowerPoint थंबनेल छवियाँ बनाना सीखें। सहज एकीकरण के लिए हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"linktitle": "Aspose.Slides में आकृति के लिए स्केलिंग फैक्टर के साथ थंबनेल बनाना"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "Aspose.Slides में आकृति के लिए स्केलिंग फैक्टर के साथ थंबनेल बनाना"
"url": "/hi/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides में आकृति के लिए स्केलिंग फैक्टर के साथ थंबनेल बनाना

## परिचय
.NET के लिए Aspose.Slides में आकृतियों के लिए सीमाओं के साथ थंबनेल बनाने पर हमारी विस्तृत मार्गदर्शिका में आपका स्वागत है। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों में PowerPoint प्रस्तुतियों के साथ सहजता से काम करने में सक्षम बनाती है। इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके किसी प्रस्तुति के भीतर आकृतियों के लिए विशिष्ट सीमाओं के साथ थंबनेल बनाने की प्रक्रिया में गहराई से उतरेंगे।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास Aspose.Slides लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/net/).
- विकास वातावरण: अपनी मशीन पर .NET के लिए उपयुक्त विकास वातावरण, जैसे कि विजुअल स्टूडियो, स्थापित करें।
## नामस्थान आयात करें
अपने .NET अनुप्रयोग में, Aspose.Slides कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नामस्थानों को आयात करके आरंभ करें:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## चरण 1: प्रस्तुति सेट करें
एक प्रेजेंटेशन क्लास को इंस्टैंशिएट करके शुरू करें जो उस पावरपॉइंट प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है जिसके साथ आप काम करना चाहते हैं:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // थंबनेल बनाने के लिए आपका कोड यहाँ है
}
```
## चरण 2: पूर्ण-पैमाने वाली छवि बनाएँ
प्रस्तुति ब्लॉक के भीतर, उस आकृति की पूर्ण-पैमाने वाली छवि बनाएं जिसके लिए आप थंबनेल बनाना चाहते हैं:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    // छवि को सहेजने के लिए आपका कोड यहां है
}
```
## चरण 3: छवि को डिस्क पर सहेजें
उत्पन्न छवि को डिस्क पर सहेजें, प्रारूप निर्दिष्ट करें (इस मामले में, PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि Aspose.Slides for .NET का उपयोग करके आकृतियों के लिए सीमाओं के साथ थंबनेल कैसे बनाएं। यह सुविधा तब अविश्वसनीय रूप से उपयोगी हो सकती है जब आपको अपने PowerPoint प्रस्तुतियों में आकृतियों की विशिष्ट-आकार की छवियाँ प्रोग्रामेटिक रूप से बनाने की आवश्यकता होती है।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न 1: क्या मैं अन्य .NET फ्रेमवर्क के साथ Aspose.Slides का उपयोग कर सकता हूँ?
हां, Aspose.Slides विभिन्न .NET फ्रेमवर्क के साथ संगत है, जो विभिन्न प्रकार के अनुप्रयोगों में एकीकरण के लिए लचीलापन प्रदान करता है।
### प्रश्न 2: क्या Aspose.Slides के लिए कोई परीक्षण संस्करण उपलब्ध है?
हां, आप परीक्षण संस्करण डाउनलोड करके Aspose.Slides की कार्यक्षमता का पता लगा सकते हैं [यहाँ](https://releases.aspose.com/).
### प्रश्न 3: मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
आप Aspose.Slides के लिए अस्थायी लाइसेंस प्राप्त करने के लिए यहां जा सकते हैं [इस लिंक](https://purchase.aspose.com/temporary-license/).
### प्रश्न 4: मैं Aspose.Slides के लिए अतिरिक्त सहायता कहां पा सकता हूं?
किसी भी प्रश्न या सहायता के लिए, कृपया Aspose.Slides सहायता फ़ोरम पर जाएँ [यहाँ](https://forum.aspose.com/c/slides/11).
### प्रश्न 5: क्या मैं .NET के लिए Aspose.Slides खरीद सकता हूँ?
ज़रूर! .NET के लिए Aspose.Slides खरीदने के लिए, कृपया खरीद पृष्ठ पर जाएँ [यहाँ](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}