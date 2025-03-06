---
title: प्रस्तुति को XAML प्रारूप में निर्यात करें
linktitle: प्रस्तुति को XAML प्रारूप में निर्यात करें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुतियों को XAML प्रारूप में निर्यात करना सीखें। सहजता से इंटरैक्टिव सामग्री बनाएँ!
weight: 27
url: /hi/net/presentation-conversion/export-presentation-to-xaml-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


सॉफ़्टवेयर डेवलपमेंट की दुनिया में, ऐसे उपकरण होना ज़रूरी है जो जटिल कार्यों को सरल बना सकें। Aspose.Slides for .NET एक ऐसा उपकरण है जो आपको प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों के साथ काम करने में सक्षम बनाता है। इस चरण-दर-चरण ट्यूटोरियल में, हम Aspose.Slides for .NET का उपयोग करके किसी प्रस्तुति को XAML फ़ॉर्मेट में निर्यात करने का तरीका जानेंगे। 

## .NET के लिए Aspose.Slides का परिचय

ट्यूटोरियल में आगे बढ़ने से पहले, आइए संक्षेप में Aspose.Slides for .NET का परिचय दें। यह एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft PowerPoint की आवश्यकता के बिना PowerPoint प्रस्तुतियाँ बनाने, संशोधित करने, परिवर्तित करने और प्रबंधित करने की अनुमति देती है। Aspose.Slides for .NET के साथ, आप PowerPoint प्रस्तुतियों से संबंधित विभिन्न कार्यों को स्वचालित कर सकते हैं, जिससे आपकी विकास प्रक्रिया अधिक कुशल बन जाती है।

## आवश्यक शर्तें

इस ट्यूटोरियल का अनुसरण करने के लिए आपको निम्नलिखित की आवश्यकता होगी:

1. Aspose.Slides for .NET: सुनिश्चित करें कि आपके पास Aspose.Slides for .NET लाइब्रेरी स्थापित है और आपके .NET प्रोजेक्ट में उपयोग के लिए तैयार है।

2. स्रोत प्रस्तुति: आपके पास एक पावरपॉइंट प्रस्तुति (PPTX) है जिसे आप XAML प्रारूप में निर्यात करना चाहते हैं। सुनिश्चित करें कि आपको इस प्रस्तुति का पथ पता है।

3. आउटपुट निर्देशिका: वह निर्देशिका चुनें जहां आप उत्पन्न XAML फ़ाइलें सहेजना चाहते हैं।

## चरण 1: अपना प्रोजेक्ट सेट करें

इस पहले चरण में, हम अपना प्रोजेक्ट सेट अप करेंगे और सुनिश्चित करेंगे कि हमारे पास सभी आवश्यक घटक तैयार हैं। सुनिश्चित करें कि आपने अपने प्रोजेक्ट में Aspose.Slides for .NET लाइब्रेरी का संदर्भ जोड़ा है।

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// स्रोत तक पथ प्रस्तुति
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

 प्रतिस्थापित करें`"Your Document Directory"` अपने स्रोत PowerPoint प्रस्तुति वाली निर्देशिका के पथ के साथ। साथ ही, आउटपुट निर्देशिका निर्दिष्ट करें जहाँ जेनरेट की गई XAML फ़ाइलें सहेजी जाएँगी।

## चरण 2: प्रस्तुति को XAML में निर्यात करें

अब, चलिए PowerPoint प्रेजेंटेशन को XAML फॉर्मेट में एक्सपोर्ट करने के लिए आगे बढ़ते हैं। हम इसे प्राप्त करने के लिए Aspose.Slides for .NET का उपयोग करेंगे। 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // रूपांतरण विकल्प बनाएँ
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // अपनी स्वयं की आउटपुट-बचत सेवा परिभाषित करें
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // स्लाइड्स परिवर्तित करें
    pres.Save(xamlOptions);

    // XAML फ़ाइलों को आउटपुट निर्देशिका में सहेजें
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

 इस कोड स्निपेट में, हम स्रोत प्रस्तुति को लोड करते हैं, XAML रूपांतरण विकल्प बनाते हैं, और एक कस्टम आउटपुट-सेविंग सेवा को परिभाषित करते हैं`NewXamlSaver`फिर हम XAML फ़ाइलों को निर्दिष्ट आउटपुट निर्देशिका में सहेजते हैं।

## चरण 3: कस्टम XAML सेवर क्लास

 कस्टम XAML सेवर को लागू करने के लिए, हम नाम से एक क्लास बनाएंगे`NewXamlSaver` जो लागू करता है`IXamlOutputSaver` इंटरफेस।

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

यह क्लास XAML फ़ाइलों को आउटपुट निर्देशिका में सहेजने का काम संभालेगा।

## निष्कर्ष

बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके PowerPoint प्रेजेंटेशन को XAML फ़ॉर्मेट में निर्यात करना सफलतापूर्वक सीख लिया है। यह एक मूल्यवान कौशल हो सकता है जब आप ऐसे प्रोजेक्ट पर काम कर रहे हों जिसमें प्रेजेंटेशन में हेरफेर करना शामिल हो।

अपने पावरपॉइंट स्वचालन कार्यों को बढ़ाने के लिए .NET के लिए Aspose.Slides की अधिक सुविधाओं और क्षमताओं का पता लगाने के लिए स्वतंत्र महसूस करें।

## पूछे जाने वाले प्रश्न

1. ### .NET के लिए Aspose.Slides क्या है?
Aspose.Slides for .NET एक .NET लाइब्रेरी है जो PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने के लिए है।

2. ### मैं .NET के लिए Aspose.Slides कहां से प्राप्त कर सकता हूं?
 आप .NET के लिए Aspose.Slides को यहां से डाउनलोड कर सकते हैं[यहाँ](https://purchase.aspose.com/buy).

3. ### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).

4. ### मैं Aspose.Slides for .NET के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

5. ### मुझे Aspose.Slides for .NET के लिए समर्थन कहां मिल सकता है?
 आप समर्थन और सामुदायिक चर्चा पा सकते हैं[यहाँ](https://forum.aspose.com/).

 अधिक ट्यूटोरियल और संसाधनों के लिए, यहां जाएं[Aspose.Slides API दस्तावेज़](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
