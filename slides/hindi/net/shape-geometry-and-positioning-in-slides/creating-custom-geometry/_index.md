---
title: .NET के लिए Aspose.Slides के साथ C# में कस्टम ज्यामिति बनाना
linktitle: Aspose.Slides का उपयोग करके ज्यामिति आकार में कस्टम ज्यामिति बनाना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: .NET के लिए Aspose.Slides में कस्टम ज्यामिति बनाना सीखें। अपनी प्रस्तुतियों को अद्वितीय आकृतियों के साथ बेहतर बनाएँ। C# डेवलपर्स के लिए चरण-दर-चरण मार्गदर्शिका।
weight: 15
url: /hi/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Slides के साथ C# में कस्टम ज्यामिति बनाना

## परिचय
प्रस्तुतियों की गतिशील दुनिया में, अद्वितीय आकृतियाँ और ज्यामिति जोड़ना आपकी सामग्री को और बेहतर बना सकता है, जिससे यह अधिक आकर्षक और दृष्टिगत रूप से आकर्षक बन सकती है। .NET के लिए Aspose.Slides आकृतियों के भीतर कस्टम ज्यामिति बनाने के लिए एक शक्तिशाली समाधान प्रदान करता है, जिससे आप पारंपरिक डिज़ाइन से मुक्त हो सकते हैं। यह ट्यूटोरियल आपको .NET के लिए Aspose.Slides का उपयोग करके GeometryShape में कस्टम ज्यामिति बनाने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- C# प्रोग्रामिंग भाषा की बुनियादी समझ।
- आपके विकास परिवेश में Aspose.Slides for .NET लाइब्रेरी स्थापित है।
- विजुअल स्टूडियो या कोई भी पसंदीदा C# विकास वातावरण स्थापित करें।
## नामस्थान आयात करें
आरंभ करने के लिए, अपने C# प्रोजेक्ट में आवश्यक नामस्थान आयात करें:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा डेवलपमेंट एनवायरनमेंट में एक नया C# प्रोजेक्ट बनाएँ। सुनिश्चित करें कि Aspose.Slides for .NET ठीक से इंस्टॉल है।
## चरण 2: अपनी दस्तावेज़ निर्देशिका निर्धारित करें
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## चरण 3: बाहरी और आंतरिक स्टार त्रिज्या सेट करें
```csharp
float R = 100, r = 50; // बाह्य और आंतरिक तारा त्रिज्या
```
## चरण 4: स्टार ज्यामिति पथ बनाएँ
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## चरण 5: एक प्रस्तुति बनाएं
```csharp
using (Presentation pres = new Presentation())
{
    // नया आकार बनाएं
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // आकृति के लिए नया ज्यामिति पथ सेट करें
    shape.SetGeometryPath(starPath);
    // प्रस्तुति सहेजें
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## चरण 6: CreateStarGeometry विधि परिभाषित करें
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके GeometryShape में कस्टम ज्यामिति बनाने का तरीका सफलतापूर्वक सीख लिया है। इससे अद्वितीय और नेत्रहीन आश्चर्यजनक प्रस्तुतियाँ बनाने की संभावनाओं की दुनिया खुल जाती है।
## पूछे जाने वाले प्रश्न
### 1. क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, Aspose.Slides विभिन्न प्रोग्रामिंग भाषाओं का समर्थन करता है, लेकिन यह ट्यूटोरियल C# पर केंद्रित है।
### 2. मैं Aspose.Slides for .NET के लिए दस्तावेज़ कहां पा सकता हूं?
 दौरा करना[प्रलेखन](https://reference.aspose.com/slides/net/) विस्तृत जानकारी के लिए.
### 3. क्या Aspose.Slides for .NET के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप खोज कर सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) सुविधाओं का अनुभव करने के लिए.
### 4. मैं .NET के लिए Aspose.Slides का समर्थन कैसे प्राप्त कर सकता हूं?
 सहायता प्राप्त करें और समुदाय के साथ जुड़ें[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### 5. मैं .NET के लिए Aspose.Slides कहां से खरीद सकता हूं?
 आप .NET के लिए Aspose.Slides खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
