---
title: .NET के लिए Aspose.Slides के साथ चार्ट श्रृंखला को एनिमेट करें
linktitle: चार्ट में श्रृंखला को एनिमेट करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: Aspose.Slides for .NET के साथ चार्ट श्रृंखला को एनिमेट करना सीखें। गतिशील प्रस्तुतियों के साथ अपने दर्शकों को आकर्षित करें। अभी शुरू करें!
weight: 12
url: /hi/net/chart-formatting-and-animation/animating-series/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


क्या आप एनिमेटेड चार्ट के साथ अपनी प्रस्तुतियों में कुछ चमक जोड़ना चाहते हैं? Aspose.Slides for .NET आपके चार्ट को जीवंत बनाने के लिए यहाँ है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको दिखाएंगे कि Aspose.Slides for .NET का उपयोग करके चार्ट में श्रृंखला को कैसे एनिमेट किया जाए। लेकिन इससे पहले कि हम कार्रवाई में उतरें, आइए पूर्वापेक्षाओं को कवर करें।

## आवश्यक शर्तें

Aspose.Slides for .NET का उपयोग करके चार्ट में श्रृंखला को सफलतापूर्वक एनिमेट करने के लिए, आपको निम्नलिखित की आवश्यकता होगी:

### 1. .NET लाइब्रेरी के लिए Aspose.Slides

 सुनिश्चित करें कि आपके पास Aspose.Slides for .NET लाइब्रेरी स्थापित है। यदि आपने पहले से ऐसा नहीं किया है, तो आप इसे यहाँ से डाउनलोड कर सकते हैं।[.NET वेबसाइट के लिए Aspose.Slides](https://releases.aspose.com/slides/net/).

### 2. चार्ट के साथ मौजूदा प्रस्तुति

किसी मौजूदा चार्ट के साथ एक पावरपॉइंट प्रेजेंटेशन (PPTX) तैयार करें जिसे आप एनिमेट करना चाहते हैं।

अब जबकि हमने सभी पूर्वापेक्षाओं को पूरा कर लिया है, तो आइए चार्ट श्रृंखला को एनिमेट करने के लिए प्रक्रिया को चरणों की एक श्रृंखला में विभाजित करें।


## चरण 1: आवश्यक नामस्थान आयात करें

.NET के लिए Aspose.Slides के साथ काम करने के लिए आपको अपने C# कोड में आवश्यक नेमस्पेस आयात करने की आवश्यकता होगी:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## चरण 2: मौजूदा प्रस्तुति लोड करें

इस चरण में, अपनी मौजूदा पावरपॉइंट प्रस्तुति (PPTX) लोड करें जिसमें वह चार्ट हो जिसे आप एनिमेट करना चाहते हैं।

```csharp
// दस्तावेज़ निर्देशिका का पथ
string dataDir = "Your Document Directory";

// प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // आपका कोड यहां जाएगा
}
```

## चरण 3: चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें

अपनी प्रस्तुति में चार्ट के साथ काम करने के लिए, आपको चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करना होगा:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## चरण 4: श्रृंखला को एनिमेट करें

अब, आपके चार्ट सीरीज में एनिमेशन इफ़ेक्ट जोड़ने का समय आ गया है। हम पूरे चार्ट में फ़ेड-इन इफ़ेक्ट जोड़ेंगे और हर सीरीज को एक-एक करके दिखाएंगे।

```csharp
// चार्ट को एनिमेट करें
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// प्रत्येक श्रृंखला में एनीमेशन जोड़ें
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## चरण 5: संशोधित प्रस्तुति को सहेजें

एक बार जब आप अपने चार्ट में एनीमेशन प्रभाव जोड़ लें, तो संशोधित प्रस्तुति को डिस्क पर सहेजें।

```csharp
//संशोधित प्रस्तुति सहेजें
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

बस! आपने .NET के लिए Aspose.Slides का उपयोग करके चार्ट में सफलतापूर्वक श्रृंखला को एनिमेट कर दिया है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने आपको .NET के लिए Aspose.Slides का उपयोग करके चार्ट में श्रृंखला को एनिमेट करने की प्रक्रिया के बारे में बताया है। इस शक्तिशाली लाइब्रेरी के साथ, आप आकर्षक और गतिशील प्रस्तुतियाँ बना सकते हैं जो आपके दर्शकों को आकर्षित करती हैं।

 यदि आपके कोई प्रश्न हैं या आपको और सहायता की आवश्यकता है, तो Aspose.Slides समुदाय से संपर्क करने में संकोच न करें।[सहयता मंच](https://forum.aspose.com/).

## पूछे जाने वाले प्रश्न

### क्या मैं .NET के लिए Aspose.Slides का उपयोग करके श्रृंखला के अलावा अन्य चार्ट तत्वों को एनिमेट कर सकता हूँ?
हां, आप .NET के लिए Aspose.Slides का उपयोग करके डेटा बिंदुओं, अक्षों और किंवदंतियों सहित विभिन्न चार्ट तत्वों को एनिमेट कर सकते हैं।

### क्या Aspose.Slides for .NET PowerPoint के नवीनतम संस्करणों के साथ संगत है?
Aspose.Slides for .NET विभिन्न PowerPoint संस्करणों का समर्थन करता है, जिसमें PowerPoint 2007 और बाद के संस्करण शामिल हैं, जो नवीनतम संस्करणों के साथ संगतता सुनिश्चित करता है।

### क्या मैं प्रत्येक चार्ट श्रृंखला के लिए एनीमेशन प्रभाव को अलग-अलग अनुकूलित कर सकता हूँ?
हां, आप अद्वितीय और आकर्षक प्रस्तुतियाँ बनाने के लिए प्रत्येक चार्ट श्रृंखला के लिए एनीमेशन प्रभाव को अनुकूलित कर सकते हैं।

### क्या .NET के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप लाइब्रेरी का निःशुल्क परीक्षण कर सकते हैं[.NET वेबसाइट के लिए Aspose.Slides](https://releases.aspose.com/).

### मैं Aspose.Slides for .NET का लाइसेंस कहां से खरीद सकता हूं?
 आप खरीद पृष्ठ से .NET के लिए Aspose.Slides का लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
