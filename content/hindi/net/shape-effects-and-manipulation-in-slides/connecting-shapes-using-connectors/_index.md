---
title: Aspose.Slides - .NET में आकृतियों को निर्बाध रूप से कनेक्ट करें
linktitle: प्रेजेंटेशन में कनेक्टर्स का उपयोग करके आकृतियों को जोड़ना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides की शक्ति का अन्वेषण करें, जो आपकी प्रस्तुतियों में आकृतियों को सहजता से जोड़ता है। डायनामिक कनेक्टर्स के साथ अपनी स्लाइड्स को ऊंचा उठाएं।
type: docs
weight: 29
url: /hi/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## परिचय
प्रस्तुतियों की गतिशील दुनिया में, कनेक्टर्स का उपयोग करके आकृतियों को जोड़ने की क्षमता आपकी स्लाइड्स में परिष्कार की एक परत जोड़ती है। .NET के लिए Aspose.Slides डेवलपर्स को इसे निर्बाध रूप से हासिल करने का अधिकार देता है। यह ट्यूटोरियल स्पष्ट समझ सुनिश्चित करने के लिए प्रत्येक चरण का विवरण देते हुए प्रक्रिया में आपका मार्गदर्शन करेगा।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- C# और .NET फ्रेमवर्क का बुनियादी ज्ञान।
-  .NET के लिए Aspose.Slides स्थापित। यदि नहीं, तो इसे डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/net/).
- एक विकास वातावरण स्थापित किया गया।
## नामस्थान आयात करें
अपने C# कोड में, आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. दस्तावेज़ निर्देशिका सेट करें
अपने दस्तावेज़ के लिए निर्देशिका को परिभाषित करके प्रारंभ करें:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. त्वरित प्रस्तुति कक्षा
अपनी PPTX फ़ाइल का प्रतिनिधित्व करने के लिए प्रेजेंटेशन क्लास का एक उदाहरण बनाएं:
```csharp
using (Presentation input = new Presentation())
{
    // चयनित स्लाइड के लिए आकृतियों के संग्रह तक पहुँचना
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. स्लाइड में आकृतियाँ जोड़ें
अपनी स्लाइड में आवश्यक आकृतियाँ जोड़ें, जैसे दीर्घवृत्त और आयत:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. कनेक्टर आकार जोड़ें
स्लाइड के आकार संग्रह में एक कनेक्टर आकार शामिल करें:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. आकृतियों को कनेक्टर से कनेक्ट करें
कनेक्टर द्वारा कनेक्ट की जाने वाली आकृतियाँ निर्दिष्ट करें:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. रीरूट कनेक्टर
आकृतियों के बीच स्वचालित सबसे छोटा पथ सेट करने के लिए पुन: मार्ग विधि को कॉल करें:
```csharp
connector.Reroute();
```
## 7. प्रस्तुति सहेजें
जुड़ी हुई आकृतियों को देखने के लिए अपनी प्रस्तुति सहेजें:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## निष्कर्ष
बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड्स में कनेक्टर्स का उपयोग करके आकृतियों को सफलतापूर्वक कनेक्ट कर लिया है। इस उन्नत सुविधा के साथ अपनी प्रस्तुतियों को बेहतर बनाएं और अपने दर्शकों को मंत्रमुग्ध करें।
## पूछे जाने वाले प्रश्न
### क्या .NET के लिए Aspose.Slides नवीनतम .NET फ्रेमवर्क के साथ संगत है?
हां, नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगतता सुनिश्चित करने के लिए .NET के लिए Aspose.Slides को नियमित रूप से अपडेट किया जाता है।
### क्या मैं एक ही कनेक्टर का उपयोग करके दो से अधिक आकृतियाँ जोड़ सकता हूँ?
बिल्कुल, आप अपने कोड में कनेक्टर लॉजिक को विस्तारित करके कई आकृतियों को कनेक्ट कर सकते हैं।
### क्या उन आकृतियों पर कोई सीमाएँ हैं जिन्हें मैं जोड़ सकता हूँ?
.NET के लिए Aspose.Slides बुनियादी आकृतियों, स्मार्ट आर्ट और कस्टम आकृतियों सहित विभिन्न आकृतियों को जोड़ने का समर्थन करता है।
### मैं कनेक्टर के स्वरूप को कैसे अनुकूलित कर सकता हूँ?
लाइन शैली और रंग जैसे कनेक्टर स्वरूप को अनुकूलित करने के तरीकों के लिए Aspose.Slides दस्तावेज़ का अन्वेषण करें।
### क्या Aspose.Slides समर्थन के लिए कोई सामुदायिक मंच है?
 हाँ, आप सहायता पा सकते हैं और अपने अनुभव साझा कर सकते हैं[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11).