---
"description": "Aspose.Slides for .NET का उपयोग करके PowerPoint स्लाइड से ऑडियो और वीडियो निकालना सीखें। सरल मल्टीमीडिया निष्कर्षण।"
"linktitle": "Aspose.Slides का उपयोग करके स्लाइड से ऑडियो और वीडियो निकालना"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": ".NET के लिए Aspose.Slides के साथ ऑडियो और वीडियो निष्कर्षण में महारत हासिल करें"
"url": "/hi/net/audio-and-video-extraction/audio-and-video-extraction/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Slides के साथ ऑडियो और वीडियो निष्कर्षण में महारत हासिल करें


## परिचय

डिजिटल युग में, मल्टीमीडिया प्रस्तुतियाँ संचार, शिक्षा और मनोरंजन का एक अभिन्न अंग बन गई हैं। पावरपॉइंट स्लाइड्स का उपयोग अक्सर जानकारी देने के लिए किया जाता है, और अक्सर उनमें ऑडियो और वीडियो जैसे आवश्यक तत्व शामिल होते हैं। इन तत्वों को निकालना विभिन्न कारणों से महत्वपूर्ण हो सकता है, जिसमें प्रस्तुतियों को संग्रहित करना से लेकर सामग्री को फिर से उपयोग में लाना शामिल है।

इस चरण-दर-चरण मार्गदर्शिका में, हम .NET के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड से ऑडियो और वीडियो निकालने का तरीका जानेंगे। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो .NET डेवलपर्स को PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है, जिससे मल्टीमीडिया निष्कर्षण जैसे कार्य पहले से कहीं अधिक सुलभ हो जाते हैं।

## आवश्यक शर्तें

इससे पहले कि हम पावरपॉइंट स्लाइडों से ऑडियो और वीडियो निकालने के विवरण में उतरें, कुछ पूर्वापेक्षाएँ हैं जो आपके पास होनी चाहिए:

1. विज़ुअल स्टूडियो: सुनिश्चित करें कि .NET विकास के लिए आपके मशीन पर विज़ुअल स्टूडियो स्थापित है।

