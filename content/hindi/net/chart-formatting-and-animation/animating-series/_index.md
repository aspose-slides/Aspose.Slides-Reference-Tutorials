---
title: .NET के लिए Aspose.Slides के साथ चार्ट श्रृंखला चेतन करें
linktitle: चार्ट में एनिमेटिंग श्रृंखला
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides के साथ चार्ट श्रृंखला को एनिमेट करना सीखें। गतिशील प्रस्तुतियों से अपने दर्शकों को बांधे रखें। अब शुरू हो जाओ!
type: docs
weight: 12
url: /hi/net/chart-formatting-and-animation/animating-series/
---

क्या आप एनिमेटेड चार्ट के साथ अपनी प्रस्तुतियों में कुछ नयापन जोड़ना चाह रहे हैं? .NET के लिए Aspose.Slides आपके चार्ट को जीवंत बनाने के लिए यहां है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको दिखाएंगे कि .NET के लिए Aspose.Slides का उपयोग करके चार्ट में श्रृंखला को कैसे एनिमेट किया जाए। लेकिन इससे पहले कि हम कार्रवाई में उतरें, आइए पूर्वापेक्षाएँ देखें।

## आवश्यक शर्तें

.NET के लिए Aspose.Slides का उपयोग करके चार्ट में श्रृंखला को सफलतापूर्वक एनिमेट करने के लिए, आपको निम्नलिखित की आवश्यकता होगी:

### 1. .NET लाइब्रेरी के लिए Aspose.Slides

 सुनिश्चित करें कि आपके पास .NET लाइब्रेरी के लिए Aspose.Slides स्थापित है। यदि आपने पहले से नहीं किया है, तो आप इसे यहां से डाउनलोड कर सकते हैं[.NET वेबसाइट के लिए Aspose.Slides](https://releases.aspose.com/slides/net/).

### 2. चार्ट के साथ मौजूदा प्रस्तुति

मौजूदा चार्ट के साथ एक पावरपॉइंट प्रेजेंटेशन (पीपीटीएक्स) तैयार करें जिसे आप एनिमेट करना चाहते हैं।

अब जब हमने आवश्यक शर्तें पूरी कर ली हैं, तो आइए चार्ट श्रृंखला को चेतन करने के लिए प्रक्रिया को चरणों की एक श्रृंखला में विभाजित करें।


## चरण 1: आवश्यक नामस्थान आयात करें

.NET के लिए Aspose.Slides के साथ काम करने के लिए आपको अपने C# कोड में आवश्यक नेमस्पेस आयात करने की आवश्यकता होगी:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## चरण 2: मौजूदा प्रस्तुति लोड करें

इस चरण में, अपने मौजूदा पावरपॉइंट प्रेजेंटेशन (पीपीटीएक्स) को लोड करें जिसमें वह चार्ट है जिसे आप एनिमेट करना चाहते हैं।

```csharp
// दस्तावेज़ निर्देशिका का पथ
string dataDir = "Your Document Directory";

//इंस्टेंटिएट प्रेजेंटेशन क्लास जो प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करती है
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // आपका कोड यहां जाता है
}
```

## चरण 3: चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें

अपनी प्रस्तुति में चार्ट के साथ काम करने के लिए, आपको चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करना होगा:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## चरण 4: श्रृंखला को चेतन करें

अब, आपकी चार्ट श्रृंखला में एनीमेशन प्रभाव जोड़ने का समय आ गया है। हम पूरे चार्ट में फ़ेड-इन प्रभाव जोड़ देंगे और प्रत्येक श्रृंखला को एक-एक करके प्रदर्शित करेंगे।

```csharp
// चार्ट को चेतन करें
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// प्रत्येक श्रृंखला में एनिमेशन जोड़ें
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## चरण 5: संशोधित प्रस्तुति सहेजें

एक बार जब आप अपने चार्ट में एनीमेशन प्रभाव जोड़ लें, तो संशोधित प्रस्तुति को डिस्क पर सहेजें।

```csharp
// संशोधित प्रस्तुति सहेजें
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

इतना ही! आपने .NET के लिए Aspose.Slides का उपयोग करके एक चार्ट में श्रृंखला को सफलतापूर्वक एनिमेटेड किया है।

## निष्कर्ष

इस ट्यूटोरियल में, हमने आपको .NET के लिए Aspose.Slides का उपयोग करके एक चार्ट में श्रृंखला को एनिमेट करने की प्रक्रिया के बारे में बताया है। इस शक्तिशाली लाइब्रेरी के साथ, आप आकर्षक और गतिशील प्रस्तुतियाँ बना सकते हैं जो आपके दर्शकों को मंत्रमुग्ध कर देती हैं।

 यदि आपके कोई प्रश्न हैं या आपको अतिरिक्त सहायता की आवश्यकता है, तो Aspose.Slides समुदाय से संपर्क करने में संकोच न करें।[सहयता मंच](https://forum.aspose.com/).

## पूछे जाने वाले प्रश्न

### क्या मैं .NET के लिए Aspose.Slides का उपयोग करके श्रृंखला के अलावा अन्य चार्ट तत्वों को एनिमेट कर सकता हूँ?
हाँ, आप .NET के लिए Aspose.Slides का उपयोग करके डेटा बिंदुओं, अक्षों और लेजेंड्स सहित विभिन्न चार्ट तत्वों को एनिमेट कर सकते हैं।

### क्या .NET के लिए Aspose.Slides PowerPoint के नवीनतम संस्करणों के साथ संगत है?
.NET के लिए Aspose.Slides, PowerPoint 2007 और उसके बाद के संस्करण सहित विभिन्न PowerPoint संस्करणों का समर्थन करता है, जो कि अधिकांश नवीनतम संस्करणों के साथ संगतता सुनिश्चित करता है।

### क्या मैं प्रत्येक चार्ट श्रृंखला के लिए एनीमेशन प्रभावों को व्यक्तिगत रूप से अनुकूलित कर सकता हूँ?
हाँ, आप अद्वितीय और आकर्षक प्रस्तुतियाँ बनाने के लिए प्रत्येक चार्ट श्रृंखला के लिए एनीमेशन प्रभावों को तैयार कर सकते हैं।

### क्या .NET के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हाँ, आप निःशुल्क परीक्षण के साथ लाइब्रेरी को आज़मा सकते हैं[.NET वेबसाइट के लिए Aspose.Slides](https://releases.aspose.com/).

### मैं .NET के लिए Aspose.Slides का लाइसेंस कहां से खरीद सकता हूं?
 आप खरीद पृष्ठ से .NET के लिए Aspose.Slides का लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/buy).