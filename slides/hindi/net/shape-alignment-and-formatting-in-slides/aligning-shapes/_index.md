---
title: .NET के लिए Aspose.Slides के साथ आकार संरेखण में महारत हासिल करें
linktitle: Aspose.Slides का उपयोग करके प्रस्तुति स्लाइड में आकृतियों को संरेखित करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET का उपयोग करके प्रस्तुति स्लाइड में आकृतियों को आसानी से संरेखित करना सीखें। सटीक संरेखण के साथ दृश्य अपील को बढ़ाएँ। अभी डाउनलोड करें!
type: docs
weight: 10
url: /hi/net/shape-alignment-and-formatting-in-slides/aligning-shapes/
---
## परिचय
आकर्षक प्रस्तुतिकरण स्लाइड बनाने के लिए अक्सर आकृतियों के सटीक संरेखण की आवश्यकता होती है। Aspose.Slides for .NET इसे आसानी से प्राप्त करने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम Aspose.Slides for .NET का उपयोग करके प्रस्तुतिकरण स्लाइड में आकृतियों को संरेखित करने का तरीका जानेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
-  Aspose.Slides for .NET लाइब्रेरी: सुनिश्चित करें कि आपके पास Aspose.Slides for .NET लाइब्रेरी स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- विकास वातावरण: अपनी मशीन पर .NET विकास वातावरण स्थापित करें।
## नामस्थान आयात करें
अपने .NET अनुप्रयोग में, Aspose.Slides के साथ काम करने के लिए आवश्यक नामस्थान आयात करें:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## चरण 1: प्रस्तुति आरंभ करें
प्रस्तुति ऑब्जेक्ट को आरंभीकृत करके और स्लाइड जोड़कर आरंभ करें:
```csharp
string dataDir = "Your Document Directory";
string outpptxFile = Path.Combine(dataDir, "ShapesAlignment_out.pptx");
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
    // कुछ आकृतियाँ बनाएँ
    // ...
}
```
## चरण 2: स्लाइड के भीतर आकृतियों को संरेखित करें
 स्लाइड में आकृतियाँ जोड़ें और उन्हें संरेखित करें`SlideUtil.AlignShapes` तरीका:
```csharp
slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 100, 100);
slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 200, 100, 100);
slide.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
// IBaseSlide के भीतर सभी आकृतियों को संरेखित करना।
SlideUtil.AlignShapes(ShapesAlignmentType.AlignBottom, true, pres.Slides[0]);
```
## चरण 3: समूह के भीतर आकृतियों को संरेखित करें
एक समूह आकृति बनाएं, उसमें आकृतियां जोड़ें, और उन्हें समूह के भीतर संरेखित करें:
```csharp
slide = pres.Slides.AddEmptySlide(slide.LayoutSlide);
IGroupShape groupShape = slide.Shapes.AddGroupShape();
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 350, 50, 50, 50);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 450, 150, 50, 50);
// IGroupShape के अंतर्गत सभी आकृतियों को संरेखित करना।
SlideUtil.AlignShapes(ShapesAlignmentType.AlignLeft, false, groupShape);
```
## चरण 4: किसी समूह के भीतर विशिष्ट आकृतियों को संरेखित करें
किसी समूह के भीतर विशिष्ट आकृतियों को उनके अनुक्रम प्रदान करके संरेखित करें:
```csharp
slide = pres.Slides.AddEmptySlide(slide.LayoutSlide);
groupShape = slide.Shapes.AddGroupShape();
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 350, 50, 50, 50);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 450, 150, 50, 50);
// IGroupShape के भीतर निर्दिष्ट अनुक्रमणिकाओं के साथ आकृतियों को संरेखित करना।
SlideUtil.AlignShapes(ShapesAlignmentType.AlignLeft, false, groupShape, new int[] { 0, 2 });
```
## निष्कर्ष
आकृतियों को सटीक रूप से संरेखित करने के लिए .NET के लिए Aspose.Slides का लाभ उठाकर अपनी प्रस्तुति स्लाइड्स की दृश्य अपील को आसानी से बढ़ाएँ। इस चरण-दर-चरण मार्गदर्शिका ने आपको संरेखण प्रक्रिया को सुव्यवस्थित करने और पेशेवर दिखने वाली प्रस्तुतियाँ बनाने के लिए ज्ञान से लैस किया है।
## पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides for .NET का उपयोग करके किसी मौजूदा प्रस्तुति में आकृतियों को संरेखित कर सकता हूँ?
 हां, आप किसी मौजूदा प्रस्तुति को लोड कर सकते हैं`Presentation.Load` और फिर आकृतियों को संरेखित करने के साथ आगे बढ़ें।
### क्या Aspose.Slides में अन्य संरेखण विकल्प उपलब्ध हैं?
Aspose.Slides विभिन्न संरेखण विकल्प प्रदान करता है, जिसमें AlignTop, AlignRight, AlignBottom, AlignLeft, आदि शामिल हैं।
### क्या मैं स्लाइड में आकृतियों के वितरण के आधार पर उन्हें संरेखित कर सकता हूँ?
बिल्कुल! Aspose.Slides क्षैतिज और ऊर्ध्वाधर दोनों तरह से आकृतियों को समान रूप से वितरित करने के तरीके प्रदान करता है।
### क्या Aspose.Slides क्रॉस-प्लेटफॉर्म विकास के लिए उपयुक्त है?
Aspose.Slides for .NET मुख्य रूप से Windows अनुप्रयोगों के लिए डिज़ाइन किया गया है, लेकिन Aspose Java और अन्य प्लेटफ़ॉर्म के लिए भी लाइब्रेरी प्रदान करता है।
### मैं आगे सहायता या समर्थन कैसे प्राप्त कर सकता हूं?
 दौरा करना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन और चर्चा के लिए।