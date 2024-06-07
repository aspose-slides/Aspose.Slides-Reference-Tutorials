---
title: जावा स्लाइड्स में श्रृंखला को एनिमेट करना
linktitle: जावा स्लाइड्स में श्रृंखला को एनिमेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java में सीरीज एनिमेशन के साथ अपनी प्रस्तुतियों को अनुकूलित करें। आकर्षक PowerPoint एनिमेशन बनाने के लिए स्रोत कोड उदाहरणों के साथ हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 11
url: /hi/java/animation-and-layout/animating-series-java-slides/
---

## Aspose.Slides for Java में सीरीज को एनिमेट करने का परिचय

इस गाइड में, हम आपको Aspose.Slides for Java API का उपयोग करके Java स्लाइड में सीरीज़ को एनिमेट करने की प्रक्रिया से परिचित कराएँगे। यह लाइब्रेरी आपको प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों के साथ काम करने की अनुमति देती है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- Aspose.Slides for Java लाइब्रेरी.
- जावा विकास वातावरण की स्थापना.

## चरण 1: प्रस्तुति लोड करें

 सबसे पहले, हमें एक मौजूदा पावरपॉइंट प्रेजेंटेशन लोड करना होगा जिसमें एक चार्ट हो।`"Your Document Directory"` अपनी प्रस्तुति फ़ाइल के वास्तविक पथ के साथ.

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## चरण 2: चार्ट तक पहुंचें

इसके बाद, हम प्रेजेंटेशन के भीतर चार्ट तक पहुंचेंगे। इस उदाहरण में, हम मानते हैं कि चार्ट पहली स्लाइड पर है और उस स्लाइड पर पहली आकृति है।

```java
// चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## चरण 3: एनिमेशन जोड़ें

अब, चार्ट के अंदर सीरीज में एनिमेशन जोड़ते हैं। हम फ़ेड-इन इफ़ेक्ट का इस्तेमाल करेंगे और हर सीरीज को एक के बाद एक दिखाएंगे।

```java
// संपूर्ण चार्ट को एनिमेट करें
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// प्रत्येक श्रृंखला में एनिमेशन जोड़ें (मान लें कि 4 श्रृंखलाएं हैं)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

उपरोक्त कोड में, हम संपूर्ण चार्ट के लिए फ़ेड-इन प्रभाव का उपयोग करते हैं और फिर एक लूप का उपयोग करके प्रत्येक श्रृंखला में एक के बाद एक "प्रकटीकरण" प्रभाव जोड़ते हैं।

## चरण 4: प्रस्तुति सहेजें

अंत में, संशोधित प्रस्तुति को डिस्क पर सहेजें।

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## जावा के लिए Aspose.Slides में श्रृंखला को एनिमेट करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// श्रृंखला को एनिमेट करें
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None,
			EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 0,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 1,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 2,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 3,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// संशोधित प्रस्तुति को डिस्क पर लिखें
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

आपने Aspose.Slides for Java का उपयोग करके PowerPoint चार्ट में सफलतापूर्वक एनिमेटेड सीरीज़ बनाई है। यह आपकी प्रस्तुतियों को अधिक आकर्षक और आकर्षक बना सकता है। अधिक एनिमेशन विकल्पों का पता लगाएं और आवश्यकतानुसार अपनी प्रस्तुतियों को बेहतर बनाएं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं श्रृंखला एनिमेशन के क्रम को कैसे नियंत्रित करूँ?

 श्रृंखला एनिमेशन के क्रम को नियंत्रित करने के लिए, का उपयोग करें`EffectTriggerType.AfterPrevious`प्रभाव जोड़ते समय पैरामीटर का उपयोग करें। इससे प्रत्येक श्रृंखला एनीमेशन पिछले एक के समाप्त होने के बाद शुरू होगा।

### क्या मैं प्रत्येक श्रृंखला पर अलग-अलग एनिमेशन लागू कर सकता हूँ?

 हां, आप अलग-अलग एनिमेशन निर्दिष्ट करके प्रत्येक श्रृंखला पर अलग-अलग एनिमेशन लागू कर सकते हैं`EffectType` और`EffectSubtype` प्रभाव जोड़ते समय मान.

### यदि मेरी प्रस्तुति में चार से अधिक श्रृंखलाएं हों तो क्या होगा?

आप अपने चार्ट में सभी श्रृंखलाओं के लिए एनिमेशन जोड़ने के लिए चरण 3 में लूप का विस्तार कर सकते हैं। बस लूप की स्थिति को तदनुसार समायोजित करें।

### मैं एनीमेशन अवधि और विलंब को कैसे अनुकूलित कर सकता हूं?

आप एनीमेशन प्रभाव पर गुण सेट करके एनीमेशन अवधि और देरी को अनुकूलित कर सकते हैं। उपलब्ध अनुकूलन विकल्पों के विवरण के लिए Aspose.Slides for Java दस्तावेज़ देखें।