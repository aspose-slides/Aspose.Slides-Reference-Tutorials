---
title: एंबेडेड फ़ॉन्ट्स के साथ प्रस्तुतियों को HTML में बदलें
linktitle: एंबेडेड फ़ॉन्ट्स के साथ प्रस्तुतियों को HTML में बदलें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके एम्बेडेड फ़ॉन्ट के साथ PowerPoint प्रस्तुतियों को HTML में कनवर्ट करें। मौलिकता को निर्बाध रूप से बनाए रखें.
type: docs
weight: 13
url: /hi/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

आज के डिजिटल युग में प्रेजेंटेशन और दस्तावेज़ ऑनलाइन साझा करना एक आम बात हो गई है। हालाँकि, एक चुनौती जो अक्सर सामने आती है वह यह सुनिश्चित करना है कि प्रस्तुतियों को HTML में परिवर्तित करते समय आपके फ़ॉन्ट सही ढंग से प्रदर्शित हों। यह चरण-दर-चरण ट्यूटोरियल प्रस्तुतियों को एम्बेडेड फ़ॉन्ट के साथ HTML में परिवर्तित करने के लिए .NET के लिए Aspose.Slides का उपयोग करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करेगा, यह सुनिश्चित करते हुए कि आपके दस्तावेज़ बिल्कुल वैसे ही दिखें जैसे आप चाहते थे।

## .NET के लिए Aspose.Slides का परिचय

इससे पहले कि हम ट्यूटोरियल में उतरें, आइए संक्षेप में .NET के लिए Aspose.Slides का परिचय दें। यह एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को .NET अनुप्रयोगों में पावरपॉइंट प्रस्तुतियों के साथ काम करने की अनुमति देती है। Aspose.Slides के साथ, आप PowerPoint फ़ाइलों को प्रोग्रामेटिक रूप से बना, संशोधित और परिवर्तित कर सकते हैं।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

-  .NET के लिए Aspose.Slides: आपके प्रोजेक्ट में Aspose.Slides लाइब्रेरी स्थापित होनी चाहिए। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).

## चरण 1: अपना प्रोजेक्ट सेट करें

1. एक नया प्रोजेक्ट बनाएं या अपने पसंदीदा .NET विकास परिवेश में मौजूदा प्रोजेक्ट खोलें।

2. अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी का संदर्भ जोड़ें।

3. अपने कोड में आवश्यक नामस्थान आयात करें:

   ```csharp
   using Aspose.Slides;
   ```

