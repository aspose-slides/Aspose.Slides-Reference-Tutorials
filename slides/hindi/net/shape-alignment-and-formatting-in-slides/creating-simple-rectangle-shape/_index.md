---
title: .NET के लिए Aspose.Slides के साथ आयताकार आकृतियाँ बनाना
linktitle: Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड में सरल आयत आकार बनाना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET के साथ गतिशील PowerPoint प्रस्तुतियों की दुनिया का अन्वेषण करें। इस चरण-दर-चरण मार्गदर्शिका के साथ स्लाइड में आकर्षक आयताकार आकृतियाँ बनाना सीखें।
weight: 12
url: /hi/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
यदि आप अपने .NET एप्लीकेशन को गतिशील और आकर्षक पावरपॉइंट प्रेजेंटेशन के साथ बेहतर बनाना चाहते हैं, तो Aspose.Slides for .NET आपके लिए सबसे अच्छा समाधान है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for .NET का उपयोग करके प्रेजेंटेशन स्लाइड में एक सरल आयताकार आकार बनाने की प्रक्रिया के बारे में बताएंगे।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- विज़ुअल स्टूडियो: सुनिश्चित करें कि आपके विकास मशीन पर विज़ुअल स्टूडियो स्थापित है।
-  Aspose.Slides for .NET: Aspose.Slides for .NET लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/slides/net/).
- बुनियादी C# ज्ञान: C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, Aspose.Slides कार्यक्षमताओं तक पहुंचने के लिए आवश्यक नामस्थानों को आयात करके प्रारंभ करें:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## चरण 1: प्रोजेक्ट सेट अप करें
Visual Studio में एक नया C# प्रोजेक्ट बनाकर शुरू करें। सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides for .NET का सही संदर्भ दिया गया है।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // अगले चरणों के लिए आपका कोड यहां जाएगा।
}
```
## चरण 3: पहली स्लाइड प्राप्त करें
```csharp
ISlide sld = pres.Slides[0];
```
## चरण 4: आयत ऑटोशेप जोड़ें
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
यह कोड निर्देशांक (50, 150) पर 150 की चौड़ाई और 50 की ऊंचाई के साथ एक आयताकार आकार जोड़ता है।
## चरण 5: प्रस्तुति सहेजें
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
यह चरण निर्दिष्ट निर्देशिका में जोड़ी गई आयत आकृति के साथ प्रस्तुति को सहेजता है।
## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड में एक सरल आयताकार आकार सफलतापूर्वक बनाया है। यह तो बस शुरुआत है - Aspose.Slides आपके प्रेजेंटेशन को और भी कस्टमाइज़ और बेहतर बनाने के लिए कई तरह की सुविधाएँ प्रदान करता है।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या मैं Windows और Linux दोनों वातावरणों में .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, .NET के लिए Aspose.Slides प्लेटफ़ॉर्म-स्वतंत्र है और इसका उपयोग विंडोज और लिनक्स दोनों वातावरणों में किया जा सकता है।
### क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
 हां, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं .NET के लिए Aspose.Slides का समर्थन कैसे प्राप्त कर सकता हूं?
 दौरा करना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन के लिए.
### क्या मैं Aspose.Slides for .NET के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, आप एक अस्थायी लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides for .NET के लिए दस्तावेज़ कहां पा सकता हूं?
 दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
