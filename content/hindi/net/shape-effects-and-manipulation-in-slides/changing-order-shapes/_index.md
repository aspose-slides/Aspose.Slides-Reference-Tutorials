---
title: .NET के लिए Aspose.Slides के साथ प्रेजेंटेशन स्लाइड्स को दोबारा आकार देना
linktitle: Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में आकृतियों का क्रम बदलना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड को दोबारा आकार देने का तरीका जानें। आकृतियों को पुन व्यवस्थित करने और दृश्य अपील बढ़ाने के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 26
url: /hi/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---
## परिचय
देखने में आकर्षक प्रस्तुति स्लाइड बनाना प्रभावी संचार का एक महत्वपूर्ण पहलू है। .NET के लिए Aspose.Slides डेवलपर्स को कार्यात्मकताओं की एक विस्तृत श्रृंखला की पेशकश करते हुए, प्रोग्रामेटिक रूप से स्लाइड्स में हेरफेर करने का अधिकार देता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में आकृतियों के क्रम को बदलने की प्रक्रिया के बारे में विस्तार से जानेंगे।
## आवश्यक शर्तें
इससे पहले कि हम इस यात्रा पर निकलें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
-  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास Aspose.Slides लाइब्रेरी आपके .NET प्रोजेक्ट में एकीकृत है। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[पृष्ठ जारी करता है](https://releases.aspose.com/slides/net/).
- विकास वातावरण: विजुअल स्टूडियो या किसी अन्य .NET विकास उपकरण के साथ एक कार्यशील विकास वातावरण स्थापित करें।
- C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, Aspose.Slides कार्यक्षमता तक पहुँचने के लिए आवश्यक नामस्थान शामिल करें:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
विजुअल स्टूडियो या अपने पसंदीदा .NET विकास परिवेश में एक नया प्रोजेक्ट बनाएं। सुनिश्चित करें कि .NET के लिए Aspose.Slides आपके प्रोजेक्ट में संदर्भित है।
## चरण 2: प्रस्तुति लोड करें
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## चरण 3: स्लाइड और आकृतियों तक पहुंचें
```csharp
ISlide slide = presentation.Slides[0];
```
## चरण 4: एक नया आकार जोड़ें
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## चरण 5: आकार में पाठ को संशोधित करें
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
## चरण 8: संशोधित प्रस्तुति सहेजें
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
यह .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में आकृतियों के क्रम को बदलने के लिए चरण-दर-चरण मार्गदर्शिका को पूरा करता है।
## निष्कर्ष
.NET के लिए Aspose.Slides प्रेजेंटेशन स्लाइड्स को प्रोग्रामेटिक रूप से हेरफेर करने के कार्य को सरल बनाता है। इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि आकृतियों को कैसे पुन: व्यवस्थित किया जाए, जिससे आप अपनी प्रस्तुतियों की दृश्य अपील को बढ़ा सकते हैं।
## पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं विंडोज़ और लिनक्स दोनों वातावरणों में .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
उ: हां, .NET के लिए Aspose.Slides विंडोज और लिनक्स दोनों वातावरणों के साथ संगत है।
### प्रश्न: क्या किसी वाणिज्यिक परियोजना में Aspose.Slides का उपयोग करने के लिए कोई लाइसेंस संबंधी विचार हैं?
 उत्तर: हां, आप लाइसेंसिंग विवरण और खरीदारी विकल्प यहां पा सकते हैं[Aspose.Slides खरीद पृष्ठ](https://purchase.aspose.com/buy).
### प्रश्न: क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हां, आप इसके साथ सुविधाओं का पता लगा सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) Aspose.Slides वेबसाइट पर उपलब्ध है।
### प्रश्न: मैं .NET के लिए Aspose.Slides से संबंधित समर्थन कहां पा सकता हूं या प्रश्न पूछ सकता हूं?
 ए: पर जाएँ[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11) समर्थन प्राप्त करने और समुदाय के साथ जुड़ने के लिए।
### प्रश्न: मैं .NET के लिए Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 ए: आप एक प्राप्त कर सकते हैं[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) मूल्यांकन प्रयोजनों के लिए.