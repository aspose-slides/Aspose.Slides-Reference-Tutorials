---
title: .NET के लिए Aspose.Slides का उपयोग करके स्लाइड से वीडियो कैसे निकालें
linktitle: स्लाइड से वीडियो निकालें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड से वीडियो निकालने का तरीका जानें। यह चरण-दर-चरण मार्गदर्शिका आपके लिए प्रक्रिया को सरल बनाती है।
type: docs
weight: 14
url: /hi/net/audio-and-video-extraction/extract-video/
---

.NET के लिए Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो आपको .NET वातावरण में PowerPoint प्रस्तुतियों के साथ काम करने की अनुमति देती है। इसके द्वारा प्रदान की जाने वाली उपयोगी सुविधाओं में से एक स्लाइड से वीडियो निकालने की क्षमता है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड से वीडियो कैसे निकाला जाए।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET के लिए Aspose.Slides: आपको .NET के लिए Aspose.Slides इंस्टॉल करना होगा। आप इसे यहां से प्राप्त कर सकते हैं[वेबसाइट](https://purchase.aspose.com/buy).

- एक पावरपॉइंट प्रेजेंटेशन: एक पावरपॉइंट प्रेजेंटेशन तैयार करें (उदाहरण के लिए, Video.pptx) जिसमें वह वीडियो हो जिसे आप निकालना चाहते हैं।

## नामस्थान आयात करें

आपको .NET के लिए Aspose.Slides के साथ काम करने के लिए आवश्यक नेमस्पेस आयात करने की आवश्यकता है। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

अब, आइए एक स्लाइड से वीडियो निकालने की प्रक्रिया को कई चरणों में विभाजित करें।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

```csharp
string dataDir = "Your Document Directory";
```

 प्रतिस्थापित करें`"Your Document Directory"` उस निर्देशिका के पथ के साथ जहां आपकी PowerPoint प्रस्तुति स्थित है।

## चरण 2: प्रस्तुति लोड करें

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

यह कोड एक प्रेजेंटेशन ऑब्जेक्ट को प्रारंभ करता है, जो आपकी पावरपॉइंट प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है।

## चरण 3: स्लाइड और आकृतियों के माध्यम से पुनरावृति करें

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

यहां, हम प्रेजेंटेशन में प्रत्येक स्लाइड के माध्यम से लूप करते हैं और फिर पहली स्लाइड में आकृतियों के माध्यम से पुनरावृत्त करते हैं (आवश्यकतानुसार संशोधित करें)।

## चरण 4: जांचें कि क्या आकृति एक वीडियो फ़्रेम है

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

यह चरण जाँचता है कि स्लाइड पर आकृति एक वीडियो फ़्रेम है या नहीं।

## चरण 5: वीडियो डेटा निकालें

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

यह कोड वीडियो के बारे में जानकारी निकालता है, जिसमें इसकी सामग्री प्रकार और बाइनरी डेटा शामिल है।

## चरण 6: वीडियो सहेजें

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

अंत में, यह चरण वीडियो को निर्दिष्ट निर्देशिका में एक नई फ़ाइल में सहेजता है।

एक बार जब आप इन चरणों को पूरा कर लेते हैं, तो आप .NET के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड से सफलतापूर्वक एक वीडियो निकाल लेंगे।

## निष्कर्ष

.NET के लिए Aspose.Slides PowerPoint प्रस्तुतियों के साथ काम करने की प्रक्रिया को सरल बनाता है, जिससे आप स्लाइड से वीडियो निकालने जैसे कार्य आसानी से कर सकते हैं। इस चरण-दर-चरण मार्गदर्शिका का पालन करके और Aspose.Slides लाइब्रेरी का उपयोग करके, आप अपने .NET अनुप्रयोगों को शक्तिशाली PowerPoint सुविधाओं के साथ बढ़ा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न (एफएक्यू)

### .NET के लिए Aspose.Slides क्या है?
.NET के लिए Aspose.Slides एक लाइब्रेरी है जो .NET अनुप्रयोगों को सामग्री बनाने, संपादित करने और निकालने सहित PowerPoint प्रस्तुतियों के साथ काम करने में सक्षम बनाती है।

### मुझे .NET के लिए Aspose.Slides का दस्तावेज़ कहां मिल सकता है?
 आप दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/slides/net/).

### क्या .NET के लिए Aspose.Slides निःशुल्क परीक्षण के लिए उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण संस्करण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

### मैं .NET के लिए Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप से अस्थायी लाइसेंस का अनुरोध कर सकते हैं[इस लिंक](https://purchase.aspose.com/temporary-license/).

### मुझे .NET के लिए Aspose.Slides के लिए समर्थन कहां मिल सकता है?
 आप पर समर्थन पा सकते हैं[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/).