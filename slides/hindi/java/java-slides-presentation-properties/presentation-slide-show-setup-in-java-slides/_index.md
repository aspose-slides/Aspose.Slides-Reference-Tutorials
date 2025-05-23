---
"description": "Aspose.Slides के साथ अपने Java स्लाइड शो को ऑप्टिमाइज़ करें। कस्टमाइज़्ड सेटिंग्स के साथ आकर्षक प्रेजेंटेशन बनाएँ। चरण-दर-चरण गाइड और FAQ देखें।"
"linktitle": "जावा स्लाइड्स में प्रेजेंटेशन स्लाइड शो सेटअप"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में प्रेजेंटेशन स्लाइड शो सेटअप"
"url": "/hi/java/presentation-properties/presentation-slide-show-setup-in-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में प्रेजेंटेशन स्लाइड शो सेटअप


## जावा स्लाइड्स में प्रेजेंटेशन स्लाइड शो सेटअप का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके प्रेजेंटेशन स्लाइड शो सेट अप करने का तरीका जानेंगे। हम पावरपॉइंट प्रेजेंटेशन बनाने और विभिन्न स्लाइड शो सेटिंग्स को कॉन्फ़िगर करने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी जोड़ी गई है। आप इसे यहाँ से डाउनलोड कर सकते हैं [Aspose वेबसाइट](https://releases.aspose.com/slides/java/).

## चरण 1: पावरपॉइंट प्रेजेंटेशन बनाएं

