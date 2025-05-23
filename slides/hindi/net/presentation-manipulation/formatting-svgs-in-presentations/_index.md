---
"description": "Aspose.Slides for .NET का उपयोग करके शानदार SVG के साथ अपनी प्रस्तुतियों को अनुकूलित करें। प्रभावशाली दृश्यों के लिए SVG को प्रारूपित करने का चरण दर चरण तरीका जानें। आज ही अपनी प्रस्तुति को और बेहतर बनाएँ!"
"linktitle": "प्रस्तुतियों में SVG का प्रारूपण"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "प्रस्तुतियों में SVG का प्रारूपण"
"url": "/hi/net/presentation-manipulation/formatting-svgs-in-presentations/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# प्रस्तुतियों में SVG का प्रारूपण


क्या आप अपनी प्रस्तुतियों को आकर्षक SVG आकृतियों से बेहतर बनाना चाहते हैं? Aspose.Slides for .NET इसे प्राप्त करने के लिए आपका अंतिम उपकरण हो सकता है। इस व्यापक ट्यूटोरियल में, हम आपको Aspose.Slides for .NET का उपयोग करके प्रस्तुतियों में SVG आकृतियों को फ़ॉर्मेट करने की प्रक्रिया से अवगत कराएँगे। दिए गए स्रोत कोड का पालन करें और अपनी प्रस्तुतियों को आकर्षक मास्टरपीस में बदलें।

## परिचय

आज के डिजिटल युग में, जानकारी को प्रभावी ढंग से व्यक्त करने में प्रस्तुतियाँ महत्वपूर्ण भूमिका निभाती हैं। स्केलेबल वेक्टर ग्राफ़िक्स (SVG) आकृतियों को शामिल करने से आपकी प्रस्तुतियाँ अधिक आकर्षक और दिखने में आकर्षक बन सकती हैं। .NET के लिए Aspose.Slides के साथ, आप अपनी विशिष्ट डिज़ाइन आवश्यकताओं को पूरा करने के लिए आसानी से SVG आकृतियों को फ़ॉर्मेट कर सकते हैं।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके विकास परिवेश में Aspose.Slides for .NET स्थापित है।
- C# प्रोग्रामिंग का कार्यसाधक ज्ञान।
- एक नमूना पावरपॉइंट प्रस्तुति फ़ाइल जिसे आप SVG आकृतियों के साथ संवर्धित करना चाहते हैं।

## शुरू करना

आइए सबसे पहले अपनी परियोजना की स्थापना करें और दिए गए स्रोत कोड को समझें।

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
string pptxFileName = Path.Combine(dataDir, "Convert_Svg_Custom.pptx");
string outSvgFileName = Path.Combine(outPath, "Convert_Svg_Custom.svg");

using (Presentation pres = new Presentation(pptxFileName))
{
    using (FileStream stream = new FileStream(outSvgFileName, FileMode.Create))
    {
        SVGOptions svgOptions = new SVGOptions
        {
            ShapeFormattingController = new MySvgShapeFormattingController()
        };

        pres.Slides[0].WriteAsSvg(stream, svgOptions);
    }
}
```

यह कोड स्निपेट आवश्यक निर्देशिकाओं और फ़ाइल पथों को आरंभ करता है, एक पावरपॉइंट प्रस्तुति खोलता है, और इसे SVG फ़ाइल में परिवर्तित करता है जबकि स्वरूपण लागू करते समय इसका उपयोग करता है। `MySvgShapeFormattingController`.

## SVG आकार स्वरूपण नियंत्रक को समझना

आइये इस पर करीब से नज़र डालें `MySvgShapeFormattingController` कक्षा:

```csharp
class MySvgShapeFormattingController : ISvgShapeAndTextFormattingController
{
    private int m_shapeIndex, m_portionIndex, m_tspanIndex;

    public MySvgShapeFormattingController(int shapeStartIndex = 0)
    {
        m_shapeIndex = shapeStartIndex;
        m_portionIndex = 0;
    }

    public void FormatShape(Aspose.Slides.Export.ISvgShape svgShape, IShape shape)
    {
        svgShape.Id = string.Format("shape-{0}", m_shapeIndex++);
        m_portionIndex = m_tspanIndex = 0;
    }

    // अधिक स्वरूपण विधियाँ यहां देखें...

