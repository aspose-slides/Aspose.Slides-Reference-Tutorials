---
title: मैक्रो हाइपरलिंक कैसे सेट करें .NET के लिए Aspose.Slides में क्लिक करें
linktitle: मैक्रोज़ का उपयोग करके हाइपरलिंक प्रबंधन
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides के साथ अपनी प्रस्तुतियों में मैक्रो हाइपरलिंक सेट करना सीखें। अन्तरक्रियाशीलता बढ़ाएँ और अपने दर्शकों को संलग्न करें।
type: docs
weight: 13
url: /hi/net/hyperlink-manipulation/macro-hyperlink/
---

आधुनिक सॉफ्टवेयर विकास की दुनिया में, गतिशील और इंटरैक्टिव प्रस्तुतियाँ बनाना एक महत्वपूर्ण पहलू है। .NET के लिए Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो आपको प्रस्तुतियों के साथ सहज तरीके से काम करने की अनुमति देती है। चाहे आप एक व्यावसायिक प्रस्तुति या शैक्षिक स्लाइड शो बना रहे हों, मैक्रो हाइपरलिंक क्लिक सेट करने की क्षमता उपयोगकर्ता अनुभव को काफी बढ़ा सकती है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको .NET के लिए Aspose.Slides का उपयोग करके मैक्रो हाइपरलिंक क्लिक सेट करने की प्रक्रिया के बारे में बताएंगे। 

## आवश्यक शर्तें

इससे पहले कि हम चरण-दर-चरण ट्यूटोरियल में उतरें, कुछ आवश्यक शर्तें हैं जो आपके पास होनी चाहिए:

1.विजुअल स्टूडियो: सुनिश्चित करें कि आपके कंप्यूटर पर विजुअल स्टूडियो स्थापित है, क्योंकि यह हमारा विकास वातावरण होगा।

 2. .NET के लिए Aspose.Slides: आपको .NET लाइब्रेरी के लिए Aspose.Slides इंस्टॉल करना होगा। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).

3.सी# का बुनियादी ज्ञान: इस ट्यूटोरियल के साथ सी# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।

## नामस्थान आयात करें

पहले चरण में, आइए Aspose.Slides के साथ काम करने के लिए आवश्यक नामस्थान आयात करें:

### चरण 1: नामस्थान आयात करें

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 हमने आयात किया है`Aspose.Slides` नेमस्पेस, जो प्रस्तुतियों के साथ काम करने के लिए मुख्य नेमस्पेस है, और`Aspose.Slides.Export` नामस्थान.

## मैक्रो हाइपरलिंक क्लिक सेट करना

अब, आइए इस ट्यूटोरियल के मुख्य भाग पर चलते हैं - अपनी प्रस्तुति में मैक्रो हाइपरलिंक क्लिक सेट करना।

### चरण 2: प्रस्तुति आरंभ करें

सबसे पहले, हमें एक नई प्रस्तुति प्रारंभ करने की आवश्यकता है।

```csharp
using (Presentation presentation = new Presentation())
{
    // आपका कोड यहां जाएगा.
}
```

इस स्टेटमेंट का उपयोग करके, आप एक नया प्रेजेंटेशन ऑब्जेक्ट बनाते हैं और उसके अंदर अपने सभी ऑपरेशन करते हैं।

### चरण 3: एक ऑटोशेप जोड़ें

मैक्रो हाइपरलिंक क्लिक सेट करने के लिए, आपको एक ऑब्जेक्ट की आवश्यकता होगी जिस पर उपयोगकर्ता क्लिक कर सके। इस उदाहरण में, हम क्लिक करने योग्य तत्व के रूप में एक ऑटोशेप का उपयोग करेंगे।

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

यहां, हम विशिष्ट निर्देशांक (20, 20) पर "ब्लैंकबटन" प्रकार और 80x30 के आयामों के साथ एक ऑटोशेप बनाते हैं। आप इन मानों को अपनी प्रस्तुति के लेआउट के अनुरूप अनुकूलित कर सकते हैं।

