---
"description": "Aspose.Slides for .NET के साथ अपनी प्रस्तुति साझाकरण को अनुकूलित करें! इस चरण-दर-चरण मार्गदर्शिका में जानें कि अपनी प्रस्तुति से मीडिया फ़ाइलों को HTML में कैसे निर्यात करें।"
"linktitle": "प्रेजेंटेशन से मीडिया फ़ाइलों को HTML में निर्यात करें"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "प्रेजेंटेशन से मीडिया फ़ाइलों को HTML में निर्यात करें"
"url": "/hi/net/presentation-manipulation/export-media-files-to-html-from-presentation/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# प्रेजेंटेशन से मीडिया फ़ाइलों को HTML में निर्यात करें


इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Slides का उपयोग करके किसी प्रेजेंटेशन से मीडिया फ़ाइलों को HTML में निर्यात करने की प्रक्रिया से परिचित कराएँगे। Aspose.Slides एक शक्तिशाली API है जो आपको PowerPoint प्रेजेंटेशन के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। इस गाइड के अंत तक, आप अपनी प्रेजेंटेशन को आसानी से HTML फ़ॉर्मेट में बदल पाएँगे। तो, चलिए शुरू करते हैं!

## 1 परिचय

पावरपॉइंट प्रेजेंटेशन में अक्सर वीडियो जैसे मल्टीमीडिया तत्व होते हैं, और आपको वेब संगतता के लिए इन प्रेजेंटेशन को HTML प्रारूप में निर्यात करने की आवश्यकता हो सकती है। Aspose.Slides for .NET इस कार्य को प्रोग्रामेटिक रूप से पूरा करने का एक सुविधाजनक तरीका प्रदान करता है।

## 2. पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- Aspose.Slides for .NET: आपके पास Aspose.Slides for .NET लाइब्रेरी स्थापित होनी चाहिए। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/net/).

## 3. प्रेजेंटेशन लोड करना

शुरू करने के लिए, आपको वह PowerPoint प्रेजेंटेशन लोड करना होगा जिसे आप HTML में बदलना चाहते हैं। आपको आउटपुट डायरेक्टरी भी निर्दिष्ट करनी होगी जहाँ HTML फ़ाइल सहेजी जाएगी। प्रेजेंटेशन लोड करने के लिए कोड यहाँ दिया गया है:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// प्रस्तुति लोड करना
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // आपका कोड यहाँ
}
```

## 4. HTML विकल्प सेट करना

अब, आइए रूपांतरण के लिए HTML विकल्प सेट करें। हम HTML नियंत्रक, HTML फ़ॉर्मेटर और स्लाइड छवि प्रारूप को कॉन्फ़िगर करेंगे। यह कोड सुनिश्चित करेगा कि आपकी HTML फ़ाइल में मल्टीमीडिया तत्वों को प्रदर्शित करने के लिए आवश्यक घटक शामिल हैं।

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// HTML विकल्प सेट करना
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. HTML फ़ाइल को सेव करना

HTML विकल्पों को कॉन्फ़िगर करने के बाद, अब आप HTML फ़ाइल को सहेज सकते हैं। `Save` प्रस्तुति ऑब्जेक्ट की विधि एम्बेडेड मल्टीमीडिया तत्वों के साथ HTML फ़ाइल उत्पन्न करेगी।

```csharp
// फ़ाइल सहेजना
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. निष्कर्ष

बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके PowerPoint प्रेजेंटेशन से मीडिया फ़ाइलों को HTML में सफलतापूर्वक निर्यात किया है। इससे आप अपनी प्रेजेंटेशन को आसानी से ऑनलाइन साझा कर सकते हैं और यह सुनिश्चित कर सकते हैं कि मल्टीमीडिया तत्व ठीक से प्रदर्शित हों।

## 7. अक्सर पूछे जाने वाले प्रश्न

### प्रश्न 1: क्या Aspose.Slides for .NET एक निःशुल्क लाइब्रेरी है?
A1: Aspose.Slides for .NET एक व्यावसायिक लाइब्रेरी है, लेकिन आप यहाँ से निःशुल्क परीक्षण प्राप्त कर सकते हैं [यहाँ](https://releases.aspose.com/) इसे आज़माने के लिए.

### प्रश्न 2: क्या मैं HTML आउटपुट को और अधिक अनुकूलित कर सकता हूँ?
उत्तर2: हां, आप कोड में HTML विकल्पों को संशोधित करके HTML आउटपुट को अनुकूलित कर सकते हैं।

### प्रश्न 3: क्या Aspose.Slides for .NET अन्य निर्यात प्रारूपों का समर्थन करता है?
A3: हाँ, Aspose.Slides for .NET विभिन्न निर्यात प्रारूपों का समर्थन करता है, जिसमें PDF, छवि प्रारूप और बहुत कुछ शामिल है।

### प्रश्न 4: मुझे .NET के लिए Aspose.Slides का समर्थन कहां मिल सकता है?
A4: आप Aspose फ़ोरम पर सहायता पा सकते हैं और प्रश्न पूछ सकते हैं [यहाँ](https://forum.aspose.com/).

### प्रश्न 5: मैं Aspose.Slides for .NET का लाइसेंस कैसे खरीदूं?
A5: आप यहां से लाइसेंस खरीद सकते हैं [इस लिंक](https://purchase.aspose.com/buy).

अब जब आपने यह ट्यूटोरियल पूरा कर लिया है, तो आपके पास Aspose.Slides for .NET का उपयोग करके PowerPoint प्रस्तुतियों से मीडिया फ़ाइलों को HTML में निर्यात करने का कौशल है। अपनी मल्टीमीडिया-समृद्ध प्रस्तुतियों को ऑनलाइन साझा करने का आनंद लें!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}