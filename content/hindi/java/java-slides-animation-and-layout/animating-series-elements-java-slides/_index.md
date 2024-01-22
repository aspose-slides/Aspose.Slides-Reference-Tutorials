---
title: जावा स्लाइड्स में श्रृंखला तत्वों को एनिमेट करना
linktitle: जावा स्लाइड्स में श्रृंखला तत्वों को एनिमेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड में श्रृंखला तत्वों को एनिमेट करना सीखें। अपनी प्रस्तुतियों को बेहतर बनाने के लिए स्रोत कोड के साथ इस व्यापक चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 12
url: /hi/java/animation-and-layout/animating-series-elements-java-slides/
---

## जावा स्लाइड्स में एनिमेटिंग श्रृंखला तत्वों का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड में श्रृंखला तत्वों को एनिमेट करने के बारे में आपका मार्गदर्शन करेंगे। एनिमेशन आपकी प्रस्तुतियों को अधिक आकर्षक और जानकारीपूर्ण बना सकते हैं। इस उदाहरण में, हम PowerPoint स्लाइड में एक चार्ट को एनिमेट करने पर ध्यान केंद्रित करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा लाइब्रेरी के लिए Aspose.Slides स्थापित।
- एक चार्ट के साथ एक मौजूदा पावरपॉइंट प्रेजेंटेशन जिसे आप एनिमेट करना चाहते हैं।
- जावा विकास पर्यावरण की स्थापना।

## चरण 1: प्रस्तुति लोड करें

सबसे पहले, आपको पावरपॉइंट प्रेजेंटेशन को लोड करना होगा जिसमें वह चार्ट है जिसे आप एनिमेट करना चाहते हैं। प्रतिस्थापित करें`"Your Document Directory"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## चरण 2: चार्ट का संदर्भ प्राप्त करें

एक बार प्रेजेंटेशन लोड हो जाने पर, उस चार्ट का संदर्भ प्राप्त करें जिसे आप एनिमेट करना चाहते हैं। इस उदाहरण में, हम मानते हैं कि चार्ट पहली स्लाइड पर है।

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## चरण 3: एनिमेशन प्रभाव जोड़ें

 अब, चार्ट तत्वों में एनीमेशन प्रभाव जोड़ें। हम उपयोग करेंगे`slide.getTimeline().getMainSequence().addEffect()` यह निर्दिष्ट करने की विधि कि चार्ट को कैसे एनिमेट करना चाहिए।

```java
// संपूर्ण चार्ट को चेतन करें
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// व्यक्तिगत श्रृंखला तत्वों को चेतन करें (आप इस भाग को अनुकूलित कर सकते हैं)
for (int seriesIndex = 0; seriesIndex < chart.getChartData().getSeries().size(); seriesIndex++) {
    for (int pointIndex = 0; pointIndex < chart.getChartData().getSeries().get_Item(seriesIndex).getPoints().size(); pointIndex++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, pointIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

उपरोक्त कोड में, हम पहले पूरे चार्ट को "फ़ेड" प्रभाव से एनिमेट करते हैं। फिर, हम चार्ट के भीतर श्रृंखला और बिंदुओं के माध्यम से लूप करते हैं और प्रत्येक तत्व पर "प्रकट" प्रभाव लागू करते हैं। आप आवश्यकतानुसार एनीमेशन प्रकार और ट्रिगर को अनुकूलित कर सकते हैं।

## चरण 4: प्रस्तुति सहेजें

अंत में, संशोधित प्रस्तुति को एनिमेशन के साथ एक नई फ़ाइल में सहेजें।

```java
presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में श्रृंखला तत्वों को एनिमेट करने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रस्तुति लोड करें
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// श्रृंखला के तत्वों को चेतन करें
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// प्रेजेंटेशन फ़ाइल को डिस्क पर लिखें
	presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

आपने जावा के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड में श्रृंखला तत्वों को एनिमेट करना सीख लिया है। एनिमेशन आपकी प्रस्तुतियों को बेहतर बना सकते हैं और उन्हें अधिक आकर्षक बना सकते हैं। अपनी विशिष्ट आवश्यकताओं के अनुरूप एनीमेशन प्रभाव और ट्रिगर को अनुकूलित करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं अलग-अलग चार्ट तत्वों के लिए एनीमेशन को कैसे अनुकूलित कर सकता हूं?

आप एनीमेशन प्रकार और कोड में ट्रिगर को संशोधित करके व्यक्तिगत चार्ट तत्वों के लिए एनीमेशन को अनुकूलित कर सकते हैं। हमारे उदाहरण में, हमने "प्रकट" प्रभाव का उपयोग किया, लेकिन आप विभिन्न एनीमेशन प्रकारों जैसे "फेड," "फ्लाई इन," आदि में से चुन सकते हैं, और विभिन्न ट्रिगर निर्दिष्ट कर सकते हैं जैसे "ऑन क्लिक," "आफ्टर प्रीवियस," या "पिछले के साथ।"

### क्या मैं PowerPoint स्लाइड में अन्य ऑब्जेक्ट पर एनिमेशन लागू कर सकता हूँ?

हां, आप केवल चार्ट ही नहीं, बल्कि PowerPoint स्लाइड में विभिन्न ऑब्जेक्ट पर एनिमेशन लागू कर सकते हैं। उपयोग`addEffect` उस ऑब्जेक्ट को निर्दिष्ट करने की विधि जिसे आप चेतन करना चाहते हैं और वांछित एनीमेशन गुण।

### मैं जावा के लिए Aspose.Slides को अपने प्रोजेक्ट में कैसे एकीकृत करूं?

अपने प्रोजेक्ट में Java के लिए Aspose.Slides को एकीकृत करने के लिए, आपको अपने बिल्ड पथ में लाइब्रेरी को शामिल करना होगा या मावेन या ग्रैडल जैसे निर्भरता प्रबंधन टूल का उपयोग करना होगा। विस्तृत एकीकरण निर्देशों के लिए Aspose.Slides दस्तावेज़ देखें।

### क्या PowerPoint एप्लिकेशन में एनिमेशन का पूर्वावलोकन करने का कोई तरीका है?

हां, प्रस्तुति को सहेजने के बाद, आप एनिमेशन का पूर्वावलोकन करने और यदि आवश्यक हो तो आगे समायोजन करने के लिए इसे पावरपॉइंट एप्लिकेशन में खोल सकते हैं। PowerPoint इस उद्देश्य के लिए एक पूर्वावलोकन मोड प्रदान करता है।

### क्या जावा के लिए Aspose.Slides में अधिक उन्नत एनिमेशन विकल्प उपलब्ध हैं?

हां, जावा के लिए Aspose.Slides गति पथ, समय और इंटरैक्टिव एनिमेशन सहित उन्नत एनीमेशन विकल्पों की एक विस्तृत श्रृंखला प्रदान करता है। आप अपनी प्रस्तुतियों में उन्नत एनिमेशन लागू करने के लिए Aspose.Slides द्वारा प्रदान किए गए दस्तावेज़ और उदाहरण देख सकते हैं।