### चरण 4: मैक्रो हाइपरलिंक क्लिक सेट करें

अब वह भाग आता है जहां आप मैक्रो हाइपरलिंक क्लिक सेट करते हैं। आपको पैरामीटर के रूप में एक मैक्रो नाम प्रदान करना होगा.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

इस उदाहरण में, हमने मैक्रो हाइपरलिंक क्लिक को "टेस्टमैक्रो" पर सेट किया है। जब उपयोगकर्ता ऑटोशेप पर क्लिक करता है, तो यह इस मैक्रो को ट्रिगर करेगा।

### चरण 5: जानकारी पुनः प्राप्त करें

आप अपने द्वारा सेट किए गए हाइपरलिंक के बारे में भी जानकारी प्राप्त कर सकते हैं।

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

कोड की ये पंक्तियाँ आपको बाहरी URL और हाइपरलिंक के क्रिया प्रकार को प्रिंट करने की अनुमति देती हैं।

और बस! आपने .NET के लिए Aspose.Slides का उपयोग करके अपनी प्रस्तुति में सफलतापूर्वक एक मैक्रो हाइपरलिंक क्लिक सेट कर लिया है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए Aspose.Slides का उपयोग करके अपनी प्रस्तुति में मैक्रो हाइपरलिंक क्लिक कैसे सेट करें। यह इंटरैक्टिव और गतिशील प्रस्तुतियाँ बनाने के लिए एक मूल्यवान सुविधा हो सकती है जो आपके दर्शकों को आकर्षित करती है। .NET के लिए Aspose.Slides के साथ, आपके पास अपनी प्रस्तुति के विकास को अगले स्तर पर ले जाने के लिए एक शक्तिशाली उपकरण है।

 अब, आपके लिए कस्टम मैक्रो हाइपरलिंक के साथ प्रयोग करने और मनोरम प्रस्तुतियाँ बनाने का समय आ गया है। अन्वेषण करने के लिए स्वतंत्र महसूस करें[.NET दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/net/) अधिक गहन जानकारी और संभावनाओं के लिए।

## अक्सर पूछे जाने वाले प्रश्न (अक्सर पूछे जाने वाले प्रश्न)

### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
Aspose.Slides मुख्य रूप से .NET के लिए डिज़ाइन किया गया है, लेकिन Aspose जावा जैसी अन्य प्रोग्रामिंग भाषाओं के लिए समान लाइब्रेरी प्रदान करता है।

### क्या .NET के लिए Aspose.Slides एक निःशुल्क लाइब्रेरी है?
.NET के लिए Aspose.Slides एक व्यावसायिक लाइब्रेरी है जिसका निःशुल्क परीक्षण संस्करण उपलब्ध है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).

### क्या .NET के लिए Aspose.Slides के साथ बनाई गई प्रस्तुतियों में मैक्रोज़ का उपयोग करने की कोई सीमाएँ हैं?
.NET के लिए Aspose.Slides आपको मैक्रोज़ के साथ काम करने की अनुमति देता है, लेकिन प्रस्तुतियों में मैक्रोज़ का उपयोग करते समय आपको सुरक्षा और अनुकूलता संबंधी विचारों के बारे में पता होना चाहिए।

### क्या मैं हाइपरलिंक के लिए प्रयुक्त ऑटोशेप के स्वरूप को अनुकूलित कर सकता हूँ?
हां, आप आकार, रंग और फ़ॉन्ट जैसे गुणों को समायोजित करके ऑटोशेप के स्वरूप को अनुकूलित कर सकते हैं।

### मुझे .NET के लिए Aspose.Slides के लिए सहायता या समर्थन कहां मिल सकता है?
 यदि आपको कोई समस्या आती है या आपके कोई प्रश्न हैं, तो आप Aspose सहायता फ़ोरम पर सहायता ले सकते हैं[यहाँ](https://forum.aspose.com/).