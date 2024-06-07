---
title: जावा स्लाइड्स को एनीमेशन में बदलें
linktitle: जावा स्लाइड्स को एनीमेशन में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ जावा में PowerPoint प्रस्तुतियों को एनिमेशन में बदलने का तरीका जानें। गतिशील दृश्यों के साथ अपने दर्शकों को आकर्षित करें।
type: docs
weight: 21
url: /hi/java/presentation-conversion/convert-to-animation-java-slides/
---

# Aspose.Slides for Java के साथ जावा स्लाइड्स को एनिमेशन में बदलने का परिचय

Aspose.Slides for Java एक शक्तिशाली API है जो आपको PowerPoint प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि Java और Aspose.Slides for Java का उपयोग करके स्थिर PowerPoint प्रस्तुति को एनिमेटेड में कैसे बदला जाए। इस ट्यूटोरियल के अंत तक, आप अपने दर्शकों को आकर्षित करने वाली गतिशील प्रस्तुतियाँ बनाने में सक्षम होंगे।

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

अपने जावा प्रोजेक्ट में, PowerPoint प्रस्तुतियों के साथ काम करने के लिए Aspose.Slides लाइब्रेरी को आयात करें:

```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.io.IOException;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन लोड करें

 आरंभ करने के लिए, उस PowerPoint प्रस्तुति को लोड करें जिसे आप एनीमेशन में बदलना चाहते हैं।`"SimpleAnimations.pptx"` अपनी प्रस्तुति फ़ाइल का पथ सहित:

```java
String presentationName = RunExamples.getDataDir_Conversion() + "SimpleAnimations.pptx";
Presentation pres = new Presentation(presentationName);
```

## चरण 3: प्रस्तुति के लिए एनिमेशन तैयार करें

 अब, आइए प्रेजेंटेशन में स्लाइड्स के लिए एनिमेशन बनाएं। हम इसका उपयोग करेंगे`PresentationAnimationsGenerator` इस उद्देश्य के लिए कक्षा:

```java
PresentationAnimationsGenerator animationsGenerator = new PresentationAnimationsGenerator(pres);
animationsGenerator.run(pres.getSlides());
```

## चरण 4: एनिमेशन रेंडर करने के लिए प्लेयर बनाएं

एनिमेशन को रेंडर करने के लिए, हमें एक प्लेयर बनाना होगा। हम प्रत्येक फ़्रेम को PNG इमेज के रूप में सहेजने के लिए फ़्रेम टिक इवेंट भी सेट करेंगे:

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

जैसे ही प्रस्तुतिकरण चलाया जाएगा, प्रत्येक फ़्रेम निर्दिष्ट आउटपुट निर्देशिका में PNG छवि के रूप में सहेजा जाएगा। आप आवश्यकतानुसार आउटपुट पथ को अनुकूलित कर सकते हैं:

```java
final String outPath = RunExamples.getOutPath();
```

## जावा स्लाइड्स में एनीमेशन में कनवर्ट करने के लिए पूर्ण स्रोत कोड

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

इस ट्यूटोरियल में, हमने सीखा है कि जावा और Aspose.Slides for Java का उपयोग करके एक स्थिर PowerPoint प्रेजेंटेशन को एनिमेटेड प्रेजेंटेशन में कैसे बदला जाए। यह आकर्षक प्रेजेंटेशन और विज़ुअल कंटेंट बनाने के लिए एक मूल्यवान तकनीक हो सकती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं एनिमेशन की गति को कैसे नियंत्रित कर सकता हूँ?

 आप कोड में फ्रेम दर (एफपीएस) को संशोधित करके एनिमेशन की गति को समायोजित कर सकते हैं।`player.setFrameTick` विधि आपको फ्रेम दर निर्दिष्ट करने की अनुमति देती है। हमारे उदाहरण में, हमने इसे 33 फ्रेम प्रति सेकंड (FPS) पर सेट किया है।

### क्या मैं पावरपॉइंट एनिमेशन को अन्य प्रारूपों, जैसे वीडियो, में परिवर्तित कर सकता हूँ?

हां, आप PowerPoint एनिमेशन को वीडियो सहित विभिन्न प्रारूपों में परिवर्तित कर सकते हैं। Aspose.Slides for Java प्रस्तुतियों को वीडियो के रूप में निर्यात करने के लिए सुविधाएँ प्रदान करता है। आप अधिक जानकारी के लिए दस्तावेज़ देख सकते हैं।

### क्या प्रस्तुतियों को एनिमेशन में परिवर्तित करने की कोई सीमाएँ हैं?

जबकि Aspose.Slides for Java शक्तिशाली एनीमेशन क्षमताएं प्रदान करता है, यह ध्यान रखना आवश्यक है कि जटिल एनिमेशन पूरी तरह से समर्थित नहीं हो सकते हैं। यह सुनिश्चित करने के लिए कि वे अपेक्षित रूप से काम करते हैं, अपने एनिमेशन का पूरी तरह से परीक्षण करना एक अच्छा अभ्यास है।

### क्या मैं निर्यातित फ़्रेमों के फ़ाइल प्रारूप को अनुकूलित कर सकता हूँ?

हां, आप निर्यात किए गए फ़्रेम के फ़ाइल फ़ॉर्मेट को कस्टमाइज़ कर सकते हैं। हमारे उदाहरण में, हमने फ़्रेम को PNG इमेज के रूप में सहेजा है, लेकिन आप अपनी ज़रूरतों के आधार पर JPEG या GIF जैसे अन्य फ़ॉर्मेट चुन सकते हैं।

### मैं Aspose.Slides for Java के लिए और अधिक संसाधन और दस्तावेज़ कहां पा सकता हूं?

 आप Aspose.Slides for Java के लिए विस्तृत दस्तावेज़ और संसाधन यहाँ पा सकते हैं[Aspose.Slides for Java API संदर्भ](https://reference.aspose.com/slides/java/) पृष्ठ।
