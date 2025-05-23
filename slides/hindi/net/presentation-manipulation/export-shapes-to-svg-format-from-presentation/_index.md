---
"description": "Aspose.Slides for .NET का उपयोग करके PowerPoint प्रस्तुति से SVG प्रारूप में आकृतियों को निर्यात करना सीखें। स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका शामिल है। विभिन्न अनुप्रयोगों के लिए कुशलतापूर्वक आकृतियों को निकालें।"
"linktitle": "प्रेजेंटेशन से आकृतियों को SVG प्रारूप में निर्यात करें"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "प्रेजेंटेशन से आकृतियों को SVG प्रारूप में निर्यात करें"
"url": "/hi/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# प्रेजेंटेशन से आकृतियों को SVG प्रारूप में निर्यात करें


आज की डिजिटल दुनिया में, जानकारी को प्रभावी ढंग से व्यक्त करने में प्रस्तुतियाँ महत्वपूर्ण भूमिका निभाती हैं। हालाँकि, कभी-कभी हमें विभिन्न उद्देश्यों के लिए अपनी प्रस्तुतियों से विशिष्ट आकृतियों को अलग-अलग फ़ॉर्मेट में निर्यात करने की आवश्यकता होती है। ऐसा ही एक फ़ॉर्मेट SVG (स्केलेबल वेक्टर ग्राफ़िक्स) है, जो अपनी मापनीयता और अनुकूलनशीलता के लिए जाना जाता है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for .NET का उपयोग करके किसी प्रस्तुति से आकृतियों को SVG फ़ॉर्मेट में निर्यात करने की प्रक्रिया के बारे में बताएँगे।

## 1 परिचय

प्रस्तुतियों में अक्सर चार्ट, आरेख और चित्रण जैसे महत्वपूर्ण दृश्य तत्व होते हैं। इन तत्वों को SVG प्रारूप में निर्यात करना वेब-आधारित अनुप्रयोगों, मुद्रण या वेक्टर ग्राफ़िक्स सॉफ़्टवेयर में आगे के संपादन के लिए मूल्यवान हो सकता है। .NET के लिए Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो आपको इस तरह के कार्यों को स्वचालित करने की अनुमति देती है।

## 2. पूर्वापेक्षाएँ

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- Aspose.Slides for .NET स्थापित एक विकास वातावरण.
- एक पावरपॉइंट प्रस्तुति (PPTX) जिसमें वह आकृति शामिल है जिसे आप निर्यात करना चाहते हैं।
- C# प्रोग्रामिंग का बुनियादी ज्ञान.

## 3. अपना वातावरण स्थापित करना

आरंभ करने के लिए, अपने पसंदीदा IDE में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपने अपने प्रोजेक्ट में Aspose.Slides for .NET लाइब्रेरी का संदर्भ दिया है।

## 4. प्रेजेंटेशन लोड करना

अपने C# कोड में, आपको अपनी प्रस्तुति की निर्देशिका और SVG फ़ाइल के लिए आउटपुट निर्देशिका निर्दिष्ट करनी होगी। यहाँ एक उदाहरण दिया गया है:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
string outSvgFileName = outPath + "SingleShape.svg";

using (Presentation pres = new Presentation(dataDir + "YourPresentation.pptx"))
{
    // आकृति निर्यात करने के लिए आपका कोड यहां जाएगा.
}
```

## 5. किसी आकृति को SVG में निर्यात करना

के अंदर `using` ब्लॉक में, आप अपनी प्रस्तुति में आकृतियों तक पहुँच सकते हैं और उन्हें SVG प्रारूप में निर्यात कर सकते हैं। यहाँ, हम पहली स्लाइड पर पहली आकृति निर्यात कर रहे हैं:

```csharp
using (Stream stream = new FileStream(outSvgFileName, FileMode.Create, FileAccess.Write))
{
    pres.Slides[0].Shapes[0].WriteAsSvg(stream);
}
```

आप इस कोड को विभिन्न आकृतियों को निर्यात करने या आवश्यकतानुसार अतिरिक्त परिवर्तन लागू करने के लिए अनुकूलित कर सकते हैं।

## 6. निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Slides for .NET का उपयोग करके PowerPoint प्रेजेंटेशन से SVG फ़ॉर्मेट में आकृतियों को निर्यात करने की प्रक्रिया को देखा है। यह शक्तिशाली लाइब्रेरी कार्य को सरल बनाती है, जिससे आप निर्यात प्रक्रिया को स्वचालित कर सकते हैं और अपने वर्कफ़्लो को बढ़ा सकते हैं।

## 7. अक्सर पूछे जाने वाले प्रश्न

### प्रश्न 1: एसवीजी प्रारूप क्या है?

स्केलेबल वेक्टर ग्राफिक्स (एसवीजी) एक XML-आधारित वेक्टर छवि प्रारूप है जिसका उपयोग इसकी मापनीयता और वेब ब्राउज़रों के साथ संगतता के लिए व्यापक रूप से किया जाता है।

### प्रश्न 2: क्या मैं एक साथ कई आकृतियाँ निर्यात कर सकता हूँ?

हां, आप अपनी प्रस्तुति में आकृतियों को लूप कर सकते हैं और उन्हें एक-एक करके निर्यात कर सकते हैं।

### प्रश्न 3: क्या Aspose.Slides for .NET एक सशुल्क लाइब्रेरी है?

हां, Aspose.Slides for .NET एक व्यावसायिक लाइब्रेरी है जिसका निःशुल्क परीक्षण उपलब्ध है।

### प्रश्न 4: क्या Aspose.Slides के साथ आकृतियों को निर्यात करने में कोई सीमाएँ हैं?

आकृतियों को निर्यात करने की क्षमता, आकृति की जटिलता और लाइब्रेरी द्वारा समर्थित सुविधाओं के आधार पर भिन्न हो सकती है।

### प्रश्न 5: मुझे .NET के लिए Aspose.Slides का समर्थन कहां मिल सकता है?

आप यहां जा सकते हैं [Aspose.Slides फ़ोरम](https://forum.aspose.com/) समर्थन और सामुदायिक चर्चा के लिए।

अब जब आपने सीख लिया है कि आकृतियों को SVG प्रारूप में कैसे निर्यात किया जाता है, तो आप अपनी प्रस्तुतियों को बेहतर बना सकते हैं और उन्हें विभिन्न उद्देश्यों के लिए अधिक बहुमुखी बना सकते हैं। हैप्पी कोडिंग!

अधिक जानकारी और उन्नत सुविधाओं के लिए, देखें [.NET API संदर्भ के लिए Aspose.Slides](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}