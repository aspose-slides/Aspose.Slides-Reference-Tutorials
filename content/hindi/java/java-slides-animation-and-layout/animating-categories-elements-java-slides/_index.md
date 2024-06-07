---
title: जावा स्लाइड्स में श्रेणियों के तत्वों को एनिमेट करना
linktitle: जावा स्लाइड्स में श्रेणियों के तत्वों को एनिमेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ अपने Java प्रेजेंटेशन को ऑप्टिमाइज़ करें। PowerPoint स्लाइड में श्रेणी तत्वों को चरण-दर-चरण एनिमेट करना सीखें।
type: docs
weight: 10
url: /hi/java/animation-and-layout/animating-categories-elements-java-slides/
---

## जावा स्लाइड्स में श्रेणियों के तत्वों को एनिमेट करने का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके Java स्लाइड में श्रेणी तत्वों को एनिमेट करने की प्रक्रिया के बारे में बताएंगे। यह चरण-दर-चरण मार्गदर्शिका आपको इस एनीमेशन प्रभाव को प्राप्त करने में मदद करने के लिए स्रोत कोड और स्पष्टीकरण प्रदान करेगी।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Aspose.Slides for Java API स्थापित.
- एक मौजूदा पावरपॉइंट प्रस्तुति जिसमें एक चार्ट शामिल है। आप इस चार्ट के श्रेणी तत्वों को एनिमेट करेंगे।

## चरण 1: Aspose.Slides लाइब्रेरी आयात करें

आरंभ करने के लिए, Aspose.Slides लाइब्रेरी को अपने Java प्रोजेक्ट में आयात करें। आप लाइब्रेरी को डाउनलोड करके अपने प्रोजेक्ट के क्लासपाथ में जोड़ सकते हैं। सुनिश्चित करें कि आपके पास आवश्यक निर्भरताएँ सेट अप हैं।

## चरण 2: प्रस्तुति लोड करें

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

 इस कोड में, हम एक मौजूदा पावरपॉइंट प्रेजेंटेशन लोड करते हैं जिसमें वह चार्ट होता है जिसे आप एनिमेट करना चाहते हैं।`"Your Document Directory"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

## चरण 3: चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

हम प्रस्तुति की पहली स्लाइड में चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करते हैं। स्लाइड इंडेक्स को समायोजित करें (`get_Item(0)`) और आकार सूचकांक (`get_Item(0)`) का उपयोग करें, ताकि आप अपने विशिष्ट चार्ट तक पहुंच सकें।

## चरण 4: श्रेणियों के तत्वों को एनिमेट करें

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

हम चार्ट के भीतर श्रेणियों के तत्वों को एनिमेट करते हैं। यह कोड पूरे चार्ट में एक फीका प्रभाव जोड़ता है और फिर प्रत्येक श्रेणी के भीतर प्रत्येक तत्व में एक "प्रकट" प्रभाव जोड़ता है। आवश्यकतानुसार प्रभाव प्रकार और उपप्रकार को समायोजित करें।

## चरण 5: प्रस्तुति सहेजें

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

 अंत में, संशोधित प्रस्तुति को एनिमेटेड चार्ट के साथ एक नई फ़ाइल में सहेजें।`"AnimatingCategoriesElements_out.pptx"` अपने इच्छित आउटपुट फ़ाइल नाम के साथ.


## जावा स्लाइड्स में श्रेणियों के तत्वों को एनिमेट करने के लिए पूर्ण स्रोत कोड
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
	// श्रेणियों के तत्वों को एनिमेट करें
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
	// प्रस्तुति फ़ाइल को डिस्क पर लिखें
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

आपने Aspose.Slides for Java का उपयोग करके Java स्लाइड में श्रेणी तत्वों को सफलतापूर्वक एनिमेट किया है। इस चरण-दर-चरण मार्गदर्शिका ने आपको अपने PowerPoint प्रस्तुतियों में इस एनीमेशन प्रभाव को प्राप्त करने के लिए आवश्यक स्रोत कोड और स्पष्टीकरण प्रदान किए हैं। अपने एनिमेशन को और अधिक अनुकूलित करने के लिए विभिन्न प्रभावों और सेटिंग्स के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं एनीमेशन प्रभाव को कैसे अनुकूलित कर सकता हूँ?

 आप एनीमेशन प्रभाव को बदलकर अनुकूलित कर सकते हैं`EffectType` और`EffectSubtype` चार्ट तत्वों में प्रभाव जोड़ते समय पैरामीटर। उपलब्ध एनीमेशन प्रभावों के बारे में अधिक जानकारी के लिए Aspose.Slides for Java दस्तावेज़ देखें।

### क्या मैं इन एनिमेशन को अन्य प्रकार के चार्ट पर लागू कर सकता हूँ?

हां, आप कोड को संशोधित करके अन्य प्रकार के चार्ट पर भी इसी तरह के एनिमेशन लागू कर सकते हैं, ताकि आप उन विशिष्ट चार्ट तत्वों को लक्षित कर सकें जिन्हें आप एनिमेट करना चाहते हैं। लूप संरचना और मापदंडों को तदनुसार समायोजित करें।

### मैं Aspose.Slides for Java के बारे में अधिक कैसे जान सकता हूँ?

 विस्तृत दस्तावेज़ीकरण और अतिरिक्त संसाधनों के लिए, कृपया देखें[Aspose.Slides for Java API संदर्भ](https://reference.aspose.com/slides/java/) . आप लाइब्रेरी को यहां से भी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
