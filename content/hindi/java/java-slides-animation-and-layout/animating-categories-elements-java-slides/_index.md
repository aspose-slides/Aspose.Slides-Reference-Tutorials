---
title: जावा स्लाइड्स में श्रेणियों के तत्वों को एनिमेट करना
linktitle: जावा स्लाइड्स में श्रेणियों के तत्वों को एनिमेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides के साथ अपनी जावा प्रस्तुतियों को अनुकूलित करें। PowerPoint स्लाइड में श्रेणी तत्वों को चरण-दर-चरण एनिमेट करना सीखें।
type: docs
weight: 10
url: /hi/java/animation-and-layout/animating-categories-elements-java-slides/
---

## जावा स्लाइड्स में श्रेणियों के तत्वों को एनिमेट करने का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में श्रेणी तत्वों को एनिमेट करने की प्रक्रिया में आपका मार्गदर्शन करेंगे। यह चरण-दर-चरण मार्गदर्शिका आपको इस एनीमेशन प्रभाव को प्राप्त करने में सहायता के लिए स्रोत कोड और स्पष्टीकरण प्रदान करेगी।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा एपीआई के लिए Aspose.Slides स्थापित।
- एक मौजूदा पावरपॉइंट प्रेजेंटेशन जिसमें एक चार्ट है। आप इस चार्ट के श्रेणी तत्वों को एनिमेट करेंगे।

## चरण 1: Aspose.Slides लाइब्रेरी आयात करें

आरंभ करने के लिए, Aspose.Slides लाइब्रेरी को अपने जावा प्रोजेक्ट में आयात करें। आप लाइब्रेरी को डाउनलोड करके अपने प्रोजेक्ट के क्लासपाथ में जोड़ सकते हैं। सुनिश्चित करें कि आपके पास आवश्यक निर्भरताएँ स्थापित हैं।

## चरण 2: प्रस्तुति लोड करें

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

इस कोड में, हम एक मौजूदा पावरपॉइंट प्रेजेंटेशन लोड करते हैं जिसमें वह चार्ट होता है जिसे आप एनिमेट करना चाहते हैं। प्रतिस्थापित करें`"Your Document Directory"` आपकी दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ।

## चरण 3: चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

हमें प्रेजेंटेशन की पहली स्लाइड में चार्ट ऑब्जेक्ट का संदर्भ मिलता है। स्लाइड इंडेक्स समायोजित करें (`get_Item(0)`) और आकार सूचकांक (`get_Item(0)`) आपके विशिष्ट चार्ट तक पहुँचने के लिए आवश्यकतानुसार।

## चरण 4: श्रेणियों के तत्वों को चेतन करें

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

हम चार्ट के भीतर श्रेणियों के तत्वों को एनिमेट करते हैं। यह कोड पूरे चार्ट में एक फीका प्रभाव जोड़ता है और फिर प्रत्येक श्रेणी के प्रत्येक तत्व में एक "प्रकट" प्रभाव जोड़ता है। प्रभाव प्रकार और उपप्रकार को आवश्यकतानुसार समायोजित करें।

## चरण 5: प्रस्तुति सहेजें

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

 अंत में, एनिमेटेड चार्ट के साथ संशोधित प्रस्तुति को एक नई फ़ाइल में सहेजें। प्रतिस्थापित करें`"AnimatingCategoriesElements_out.pptx"` आपके इच्छित आउटपुट फ़ाइल नाम के साथ।


## जावा स्लाइड्स में श्रेणियों के तत्वों को एनिमेट करने के लिए संपूर्ण स्रोत कोड
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// चेतन श्रेणियों के तत्व
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	//प्रेजेंटेशन फ़ाइल को डिस्क पर लिखें
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

आपने जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में श्रेणी तत्वों को सफलतापूर्वक एनिमेटेड किया है। इस चरण-दर-चरण मार्गदर्शिका ने आपको अपनी PowerPoint प्रस्तुतियों में इस एनीमेशन प्रभाव को प्राप्त करने के लिए आवश्यक स्रोत कोड और स्पष्टीकरण प्रदान किए हैं। अपने एनिमेशन को और अधिक अनुकूलित करने के लिए विभिन्न प्रभावों और सेटिंग्स के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं एनीमेशन प्रभावों को कैसे अनुकूलित कर सकता हूँ?

 आप एनीमेशन प्रभावों को बदलकर अनुकूलित कर सकते हैं`EffectType` और`EffectSubtype` चार्ट तत्वों पर प्रभाव जोड़ते समय पैरामीटर। उपलब्ध एनिमेशन प्रभावों पर अधिक जानकारी के लिए Aspose.Slides for Java दस्तावेज़ देखें।

### क्या मैं इन एनिमेशनों को अन्य प्रकार के चार्ट पर लागू कर सकता हूँ?

हां, आप जिन विशिष्ट चार्ट तत्वों को एनिमेट करना चाहते हैं, उन्हें लक्षित करने के लिए कोड को संशोधित करके अन्य प्रकार के चार्ट पर समान एनिमेशन लागू कर सकते हैं। लूप संरचना और मापदंडों को तदनुसार समायोजित करें।

### मैं Java के लिए Aspose.Slides के बारे में और अधिक कैसे जान सकता हूँ?

व्यापक दस्तावेज़ीकरण और अतिरिक्त संसाधनों के लिए, पर जाएँ[जावा एपीआई संदर्भ के लिए Aspose.Slides](https://reference.aspose.com/slides/java/) . आप यहां से लाइब्रेरी भी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
