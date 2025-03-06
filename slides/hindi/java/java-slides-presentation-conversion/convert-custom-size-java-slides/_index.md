---
title: जावा स्लाइड्स में कस्टम आकार के साथ कनवर्ट करें
linktitle: जावा स्लाइड्स में कस्टम आकार के साथ कनवर्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों को कस्टम आकार के साथ TIFF छवियों में परिवर्तित करना सीखें। डेवलपर्स के लिए कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 31
url: /hi/java/presentation-conversion/convert-custom-size-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में कस्टम आकार के साथ कनवर्ट करें


## जावा स्लाइड्स में कस्टम आकार के साथ कनवर्ट करने का परिचय

इस लेख में, हम यह पता लगाएंगे कि Aspose.Slides for Java API का उपयोग करके PowerPoint प्रस्तुतियों को कस्टम आकार के साथ TIFF छवियों में कैसे परिवर्तित किया जाए। Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को PowerPoint फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देती है। हम चरण दर चरण आगे बढ़ेंगे और आपको इस कार्य को पूरा करने के लिए आवश्यक Java कोड प्रदान करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा डेवलपमेंट किट (JDK) स्थापित
- Aspose.Slides for Java लाइब्रेरी

 आप वेबसाइट से Aspose.Slides for Java लाइब्रेरी डाउनलोड कर सकते हैं:[Java के लिए Aspose.Slides डाउनलोड करें](https://releases.aspose.com/slides/java/)

## चरण 1: Aspose.Slides लाइब्रेरी आयात करें

आरंभ करने के लिए, आपको अपने जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी को आयात करना होगा। आप इसे इस प्रकार कर सकते हैं:

```java
// आवश्यक आयात विवरण जोड़ें
import com.aspose.slides.*;
```

## चरण 2: पावरपॉइंट प्रेजेंटेशन लोड करें

 इसके बाद, आपको उस पावरपॉइंट प्रेजेंटेशन को लोड करना होगा जिसे आप TIFF इमेज में बदलना चाहते हैं।`"Your Document Directory"` अपनी प्रस्तुति फ़ाइल के वास्तविक पथ के साथ.

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## चरण 3: TIFF रूपांतरण विकल्प सेट करें

अब, आइए TIFF रूपांतरण के लिए विकल्प सेट करें। हम संपीड़न प्रकार, DPI (डॉट्स प्रति इंच), छवि आकार और नोट्स की स्थिति निर्दिष्ट करेंगे। आप अपनी आवश्यकताओं के अनुसार इन विकल्पों को अनुकूलित कर सकते हैं।

```java
// TiffOptions वर्ग को तत्कालित करें
TiffOptions opts = new TiffOptions();

// संपीड़न प्रकार सेट करना
opts.setCompressionType(TiffCompressionTypes.Default);

// छवि DPI सेट करना
opts.setDpiX(200);
opts.setDpiY(100);

// छवि का आकार सेट करें
opts.setImageSize(new Dimension(1728, 1078));

// नोट्स की स्थिति निर्धारित करें
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## चरण 4: TIFF के रूप में सहेजें

सभी विकल्पों को कॉन्फ़िगर करने के बाद, अब आप निर्दिष्ट सेटिंग्स के साथ प्रस्तुति को TIFF छवि के रूप में सहेज सकते हैं।

```java
// निर्दिष्ट छवि आकार के साथ प्रस्तुति को TIFF में सहेजें
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## जावा स्लाइड्स में कस्टम आकार के साथ कन्वर्ट करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// TiffOptions वर्ग को तत्कालित करें
	TiffOptions opts = new TiffOptions();
	// संपीड़न प्रकार सेट करना
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// संपीड़न प्रकार
	// डिफ़ॉल्ट - डिफ़ॉल्ट संपीड़न योजना (LZW) निर्दिष्ट करता है.
	// कोई नहीं - कोई संपीड़न निर्दिष्ट नहीं करता है।
	// सीसीआईटीटी3
	// सीसीआईटीटी4
	// एलजेडडब्ल्यू
	// आरएलई
	// गहराई संपीड़न के प्रकार पर निर्भर करती है और इसे मैन्युअल रूप से सेट नहीं किया जा सकता है।
	// रिज़ॉल्यूशन इकाई हमेशा “2” (डॉट्स प्रति इंच) के बराबर होती है
	// छवि DPI सेट करना
	opts.setDpiX(200);
	opts.setDpiY(100);
	// छवि का आकार सेट करें
	opts.setImageSize(new Dimension(1728, 1078));
	// निर्दिष्ट छवि आकार के साथ प्रस्तुति को TIFF में सहेजें
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन को कस्टम आकार के साथ TIFF इमेज में सफलतापूर्वक परिवर्तित कर लिया है। यह एक मूल्यवान सुविधा हो सकती है जब आपको विभिन्न उद्देश्यों के लिए अपनी प्रस्तुतियों से उच्च-गुणवत्ता वाली छवियां बनाने की आवश्यकता होती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं TIFF छवि के लिए संपीड़न प्रकार कैसे बदल सकता हूँ?

 आप संपीड़न प्रकार को संशोधित करके बदल सकते हैं`setCompressionType` विधि में`TiffOptions` क्लास। विभिन्न संपीड़न प्रकार उपलब्ध हैं, जैसे डिफ़ॉल्ट, कोई नहीं, CCITT3, CCITT4, LZW, और RLE।

### क्या मैं TIFF छवि का DPI (डॉट्स प्रति इंच) समायोजित कर सकता हूँ?

हां, आप DPI को निम्न का उपयोग करके समायोजित कर सकते हैं:`setDpiX` और`setDpiY` तरीकों में`TiffOptions` वर्ग। छवि रिज़ॉल्यूशन को नियंत्रित करने के लिए बस वांछित मान सेट करें।

### TIFF छवि में नोट्स की स्थिति के लिए उपलब्ध विकल्प क्या हैं?

 TIFF छवि में नोट्स की स्थिति को कॉन्फ़िगर किया जा सकता है`setNotesPosition` बॉटमफुल, बॉटमट्रंकेटेड और स्लाइडऑनली जैसे विकल्पों के साथ विधि। अपनी ज़रूरतों के हिसाब से सबसे अच्छा विकल्प चुनें।

### क्या TIFF रूपांतरण के लिए कस्टम छवि आकार निर्दिष्ट करना संभव है?

 बिल्कुल! आप इसका उपयोग करके एक कस्टम छवि आकार सेट कर सकते हैं`setImageSize` विधि में`TiffOptions` क्लास. आउटपुट छवि के लिए इच्छित आयाम (चौड़ाई और ऊंचाई) प्रदान करें.

### मैं Aspose.Slides for Java के बारे में अधिक जानकारी कहां पा सकता हूं?

 Aspose.Slides for Java के बारे में विस्तृत दस्तावेज़ीकरण और अतिरिक्त जानकारी के लिए, कृपया दस्तावेज़ीकरण देखें:[Aspose.Slides for Java API संदर्भ](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
