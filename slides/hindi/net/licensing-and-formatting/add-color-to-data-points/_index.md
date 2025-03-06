---
title: .NET के लिए Aspose.Slides के साथ चार्ट रंगीकरण
linktitle: चार्ट में डेटा बिंदुओं में रंग जोड़ें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET के साथ चार्ट में डेटा पॉइंट्स में रंग जोड़ने का तरीका जानें। अपनी प्रस्तुतियों को विज़ुअल रूप से बेहतर बनाएँ और अपने दर्शकों को प्रभावी ढंग से आकर्षित करें।
weight: 12
url: /hi/net/licensing-and-formatting/add-color-to-data-points/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


इस चरण-दर-चरण मार्गदर्शिका में, हम आपको .NET के लिए Aspose.Slides का उपयोग करके चार्ट में डेटा बिंदुओं में रंग जोड़ने की प्रक्रिया से परिचित कराएँगे। Aspose.Slides .NET अनुप्रयोगों में PowerPoint प्रस्तुतियों के साथ काम करने के लिए एक शक्तिशाली लाइब्रेरी है। चार्ट में डेटा बिंदुओं में रंग जोड़ने से आपकी प्रस्तुतियाँ अधिक आकर्षक और समझने में आसान हो सकती हैं।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. विज़ुअल स्टूडियो: आपके कंप्यूटर पर विज़ुअल स्टूडियो स्थापित होना चाहिए।

2.  Aspose.Slides for .NET: Aspose.Slides for .NET को डाउनलोड करें और इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/slides/net/).

3. C# की बुनियादी समझ: आपको C# प्रोग्रामिंग का बुनियादी ज्ञान होना चाहिए।

4. आपकी दस्तावेज़ निर्देशिका: कोड में "आपकी दस्तावेज़ निर्देशिका" को अपनी दस्तावेज़ निर्देशिका के वास्तविक पथ से प्रतिस्थापित करें।

## नामस्थान आयात करना

इससे पहले कि आप .NET के लिए Aspose.Slides के साथ काम कर सकें, आपको आवश्यक नामस्थानों को आयात करना होगा। 

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
    
    // शेष कोड अगले चरणों में जोड़ा जाएगा।
}
```

## चरण 1: डेटा बिंदुओं तक पहुँचना

चार्ट में विशिष्ट डेटा बिंदुओं में रंग जोड़ने के लिए, आपको उन डेटा बिंदुओं तक पहुँच की आवश्यकता होती है। इस उदाहरण में, हम डेटा बिंदु 3 को लक्षित करेंगे।

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## चरण 2: डेटा लेबल को अनुकूलित करना

अब, डेटा बिंदु 0 के लिए डेटा लेबल को अनुकूलित करें। हम श्रेणी का नाम छिपाएंगे और श्रृंखला का नाम दिखाएंगे।

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## चरण 3: टेक्स्ट प्रारूप और भरण रंग सेट करना

हम टेक्स्ट फ़ॉर्मेट और फ़िल कलर सेट करके डेटा लेबल की दिखावट को और बेहतर बना सकते हैं। इस चरण में, हम डेटा पॉइंट 0 के लिए टेक्स्ट का रंग पीला सेट करेंगे।

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## चरण 4: डेटा बिंदु भरण रंग को अनुकूलित करना

अब, आइए डेटा बिंदु 9 का भरण रंग बदलें। हम इसे एक विशिष्ट रंग पर सेट करेंगे।

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## चरण 5: प्रस्तुति को सहेजना

चार्ट को अनुकूलित करने के बाद, आप परिवर्तनों के साथ प्रस्तुति को सहेज सकते हैं।

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

बधाई हो! आपने Aspose.Slides for .NET का उपयोग करके चार्ट में डेटा बिंदुओं में सफलतापूर्वक रंग जोड़ दिया है। यह आपकी प्रस्तुतियों की दृश्य अपील और स्पष्टता को बहुत बढ़ा सकता है।

## निष्कर्ष

चार्ट में डेटा बिंदुओं में रंग जोड़ना आपकी प्रस्तुतियों को अधिक आकर्षक और जानकारीपूर्ण बनाने का एक शक्तिशाली तरीका है। .NET के लिए Aspose.Slides के साथ, आपके पास ऐसे आकर्षक चार्ट बनाने के लिए उपकरण हैं जो आपके डेटा को प्रभावी ढंग से व्यक्त करते हैं।

## अक्सर पूछे जाने वाले प्रश्न (एफएक्यू)

### .NET के लिए Aspose.Slides क्या है?
   Aspose.Slides for .NET एक लाइब्रेरी है जो .NET डेवलपर्स को पावरपॉइंट प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है।

### क्या मैं Aspose.Slides का उपयोग करके अन्य चार्ट गुणों को अनुकूलित कर सकता हूँ?
   हां, आप .NET के लिए Aspose.Slides का उपयोग करके चार्ट के विभिन्न पहलुओं, जैसे डेटा लेबल, फ़ॉन्ट, रंग आदि को अनुकूलित कर सकते हैं।

### मैं Aspose.Slides for .NET के लिए दस्तावेज़ कहां पा सकता हूं?
    आप विस्तृत दस्तावेज यहां पा सकते हैं[दस्तावेज़ लिंक](https://reference.aspose.com/slides/net/).

### क्या .NET के लिए Aspose.Slides का निःशुल्क परीक्षण उपलब्ध है?
    हां, आप यहां से निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).

### मैं .NET के लिए Aspose.Slides का समर्थन कैसे प्राप्त करूं?
    समर्थन और चर्चा के लिए, यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
