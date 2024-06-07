---
title: .NET के लिए Aspose.Slides के साथ प्रस्तुति स्लाइड्स को नया आकार देना
linktitle: Aspose.Slides का उपयोग करके प्रस्तुति स्लाइडों में आकृतियों का क्रम बदलना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET का उपयोग करके प्रस्तुतिकरण स्लाइड को पुनः आकार देने का तरीका जानें। आकृतियों को पुनः क्रमित करने और दृश्य अपील को बढ़ाने के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 26
url: /hi/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---
## परिचय
दृश्य रूप से आकर्षक प्रस्तुति स्लाइड बनाना प्रभावी संचार का एक महत्वपूर्ण पहलू है। Aspose.Slides for .NET डेवलपर्स को प्रोग्रामेटिक रूप से स्लाइड में हेरफेर करने की शक्ति देता है, जो कई प्रकार की कार्यक्षमता प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Slides for .NET का उपयोग करके प्रस्तुति स्लाइड में आकृतियों के क्रम को बदलने की प्रक्रिया में गहराई से उतरेंगे।
## आवश्यक शर्तें
इससे पहले कि हम इस यात्रा पर निकलें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
-  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके .NET प्रोजेक्ट में Aspose.Slides लाइब्रेरी एकीकृत है। यदि नहीं, तो आप इसे यहाँ से डाउनलोड कर सकते हैं।[विज्ञप्ति पृष्ठ](https://releases.aspose.com/slides/net/).
- विकास परिवेश: विजुअल स्टूडियो या किसी अन्य .NET विकास उपकरण के साथ कार्यशील विकास परिवेश स्थापित करें।
- C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा की मूल बातों से स्वयं को परिचित कराएं।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, Aspose.Slides कार्यक्षमता तक पहुँचने के लिए आवश्यक नामस्थान शामिल करें:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
Visual Studio या अपने पसंदीदा .NET डेवलपमेंट वातावरण में एक नया प्रोजेक्ट बनाएँ। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides for .NET का संदर्भ दिया गया है।
## चरण 2: प्रस्तुति लोड करें
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## चरण 3: स्लाइड और आकृतियों तक पहुँचें
```csharp
ISlide slide = presentation.Slides[0];
```
## चरण 4: नया आकार जोड़ें
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## चरण 5: आकृति में पाठ संशोधित करें
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## चरण 6: एक और आकृति जोड़ें
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## चरण 7: आकृतियों का क्रम बदलें
```csharp
slide.Shapes.Reorder(2, shp3);
```
## चरण 8: संशोधित प्रस्तुति को सहेजें
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
यह Aspose.Slides for .NET का उपयोग करके प्रस्तुति स्लाइडों में आकृतियों के क्रम को बदलने के लिए चरण-दर-चरण मार्गदर्शिका को पूरा करता है।
## निष्कर्ष
Aspose.Slides for .NET प्रेजेंटेशन स्लाइड्स को प्रोग्रामेटिक रूप से मैनिपुलेट करने के कार्य को सरल बनाता है। इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि आकृतियों को कैसे पुनर्व्यवस्थित किया जाए, जिससे आप अपनी प्रेजेंटेशन की दृश्य अपील को बढ़ा सकें।
## पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं Windows और Linux दोनों वातावरणों में .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
उत्तर: हां, Aspose.Slides for .NET विंडोज और लिनक्स दोनों वातावरणों के साथ संगत है।
### प्रश्न: क्या किसी व्यावसायिक परियोजना में Aspose.Slides का उपयोग करने के लिए कोई लाइसेंसिंग संबंधी विचारणीय बातें हैं?
 उत्तर: हां, आप वेबसाइट पर लाइसेंसिंग विवरण और खरीद विकल्प पा सकते हैं।[Aspose.Slides खरीद पृष्ठ](https://purchase.aspose.com/buy).
### प्रश्न: क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हां, आप इसके फीचर्स देख सकते हैं।[मुफ्त परीक्षण](https://releases.aspose.com/) Aspose.Slides वेबसाइट पर उपलब्ध है।
### प्रश्न: मैं Aspose.Slides for .NET से संबंधित सहायता कहां पा सकता हूं या प्रश्न कहां पूछ सकता हूं?
उत्तर: यहाँ जाएँ[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) समर्थन प्राप्त करने और समुदाय के साथ जुड़ने के लिए।
### प्रश्न: मैं .NET के लिए Aspose.Slides हेतु अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 उत्तर: आप एक प्राप्त कर सकते हैं[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) मूल्यांकन प्रयोजनों के लिए।