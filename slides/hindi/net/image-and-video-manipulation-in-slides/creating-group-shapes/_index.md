---
"description": "जानें कि Aspose.Slides for .NET के साथ PowerPoint में समूह आकृतियाँ कैसे बनाएँ। आकर्षक प्रस्तुतिकरणों के लिए हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"linktitle": "Aspose.Slides के साथ प्रेजेंटेशन स्लाइड में समूह आकृतियाँ बनाना"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "Aspose.Slides - .NET में समूह आकृतियाँ बनाना"
"url": "/hi/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - .NET में समूह आकृतियाँ बनाना

## परिचय
यदि आप अपनी प्रस्तुति स्लाइड्स की दृश्य अपील को बढ़ाना चाहते हैं और सामग्री को अधिक कुशलता से व्यवस्थित करना चाहते हैं, तो समूह आकृतियों को शामिल करना एक शक्तिशाली समाधान है। .NET के लिए Aspose.Slides आपके PowerPoint प्रस्तुतियों में समूह आकृतियों को बनाने और उनमें हेरफेर करने का एक सहज तरीका प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके समूह आकृतियों को बनाने की प्रक्रिया से गुजरेंगे, इसे आसानी से पालन किए जाने वाले चरणों में विभाजित करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास Aspose.Slides लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं [वेबसाइट](https://releases.aspose.com/slides/net/).
- विकास परिवेश: Visual Studio जैसे .NET-संगत IDE के साथ कार्य परिवेश सेट अप करें।
- C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा की मूल बातों से स्वयं को परिचित कराएं।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, आवश्यक नामस्थानों को आयात करके आरंभ करें:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## चरण 1: प्रेजेंटेशन क्लास को इंस्टैंशिएट करें

इसका एक उदाहरण बनाएं `Presentation` class पर जाएँ और वह निर्देशिका निर्दिष्ट करें जहाँ आपके दस्तावेज़ संग्रहीत हैं:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // इस उपयोग ब्लॉक के भीतर निम्नलिखित चरणों के साथ जारी रखें
}
```

## चरण 2: पहली स्लाइड तक पहुंचें

प्रस्तुति से पहली स्लाइड प्राप्त करें:

```csharp
ISlide sld = pres.Slides[0];
```

## चरण 3: आकृति संग्रह तक पहुँचना

स्लाइड पर आकृतियों के संग्रह तक पहुंचें:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## चरण 4: समूह आकार जोड़ना

स्लाइड में समूह आकार जोड़ें:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## चरण 5: समूह आकृति के अंदर आकृतियाँ जोड़ना

समूह आकृति को अलग-अलग आकृतियों से भरें:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## चरण 6: समूह आकार फ़्रेम जोड़ना

संपूर्ण समूह आकृति के लिए फ़्रेम परिभाषित करें:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## चरण 7: प्रस्तुति सहेजें

संशोधित प्रस्तुति को अपनी निर्दिष्ट निर्देशिका में सहेजें:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Aspose.Slides का उपयोग करके अपनी प्रस्तुति स्लाइडों में समूह आकृतियाँ सफलतापूर्वक बनाने के लिए अपने C# अनुप्रयोग में इन चरणों को दोहराएँ।

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Aspose.Slides के साथ समूह आकृतियाँ बनाने की प्रक्रिया का पता लगाया। इन चरणों का पालन करके, आप अपने PowerPoint प्रस्तुतियों की दृश्य अपील और संगठन को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या Aspose.Slides .NET के नवीनतम संस्करण के साथ संगत है?
हां, Aspose.Slides को नवीनतम .NET संस्करणों का समर्थन करने के लिए नियमित रूप से अपडेट किया जाता है। [प्रलेखन](https://reference.aspose.com/slides/net/) संगतता विवरण के लिए.
### क्या मैं खरीदने से पहले Aspose.Slides आज़मा सकता हूँ?
बिलकुल! आप इसका निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides-संबंधित प्रश्नों के लिए समर्थन कहां पा सकता हूं?
Aspose.Slides पर जाएँ [मंच](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन और चर्चा के लिए।
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
आप अस्थायी लाइसेंस प्राप्त कर सकते हैं [यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides के लिए पूर्ण लाइसेंस कहां से खरीद सकता हूं?
आप यहां से लाइसेंस खरीद सकते हैं [खरीद पृष्ठ](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}