    public ISvgShapeFormattingController AsISvgShapeFormattingController
    {
        get { return this; }
    }
}
```

यह कंट्रोलर क्लास SVG आउटपुट में आकृतियों और टेक्स्ट दोनों के फ़ॉर्मेटिंग को संभालता है। यह आकृतियों और टेक्स्ट स्पैन को अद्वितीय आईडी प्रदान करता है, जिससे उचित रेंडरिंग सुनिश्चित होती है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Slides for .NET का उपयोग करके प्रस्तुतियों में SVG आकृतियों को फ़ॉर्मेट करने का तरीका खोजा है। आपने सीखा है कि अपना प्रोजेक्ट कैसे सेट करें, लागू करें `MySvgShapeFormattingController` सटीक फ़ॉर्मेटिंग के लिए, और अपनी प्रस्तुति को SVG फ़ाइल में बदलें। इन चरणों का पालन करके, आप आकर्षक प्रस्तुतियाँ बना सकते हैं जो आपके दर्शकों पर एक स्थायी छाप छोड़ती हैं।

अपनी रचनात्मकता को उजागर करने के लिए विभिन्न SVG आकृतियों और स्वरूपण विकल्पों के साथ प्रयोग करने में संकोच न करें। Aspose.Slides for .NET आपके प्रेजेंटेशन डिज़ाइन को बेहतर बनाने के लिए एक शक्तिशाली प्लेटफ़ॉर्म प्रदान करता है।

अधिक जानकारी, विस्तृत दस्तावेज़ीकरण और समर्थन के लिए, .NET संसाधनों के लिए Aspose.Slides पर जाएँ:

- [एपीआई दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/): गहन विवरण के लिए API संदर्भ देखें.
- [डाउनलोड करना](https://releases.aspose.com/slides/net/): .NET के लिए नवीनतम Aspose.Slides संस्करण प्राप्त करें।
- [खरीदना](https://purchase.aspose.com/buy)विस्तारित उपयोग के लिए लाइसेंस प्राप्त करें।
- [मुफ्त परीक्षण](https://releases.aspose.com/): .NET के लिए Aspose.Slides को निःशुल्क आज़माएँ।
- [अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/): अपनी परियोजनाओं के लिए अस्थायी लाइसेंस प्राप्त करें।
- [सहायता](https://forum.aspose.com/)सहायता और चर्चा के लिए Aspose समुदाय में शामिल हों।

अब, आपके पास SVG आकृतियों के साथ आकर्षक प्रस्तुतियाँ बनाने का ज्ञान और उपकरण हैं। अपनी प्रस्तुतियों को बेहतर बनाएँ और अपने दर्शकों को पहले से कहीं ज़्यादा आकर्षित करें!

## पूछे जाने वाले प्रश्न

### SVG फ़ॉर्मेटिंग क्या है और प्रस्तुतियों में यह क्यों महत्वपूर्ण है?
SVG फ़ॉर्मेटिंग का मतलब प्रेजेंटेशन में इस्तेमाल किए जाने वाले स्केलेबल वेक्टर ग्राफ़िक्स की स्टाइलिंग और डिज़ाइन से है। यह महत्वपूर्ण है क्योंकि यह आपकी स्लाइड्स में विज़ुअल अपील और जुड़ाव को बढ़ाता है।

### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
Aspose.Slides for .NET मुख्य रूप से C# के लिए डिज़ाइन किया गया है, लेकिन यह VB.NET जैसी अन्य .NET भाषाओं के साथ भी काम करता है।

### क्या .NET के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
हां, आप वेबसाइट से परीक्षण संस्करण डाउनलोड करके Aspose.Slides for .NET को निःशुल्क आज़मा सकते हैं।

### मैं Aspose.Slides for .NET के लिए तकनीकी सहायता कैसे प्राप्त कर सकता हूं?
आप तकनीकी सहायता प्राप्त करने और विशेषज्ञों और साथी डेवलपर्स के साथ चर्चा करने के लिए Aspose सामुदायिक मंच (ऊपर दिया गया लिंक) पर जा सकते हैं।

### दृश्यात्मक रूप से आकर्षक प्रस्तुतियाँ बनाने के लिए कुछ सर्वोत्तम अभ्यास क्या हैं?
आकर्षक प्रस्तुतिकरण बनाने के लिए, डिज़ाइन की एकरूपता पर ध्यान दें, उच्च-गुणवत्ता वाले ग्राफ़िक्स का उपयोग करें, और अपनी सामग्री को संक्षिप्त और आकर्षक बनाए रखें। इस ट्यूटोरियल में दिखाए गए अनुसार विभिन्न फ़ॉर्मेटिंग विकल्पों के साथ प्रयोग करें।

अब, आगे बढ़ें और इन तकनीकों को लागू करके ऐसी शानदार प्रस्तुतियाँ बनाएँ जो आपके दर्शकों को मोहित कर दें!


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}