## चरण 2: अपनी प्रस्तुति लोड करें

 आरंभ करने के लिए, आपको उस प्रस्तुति को लोड करना होगा जिसे आप HTML में कनवर्ट करना चाहते हैं। प्रतिस्थापित करें`"Your Document Directory"` वास्तविक निर्देशिका के साथ जहां आपकी प्रस्तुति फ़ाइल स्थित है।

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // आपका कोड यहां जाता है
}
```

## चरण 3: डिफ़ॉल्ट प्रस्तुति फ़ॉन्ट को बाहर निकालें

इस चरण में, आप कोई भी डिफ़ॉल्ट प्रस्तुति फ़ॉन्ट निर्दिष्ट कर सकते हैं जिसे आप एम्बेडिंग से बाहर करना चाहते हैं। यह परिणामी HTML फ़ाइल के आकार को अनुकूलित करने में मदद कर सकता है।

```csharp
string[] fontNameExcludeList = { };
```

## चरण 4: एक HTML नियंत्रक चुनें

अब, आपके पास HTML में फ़ॉन्ट एम्बेड करने के लिए दो विकल्प हैं:

### विकल्प 1: सभी फ़ॉन्ट एम्बेड करें

 प्रेजेंटेशन में उपयोग किए गए सभी फ़ॉन्ट्स को एम्बेड करने के लिए, का उपयोग करें`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### विकल्प 2: सभी फ़ॉन्ट लिंक करें

 प्रेजेंटेशन में उपयोग किए गए सभी फ़ॉन्ट से लिंक करने के लिए, का उपयोग करें`LinkAllFontsHtmlController`. आपको वह निर्देशिका निर्दिष्ट करनी चाहिए जहां फ़ॉन्ट आपके सिस्टम पर स्थित हैं।

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## चरण 5: HTML विकल्पों को परिभाषित करें

 एक बनाएं`HtmlOptions` ऑब्जेक्ट बनाएं और HTML फ़ॉर्मेटर को उस पर सेट करें जिसे आपने पिछले चरण में चुना था।

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // सभी फ़ॉन्ट एम्बेड करने के लिए EmbedFontsController का उपयोग करें
};
```

## चरण 6: HTML के रूप में सहेजें

 अंत में, प्रेजेंटेशन को HTML फ़ाइल के रूप में सहेजें। आप कोई भी चुन सकते हैं`SaveFormat.Html` या`SaveFormat.Html5` आपकी आवश्यकताओं के आधार पर।

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## निष्कर्ष

बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके अपनी प्रस्तुति को एम्बेडेड फ़ॉन्ट के साथ HTML में सफलतापूर्वक परिवर्तित कर लिया है। यह सुनिश्चित करता है कि आपकी प्रस्तुतियाँ ऑनलाइन साझा करते समय आपके फ़ॉन्ट सही ढंग से प्रदर्शित होंगे।

अब, आप अपनी खूबसूरती से तैयार की गई प्रस्तुतियों को आत्मविश्वास के साथ आसानी से साझा कर सकते हैं, यह जानते हुए कि आपके दर्शक उन्हें बिल्कुल वैसे ही देखेंगे जैसा आप चाहते थे।

 अधिक जानकारी और विस्तृत एपीआई संदर्भों के लिए, देखें[.NET दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/net/).

## पूछे जाने वाले प्रश्न

### 1. क्या मैं बैच मोड में .NET के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों को HTML में परिवर्तित कर सकता हूँ?

हां, आप अपनी प्रस्तुति फ़ाइलों के माध्यम से लूपिंग करके और प्रत्येक में रूपांतरण प्रक्रिया लागू करके .NET के लिए Aspose.Slides का उपयोग करके एकाधिक प्रस्तुतियों को HTML में परिवर्तित कर सकते हैं।

### 2. क्या HTML आउटपुट के स्वरूप को अनुकूलित करने का कोई तरीका है?

निश्चित रूप से! .NET के लिए Aspose.Slides HTML आउटपुट की उपस्थिति और फ़ॉर्मेटिंग को अनुकूलित करने के लिए विभिन्न विकल्प प्रदान करता है, जैसे कि रंग, फ़ॉन्ट और लेआउट समायोजित करना।

### 3. क्या .NET के लिए Aspose.Slides का उपयोग करके HTML में फ़ॉन्ट एम्बेड करने की कोई सीमाएँ हैं?

जबकि .NET के लिए Aspose.Slides उत्कृष्ट फ़ॉन्ट एम्बेडिंग क्षमताएं प्रदान करता है, ध्यान रखें कि फ़ॉन्ट एम्बेड करते समय आपकी HTML फ़ाइलों का आकार बढ़ सकता है। वेब उपयोग के लिए अपने फ़ॉन्ट विकल्पों को अनुकूलित करना सुनिश्चित करें।

### 4. क्या मैं .NET के लिए Aspose.Slides के साथ PowerPoint प्रस्तुतियों को अन्य प्रारूपों में परिवर्तित कर सकता हूँ?

हां, .NET के लिए Aspose.Slides पीडीएफ, छवियों और अन्य सहित आउटपुट स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है। आप अपनी प्रस्तुतियों को आसानी से अपनी पसंद के प्रारूप में परिवर्तित कर सकते हैं।

### 5. मुझे .NET के लिए Aspose.Slides के लिए अतिरिक्त संसाधन और समर्थन कहां मिल सकता है?

 आप दस्तावेज़ीकरण सहित ढेर सारे संसाधनों तक पहुंच सकते हैं[.NET API संदर्भ के लिए Aspose.Slides](https://reference.aspose.com/slides/net/).