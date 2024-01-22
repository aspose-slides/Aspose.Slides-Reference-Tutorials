---
title: .NET के लिए Aspose.Slides के साथ शक्तिशाली चार्ट एनिमेशन
linktitle: चार्ट में श्रेणियों के तत्वों को एनिमेट करना
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Slides के साथ PowerPoint में चार्ट तत्वों को एनिमेट करना सीखें। शानदार प्रस्तुतियों के लिए चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 11
url: /hi/net/chart-formatting-and-animation/animating-categories-elements/
---

प्रस्तुतियों की दुनिया में, एनिमेशन आपकी सामग्री को जीवंत बना सकते हैं, खासकर चार्ट के साथ काम करते समय। .NET के लिए Aspose.Slides शक्तिशाली सुविधाओं की एक श्रृंखला प्रदान करता है जो आपको अपने चार्ट के लिए आश्चर्यजनक एनिमेशन बनाने की अनुमति देता है। इस चरण-दर-चरण मार्गदर्शिका में, हम आपको .NET के लिए Aspose.Slides का उपयोग करके चार्ट में श्रेणी तत्वों को एनिमेट करने की प्रक्रिया के बारे में बताएंगे।

## आवश्यक शर्तें

इससे पहले कि हम ट्यूटोरियल में उतरें, आपके पास निम्नलिखित पूर्वापेक्षाएँ होनी चाहिए:

-  .NET के लिए Aspose.Slides: सुनिश्चित करें कि आपके विकास परिवेश में .NET के लिए Aspose.Slides स्थापित हैं। यदि आपने पहले से नहीं किया है, तो आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/net/).

- मौजूदा प्रस्तुति: आपके पास एक चार्ट के साथ एक पावरपॉइंट प्रस्तुति होनी चाहिए जिसे आप एनिमेट करना चाहते हैं। यदि आपके पास कोई नहीं है, तो परीक्षण उद्देश्यों के लिए एक चार्ट के साथ एक नमूना प्रस्तुति बनाएं।

अब जब आपके पास सब कुछ है, तो आइए उन चार्ट तत्वों को एनिमेट करना शुरू करें!

## नामस्थान आयात करें

पहला कदम Aspose.Slides की कार्यक्षमता तक पहुंचने के लिए आवश्यक नामस्थान आयात करना है। अपने प्रोजेक्ट में निम्नलिखित नामस्थान जोड़ें:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## चरण 1: प्रस्तुति लोड करें

```csharp
// आपकी दस्तावेज़ निर्देशिका का पथ
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

इस चरण में, हम मौजूदा पावरपॉइंट प्रेजेंटेशन को लोड करते हैं जिसमें वह चार्ट होता है जिसे आप एनिमेट करना चाहते हैं। फिर हम पहली स्लाइड के भीतर चार्ट ऑब्जेक्ट तक पहुंचते हैं।

## चरण 2: श्रेणियों के तत्वों को चेतन करें

```csharp
// चेतन श्रेणियों के तत्व
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

यह चरण पूरे चार्ट में एक "फ़ेड" एनीमेशन प्रभाव जोड़ता है, जिससे यह पिछले एनीमेशन के बाद दिखाई देता है।

इसके बाद, हम चार्ट की प्रत्येक श्रेणी में अलग-अलग तत्वों में एनीमेशन जोड़ेंगे। यहीं असली जादू होता है।

## चरण 3: व्यक्तिगत तत्वों को चेतन करें

हम प्रत्येक श्रेणी के भीतर अलग-अलग तत्वों के एनीमेशन को निम्नलिखित चरणों में विभाजित करेंगे:

### चरण 3.1: श्रेणी 0 में तत्वों को एनिमेट करना

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

यहां, हम चार्ट की श्रेणी 0 के भीतर अलग-अलग तत्वों को एनिमेट कर रहे हैं, जिससे वे एक के बाद एक दिखाई दे रहे हैं। इस एनीमेशन के लिए "प्रकट" प्रभाव का उपयोग किया जाता है।

### चरण 3.2: श्रेणी 1 में तत्वों को एनिमेट करना

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

श्रेणी 1 के लिए प्रक्रिया को दोहराया जाता है, "प्रकट" प्रभाव का उपयोग करके उसके व्यक्तिगत तत्वों को एनिमेट किया जाता है।

### चरण 3.3: श्रेणी 2 में तत्वों को एनिमेट करना

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

श्रेणी 2 के लिए भी यही प्रक्रिया जारी रहती है, इसके तत्वों को व्यक्तिगत रूप से एनिमेट किया जाता है।

## चरण 4: प्रस्तुति सहेजें

```csharp
//प्रेजेंटेशन फ़ाइल को डिस्क पर लिखें
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

अंतिम चरण में, हम प्रेजेंटेशन को नए जोड़े गए एनिमेशन के साथ सहेजते हैं। अब, जब आप प्रेजेंटेशन चलाएंगे तो आपके चार्ट तत्व खूबसूरती से एनिमेट होंगे।

## निष्कर्ष

चार्ट में श्रेणी तत्वों को एनिमेट करने से आपकी प्रस्तुतियों की दृश्य अपील बढ़ सकती है। .NET के लिए Aspose.Slides के साथ, यह प्रक्रिया सीधी और कुशल हो जाती है। आपने सीखा है कि नेमस्पेस कैसे आयात करें, प्रेजेंटेशन कैसे लोड करें और पूरे चार्ट और उसके अलग-अलग तत्वों में एनिमेशन कैसे जोड़ें। .NET के लिए Aspose.Slides के साथ रचनात्मक बनें और अपनी प्रस्तुतियों को अधिक आकर्षक बनाएं।

## पूछे जाने वाले प्रश्न

### 1. मैं .NET के लिए Aspose.Slides कैसे डाउनलोड कर सकता हूं?
 आप .NET के लिए Aspose.Slides डाउनलोड कर सकते हैं[इस लिंक](https://releases.aspose.com/slides/net/).

### 2. क्या मुझे .NET के लिए Aspose.Slides का उपयोग करने के लिए कोडिंग अनुभव की आवश्यकता है?
जबकि कोडिंग अनुभव सहायक है, .NET के लिए Aspose.Slides सभी कौशल स्तरों पर उपयोगकर्ताओं की सहायता के लिए व्यापक दस्तावेज़ और उदाहरण प्रदान करता है।

### 3. क्या मैं PowerPoint के किसी भी संस्करण के साथ .NET के लिए Aspose.Slides का उपयोग कर सकता हूँ?
.NET के लिए Aspose.Slides को संगतता सुनिश्चित करते हुए विभिन्न PowerPoint संस्करणों के साथ काम करने के लिए डिज़ाइन किया गया है।

### 4. मैं .NET के लिए Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप .NET के लिए Aspose.Slides के लिए एक अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).

### 5. क्या .NET समर्थन के लिए Aspose.Slides के लिए कोई सामुदायिक मंच है?
 हाँ, आप .NET के लिए Aspose.Slides के लिए एक सहायक सामुदायिक मंच पा सकते हैं[यहाँ](https://forum.aspose.com/).
