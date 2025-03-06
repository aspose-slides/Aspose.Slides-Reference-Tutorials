---
title: Aspose.Slides में चार्ट फ़ॉर्मेटिंग और एनिमेशन
linktitle: Aspose.Slides में चार्ट फ़ॉर्मेटिंग और एनिमेशन
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET में चार्ट को प्रारूपित और एनिमेट करना सीखें, तथा आकर्षक दृश्यों के साथ अपनी प्रस्तुतियों को बेहतर बनाएं।
weight: 10
url: /hi/net/chart-formatting-and-animation/chart-formatting-and-animation/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


गतिशील चार्ट और एनिमेशन के साथ आकर्षक प्रस्तुतियाँ बनाना आपके संदेश के प्रभाव को बहुत बढ़ा सकता है। Aspose.Slides for .NET आपको बस यही हासिल करने में सक्षम बनाता है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for .NET का उपयोग करके चार्ट को एनिमेट करने और फ़ॉर्मेट करने की प्रक्रिया के बारे में बताएंगे। हम चरणों को प्रबंधनीय अनुभागों में विभाजित करेंगे ताकि आप अवधारणा को अच्छी तरह से समझ सकें।

## आवश्यक शर्तें

इससे पहले कि आप Aspose.Slides के साथ चार्ट फ़ॉर्मेटिंग और एनीमेशन में गोता लगाएँ, आपको निम्नलिखित की आवश्यकता होगी:

1.  Aspose.Slides for .NET: सुनिश्चित करें कि आपने Aspose.Slides for .NET इंस्टॉल किया है। यदि आपने पहले से ऐसा नहीं किया है, तो आप यह कर सकते हैं[यहाँ पर डाउनलोड करो](https://releases.aspose.com/slides/net/).

2. मौजूदा प्रस्तुति: एक मौजूदा प्रस्तुति जिसमें एक चार्ट है जिसे आप प्रारूपित और एनिमेट करना चाहते हैं।

3. बुनियादी C# ज्ञान: C# से परिचित होना चरणों को लागू करने में सहायक होगा।

अब, चलिए शुरू करते हैं।

## नामस्थान आयात करें

आरंभ करने के लिए, आपको Aspose.Slides सुविधाओं तक पहुँचने के लिए आवश्यक नामस्थानों को आयात करना होगा। अपने C# प्रोजेक्ट में, निम्न जोड़ें:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## चार्ट में श्रेणियों के तत्वों को एनिमेट करना

### चरण 1: प्रस्तुति लोड करें और चार्ट तक पहुँचें

सबसे पहले, अपनी मौजूदा प्रस्तुति को लोड करें और उस चार्ट तक पहुँचें जिसे आप एनिमेट करना चाहते हैं। यह उदाहरण मानता है कि चार्ट आपकी प्रस्तुति की पहली स्लाइड पर स्थित है।

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### चरण 2: श्रेणियों के तत्वों में एनीमेशन जोड़ें

अब, आइए श्रेणियों के तत्वों में एनीमेशन जोड़ें। इस उदाहरण में, हम फ़ेड-इन प्रभाव का उपयोग कर रहे हैं।

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

## चार्ट में श्रृंखला को एनिमेट करना

### चरण 1: प्रस्तुति लोड करें और चार्ट तक पहुँचें

पिछले उदाहरण के समान, आप प्रस्तुति लोड करेंगे और चार्ट तक पहुंचेंगे।

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### चरण 2: श्रृंखला में एनीमेशन जोड़ें

अब, चार्ट श्रृंखला में एनीमेशन जोड़ते हैं। हम यहाँ फ़ेड-इन इफ़ेक्ट का भी उपयोग कर रहे हैं।

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

### चरण 1: प्रस्तुति लोड करें और चार्ट तक पहुँचें

पहले की तरह, प्रस्तुति लोड करें और चार्ट तक पहुंचें।

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### चरण 2: श्रृंखला तत्वों में एनीमेशन जोड़ें

इस चरण में, आप श्रृंखला तत्वों में एनीमेशन जोड़ेंगे, जिससे एक प्रभावशाली दृश्य प्रभाव पैदा होगा।

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

एनिमेटेड श्रृंखला तत्वों के साथ प्रस्तुति को सहेजना न भूलें।

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

बधाई हो! अब आपने Aspose.Slides for .NET में चार्ट को फ़ॉर्मेट और एनिमेट करना सीख लिया है। ये तकनीकें आपकी प्रस्तुतियों को ज़्यादा आकर्षक और जानकारीपूर्ण बना सकती हैं।

## निष्कर्ष

Aspose.Slides for .NET चार्ट फ़ॉर्मेटिंग और एनीमेशन के लिए शक्तिशाली उपकरण प्रदान करता है, जिससे आप अपने दर्शकों को आकर्षित करने वाले आकर्षक प्रस्तुतिकरण बना सकते हैं। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आप चार्ट एनीमेशन की कला में महारत हासिल कर सकते हैं और अपनी प्रस्तुतियों को बेहतर बना सकते हैं।

## पूछे जाने वाले प्रश्न

### 1. मैं Aspose.Slides for .NET के लिए दस्तावेज़ कहां पा सकता हूं?

 आप दस्तावेज़ों तक यहां पहुंच सकते हैं[https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. मैं .NET के लिए Aspose.Slides कैसे डाउनलोड करूं?

 आप .NET के लिए Aspose.Slides को यहां से डाउनलोड कर सकते हैं[https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. क्या कोई निःशुल्क परीक्षण उपलब्ध है?

 हां, आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण प्राप्त कर सकते हैं[https://releases.aspose.com/](https://releases.aspose.com/).

### 4. क्या मैं Aspose.Slides for .NET के लिए अस्थायी लाइसेंस खरीद सकता हूँ?

 हां, आप यहां से अस्थायी लाइसेंस खरीद सकते हैं[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. मैं Aspose.Slides for .NET के बारे में सहायता कहां से प्राप्त कर सकता हूं या प्रश्न कहां पूछ सकता हूं?

 सहायता और प्रश्नों के लिए, Aspose.Slides फ़ोरम पर जाएँ[https://forum.aspose.com/](https://forum.aspose.com/).


{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