2. Aspose.Slides for .NET: Aspose.Slides for .NET डाउनलोड करें और इंस्टॉल करें। आप लाइब्रेरी और डॉक्यूमेंटेशन यहाँ पा सकते हैं। [.NET वेबसाइट के लिए Aspose.Slides](https://releases.aspose.com/slides/net/).

3. पावरपॉइंट प्रेजेंटेशन: एक पावरपॉइंट प्रेजेंटेशन तैयार करें जिसमें निष्कर्षण का अभ्यास करने के लिए ऑडियो और वीडियो तत्व शामिल हों।

अब, आइए पावरपॉइंट स्लाइड्स से ऑडियो और वीडियो निकालने की प्रक्रिया को कई आसान चरणों में विभाजित करें।

## स्लाइड से ऑडियो निकालना

### चरण 1: अपना प्रोजेक्ट सेट करें

Visual Studio में एक नया प्रोजेक्ट बनाकर और आवश्यक Aspose.Slides नामस्थानों को आयात करके आरंभ करें:

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideShow;
```

### चरण 2: प्रस्तुति लोड करें

वह पावरपॉइंट प्रस्तुति लोड करें जिसमें वह ऑडियो है जिसे आप निकालना चाहते हैं:

```csharp
string dataDir = "Your Document Directory";
string presName = dataDir + "AudioSlide.ppt";
Presentation pres = new Presentation(presName);
```

### चरण 3: इच्छित स्लाइड तक पहुंचें

किसी विशिष्ट स्लाइड तक पहुंचने के लिए, आप इसका उपयोग कर सकते हैं `ISlide` इंटरफ़ेस:

```csharp
ISlide slide = pres.Slides[0];
```

### चरण 4: ऑडियो निकालें

स्लाइड के संक्रमण प्रभाव से ऑडियो डेटा पुनः प्राप्त करें:

```csharp
ISlideShowTransition transition = slide.SlideShowTransition;
byte[] audio = transition.Sound.BinaryData;
System.Console.WriteLine("Length: " + audio.Length);
```

## स्लाइड से वीडियो निकालना

### चरण 1: अपना प्रोजेक्ट सेट करें

ऑडियो निष्कर्षण उदाहरण की तरह, एक नया प्रोजेक्ट बनाकर और आवश्यक Aspose.Slides नामस्थानों को आयात करके शुरू करें।

### चरण 2: प्रस्तुति लोड करें

वह पावरपॉइंट प्रस्तुति लोड करें जिसमें वह वीडियो है जिसे आप निकालना चाहते हैं:

```csharp
string dataDir = "Your Document Directory";
string presName = dataDir + "Video.pptx";
Presentation pres = new Presentation(presName);
```

### चरण 3: स्लाइड और आकृतियों के माध्यम से पुनरावृति करें

वीडियो फ़्रेम की पहचान करने के लिए स्लाइडों और आकृतियों को देखें:

```csharp
foreach (ISlide slide in pres.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
        if (shape is VideoFrame)
        {
            // वीडियो फ़्रेम जानकारी निकालें
            IVideoFrame vf = shape as IVideoFrame;
            String type = vf.EmbeddedVideo.ContentType;
            int ss = type.LastIndexOf('/');
            type = type.Remove(0, type.LastIndexOf('/') + 1);
            
            // वीडियो डेटा को बाइट सरणी के रूप में प्राप्त करें
            Byte[] buffer = vf.EmbeddedVideo.BinaryData;
            
            // वीडियो को फ़ाइल में सहेजें
            using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
            {
                stream.Write(buffer, 0, buffer.Length);
            }
        }
    }
}
```

## निष्कर्ष

Aspose.Slides for .NET पावरपॉइंट प्रेजेंटेशन से ऑडियो और वीडियो निकालने की प्रक्रिया को सरल बनाता है। चाहे आप आर्काइविंग, रीपरपसिंग या मल्टीमीडिया कंटेंट का विश्लेषण करने पर काम कर रहे हों, यह लाइब्रेरी कार्य को सरल बनाती है।

इस गाइड में बताए गए चरणों का पालन करके, आप आसानी से अपने पावरपॉइंट प्रस्तुतियों से ऑडियो और वीडियो निकाल सकते हैं और इन तत्वों का विभिन्न तरीकों से लाभ उठा सकते हैं।

याद रखें, Aspose.Slides for .NET के साथ प्रभावी मल्टीमीडिया निष्कर्षण सही उपकरण, लाइब्रेरी और मल्टीमीडिया तत्वों के साथ एक पावरपॉइंट प्रस्तुति पर निर्भर करता है।

## पूछे जाने वाले प्रश्न

### क्या Aspose.Slides for .NET नवीनतम PowerPoint प्रारूपों के साथ संगत है?
हां, Aspose.Slides for .NET, PPTX सहित नवीनतम PowerPoint प्रारूपों का समर्थन करता है।

### क्या मैं एक साथ कई स्लाइडों से ऑडियो और वीडियो निकाल सकता हूँ?
हां, आप एकाधिक स्लाइडों को दोहराने के लिए कोड को संशोधित कर सकते हैं और उनमें से प्रत्येक से मल्टीमीडिया निकाल सकते हैं।

### क्या .NET के लिए Aspose.Slides के लिए कोई लाइसेंसिंग विकल्प हैं?
Aspose कई तरह के लाइसेंसिंग विकल्प प्रदान करता है, जिसमें निःशुल्क परीक्षण और अस्थायी लाइसेंस शामिल हैं। आप इन विकल्पों को उनके यहाँ देख सकते हैं [वेबसाइट](https://purchase.aspose.com/buy).

### मैं .NET के लिए Aspose.Slides का समर्थन कैसे प्राप्त कर सकता हूं?
तकनीकी सहायता और सामुदायिक चर्चाओं के लिए, आप Aspose.Slides पर जा सकते हैं [मंच](https://forum.aspose.com/).

### मैं Aspose.Slides for .NET के साथ अन्य कौन से कार्य कर सकता हूँ?
Aspose.Slides for .NET कई तरह की सुविधाएँ प्रदान करता है, जिसमें PowerPoint प्रस्तुतियाँ बनाना, संशोधित करना और परिवर्तित करना शामिल है। आप अधिक जानकारी के लिए दस्तावेज़ देख सकते हैं: [.NET दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}