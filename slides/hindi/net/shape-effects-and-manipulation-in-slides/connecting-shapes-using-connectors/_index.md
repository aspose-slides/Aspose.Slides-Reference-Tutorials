---
"description": "Aspose.Slides for .NET की शक्ति का अनुभव करें, अपनी प्रस्तुतियों में आकृतियों को आसानी से कनेक्ट करें। डायनेमिक कनेक्टर के साथ अपनी स्लाइड्स को बेहतर बनाएँ।"
"linktitle": "प्रेजेंटेशन में कनेक्टर्स का उपयोग करके आकृतियों को जोड़ना"
"second_title": "Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API"
"title": "Aspose.Slides - .NET में आकृतियों को सहजता से जोड़ें"
"url": "/hi/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - .NET में आकृतियों को सहजता से जोड़ें

## परिचय
प्रस्तुतियों की गतिशील दुनिया में, कनेक्टर का उपयोग करके आकृतियों को जोड़ने की क्षमता आपकी स्लाइड्स में परिष्कार की एक परत जोड़ती है। Aspose.Slides for .NET डेवलपर्स को इसे सहजता से प्राप्त करने में सक्षम बनाता है। यह ट्यूटोरियल आपको प्रक्रिया के माध्यम से मार्गदर्शन करेगा, एक स्पष्ट समझ सुनिश्चित करने के लिए प्रत्येक चरण को तोड़ देगा।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- C# और .NET फ्रेमवर्क का बुनियादी ज्ञान।
- Aspose.Slides for .NET इंस्टॉल है। यदि नहीं, तो इसे डाउनलोड करें [यहाँ](https://releases.aspose.com/slides/net/).
- एक विकास वातावरण स्थापित किया गया।
## नामस्थान आयात करें
अपने C# कोड में, आवश्यक नामस्थानों को आयात करके प्रारंभ करें:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. दस्तावेज़ निर्देशिका सेट करें
अपने दस्तावेज़ के लिए निर्देशिका परिभाषित करके आरंभ करें:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. इंस्टैंशियेट प्रेजेंटेशन क्लास
अपनी PPTX फ़ाइल को दर्शाने के लिए प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ:
```csharp
using (Presentation input = new Presentation())
{
    // चयनित स्लाइड के लिए आकृति संग्रह तक पहुँचना
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. स्लाइड में आकृतियाँ जोड़ें
अपनी स्लाइड में आवश्यक आकृतियाँ जोड़ें, जैसे दीर्घवृत्त और आयत:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. कनेक्टर आकार जोड़ें
स्लाइड के आकार संग्रह में कनेक्टर आकार शामिल करें:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. कनेक्टर के साथ आकृतियाँ कनेक्ट करें
कनेक्टर द्वारा कनेक्ट की जाने वाली आकृतियों को निर्दिष्ट करें:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. रीरूट कनेक्टर
आकृतियों के बीच स्वचालित सबसे छोटा रास्ता निर्धारित करने के लिए रीराउट विधि को कॉल करें:
```csharp
connector.Reroute();
```
## 7. प्रस्तुति सहेजें
जुड़ी हुई आकृतियों को देखने के लिए अपनी प्रस्तुति सहेजें:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके प्रेजेंटेशन स्लाइड में कनेक्टर का उपयोग करके आकृतियों को सफलतापूर्वक कनेक्ट किया है। इस उन्नत सुविधा के साथ अपनी प्रेजेंटेशन को बेहतर बनाएँ और अपने दर्शकों को आकर्षित करें।
## पूछे जाने वाले प्रश्न
### क्या Aspose.Slides for .NET नवीनतम .NET फ्रेमवर्क के साथ संगत है?
हां, नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगतता सुनिश्चित करने के लिए Aspose.Slides for .NET को नियमित रूप से अपडेट किया जाता है।
### क्या मैं एक ही कनेक्टर का उपयोग करके दो से अधिक आकृतियों को जोड़ सकता हूँ?
बिल्कुल, आप अपने कोड में कनेक्टर लॉजिक का विस्तार करके एकाधिक आकृतियों को जोड़ सकते हैं।
### क्या मेरे द्वारा जोड़े जा सकने वाले आकृतियों पर कोई सीमाएं हैं?
Aspose.Slides for .NET विभिन्न आकृतियों को जोड़ने का समर्थन करता है, जिसमें मूल आकृतियाँ, स्मार्ट आर्ट और कस्टम आकृतियाँ शामिल हैं।
### मैं कनेक्टर के स्वरूप को कैसे अनुकूलित कर सकता हूँ?
कनेक्टर उपस्थिति को अनुकूलित करने के तरीकों के लिए Aspose.Slides दस्तावेज़ देखें, जैसे लाइन शैली और रंग।
### क्या Aspose.Slides समर्थन के लिए कोई सामुदायिक मंच है?
हां, आप सहायता पा सकते हैं और अपने अनुभव साझा कर सकते हैं [Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}