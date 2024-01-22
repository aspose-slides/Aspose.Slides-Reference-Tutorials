---
title: प्रेजेंटेशन से HTML में मीडिया फ़ाइलें निर्यात करें
linktitle: प्रेजेंटेशन से HTML में मीडिया फ़ाइलें निर्यात करें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides के साथ अपनी प्रस्तुति साझाकरण को अनुकूलित करें! इस चरण-दर-चरण मार्गदर्शिका में जानें कि अपनी प्रस्तुति से मीडिया फ़ाइलों को HTML में कैसे निर्यात करें।
type: docs
weight: 15
url: /hi/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Slides का उपयोग करके एक प्रेजेंटेशन से HTML में मीडिया फ़ाइलों को निर्यात करने की प्रक्रिया के बारे में बताएंगे। Aspose.Slides एक शक्तिशाली API है जो आपको PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। इस गाइड के अंत तक, आप अपनी प्रस्तुतियों को आसानी से HTML प्रारूप में परिवर्तित करने में सक्षम होंगे। तो चलो शुरू हो जाओ!

## 1 परिचय

पावरपॉइंट प्रस्तुतियों में अक्सर वीडियो जैसे मल्टीमीडिया तत्व होते हैं, और आपको वेब संगतता के लिए इन प्रस्तुतियों को HTML प्रारूप में निर्यात करने की आवश्यकता हो सकती है। .NET के लिए Aspose.Slides इस कार्य को प्रोग्रामेटिक रूप से पूरा करने का एक सुविधाजनक तरीका प्रदान करता है।

## 2. पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET के लिए Aspose.Slides: आपके पास .NET लाइब्रेरी के लिए Aspose.Slides स्थापित होना चाहिए। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).

## 3. प्रेजेंटेशन लोड हो रहा है

आरंभ करने के लिए, आपको उस PowerPoint प्रस्तुति को लोड करना होगा जिसे आप HTML में कनवर्ट करना चाहते हैं। आपको आउटपुट निर्देशिका भी निर्दिष्ट करनी होगी जहां HTML फ़ाइल सहेजी जाएगी। प्रेजेंटेशन लोड करने के लिए कोड यहां दिया गया है:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// प्रेजेंटेशन लोड हो रहा है
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // आपका कोड यहाँ
}
```

## 4. HTML विकल्प सेट करना

अब, रूपांतरण के लिए HTML विकल्प सेट करें। हम एक HTML नियंत्रक, HTML फ़ॉर्मेटर और स्लाइड छवि प्रारूप कॉन्फ़िगर करेंगे। यह कोड सुनिश्चित करेगा कि आपकी HTML फ़ाइल में मल्टीमीडिया तत्वों को प्रदर्शित करने के लिए आवश्यक घटक शामिल हैं।

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

## 5. HTML फ़ाइल को सहेजना

 HTML विकल्पों को कॉन्फ़िगर करने के साथ, अब आप HTML फ़ाइल को सहेज सकते हैं।`Save` प्रेजेंटेशन ऑब्जेक्ट की विधि एम्बेडेड मल्टीमीडिया तत्वों के साथ HTML फ़ाइल उत्पन्न करेगी।

```csharp
// फ़ाइल सहेजा जा रहा है
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6। निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके PowerPoint प्रेजेंटेशन से HTML में मीडिया फ़ाइलों को सफलतापूर्वक निर्यात किया है। यह आपको अपनी प्रस्तुतियों को आसानी से ऑनलाइन साझा करने और यह सुनिश्चित करने की अनुमति देता है कि मल्टीमीडिया तत्व ठीक से प्रदर्शित हों।

## 7. अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या .NET के लिए Aspose.Slides एक निःशुल्क लाइब्रेरी है?
 A1: .NET के लिए Aspose.Slides एक व्यावसायिक लाइब्रेरी है, लेकिन आप इसका निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/) इसे आज़माने के लिए.

### Q2: क्या मैं HTML आउटपुट को और अधिक अनुकूलित कर सकता हूँ?
उ2: हां, आप कोड में HTML विकल्पों को संशोधित करके HTML आउटपुट को कस्टमाइज़ कर सकते हैं।

### Q3: क्या .NET के लिए Aspose.Slides अन्य निर्यात प्रारूपों का समर्थन करता है?
A3: हां, .NET के लिए Aspose.Slides पीडीएफ, छवि प्रारूप और अन्य सहित विभिन्न निर्यात प्रारूपों का समर्थन करता है।

### Q4: मुझे .NET के लिए Aspose.Slides के लिए समर्थन कहां मिल सकता है?
 A4: आप Aspose मंचों पर समर्थन पा सकते हैं और प्रश्न पूछ सकते हैं[यहाँ](https://forum.aspose.com/).

### Q5: मैं .NET के लिए Aspose.Slides का लाइसेंस कैसे खरीदूं?
 A5: आप यहां से लाइसेंस खरीद सकते हैं[इस लिंक](https://purchase.aspose.com/buy).

अब जब आपने यह ट्यूटोरियल पूरा कर लिया है, तो आपके पास .NET के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों से मीडिया फ़ाइलों को HTML में निर्यात करने का कौशल है। अपनी मल्टीमीडिया-समृद्ध प्रस्तुतियाँ ऑनलाइन साझा करने का आनंद लें!