---
"date": "2025-04-15"
"description": "जानें कि .NET के लिए Aspose.Slides का उपयोग करके सीधे फ़ॉन्ट एम्बेड करके प्रस्तुतिकरणों को HTML में परिवर्तित करते समय सुसंगत फ़ॉन्ट रेंडरिंग कैसे सुनिश्चित करें।"
"title": ".NET के लिए Aspose.Slides का उपयोग करके HTML में फ़ॉन्ट्स कैसे लिंक करें - एक चरण-दर-चरण मार्गदर्शिका"
"url": "/hi/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# .NET के लिए Aspose.Slides का उपयोग करके HTML में फ़ॉन्ट्स कैसे लिंक करें

## परिचय

विभिन्न प्लेटफार्मों पर एकसमान फॉन्ट रेंडरिंग बनाए रखते हुए प्रस्तुतियों को HTML में परिवर्तित करना चुनौतीपूर्ण हो सकता है। **.NET के लिए Aspose.Slides** यह आपको एक प्रस्तुति में प्रयुक्त सभी फ़ॉन्ट्स को एम्बेडेड फ़ॉन्ट फ़ाइलों के माध्यम से HTML आउटपुट में सीधे लिंक करने की अनुमति देकर एक सहज समाधान प्रदान करता है।

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Slides का उपयोग करके फ़ॉन्ट लिंकिंग को कैसे लागू किया जाए और विभिन्न प्लेटफार्मों पर डिज़ाइन की स्थिरता सुनिश्चित की जाए। 

**आप क्या सीखेंगे:**
- .NET के लिए Aspose.Slides के साथ अपना परिवेश सेट अप करना
- HTML रूपांतरण में फ़ॉन्ट लिंक करना
- फ़ॉन्ट एम्बेडिंग के लिए कस्टम नियंत्रक लिखना
- व्यावहारिक अनुप्रयोग और प्रदर्शन संबंधी विचार

आइये इस लक्ष्य को प्राप्त करने के लिए आवश्यक कदमों पर नजर डालें।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### आवश्यक लाइब्रेरी और निर्भरताएँ
- **.NET के लिए Aspose.Slides** लाइब्रेरी: हमारे कार्यान्वयन के लिए मुख्य घटक.

### पर्यावरण सेटअप आवश्यकताएँ
- .NET फ्रेमवर्क या .NET कोर स्थापित एक विकास वातावरण.

### ज्ञान पूर्वापेक्षाएँ
- C# प्रोग्रामिंग की बुनियादी समझ.
- HTML और CSS से परिचित होना, विशेष रूप से `@font-face` नियम।

## .NET के लिए Aspose.Slides सेट अप करना

अपने .NET प्रोजेक्ट में Aspose.Slides का उपयोग करने के लिए, आपको लाइब्रेरी इंस्टॉल करनी होगी। यहाँ कई तरीके दिए गए हैं:

### .NET CLI का उपयोग करना
```bash
dotnet add package Aspose.Slides
```

### पैकेज मैनेजर कंसोल का उपयोग करना
```powershell
Install-Package Aspose.Slides
```

### NuGet पैकेज मैनेजर UI के माध्यम से
- अपना प्रोजेक्ट Visual Studio में खोलें.
- "NuGet पैकेज मैनेजर" पर जाएँ।
- "Aspose.Slides" खोजें और नवीनतम संस्करण स्थापित करें।

### लाइसेंस प्राप्ति चरण
आप इन चरणों का पालन करके बिना किसी सीमा के सभी सुविधाओं का परीक्षण करने के लिए निःशुल्क परीक्षण लाइसेंस प्राप्त कर सकते हैं:
1. **मुफ्त परीक्षण**: अस्थायी लाइसेंस डाउनलोड करें [यहाँ](https://releases.aspose.com/slides/net/).
2. **अस्थायी लाइसेंस**: विस्तारित पहुँच के लिए आवेदन करें [यहाँ](https://purchase.aspose.com/temporary-license/).
3. **खरीदना**: पूर्ण कार्यक्षमता के लिए, लाइसेंस खरीदें [यहाँ](https://purchase.aspose.com/buy).

### बुनियादी आरंभीकरण और सेटअप
```csharp
// लाइसेंस वर्ग का एक उदाहरण बनाएँ
easpose.slides.License license = new aspose.slides.License();

// फ़ाइल पथ से लाइसेंस लागू करें
license.SetLicense("Aspose.Slides.lic");
```

## कार्यान्वयन मार्गदर्शिका

अब, आइए HTML रूपांतरण में फ़ॉन्ट लिंकिंग को लागू करें **.NET के लिए Aspose.Slides**.

### फ़ीचर अवलोकन: HTML रूपांतरण में फ़ॉन्ट लिंक करना
यह सुविधा सुनिश्चित करती है कि प्रस्तुति में उपयोग किए गए सभी फ़ॉन्ट फ़ॉन्ट फ़ाइलों को एम्बेड करके परिणामी HTML फ़ाइल में सीधे लिंक किए गए हैं। यह विधि विभिन्न ब्राउज़रों और प्लेटफ़ॉर्म पर डिज़ाइन की स्थिरता बनाए रखने के लिए एक मज़बूत समाधान प्रदान करती है।

#### चरण 1: कस्टम नियंत्रक बनाएँ
एक कस्टम नियंत्रक वर्ग बनाएँ `LinkAllFontsHtmlController` जो विरासत में मिला है `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // वह निर्देशिका सेट करें जहां फ़ॉन्ट फ़ाइलें संग्रहीत की जाएंगी
    }
}
```
#### चरण 2: फ़ॉन्ट लेखन विधि लागू करें
The `WriteFont` विधि फ़ॉन्ट डेटा को एक फ़ाइल में लिखती है और एम्बेडिंग के लिए संबंधित HTML कोड उत्पन्न करती है:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // उपयोग करने के लिए फ़ॉन्ट का नाम निर्धारित करें, यदि उपलब्ध हो तो प्रतिस्थापित फ़ॉन्ट को प्राथमिकता दें।
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // .woff फ़ॉन्ट फ़ाइल के लिए फ़ाइल पथ बनाएँ.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // फ़ॉन्ट डेटा को निर्दिष्ट फ़ाइल पथ पर लिखें.
    File.WriteAllBytes(path, fontData);

    // @font-face नियम का उपयोग करके फ़ॉन्ट एम्बेड करते हुए HTML स्टाइल ब्लॉक उत्पन्न करें।
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}