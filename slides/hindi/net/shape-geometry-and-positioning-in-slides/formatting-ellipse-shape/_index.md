---
title: .NET के लिए Aspose.Slides के साथ दीर्घवृत्त आकार स्वरूपण ट्यूटोरियल
linktitle: Aspose.Slides के साथ स्लाइड्स में दीर्घवृत्त आकार को प्रारूपित करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: .NET के लिए Aspose.Slides का उपयोग करके PowerPoint में शानदार दीर्घवृत्त आकार बनाएँ। पेशेवर प्रस्तुतियों के लिए हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/net/shape-geometry-and-positioning-in-slides/formatting-ellipse-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET के लिए Aspose.Slides के साथ दीर्घवृत्त आकार स्वरूपण ट्यूटोरियल

## परिचय
अपने दर्शकों को आकर्षित करने के लिए अपने PowerPoint प्रेजेंटेशन को आकर्षक आकृतियों से बेहतर बनाना बहुत ज़रूरी है। ऐसी ही एक आकृति है दीर्घवृत्त, जो आपकी स्लाइड्स में सुंदरता और व्यावसायिकता का स्पर्श जोड़ सकती है। इस ट्यूटोरियल में, हम आपको .NET के लिए Aspose.Slides का उपयोग करके PowerPoint में दीर्घवृत्त आकृतियों को फ़ॉर्मेट करने की प्रक्रिया के बारे में बताएँगे।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके मशीन पर Visual Studio स्थापित है.
-  Aspose.Slides for .NET लाइब्रेरी, जिसे आप यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
- सुनिश्चित करें कि आपके पास अपने सिस्टम पर फ़ाइलें बनाने और सहेजने के लिए आवश्यक अनुमतियाँ हैं।
## नामस्थान आयात करें
आरंभ करने के लिए, आपको अपने C# प्रोजेक्ट में आवश्यक नेमस्पेस आयात करने की आवश्यकता है। यह सुनिश्चित करता है कि आपके पास Aspose.Slides के साथ काम करने के लिए आवश्यक क्लासेस और विधियों तक पहुँच है।
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using System.Drawing;
```
अब, आइए इस उदाहरण को कई चरणों में विभाजित करें, जिससे .NET के लिए Aspose.Slides का उपयोग करके PowerPoint में दीर्घवृत्त आकृतियों को प्रारूपित करने के बारे में एक व्यापक मार्गदर्शिका प्राप्त होगी।
## चरण 1: अपना प्रोजेक्ट सेट करें
 Visual Studio में एक नया C# प्रोजेक्ट बनाएँ और Aspose.Slides लाइब्रेरी का संदर्भ जोड़ें। यदि आपने इसे अभी तक डाउनलोड नहीं किया है, तो आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).
## चरण 2: अपनी दस्तावेज़ निर्देशिका निर्धारित करें
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
सुनिश्चित करें कि निर्दिष्ट निर्देशिका मौजूद है या नहीं तो उसे बनाएं।
## चरण 3: प्रेजेंटेशन क्लास को इंस्टैंशिएट करें
```csharp
using (Presentation pres = new Presentation())
{
    // दीर्घवृत्त आकार स्वरूपण के लिए आपका कोड यहाँ है
}
```
 इसका एक उदाहरण बनाएं`Presentation` क्लास, जो पावरपॉइंट फ़ाइल का प्रतिनिधित्व करता है।
## चरण 4: पहली स्लाइड प्राप्त करें
```csharp
ISlide sld = pres.Slides[0];
```
अपनी प्रस्तुति की पहली स्लाइड तक पहुँचें.
## चरण 5: दीर्घवृत्त ऑटोशेप जोड़ें
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
स्लाइड पर एक दीर्घवृत्त ऑटोशेप डालें, इसकी स्थिति और आयाम निर्दिष्ट करें।
## चरण 6: दीर्घवृत्त आकार को प्रारूपित करें
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
दीर्घवृत्त आकार पर स्वरूपण लागू करें, भरण रंग और रेखा गुण सेट करें।
## चरण 7: प्रेजेंटेशन सहेजें
```csharp
pres.Save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
संशोधित प्रस्तुति को डिस्क पर सहेजें.
इन चरणों का सावधानीपूर्वक पालन करें, और आपके पावरपॉइंट प्रेजेंटेशन में एक सुंदर स्वरूपित दीर्घवृत्त आकार होगा।
## निष्कर्ष
दीर्घवृत्त जैसी दिखने वाली आकर्षक आकृतियों को शामिल करने से आपके पावरपॉइंट प्रेजेंटेशन की सौंदर्य अपील में उल्लेखनीय वृद्धि हो सकती है। Aspose.Slides for .NET इस प्रक्रिया को सहज बनाता है, जिससे आप आसानी से पेशेवर दिखने वाली स्लाइड बना सकते हैं।

## पूछे जाने वाले प्रश्न
### क्या Aspose.Slides PowerPoint के नवीनतम संस्करणों के साथ संगत है?
Aspose.Slides नवीनतम सहित विभिन्न PowerPoint संस्करणों के साथ संगतता सुनिश्चित करता है।[प्रलेखन](https://reference.aspose.com/slides/net/) विशिष्ट विवरण के लिए कृपया देखें.
### क्या मैं .NET के लिए Aspose.Slides का निःशुल्क परीक्षण डाउनलोड कर सकता हूँ?
 हां, आप निःशुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 मिलने जाना[इस लिंक](https://purchase.aspose.com/temporary-license/) अस्थायी लाइसेंस प्राप्त करने के लिए।
### मैं Aspose.Slides-संबंधित प्रश्नों के लिए समर्थन कहां पा सकता हूं?
 समुदाय से सहायता मांगें[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
### क्या Aspose.Slides for .NET के लिए कोई प्रत्यक्ष खरीद विकल्प है?
 हां, आप सीधे लाइब्रेरी खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
