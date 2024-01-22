---
title: Aspose.Slides में चार्ट फ़ॉर्मेटिंग और एनिमेशन
linktitle: Aspose.Slides में चार्ट फ़ॉर्मेटिंग और एनिमेशन
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि .NET के लिए Aspose.Slides में चार्ट को कैसे प्रारूपित और एनिमेट करें, अपनी प्रस्तुतियों को आकर्षक दृश्यों के साथ बेहतर बनाएं।
type: docs
weight: 10
url: /hi/net/chart-formatting-and-animation/chart-formatting-and-animation/
---

गतिशील चार्ट और एनिमेशन के साथ सम्मोहक प्रस्तुतियाँ बनाने से आपके संदेश का प्रभाव काफी बढ़ सकता है। .NET के लिए Aspose.Slides आपको यह हासिल करने का अधिकार देता है। इस ट्यूटोरियल में, हम .NET के लिए Aspose.Slides का उपयोग करके चार्ट को एनिमेट और फ़ॉर्मेट करने की प्रक्रिया में आपका मार्गदर्शन करेंगे। यह सुनिश्चित करने के लिए कि आप अवधारणा को पूरी तरह से समझ सकें, हम चरणों को प्रबंधनीय अनुभागों में विभाजित करेंगे।

## आवश्यक शर्तें

इससे पहले कि आप Aspose.Slides के साथ चार्ट फ़ॉर्मेटिंग और एनीमेशन में उतरें, आपको निम्नलिखित की आवश्यकता होगी:

1.  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपने .NET के लिए Aspose.Slides इंस्टॉल कर लिया है। यदि आपने पहले से नहीं किया है, तो आप कर सकते हैं[यहाँ पर डाउनलोड करो](https://releases.aspose.com/slides/net/).

2. मौजूदा प्रस्तुति: एक मौजूदा प्रस्तुति है जिसमें एक चार्ट है जिसे आप प्रारूपित और एनिमेट करना चाहते हैं।

3. बुनियादी सी# ज्ञान: सी# से परिचित होना चरणों को लागू करने में सहायक होगा।

अब, चलिए शुरू करते हैं।

## नामस्थान आयात करें

आरंभ करने के लिए, आपको Aspose.Slides सुविधाओं तक पहुंचने के लिए आवश्यक नामस्थान आयात करने की आवश्यकता होगी। अपने C# प्रोजेक्ट में, निम्नलिखित जोड़ें:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## चार्ट में श्रेणियों के तत्वों को एनिमेट करना

### चरण 1: प्रेजेंटेशन लोड करें और चार्ट तक पहुंचें

सबसे पहले, अपनी मौजूदा प्रस्तुति लोड करें और उस चार्ट तक पहुंचें जिसे आप एनिमेट करना चाहते हैं। यह उदाहरण मानता है कि चार्ट आपकी प्रस्तुति की पहली स्लाइड पर स्थित है।

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### चरण 2: श्रेणियों के तत्वों में एनिमेशन जोड़ें

अब, श्रेणियों के तत्वों में एनीमेशन जोड़ें। इस उदाहरण में, हम फ़ेड-इन प्रभाव का उपयोग कर रहे हैं।

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### चरण 3: प्रस्तुति सहेजें

अंत में, संशोधित प्रस्तुति को डिस्क पर सहेजें।

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## चार्ट में एनिमेटिंग श्रृंखला

### चरण 1: प्रेजेंटेशन लोड करें और चार्ट तक पहुंचें

पिछले उदाहरण के समान, आप प्रेजेंटेशन लोड करेंगे और चार्ट तक पहुंचेंगे।

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### चरण 2: श्रृंखला में एनिमेशन जोड़ें

अब, चार्ट श्रृंखला में एनीमेशन जोड़ें। हम यहां फ़ेड-इन प्रभाव का भी उपयोग कर रहे हैं।

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### चरण 3: प्रस्तुति सहेजें

संशोधित प्रस्तुति को एनिमेटेड श्रृंखला के साथ सहेजें।

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## चार्ट में श्रृंखला तत्वों को एनिमेट करना

### चरण 1: प्रेजेंटेशन लोड करें और चार्ट तक पहुंचें

पहले की तरह, प्रेजेंटेशन लोड करें और चार्ट तक पहुंचें।

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### चरण 2: श्रृंखला तत्वों में एनिमेशन जोड़ें

इस चरण में, आप श्रृंखला के तत्वों में एनीमेशन जोड़ेंगे, जिससे एक प्रभावशाली दृश्य प्रभाव पैदा होगा।

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int seriesIndex = 0; seriesIndex < chart.ChartData.Series.Count; seriesIndex++)
{
    for (int elementIndex = 0; elementIndex < chart.ChartData.Categories.Count; elementIndex++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, elementIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

### चरण 3: प्रस्तुति सहेजें

प्रस्तुतिकरण को एनिमेटेड श्रृंखला तत्वों के साथ सहेजना न भूलें।

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

बधाई हो! अब आप सीख गए हैं कि .NET के लिए Aspose.Slides में चार्ट को कैसे प्रारूपित और एनिमेट किया जाए। ये तकनीकें आपकी प्रस्तुतियों को अधिक आकर्षक और जानकारीपूर्ण बना सकती हैं।

## निष्कर्ष

.NET के लिए Aspose.Slides चार्ट फ़ॉर्मेटिंग और एनीमेशन के लिए शक्तिशाली उपकरण प्रदान करता है, जिससे आप दृश्य रूप से आकर्षक प्रस्तुतियाँ बना सकते हैं जो आपके दर्शकों को मंत्रमुग्ध कर देती हैं। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप चार्ट एनीमेशन की कला में महारत हासिल कर सकते हैं और अपनी प्रस्तुतियों को बेहतर बना सकते हैं।

## पूछे जाने वाले प्रश्न

### 1. मुझे .NET के लिए Aspose.Slides का दस्तावेज़ कहां मिल सकता है?

 आप दस्तावेज़ तक पहुंच सकते हैं[https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. मैं .NET के लिए Aspose.Slides कैसे डाउनलोड करूं?

 आप .NET के लिए Aspose.Slides डाउनलोड कर सकते हैं[https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. क्या कोई निःशुल्क परीक्षण उपलब्ध है?

 हां, आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण यहां प्राप्त कर सकते हैं[https://releases.aspose.com/](https://releases.aspose.com/).

### 4. क्या मैं .NET के लिए Aspose.Slides के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?

 हां, आप यहां अस्थायी लाइसेंस खरीद सकते हैं[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. मुझे .NET के लिए Aspose.Slides के बारे में समर्थन कहां मिल सकता है या प्रश्न पूछ सकते हैं?

 समर्थन और प्रश्नों के लिए, Aspose.Slides फोरम पर जाएँ[https://forum.aspose.com/](https://forum.aspose.com/).

