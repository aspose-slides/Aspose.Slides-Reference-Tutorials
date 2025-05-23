---
"description": "Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में श्रृंखला तत्वों को एनिमेट करना सीखें। अपने प्रस्तुतियों को बेहतर बनाने के लिए स्रोत कोड के साथ इस व्यापक चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"linktitle": "जावा स्लाइड्स में श्रृंखला तत्वों को एनिमेट करना"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में श्रृंखला तत्वों को एनिमेट करना"
"url": "/hi/java/animation-and-layout/animating-series-elements-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में श्रृंखला तत्वों को एनिमेट करना


## जावा स्लाइड्स में श्रृंखला तत्वों को एनिमेट करने का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में श्रृंखला तत्वों को एनिमेट करने के बारे में मार्गदर्शन करेंगे। एनिमेशन आपकी प्रस्तुतियों को अधिक आकर्षक और जानकारीपूर्ण बना सकते हैं। इस उदाहरण में, हम PowerPoint स्लाइड में चार्ट को एनिमेट करने पर ध्यान केंद्रित करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Aspose.Slides for Java लाइब्रेरी स्थापित की गई।
- एक मौजूदा पावरपॉइंट प्रस्तुति जिसमें एक चार्ट है जिसे आप एनिमेट करना चाहते हैं।
- जावा विकास वातावरण की स्थापना.

## चरण 1: प्रस्तुति लोड करें

सबसे पहले, आपको पावरपॉइंट प्रेजेंटेशन को लोड करना होगा जिसमें वह चार्ट हो जिसे आप एनिमेट करना चाहते हैं। `"Your Document Directory"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## चरण 2: चार्ट का संदर्भ प्राप्त करें

एक बार प्रस्तुति लोड हो जाने के बाद, उस चार्ट का संदर्भ प्राप्त करें जिसे आप एनिमेट करना चाहते हैं। इस उदाहरण में, हम मानते हैं कि चार्ट पहली स्लाइड पर है।

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## चरण 3: एनीमेशन प्रभाव जोड़ें

अब, चार्ट तत्वों में एनीमेशन प्रभाव जोड़ते हैं। हम इसका उपयोग करेंगे `slide.getTimeline().getMainSequence().addEffect()` चार्ट को कैसे एनिमेट किया जाना चाहिए यह निर्दिष्ट करने के लिए विधि।

```java
// संपूर्ण चार्ट को एनिमेट करें
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// अलग-अलग श्रृंखला तत्वों को एनिमेट करें (आप इस भाग को अनुकूलित कर सकते हैं)
for (int seriesIndex = 0; seriesIndex < chart.getChartData().getSeries().size(); seriesIndex++) {
    for (int pointIndex = 0; pointIndex < chart.getChartData().getSeries().get_Item(seriesIndex).getPoints().size(); pointIndex++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, pointIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

उपरोक्त कोड में, हम पहले पूरे चार्ट को "फीका" प्रभाव के साथ एनिमेट करते हैं। फिर, हम चार्ट के भीतर श्रृंखला और बिंदुओं के माध्यम से लूप करते हैं और प्रत्येक तत्व पर "दिखने" प्रभाव लागू करते हैं। आप एनीमेशन प्रकार और ट्रिगर को आवश्यकतानुसार अनुकूलित कर सकते हैं।

## चरण 4: प्रस्तुति सहेजें

अंत में, संशोधित प्रस्तुति को एनिमेशन के साथ एक नई फ़ाइल में सहेजें।

```java
presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में श्रृंखला तत्वों को एनिमेट करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रस्तुति लोड करें
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// श्रृंखला तत्वों को एनिमेट करें
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
	// प्रस्तुति फ़ाइल को डिस्क पर लिखें 
	presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

आपने सीखा है कि Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में श्रृंखला तत्वों को कैसे एनिमेट किया जाए। एनिमेशन आपकी प्रस्तुतियों को बेहतर बना सकते हैं और उन्हें अधिक आकर्षक बना सकते हैं। अपनी विशिष्ट आवश्यकताओं के अनुरूप एनिमेशन प्रभाव और ट्रिगर्स को अनुकूलित करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं अलग-अलग चार्ट तत्वों के लिए एनीमेशन को कैसे अनुकूलित कर सकता हूं?

आप कोड में एनीमेशन प्रकार और ट्रिगर को संशोधित करके अलग-अलग चार्ट तत्वों के लिए एनीमेशन को कस्टमाइज़ कर सकते हैं। हमारे उदाहरण में, हमने "अपीयर" प्रभाव का उपयोग किया है, लेकिन आप "फीका," "फ्लाई इन," आदि जैसे विभिन्न एनीमेशन प्रकारों में से चुन सकते हैं, और "ऑन क्लिक," "पिछला होने के बाद," या "पिछले के साथ" जैसे विभिन्न ट्रिगर निर्दिष्ट कर सकते हैं।

### क्या मैं पावरपॉइंट स्लाइड में अन्य ऑब्जेक्ट्स पर एनिमेशन लागू कर सकता हूं?

हां, आप पावरपॉइंट स्लाइड में सिर्फ चार्ट ही नहीं, बल्कि विभिन्न ऑब्जेक्ट पर एनिमेशन लागू कर सकते हैं। `addEffect` विधि का उपयोग उस ऑब्जेक्ट को निर्दिष्ट करने के लिए करें जिसे आप एनिमेट करना चाहते हैं और वांछित एनीमेशन गुणधर्मों को निर्दिष्ट करें।

### मैं अपने प्रोजेक्ट में Aspose.Slides for Java को कैसे एकीकृत करूं?

Aspose.Slides for Java को अपने प्रोजेक्ट में एकीकृत करने के लिए, आपको अपने बिल्ड पथ में लाइब्रेरी को शामिल करना होगा या Maven या Gradle जैसे निर्भरता प्रबंधन टूल का उपयोग करना होगा। विस्तृत एकीकरण निर्देशों के लिए Aspose.Slides दस्तावेज़ देखें।

### क्या पावरपॉइंट अनुप्रयोग में एनिमेशन का पूर्वावलोकन करने का कोई तरीका है?

हां, प्रेजेंटेशन को सेव करने के बाद, आप एनिमेशन का पूर्वावलोकन करने और ज़रूरत पड़ने पर आगे समायोजन करने के लिए इसे PowerPoint एप्लिकेशन में खोल सकते हैं। PowerPoint इस उद्देश्य के लिए एक पूर्वावलोकन मोड प्रदान करता है।

### क्या Aspose.Slides for Java में अधिक उन्नत एनीमेशन विकल्प उपलब्ध हैं?

हां, Aspose.Slides for Java मोशन पाथ, टाइमिंग और इंटरैक्टिव एनिमेशन सहित उन्नत एनिमेशन विकल्पों की एक विस्तृत श्रृंखला प्रदान करता है। आप अपनी प्रस्तुतियों में उन्नत एनिमेशन लागू करने के लिए Aspose.Slides द्वारा प्रदान किए गए दस्तावेज़ों और उदाहरणों का पता लगा सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}