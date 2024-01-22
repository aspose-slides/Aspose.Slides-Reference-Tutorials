---
title: प्रस्तुतिकरण को XAML प्रारूप में निर्यात करें
linktitle: प्रस्तुतिकरण को XAML प्रारूप में निर्यात करें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुतियों को XAML प्रारूप में निर्यात करना सीखें। सहजता से इंटरैक्टिव सामग्री बनाएं!
type: docs
weight: 27
url: /hi/net/presentation-conversion/export-presentation-to-xaml-format/
---

सॉफ़्टवेयर विकास की दुनिया में, ऐसे टूल का होना आवश्यक है जो जटिल कार्यों को सरल बना सकें। .NET के लिए Aspose.Slides एक ऐसा उपकरण है जो आपको PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने में सक्षम बनाता है। इस चरण-दर-चरण ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Slides का उपयोग करके XAML प्रारूप में एक प्रस्तुति कैसे निर्यात करें। 

## .NET के लिए Aspose.Slides का परिचय

इससे पहले कि हम ट्यूटोरियल में उतरें, आइए संक्षेप में .NET के लिए Aspose.Slides का परिचय दें। यह एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft PowerPoint की आवश्यकता के बिना PowerPoint प्रस्तुतियाँ बनाने, संशोधित करने, परिवर्तित करने और प्रबंधित करने की अनुमति देती है। .NET के लिए Aspose.Slides के साथ, आप PowerPoint प्रस्तुतियों से संबंधित विभिन्न कार्यों को स्वचालित कर सकते हैं, जिससे आपकी विकास प्रक्रिया अधिक कुशल हो जाएगी।

## आवश्यक शर्तें

इस ट्यूटोरियल का अनुसरण करने के लिए, आपको निम्नलिखित की आवश्यकता होगी:

1. .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Slides स्थापित है और आपके .NET प्रोजेक्ट में उपयोग के लिए तैयार है।

2. स्रोत प्रस्तुति: एक पावरपॉइंट प्रेजेंटेशन (पीपीटीएक्स) रखें जिसे आप XAML प्रारूप में निर्यात करना चाहते हैं। सुनिश्चित करें कि आप इस प्रस्तुति का पथ जानते हैं।

3. आउटपुट निर्देशिका: एक निर्देशिका चुनें जहां आप जेनरेट की गई XAML फ़ाइलों को सहेजना चाहते हैं।

## चरण 1: अपना प्रोजेक्ट सेट करें

इस पहले चरण में, हम अपना प्रोजेक्ट स्थापित करेंगे और सुनिश्चित करेंगे कि हमारे पास सभी आवश्यक घटक तैयार हैं। सुनिश्चित करें कि आपने अपने प्रोजेक्ट में .NET लाइब्रेरी के लिए Aspose.Slides का एक संदर्भ जोड़ा है।

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// स्रोत प्रस्तुति का पथ
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

 प्रतिस्थापित करें`"Your Document Directory"` आपके स्रोत PowerPoint प्रस्तुति वाली निर्देशिका के पथ के साथ। साथ ही, आउटपुट निर्देशिका निर्दिष्ट करें जहां जेनरेट की गई XAML फ़ाइलें सहेजी जाएंगी।

## चरण 2: प्रस्तुति को XAML में निर्यात करें

अब, PowerPoint प्रेजेंटेशन को XAML प्रारूप में निर्यात करने के लिए आगे बढ़ें। इसे प्राप्त करने के लिए हम .NET के लिए Aspose.Slides का उपयोग करेंगे। 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // रूपांतरण विकल्प बनाएँ
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // अपनी स्वयं की आउटपुट-सेविंग सेवा को परिभाषित करें
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // स्लाइड परिवर्तित करें
    pres.Save(xamlOptions);

    // XAML फ़ाइलों को आउटपुट निर्देशिका में सहेजें
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

 इस कोड स्निपेट में, हम स्रोत प्रस्तुति को लोड करते हैं, XAML रूपांतरण विकल्प बनाते हैं, और एक कस्टम आउटपुट-सेविंग सेवा को परिभाषित करते हैं`NewXamlSaver`. फिर हम XAML फ़ाइलों को निर्दिष्ट आउटपुट निर्देशिका में सहेजते हैं।

## चरण 3: कस्टम XAML सेवर क्लास

 कस्टम XAML सेवर को लागू करने के लिए, हम नामक एक क्लास बनाएंगे`NewXamlSaver` जो लागू करता है`IXamlOutputSaver` इंटरफेस।

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

यह क्लास XAML फ़ाइलों को आउटपुट डायरेक्टरी में सेव करने का काम संभालेगी।

## निष्कर्ष

बधाई हो! आपने सफलतापूर्वक सीख लिया है कि .NET के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुति को XAML प्रारूप में कैसे निर्यात किया जाए। उन परियोजनाओं पर काम करते समय यह एक मूल्यवान कौशल हो सकता है जिसमें प्रस्तुतियों में हेरफेर शामिल है।

अपने PowerPoint स्वचालन कार्यों को बढ़ाने के लिए .NET के लिए Aspose.Slides की अधिक सुविधाओं और क्षमताओं का पता लगाने के लिए स्वतंत्र महसूस करें।

## पूछे जाने वाले प्रश्न

1. ### .NET के लिए Aspose.Slides क्या है?
.NET के लिए Aspose.Slides प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों के साथ काम करने के लिए एक .NET लाइब्रेरी है।

2. ### मैं .NET के लिए Aspose.Slides कहां से प्राप्त कर सकता हूं?
 आप .NET के लिए Aspose.Slides डाउनलोड कर सकते हैं[यहाँ](https://purchase.aspose.com/buy).

3. ### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

4. ### मैं .NET के लिए Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

5. ### मुझे .NET के लिए Aspose.Slides के लिए समर्थन कहां मिल सकता है?
 आप समर्थन और सामुदायिक चर्चाएँ पा सकते हैं[यहाँ](https://forum.aspose.com/).

 अधिक ट्यूटोरियल और संसाधनों के लिए, पर जाएँ[Aspose.Slides API दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/).