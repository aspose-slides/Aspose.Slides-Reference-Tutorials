---
"description": "Aspose.Slides for .NET में हाइपरलिंक जोड़ने और हटाने का तरीका जानें। इंटरैक्टिव लिंक के साथ आसानी से अपनी प्रस्तुतियों को बेहतर बनाएँ।"
"linktitle": "Aspose.Slides में हाइपरलिंक हेरफेर"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "Aspose.Slides में हाइपरलिंक हेरफेर"
"url": "/hi/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides में हाइपरलिंक हेरफेर


हाइपरलिंक्स प्रेजेंटेशन में आवश्यक तत्व हैं, क्योंकि वे स्लाइड्स के बीच नेविगेट करने या बाहरी संसाधनों तक पहुँचने का एक सुविधाजनक तरीका प्रदान करते हैं। Aspose.Slides for .NET आपकी प्रेजेंटेशन स्लाइड्स में हाइपरलिंक्स जोड़ने और हटाने के लिए शक्तिशाली सुविधाएँ प्रदान करता है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for .NET का उपयोग करके हाइपरलिंक हेरफेर की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे। हम एक स्लाइड में हाइपरलिंक्स जोड़ने और एक स्लाइड से हाइपरलिंक्स हटाने को कवर करेंगे। तो, चलिए शुरू करते हैं!

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. Aspose.Slides for .NET: आपके पास Aspose.Slides for .NET लाइब्रेरी स्थापित और सेट अप होनी चाहिए। आप दस्तावेज़ पा सकते हैं [यहाँ](https://reference.aspose.com/slides/net/) और इसे यहाँ से डाउनलोड करें [इस लिंक](https://releases.aspose.com/slides/net/).

2. आपकी दस्तावेज़ निर्देशिका: आपको एक निर्देशिका की आवश्यकता है जहाँ आप अपनी प्रस्तुति फ़ाइलें संग्रहीत करेंगे। अपने कोड में इस निर्देशिका का पथ निर्दिष्ट करना सुनिश्चित करें।

3. C# का बुनियादी ज्ञान: यह ट्यूटोरियल मानता है कि आपको C# प्रोग्रामिंग की बुनियादी समझ है।

अब जब आपने अपनी पूर्व-आवश्यकताएं पूरी कर ली हैं, तो आइए Aspose.Slides for .NET का उपयोग करके हाइपरलिंक हेरफेर के लिए चरण-दर-चरण मार्गदर्शिका पर चलते हैं।

## स्लाइड में हाइपरलिंक जोड़ना

### चरण 1: प्रस्तुति आरंभ करें

आरंभ करने के लिए, आपको Aspose.Slides का उपयोग करके एक प्रस्तुति आरंभ करनी होगी। आप निम्न कोड के साथ ऐसा कर सकते हैं:

```csharp
using (Presentation presentation = new Presentation())
{
    // आपका कोड यहाँ
}
```

### चरण 2: टेक्स्ट फ़्रेम जोड़ें

अब, स्लाइड में टेक्स्ट फ़्रेम जोड़ें। यह कोड टेक्स्ट के साथ एक आयताकार आकार बनाता है:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### चरण 3: हाइपरलिंक जोड़ें

इसके बाद, आप अपने द्वारा बनाए गए आकार में टेक्स्ट में हाइपरलिंक जोड़ेंगे। आप यह कैसे कर सकते हैं, यहाँ बताया गया है:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### चरण 4: प्रस्तुति सहेजें

अंत में, जोड़े गए हाइपरलिंक के साथ अपनी प्रस्तुति को सहेजें:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके स्लाइड में हाइपरलिंक सफलतापूर्वक जोड़ लिया है।

## स्लाइड से हाइपरलिंक हटाना

### चरण 1: प्रस्तुति आरंभ करें

किसी स्लाइड से हाइपरलिंक हटाने के लिए, आपको एक मौजूदा प्रस्तुति खोलनी होगी:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### चरण 2: हाइपरलिंक हटाएं

अब, निम्नलिखित कोड का उपयोग करके प्रस्तुति से सभी हाइपरलिंक हटाएँ:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### चरण 3: प्रस्तुति सहेजें

हाइपरलिंक हटाने के बाद, प्रस्तुति सहेजें:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

और बस! आपने Aspose.Slides for .NET का उपयोग करके स्लाइड से हाइपरलिंक्स को सफलतापूर्वक हटा दिया है।

निष्कर्ष में, Aspose.Slides for .NET आपके प्रेजेंटेशन में हाइपरलिंक्स को मैनिपुलेट करने का एक कुशल तरीका प्रदान करता है, जिससे आप इंटरैक्टिव और आकर्षक स्लाइड बना सकते हैं। चाहे आप बाहरी संसाधनों में हाइपरलिंक जोड़ना चाहते हों या उन्हें हटाना चाहते हों, Aspose.Slides प्रक्रिया को सरल बनाता है और आपकी प्रेजेंटेशन-निर्माण क्षमताओं को बढ़ाता है।

Aspose.Slides for .NET में हाइपरलिंक मैनिपुलेशन पर इस ट्यूटोरियल में शामिल होने के लिए आपका धन्यवाद। यदि आपके पास कोई प्रश्न है या आपको और सहायता की आवश्यकता है, तो बेझिझक इसका पता लगाएँ। [Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/) या Aspose समुदाय तक पहुंचें [सहयता मंच](https://forum.aspose.com/).

---

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुतियों में हाइपरलिंक्स को कैसे हेरफेर किया जाए। हमने हाइपरलिंक्स को जोड़ने और हटाने दोनों को कवर किया है, जिससे आप गतिशील और इंटरैक्टिव प्रस्तुतियाँ बना सकते हैं। Aspose.Slides प्रक्रिया को सरल बनाता है, जिससे बाहरी संसाधनों के लिए हाइपरलिंक्स के साथ अपनी स्लाइड्स को बेहतर बनाना आसान हो जाता है।

क्या आपके पास Aspose.Slides के साथ काम करने या प्रेजेंटेशन डिज़ाइन के अन्य पहलुओं के बारे में कोई और सवाल है? अधिक जानकारी के लिए नीचे दिए गए FAQ देखें।

## अक्सर पूछे जाने वाले प्रश्न (FAQs)

### .NET के लिए Aspose.Slides का उपयोग करने के मुख्य लाभ क्या हैं?
Aspose.Slides for .NET प्रेजेंटेशन बनाने, उसमें हेरफेर करने और उसे बदलने के लिए कई तरह की सुविधाएँ प्रदान करता है। यह आपकी स्लाइड्स में कंटेंट, एनिमेशन और इंटरैक्शन जोड़ने के लिए उपकरणों का एक व्यापक सेट प्रदान करता है।

### क्या मैं Aspose.Slides में पाठ के अलावा अन्य ऑब्जेक्ट्स में हाइपरलिंक जोड़ सकता हूं?
हां, Aspose.Slides आपको आकृतियों, छवियों और पाठ सहित विभिन्न ऑब्जेक्ट्स में हाइपरलिंक जोड़ने की अनुमति देता है, जिससे आपको इंटरैक्टिव प्रस्तुतियाँ बनाने में लचीलापन मिलता है।

### क्या Aspose.Slides विभिन्न PowerPoint फ़ाइल स्वरूपों के साथ संगत है?
बिल्कुल। Aspose.Slides विभिन्न PowerPoint प्रारूपों का समर्थन करता है, जिसमें PPT, PPTX, PPS, और बहुत कुछ शामिल है। यह Microsoft PowerPoint के विभिन्न संस्करणों के साथ संगतता सुनिश्चित करता है।

### मैं Aspose.Slides के लिए अतिरिक्त संसाधन और समर्थन कहां पा सकता हूं?
गहन दस्तावेज़ीकरण और सामुदायिक सहायता के लिए, यहां जाएं [Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/) और यह [Aspose समर्थन मंच](https://forum.aspose.com/).

### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
यदि आपको Aspose.Slides के लिए अस्थायी लाइसेंस की आवश्यकता है, तो आप इसे प्राप्त कर सकते हैं [यहाँ](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}