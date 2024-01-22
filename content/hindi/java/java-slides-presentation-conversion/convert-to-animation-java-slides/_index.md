---
title: जावा स्लाइड्स में एनिमेशन में कनवर्ट करें
linktitle: जावा स्लाइड्स में एनिमेशन में कनवर्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Aspose.Slides के साथ जावा में PowerPoint प्रस्तुतियों को एनिमेशन में कैसे परिवर्तित करें। अपने दर्शकों को गतिशील दृश्यों से जोड़े रखें।
type: docs
weight: 21
url: /hi/java/presentation-conversion/convert-to-animation-java-slides/
---

# जावा के लिए Aspose.Slides के साथ जावा स्लाइड्स में एनीमेशन में कनवर्ट करने का परिचय

जावा के लिए Aspose.Slides एक शक्तिशाली API है जो आपको PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि जावा और Aspose.Slides for Java का उपयोग करके एक स्थिर पावरपॉइंट प्रेजेंटेशन को एनिमेटेड में कैसे परिवर्तित किया जाए। इस ट्यूटोरियल के अंत तक, आप गतिशील प्रस्तुतियाँ बनाने में सक्षम होंगे जो आपके दर्शकों को आकर्षित करेंगी।

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Slides। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: आवश्यक पुस्तकालय आयात करें

अपने जावा प्रोजेक्ट में, PowerPoint प्रस्तुतियों के साथ काम करने के लिए Aspose.Slides लाइब्रेरी आयात करें:

