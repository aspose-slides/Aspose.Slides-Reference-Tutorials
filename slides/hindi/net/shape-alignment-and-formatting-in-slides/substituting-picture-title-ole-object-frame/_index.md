---
title: .NET के लिए Aspose.Slides के साथ OLE ऑब्जेक्ट एम्बेड करने की गाइड
linktitle: प्रस्तुति स्लाइड में OLE ऑब्जेक्ट फ़्रेम का चित्र शीर्षक प्रतिस्थापित करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: जानें कि Aspose.Slides for .NET का उपयोग करके डायनेमिक OLE ऑब्जेक्ट के साथ अपनी प्रेजेंटेशन स्लाइड को कैसे बेहतर बनाया जाए। सहज एकीकरण के लिए हमारे चरण-दर-चरण गाइड का पालन करें।
weight: 15
url: /hi/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
गतिशील और आकर्षक प्रस्तुतिकरण स्लाइड बनाने में अक्सर विभिन्न मल्टीमीडिया तत्वों को शामिल करना शामिल होता है। इस ट्यूटोरियल में, हम शक्तिशाली Aspose.Slides for .NET लाइब्रेरी का उपयोग करके प्रस्तुतिकरण स्लाइड में OLE (ऑब्जेक्ट लिंकिंग और एम्बेडिंग) ऑब्जेक्ट फ़्रेम के चित्र शीर्षक को प्रतिस्थापित करने का तरीका जानेंगे। Aspose.Slides OLE ऑब्जेक्ट को संभालने की प्रक्रिया को सरल बनाता है, डेवलपर्स को आसानी से अपनी प्रस्तुतियों को बेहतर बनाने के लिए उपकरण प्रदान करता है।
## आवश्यक शर्तें
इससे पहले कि हम चरण-दर-चरण मार्गदर्शिका में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
-  Aspose.Slides for .NET लाइब्रेरी: सुनिश्चित करें कि आपके पास Aspose.Slides for .NET लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Slides .NET दस्तावेज़ीकरण](https://reference.aspose.com/slides/net/).
- नमूना डेटा: एक नमूना Excel फ़ाइल (जैसे, "ExcelObject.xlsx") तैयार करें जिसे आप प्रस्तुति में OLE ऑब्जेक्ट के रूप में एम्बेड करना चाहते हैं। इसके अतिरिक्त, एक छवि फ़ाइल (जैसे, "Image.png") रखें जो OLE ऑब्जेक्ट के लिए आइकन के रूप में काम करेगी।
- विकास परिवेश: आवश्यक उपकरणों, जैसे कि .NET विकास के लिए Visual Studio या कोई अन्य पसंदीदा IDE, के साथ विकास परिवेश स्थापित करें।
## नामस्थान आयात करें
अपने .NET प्रोजेक्ट में, Aspose.Slides के साथ काम करने के लिए आवश्यक नामस्थानों को आयात करना सुनिश्चित करें:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
```csharp
string dataDir = "Your Document Directory";
```
"आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करना सुनिश्चित करें।
## चरण 2: OLE स्रोत फ़ाइल और आइकन फ़ाइल पथ परिभाषित करें
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
इन पथों को अपनी नमूना एक्सेल फ़ाइल और छवि फ़ाइल के वास्तविक पथों के साथ अद्यतन करें।
## चरण 3: एक प्रेजेंटेशन इंस्टेंस बनाएं
```csharp
using (Presentation pres = new Presentation())
{
    // अगले चरणों के लिए कोड यहाँ दिया जाएगा
}
```
 का एक नया उदाहरण आरंभ करें`Presentation` कक्षा।
## चरण 4: OLE ऑब्जेक्ट फ़्रेम जोड़ें
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
स्लाइड में OLE ऑब्जेक्ट फ़्रेम जोड़ें, इसकी स्थिति और आयाम निर्दिष्ट करें।
## चरण 5: छवि ऑब्जेक्ट जोड़ें
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
छवि फ़ाइल को पढ़ें और उसे छवि ऑब्जेक्ट के रूप में प्रस्तुति में जोड़ें।
## चरण 6: कैप्शन को OLE आइकन पर सेट करें
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
OLE आइकन के लिए वांछित कैप्शन सेट करें।
## निष्कर्ष
Aspose.Slides for .NET का उपयोग करके अपनी प्रस्तुति स्लाइड में OLE ऑब्जेक्ट को शामिल करना एक सीधी प्रक्रिया है। इस ट्यूटोरियल ने आपको दस्तावेज़ निर्देशिका सेट अप करने से लेकर OLE ऑब्जेक्ट को जोड़ने और कस्टमाइज़ करने तक के आवश्यक चरणों के माध्यम से मार्गदर्शन किया है। अपनी प्रस्तुतियों की दृश्य अपील को बढ़ाने के लिए विभिन्न फ़ाइल प्रकारों और कैप्शन के साथ प्रयोग करें।
## पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides का उपयोग करके अन्य प्रकार की फ़ाइलों को OLE ऑब्जेक्ट के रूप में एम्बेड कर सकता हूँ?
हां, Aspose.Slides विभिन्न प्रकार की फ़ाइलों को एम्बेड करने का समर्थन करता है, जैसे एक्सेल स्प्रेडशीट, वर्ड दस्तावेज़, और बहुत कुछ।
### क्या OLE ऑब्जेक्ट आइकन अनुकूलन योग्य है?
बिल्कुल। आप अपनी प्रस्तुति की थीम के अनुरूप डिफ़ॉल्ट आइकन को अपनी पसंद की किसी भी छवि से बदल सकते हैं।
### क्या Aspose.Slides OLE ऑब्जेक्ट्स के साथ एनिमेशन के लिए समर्थन प्रदान करता है?
नवीनतम संस्करण के अनुसार, Aspose.Slides OLE ऑब्जेक्ट एम्बेडिंग और डिस्प्ले पर ध्यान केंद्रित करता है, और OLE ऑब्जेक्ट्स के भीतर एनिमेशन को सीधे संभालता नहीं है।
### क्या मैं स्लाइड में जोड़ने के बाद OLE ऑब्जेक्ट्स को प्रोग्रामेटिक रूप से परिवर्तित कर सकता हूँ?
निश्चित रूप से। आपके पास OLE ऑब्जेक्ट्स पर पूर्ण प्रोग्रामेटिक नियंत्रण है, जिससे आप आवश्यकतानुसार उनके गुणों और उपस्थिति को संशोधित कर सकते हैं।
### क्या एम्बेडेड OLE ऑब्जेक्ट्स के आकार पर कोई सीमाएं हैं?
हालांकि आकार की सीमाएं हैं, लेकिन वे आम तौर पर उदार हैं। इष्टतम प्रदर्शन सुनिश्चित करने के लिए अपने विशिष्ट उपयोग के मामले के साथ परीक्षण करने की अनुशंसा की जाती है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
