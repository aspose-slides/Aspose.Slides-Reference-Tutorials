---
title: .NET के लिए Aspose.Slides के साथ चार्ट रंगीकरण
linktitle: चार्ट में डेटा बिंदुओं में रंग जोड़ें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides के साथ चार्ट में डेटा बिंदुओं में रंग जोड़ने का तरीका जानें। अपनी प्रस्तुतियों को दृष्टिगत रूप से उन्नत करें और अपने दर्शकों को प्रभावी ढंग से संलग्न करें।
type: docs
weight: 12
url: /hi/net/licensing-and-formatting/add-color-to-data-points/
---

इस चरण-दर-चरण मार्गदर्शिका में, हम आपको .NET के लिए Aspose.Slides का उपयोग करके चार्ट में डेटा बिंदुओं में रंग जोड़ने की प्रक्रिया के बारे में बताएंगे। Aspose.Slides .NET अनुप्रयोगों में PowerPoint प्रस्तुतियों के साथ काम करने के लिए एक शक्तिशाली लाइब्रेरी है। चार्ट में डेटा बिंदुओं में रंग जोड़ने से आपकी प्रस्तुतियाँ अधिक आकर्षक और समझने में आसान हो सकती हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1. विजुअल स्टूडियो: आपको अपने कंप्यूटर पर विजुअल स्टूडियो स्थापित करना होगा।

2. .NET के लिए Aspose.Slides: .NET के लिए Aspose.Slides को डाउनलोड और इंस्टॉल करें।[लिंक को डाउनलोड करें](https://releases.aspose.com/slides/net/).

3. C# की बुनियादी समझ: आपको C# प्रोग्रामिंग का बुनियादी ज्ञान होना चाहिए।

4. आपकी दस्तावेज़ निर्देशिका: कोड में "आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से बदलें।

## नामस्थान आयात करना

इससे पहले कि आप .NET के लिए Aspose.Slides के साथ काम कर सकें, आपको आवश्यक नेमस्पेस आयात करना होगा। 

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides;
```


इस उदाहरण में, हम सनबर्स्ट चार्ट प्रकार का उपयोग करके चार्ट में डेटा बिंदुओं में रंग जोड़ेंगे।

```csharp
using (Presentation pres = new Presentation())
{
    // दस्तावेज़ निर्देशिका का पथ.
    string dataDir = "Your Document Directory";

    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Sunburst, 100, 100, 450, 400);
    
    // बाकी कोड निम्नलिखित चरणों में जोड़ा जाएगा।
}
```

## चरण 1: डेटा बिंदुओं तक पहुँचना

किसी चार्ट में विशिष्ट डेटा बिंदुओं में रंग जोड़ने के लिए, आपको उन डेटा बिंदुओं तक पहुंचने की आवश्यकता है। इस उदाहरण में, हम डेटा बिंदु 3 को लक्षित करेंगे।

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## चरण 2: डेटा लेबल को अनुकूलित करना

अब, डेटा बिंदु 0 के लिए डेटा लेबल को कस्टमाइज़ करें। हम श्रेणी का नाम छिपाएंगे और श्रृंखला का नाम दिखाएंगे।

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## चरण 3: टेक्स्ट फ़ॉर्मेट सेट करें और रंग भरें

हम टेक्स्ट प्रारूप सेट करके और रंग भरकर डेटा लेबल की उपस्थिति को और बढ़ा सकते हैं। इस चरण में, हम डेटा बिंदु 0 के लिए टेक्स्ट का रंग पीला पर सेट करेंगे।

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## चरण 4: डेटा प्वाइंट भरण रंग को अनुकूलित करना

अब, डेटा बिंदु 9 का भरण रंग बदलें। हम इसे एक विशिष्ट रंग पर सेट करेंगे।

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## चरण 5: प्रस्तुति को सहेजना

चार्ट को कस्टमाइज़ करने के बाद, आप बदलावों के साथ प्रेजेंटेशन को सेव कर सकते हैं।

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

बधाई हो! आपने .NET के लिए Aspose.Slides का उपयोग करके चार्ट में डेटा बिंदुओं में सफलतापूर्वक रंग जोड़ दिया है। यह आपकी प्रस्तुतियों की दृश्य अपील और स्पष्टता को काफी बढ़ा सकता है।

## निष्कर्ष

चार्ट में डेटा बिंदुओं में रंग जोड़ना आपकी प्रस्तुतियों को अधिक आकर्षक और जानकारीपूर्ण बनाने का एक शक्तिशाली तरीका है। .NET के लिए Aspose.Slides के साथ, आपके पास दिखने में आकर्षक चार्ट बनाने के उपकरण हैं जो आपके डेटा को प्रभावी ढंग से व्यक्त करते हैं।

## अक्सर पूछे जाने वाले प्रश्न (एफएक्यू)

### .NET के लिए Aspose.Slides क्या है?
   .NET के लिए Aspose.Slides एक लाइब्रेरी है जो .NET डेवलपर्स को PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है।

### क्या मैं Aspose.Slides का उपयोग करके अन्य चार्ट गुणों को अनुकूलित कर सकता हूँ?
   हाँ, आप .NET के लिए Aspose.Slides का उपयोग करके चार्ट के विभिन्न पहलुओं, जैसे डेटा लेबल, फ़ॉन्ट, रंग और बहुत कुछ को अनुकूलित कर सकते हैं।

### मुझे .NET के लिए Aspose.Slides के लिए दस्तावेज़ कहां मिल सकते हैं?
    आप विस्तृत दस्तावेज़ यहाँ पा सकते हैं[दस्तावेज़ीकरण लिंक](https://reference.aspose.com/slides/net/).

### क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
    हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).

### मैं .NET के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त करूं?
    समर्थन और चर्चा के लिए, पर जाएँ[Aspose.स्लाइड्स फोरम](https://forum.aspose.com/).