```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.io.IOException;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन लोड करें

 आरंभ करने के लिए, उस PowerPoint प्रस्तुति को लोड करें जिसे आप एनीमेशन में कनवर्ट करना चाहते हैं। प्रतिस्थापित करें`"SimpleAnimations.pptx"` आपकी प्रस्तुति फ़ाइल के पथ के साथ:

```java
String presentationName = RunExamples.getDataDir_Conversion() + "SimpleAnimations.pptx";
Presentation pres = new Presentation(presentationName);
```

## चरण 3: प्रस्तुति के लिए एनिमेशन तैयार करें

 अब, प्रेजेंटेशन में स्लाइड्स के लिए एनिमेशन तैयार करते हैं। हम उपयोग करेंगे`PresentationAnimationsGenerator` इस उद्देश्य के लिए कक्षा:

```java
PresentationAnimationsGenerator animationsGenerator = new PresentationAnimationsGenerator(pres);
animationsGenerator.run(pres.getSlides());
```

## चरण 4: एनिमेशन प्रस्तुत करने के लिए एक प्लेयर बनाएं

एनिमेशन प्रस्तुत करने के लिए, हमें एक प्लेयर बनाना होगा। हम प्रत्येक फ्रेम को पीएनजी छवि के रूप में सहेजने के लिए फ्रेम टिक इवेंट भी सेट करेंगे:

```java
PresentationPlayer player = new PresentationPlayer(animationsGenerator, 33);
player.setFrameTick(new PresentationPlayer.FrameTick() {
    public void invoke(PresentationPlayer sender, FrameTickEventArgs arg) {
        try {
            ImageIO.write(arg.getFrame(), "PNG", new java.io.File(outPath + "frame_" + sender.getFrameIndex() + ".png"));
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
    }
});
```

## चरण 5: एनिमेटेड फ़्रेम सहेजें

जैसे ही प्रेजेंटेशन चलाया जाएगा, प्रत्येक फ्रेम निर्दिष्ट आउटपुट निर्देशिका में पीएनजी छवि के रूप में सहेजा जाएगा। आप आवश्यकतानुसार आउटपुट पथ को अनुकूलित कर सकते हैं:

```java
final String outPath = RunExamples.getOutPath();
```

## जावा स्लाइड्स में एनिमेशन में कनवर्ट करने के लिए संपूर्ण स्रोत कोड

```java
String presentationName = RunExamples.getDataDir_Conversion() + "SimpleAnimations.pptx";
final String outPath = RunExamples.getOutPath();
final int FPS = 30;
Presentation pres = new Presentation(presentationName);
try {
	PresentationAnimationsGenerator animationsGenerator = new PresentationAnimationsGenerator(pres);
	try {
		PresentationPlayer player = new PresentationPlayer(animationsGenerator, 33);
		try {
			player.setFrameTick(new PresentationPlayer.FrameTick() {
				public void invoke(PresentationPlayer sender, FrameTickEventArgs arg) {
					try {
						ImageIO.write(arg.getFrame(), "PNG", new java.io.File(outPath + "frame_" + sender.getFrameIndex() + ".png"));
					} catch (IOException e) {
						throw new RuntimeException(e);
					}
				}
			});
			animationsGenerator.run(pres.getSlides());
		} finally {
			if (player != null) player.dispose();
		}
	} finally {
		if (animationsGenerator != null) animationsGenerator.dispose();
	}
} finally {
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि जावा और Aspose.Slides for Java का उपयोग करके एक स्थिर पावरपॉइंट प्रेजेंटेशन को एनिमेटेड में कैसे परिवर्तित किया जाए। आकर्षक प्रस्तुतियाँ और दृश्य सामग्री बनाने के लिए यह एक मूल्यवान तकनीक हो सकती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं एनिमेशन की गति को कैसे नियंत्रित कर सकता हूं?

 आप कोड में फ्रेम दर (एफपीएस) को संशोधित करके एनिमेशन की गति को समायोजित कर सकते हैं।`player.setFrameTick` विधि आपको फ़्रेम दर निर्दिष्ट करने की अनुमति देती है। हमारे उदाहरण में, हमने इसे 33 फ्रेम प्रति सेकंड (एफपीएस) पर सेट किया है।

### क्या मैं PowerPoint एनिमेशन को वीडियो जैसे अन्य प्रारूपों में परिवर्तित कर सकता हूँ?

हाँ, आप PowerPoint एनिमेशन को वीडियो सहित विभिन्न प्रारूपों में परिवर्तित कर सकते हैं। जावा के लिए Aspose.Slides प्रस्तुतियों को वीडियो के रूप में निर्यात करने की सुविधाएँ प्रदान करता है। आप अधिक विवरण के लिए दस्तावेज़ का पता लगा सकते हैं।

### क्या प्रस्तुतियों को एनिमेशन में परिवर्तित करने की कोई सीमाएँ हैं?

जबकि जावा के लिए Aspose.Slides शक्तिशाली एनीमेशन क्षमताएं प्रदान करता है, यह ध्यान रखना आवश्यक है कि जटिल एनिमेशन पूरी तरह से समर्थित नहीं हो सकते हैं। यह सुनिश्चित करने के लिए कि वे अपेक्षा के अनुरूप काम करते हैं, अपने एनिमेशन का पूरी तरह से परीक्षण करना एक अच्छा अभ्यास है।

### क्या मैं निर्यातित फ़्रेमों के फ़ाइल स्वरूप को अनुकूलित कर सकता हूँ?

हां, आप निर्यात किए गए फ़्रेम के फ़ाइल स्वरूप को अनुकूलित कर सकते हैं। हमारे उदाहरण में, हमने फ़्रेम को पीएनजी छवियों के रूप में सहेजा है, लेकिन आप अपनी आवश्यकताओं के आधार पर जेपीईजी या जीआईएफ जैसे अन्य प्रारूप चुन सकते हैं।

### जावा के लिए Aspose.Slides के लिए मुझे और अधिक संसाधन और दस्तावेज़ कहां मिल सकते हैं?

 आप जावा के लिए Aspose.Slides के लिए व्यापक दस्तावेज़ और संसाधन पा सकते हैं[जावा एपीआई संदर्भ के लिए Aspose.Slides](https://reference.aspose.com/slides/java/) पृष्ठ।
