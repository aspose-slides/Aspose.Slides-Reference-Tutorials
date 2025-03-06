---
title: Aspose.Slides .NET ट्यूटोरियल के साथ PowerPoint में आकृतियाँ छिपाएँ
linktitle: Aspose.Slides के साथ प्रेजेंटेशन स्लाइड में आकृतियाँ छिपाना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET का उपयोग करके PowerPoint स्लाइड में आकृतियों को छिपाने का तरीका जानें। इस चरण-दर-चरण मार्गदर्शिका के साथ प्रस्तुतियों को प्रोग्रामेटिक रूप से अनुकूलित करें।
weight: 21
url: /hi/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
प्रस्तुतियों की गतिशील दुनिया में, अनुकूलन महत्वपूर्ण है। Aspose.Slides for .NET, PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से हेरफेर करने के लिए एक शक्तिशाली समाधान प्रदान करता है। एक सामान्य आवश्यकता स्लाइड के भीतर विशिष्ट आकृतियों को छिपाने की क्षमता है। यह ट्यूटोरियल आपको Aspose.Slides for .NET का उपयोग करके प्रस्तुति स्लाइड में आकृतियों को छिपाने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
-  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके पास Aspose.Slides लाइब्रेरी स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- विकास वातावरण: .NET के लिए अपना पसंदीदा विकास वातावरण सेट करें।
- C# का मूलभूत ज्ञान: C# से परिचित हो जाएं क्योंकि दिए गए कोड उदाहरण इसी भाषा में हैं।
## नामस्थान आयात करें
Aspose.Slides के साथ काम करना शुरू करने के लिए, अपने C# प्रोजेक्ट में आवश्यक नेमस्पेस आयात करें। यह सुनिश्चित करता है कि आपके पास आवश्यक क्लास और विधियों तक पहुँच है।
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
अब, स्पष्ट और संक्षिप्त समझ के लिए आइए उदाहरण कोड को कई चरणों में विभाजित करें।
## चरण 1: अपना प्रोजेक्ट सेट करें
एक नया C# प्रोजेक्ट बनाएं और Aspose.Slides लाइब्रेरी को शामिल करना सुनिश्चित करें।
## चरण 2: एक प्रस्तुति बनाएं
 उदाहरण प्रस्तुत करें`Presentation` क्लास, जो PowerPoint फ़ाइल का प्रतिनिधित्व करता है। एक स्लाइड जोड़ें और उसका संदर्भ प्राप्त करें।
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## चरण 3: स्लाइड में आकृतियाँ जोड़ें
स्लाइड में विशिष्ट आयामों के साथ आयत और चंद्रमा जैसे स्वतः आकृतियाँ जोड़ें।
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## चरण 4: वैकल्पिक पाठ के आधार पर आकृतियाँ छिपाएँ
वैकल्पिक पाठ निर्दिष्ट करें और इस पाठ से मेल खाने वाली आकृतियाँ छिपाएँ.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## चरण 5: प्रस्तुति सहेजें
संशोधित प्रस्तुति को PPTX प्रारूप में डिस्क पर सहेजें।
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## निष्कर्ष
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## पूछे जाने वाले प्रश्न
### क्या Aspose.Slides .NET कोर के साथ संगत है?
हां, Aspose.Slides .NET कोर का समर्थन करता है, जो आपके विकास वातावरण में लचीलापन प्रदान करता है।
### क्या मैं वैकल्पिक पाठ के अलावा अन्य स्थितियों के आधार पर आकृतियों को छिपा सकता हूँ?
बिल्कुल! आप आकृति प्रकार, रंग या स्थिति जैसी विभिन्न विशेषताओं के आधार पर छिपाने के तर्क को अनुकूलित कर सकते हैं।
### मैं अतिरिक्त Aspose.Slides दस्तावेज़ कहां पा सकता हूं?
 दस्तावेज़ देखें[यहाँ](https://reference.aspose.com/slides/net/)गहन जानकारी और उदाहरण के लिए.
### क्या Aspose.Slides के लिए अस्थायी लाइसेंस उपलब्ध हैं?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/)परीक्षण प्रयोजनों के लिए.
### मैं Aspose.Slides के लिए सामुदायिक समर्थन कैसे प्राप्त कर सकता हूं?
 Aspose.Slides समुदाय में शामिल हों[मंच](https://forum.aspose.com/c/slides/11) चर्चा और सहायता के लिए।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
