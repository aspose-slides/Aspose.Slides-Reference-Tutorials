---
title: Aspose.Slides में आकार के लिए सीमाओं के साथ थंबनेल बनाना
linktitle: Aspose.Slides में आकार के लिए सीमाओं के साथ थंबनेल बनाना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides की शक्ति अनलॉक करें! हमारे चरण-दर-चरण मार्गदर्शिका का उपयोग करके सीमाओं के साथ सहजता से आकार के थंबनेल बनाना सीखें।
type: docs
weight: 10
url: /hi/net/image-and-video-manipulation-in-slides/creating-thumbnail-bounds-shape/
---
## परिचय
यदि आप एक .NET डेवलपर हैं जो PowerPoint प्रस्तुतियों में आकृतियों की सीमा के साथ थंबनेल छवियां बनाने के लिए एक मजबूत समाधान ढूंढ रहे हैं, तो .NET के लिए Aspose.Slides आपका पसंदीदा उपकरण है। यह शक्तिशाली लाइब्रेरी निर्बाध एकीकरण प्रदान करती है, जो आपको PowerPoint फ़ाइलों से मूल्यवान जानकारी को कुशलतापूर्वक हेरफेर करने और निकालने की अनुमति देती है। इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके किसी आकृति की सीमाओं के साथ एक थंबनेल बनाने की प्रक्रिया से गुजरेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET लाइब्रेरी के लिए Aspose.Slides: .NET लाइब्रेरी के लिए Aspose.Slides को यहां से डाउनलोड और इंस्टॉल करें।[यहाँ](https://releases.aspose.com/slides/net/).
2. आपकी दस्तावेज़ निर्देशिका: कोड स्निपेट में "आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलें।
## नामस्थान आयात करें
Aspose.Slides की कार्यक्षमता का लाभ उठाने के लिए आवश्यक नामस्थान आयात करके शुरुआत करें। अपने प्रोजेक्ट की शुरुआत में निम्नलिखित कोड जोड़ें:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
अब, व्यापक समझ के लिए दिए गए कोड को कई चरणों में तोड़ते हैं:
## चरण 1: त्वरित प्रस्तुति कक्षा
```csharp
string dataDir = "Your Documents Directory";
// प्रेजेंटेशन क्लास को इंस्टेंट करें जो प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // प्रेजेंटेशन ऑब्जेक्ट अब आगे के हेरफेर के लिए तैयार है।
}
```
 इस चरण में, हम Aspose.Slides को आरंभ करते हैं`Presentation` क्लास, पावरपॉइंट प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है।`using` ब्लॉक से बाहर निकलने के बाद स्टेटमेंट संसाधनों का उचित निपटान सुनिश्चित करता है।
## चरण 2: एक बंधी हुई आकृति वाली छवि बनाएं
```csharp
// एक उपस्थिति बाध्य आकार छवि बनाएं
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
    // बिटमैप ऑब्जेक्ट में अब निर्दिष्ट सीमाओं के साथ थंबनेल छवि शामिल है।
}
```
 इस चरण में निर्दिष्ट सीमाओं के साथ किसी आकृति की थंबनेल छवि बनाना शामिल है। यहाँ,`ShapeThumbnailBounds.Appearance`उपस्थिति सीमा को परिभाषित करने के लिए उपयोग किया जाता है। अपनी आवश्यकताओं के अनुसार पैरामीटर (1, 1) समायोजित करें।
## चरण 3: छवि को डिस्क पर सहेजें
```csharp
// छवि को पीएनजी प्रारूप में डिस्क पर सहेजें
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```
इस अंतिम चरण में, उत्पन्न थंबनेल छवि को पीएनजी प्रारूप में डिस्क पर सहेजा जाता है। आप अपनी प्राथमिकताओं के आधार पर फ़ाइल नाम और प्रारूप को अनुकूलित कर सकते हैं।
अब, आपने .NET के लिए Aspose.Slides का उपयोग करके किसी आकृति की सीमाओं के साथ सफलतापूर्वक एक थंबनेल बना लिया है! यह प्रक्रिया कुशल है और PowerPoint प्रस्तुतियों को संभालने के लिए इसे आपके .NET प्रोजेक्ट में सहजता से एकीकृत किया जा सकता है।
## निष्कर्ष
.NET के लिए Aspose.Slides PowerPoint प्रस्तुतियों के साथ काम करने की प्रक्रिया को सरल बनाता है, डेवलपर्स को आकृतियों की सीमाओं के साथ थंबनेल बनाने जैसे कार्यों के लिए शक्तिशाली उपकरण प्रदान करता है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आपने अपने .NET प्रोजेक्टों के लिए इस लाइब्रेरी का कुशलतापूर्वक उपयोग करने के बारे में जानकारी प्राप्त की है।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या Aspose.Slides नवीनतम .NET फ्रेमवर्क के साथ संगत है?
हां, नवीनतम .NET फ्रेमवर्क संस्करणों के साथ संगतता सुनिश्चित करने के लिए Aspose.Slides को नियमित रूप से अपडेट किया जाता है।
### क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.Slides का उपयोग कर सकता हूँ?
बिल्कुल! Aspose.Slides व्यक्तिगत और व्यावसायिक उपयोग दोनों के लिए लाइसेंसिंग विकल्प प्रदान करता है। मिलने जाना[यहाँ](https://purchase.aspose.com/buy) लाइसेंसिंग विवरण का पता लगाने के लिए।
### क्या Aspose.Slides के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप निःशुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/) खरीदारी करने से पहले सुविधाओं का पता लगाएं।
### मैं Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 दौरा करना[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/c/slides/11) समुदाय से जुड़ने और अनुभवी डेवलपर्स से सहायता लेने के लिए।
### क्या मैं Aspose.Slides के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) अल्पकालिक परियोजना आवश्यकताओं के लिए.