सबसे पहले, हमें एक नया पावरपॉइंट प्रेजेंटेशन बनाना होगा। जावा में आप इसे इस तरह बना सकते हैं:

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
```

उपरोक्त कोड में, हम अपनी प्रस्तुति के लिए आउटपुट फ़ाइल पथ निर्दिष्ट करते हैं और एक नया बनाते हैं `Presentation` वस्तु।

## चरण 2: स्लाइड शो सेटिंग कॉन्फ़िगर करें

इसके बाद, हम अपनी प्रस्तुति के लिए विभिन्न स्लाइड शो सेटिंग्स कॉन्फ़िगर करेंगे। 

### टाइमिंग पैरामीटर का उपयोग करें

हम "समय का उपयोग" पैरामीटर को सेट करके यह नियंत्रित कर सकते हैं कि स्लाइड शो के दौरान स्लाइड स्वचालित रूप से आगे बढ़ें या मैन्युअल रूप से।

```java
SlideShowSettings slideShow = pres.getSlideShowSettings();
slideShow.setUseTimings(false); // मैन्युअल अग्रिम के लिए गलत पर सेट करें
```

इस उदाहरण में, हमने इसे सेट किया है `false` स्लाइडों को मैन्युअल रूप से आगे बढ़ाने की अनुमति देने के लिए।

### पेन का रंग सेट करें

आप स्लाइड शो के दौरान इस्तेमाल किए जाने वाले पेन के रंग को भी कस्टमाइज़ कर सकते हैं। इस उदाहरण में, हम पेन का रंग हरा सेट करेंगे।

```java
IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
penColor.setColor(Color.GREEN);
```

### स्लाइड्स जोड़ें

आइए अपनी प्रस्तुति में कुछ स्लाइड जोड़ें। हम चीजों को सरल रखने के लिए मौजूदा स्लाइड का क्लोन बनाएंगे।

```java
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
```

इस कोड में, हम पहली स्लाइड को चार बार क्लोन कर रहे हैं। आप अपनी खुद की सामग्री जोड़ने के लिए इस भाग को संशोधित कर सकते हैं।

## चरण 3: स्लाइड शो के लिए स्लाइड रेंज निर्धारित करें

आप निर्दिष्ट कर सकते हैं कि स्लाइड शो में कौन सी स्लाइड शामिल की जानी चाहिए। इस उदाहरण में, हम दूसरी स्लाइड से लेकर पाँचवीं स्लाइड तक स्लाइड की एक सीमा निर्धारित करेंगे।

```java
SlidesRange slidesRange = new SlidesRange();
slidesRange.setStart(2);
slidesRange.setEnd(5);
slideShow.setSlides(slidesRange);
```

आरंभिक और अंतिम स्लाइड संख्या निर्धारित करके, आप नियंत्रित कर सकते हैं कि कौन सी स्लाइडें स्लाइड शो का हिस्सा होंगी।

## चरण 4: प्रस्तुति सहेजें

अंत में, हम कॉन्फ़िगर की गई प्रस्तुति को एक फ़ाइल में सहेज लेंगे।

```java
pres.save(outPptxPath, SaveFormat.Pptx);
```

वांछित आउटपुट फ़ाइल पथ प्रदान करना सुनिश्चित करें.

## जावा स्लाइड्स में प्रेजेंटेशन स्लाइड शो सेटअप के लिए पूरा सोर्स कोड

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
try {
	// स्लाइड शो सेटिंग्स प्राप्त करता है
	SlideShowSettings slideShow = pres.getSlideShowSettings();
	// "समय का उपयोग" पैरामीटर सेट करता है
	slideShow.setUseTimings(false);
	// पेन का रंग सेट करता है
	IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
	penColor.setColor(Color.GREEN);
	// इसके लिए स्लाइड्स जोड़ता है
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	// स्लाइड दिखाएँ पैरामीटर सेट करता है
	SlidesRange slidesRange = new SlidesRange();
	slidesRange.setStart(2);
	slidesRange.setEnd(5);
	slideShow.setSlides(slidesRange);
	// प्रस्तुति सहेजें
	pres.save(outPptxPath, SaveFormat.Pptx);
} finally {
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके Java में प्रेजेंटेशन स्लाइड शो कैसे सेट किया जाता है। आप इंटरैक्टिव और आकर्षक प्रेजेंटेशन बनाने के लिए टाइमिंग, पेन कलर और स्लाइड रेंज सहित विभिन्न स्लाइड शो सेटिंग्स को कस्टमाइज़ कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं स्लाइड ट्रांज़िशन के लिए समय कैसे बदलूं?

स्लाइड ट्रांज़िशन के लिए समय बदलने के लिए, आप स्लाइड शो सेटिंग में "समय का उपयोग करना" पैरामीटर को संशोधित कर सकते हैं। इसे इस पर सेट करें `true` पूर्वनिर्धारित समय के साथ स्वचालित उन्नति के लिए या `false` स्लाइड शो के दौरान मैन्युअल अग्रिम के लिए।

### मैं स्लाइड शो के दौरान उपयोग किए जाने वाले पेन के रंग को कैसे अनुकूलित कर सकता हूँ?

आप स्लाइड शो सेटिंग में पेन कलर सेटिंग तक पहुंचकर पेन कलर को कस्टमाइज़ कर सकते हैं। `setColor` मनचाहा रंग सेट करने की विधि। उदाहरण के लिए, पेन का रंग हरा सेट करने के लिए, उपयोग करें `penColor.setColor(Color.GREEN)`.

### मैं स्लाइड शो में विशिष्ट स्लाइड कैसे जोड़ूं?

स्लाइड शो में विशिष्ट स्लाइड्स शामिल करने के लिए, एक बनाएं `SlidesRange` ऑब्जेक्ट और प्रारंभ और अंत स्लाइड संख्या का उपयोग कर सेट करें `setStart` और `setEnd` विधियाँ। फिर, इस श्रेणी को स्लाइड शो सेटिंग्स में असाइन करें `slideShow.setSlides(slidesRange)`.

### क्या मैं प्रस्तुति में और स्लाइडें जोड़ सकता हूँ?

हां, आप अपनी प्रस्तुति में अतिरिक्त स्लाइड जोड़ सकते हैं। `pres.getSlides().addClone()` मौजूदा स्लाइड्स को क्लोन करने या आवश्यकतानुसार नई स्लाइड्स बनाने की विधि। अपनी आवश्यकताओं के अनुसार इन स्लाइड्स की सामग्री को अनुकूलित करना सुनिश्चित करें।

### मैं कॉन्फ़िगर की गई प्रस्तुति को फ़ाइल में कैसे सहेजूँ?

कॉन्फ़िगर की गई प्रस्तुति को फ़ाइल में सहेजने के लिए, का उपयोग करें `pres.save()` विधि और आउटपुट फ़ाइल पथ के साथ-साथ वांछित प्रारूप निर्दिष्ट करें। उदाहरण के लिए, आप इसे PPTX प्रारूप में सहेज सकते हैं `pres.save(outPptxPath, SaveFormat.Pptx)`.

### मैं स्लाइड शो सेटिंग को और अधिक अनुकूलित कैसे कर सकता हूं?

आप अपनी ज़रूरतों के हिसाब से स्लाइड शो अनुभव को अनुकूलित करने के लिए Aspose.Slides for Java द्वारा प्रदान की गई अतिरिक्त स्लाइड शो सेटिंग्स का पता लगा सकते हैं। दस्तावेज़ देखें [यहाँ](https://reference.aspose.com/slides/java/) उपलब्ध विकल्पों और कॉन्फ़िगरेशन पर विस्तृत जानकारी के लिए.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}