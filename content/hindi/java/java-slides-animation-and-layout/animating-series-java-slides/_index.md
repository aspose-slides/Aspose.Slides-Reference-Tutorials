---
title: जावा स्लाइड्स में एनिमेटिंग श्रृंखला
linktitle: जावा स्लाइड्स में एनिमेटिंग श्रृंखला
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides में श्रृंखला एनिमेशन के साथ अपनी प्रस्तुतियों को अनुकूलित करें। आकर्षक पावरपॉइंट एनिमेशन बनाने के लिए स्रोत कोड उदाहरणों के साथ हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 11
url: /hi/java/animation-and-layout/animating-series-java-slides/
---

## जावा के लिए Aspose.Slides में एनिमेटिंग श्रृंखला का परिचय

इस गाइड में, हम आपको जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में श्रृंखला को एनिमेट करने की प्रक्रिया के बारे में बताएंगे। यह लाइब्रेरी आपको PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- जावा लाइब्रेरी के लिए Aspose.Slides।
- जावा विकास पर्यावरण की स्थापना।

## चरण 1: प्रस्तुति लोड करें

 सबसे पहले, हमें एक मौजूदा पावरपॉइंट प्रेजेंटेशन को लोड करना होगा जिसमें एक चार्ट है। प्रतिस्थापित करें`"Your Document Directory"` आपकी प्रस्तुति फ़ाइल के वास्तविक पथ के साथ।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
//इंस्टेंटिएट प्रेजेंटेशन क्लास जो प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करती है
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

अब, चार्ट के भीतर श्रृंखला में एनिमेशन जोड़ें। हम फ़ेड-इन प्रभाव का उपयोग करेंगे और प्रत्येक श्रृंखला को एक के बाद एक प्रदर्शित करेंगे।

```java
// संपूर्ण चार्ट को चेतन करें
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// प्रत्येक श्रृंखला में एनिमेशन जोड़ें (मान लें कि 4 श्रृंखलाएं हैं)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

उपरोक्त कोड में, हम पूरे चार्ट के लिए फ़ेड-इन प्रभाव का उपयोग करते हैं और फिर एक के बाद एक प्रत्येक श्रृंखला में "प्रकट" प्रभाव जोड़ने के लिए एक लूप का उपयोग करते हैं।

## चरण 4: प्रस्तुति सहेजें

अंत में, संशोधित प्रस्तुति को डिस्क पर सहेजें।

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## जावा के लिए Aspose.Slides में एनिमेटिंग श्रृंखला के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
//इंस्टेंटिएट प्रेजेंटेशन क्लास जो प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करती है
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// चार्ट ऑब्जेक्ट का संदर्भ प्राप्त करें
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// श्रृंखला को चेतन करें
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

आपने Java के लिए Aspose.Slides का उपयोग करके PowerPoint चार्ट में श्रृंखला को सफलतापूर्वक एनिमेटेड किया है। यह आपकी प्रस्तुतियों को अधिक आकर्षक और देखने में आकर्षक बना सकता है। अधिक एनीमेशन विकल्पों का अन्वेषण करें और आवश्यकतानुसार अपनी प्रस्तुतियों को बेहतर बनाएं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं श्रृंखला एनिमेशन के क्रम को कैसे नियंत्रित करूं?

 श्रृंखला एनिमेशन के क्रम को नियंत्रित करने के लिए, इसका उपयोग करें`EffectTriggerType.AfterPrevious` प्रभाव जोड़ते समय पैरामीटर। इससे प्रत्येक श्रृंखला का एनीमेशन पिछली श्रृंखला के ख़त्म होने के बाद शुरू होगा।

### क्या मैं प्रत्येक श्रृंखला में अलग-अलग एनिमेशन लागू कर सकता हूँ?

 हां, आप अलग-अलग निर्दिष्ट करके प्रत्येक श्रृंखला में अलग-अलग एनिमेशन लागू कर सकते हैं`EffectType` और`EffectSubtype` प्रभाव जोड़ते समय मान।

### यदि मेरी प्रस्तुति में चार से अधिक श्रृंखलाएँ हों तो क्या होगा?

आप अपने चार्ट में सभी श्रृंखलाओं के लिए एनिमेशन जोड़ने के लिए चरण 3 में लूप का विस्तार कर सकते हैं। बस लूप की स्थिति को तदनुसार समायोजित करें।

### मैं एनीमेशन अवधि और विलंब को कैसे अनुकूलित कर सकता हूं?

आप एनीमेशन प्रभावों पर गुण सेट करके एनीमेशन की अवधि और देरी को अनुकूलित कर सकते हैं। उपलब्ध अनुकूलन विकल्पों के विवरण के लिए Aspose.Slides for Java दस्तावेज़ देखें।