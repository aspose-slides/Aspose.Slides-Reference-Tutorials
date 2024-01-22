---
title: जावा स्लाइड्स में मूल फ़ॉन्ट्स को संरक्षित करके प्रेजेंटेशन को HTML में परिवर्तित करना
linktitle: जावा स्लाइड्स में मूल फ़ॉन्ट्स को संरक्षित करके प्रेजेंटेशन को HTML में परिवर्तित करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Java के लिए Aspose.Slides का उपयोग करके मूल फ़ॉन्ट को संरक्षित करते हुए PowerPoint प्रस्तुतियों को HTML में बदलें।
type: docs
weight: 14
url: /hi/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## जावा स्लाइड्स में मूल फ़ॉन्ट्स को संरक्षित करके प्रेजेंटेशन को HTML में परिवर्तित करने का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके मूल फ़ॉन्ट को संरक्षित करते हुए पावरपॉइंट प्रेजेंटेशन (PPTX) को HTML में कैसे परिवर्तित किया जाए। इससे यह सुनिश्चित हो जाएगा कि परिणामी HTML मूल प्रस्तुति के स्वरूप से काफी मिलता-जुलता है।

## चरण 1: परियोजना की स्थापना
इससे पहले कि हम कोड में उतरें, आइए सुनिश्चित करें कि आपके पास आवश्यक सेटअप मौजूद है:

1. जावा के लिए Aspose.Slides डाउनलोड करें: यदि आपने पहले से नहीं किया है, तो जावा लाइब्रेरी के लिए Aspose.Slides डाउनलोड करें और अपने प्रोजेक्ट में शामिल करें।

2. एक जावा प्रोजेक्ट बनाएं: अपने पसंदीदा आईडीई में एक जावा प्रोजेक्ट सेट करें, और सुनिश्चित करें कि आपके पास एक "lib" फ़ोल्डर है जहां आप Aspose.Slides JAR फ़ाइल रख सकते हैं।

3. आवश्यक कक्षाएं आयात करें: अपनी जावा फ़ाइल की शुरुआत में आवश्यक कक्षाएं आयात करें:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## चरण 2: प्रेजेंटेशन को मूल फ़ॉन्ट के साथ HTML में परिवर्तित करना

अब, आइए मूल फ़ॉन्ट को संरक्षित करते हुए एक PowerPoint प्रेजेंटेशन को HTML में परिवर्तित करें:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// प्रेजेंटेशन लोड करें
Presentation pres = new Presentation("input.pptx");

try {
    //कैलीबरी और एरियल जैसे डिफ़ॉल्ट प्रेजेंटेशन फ़ॉन्ट को बाहर निकालें
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // HTML विकल्प बनाएं और कस्टम HTML फ़ॉर्मेटर सेट करें
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // प्रस्तुतिकरण को HTML के रूप में सहेजें
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // प्रेजेंटेशन ऑब्जेक्ट का निपटान करें
    if (pres != null) pres.dispose();
}
```

इस कोड स्निपेट में:

-  हम इनपुट पॉवरपॉइंट प्रेजेंटेशन का उपयोग करके लोड करते हैं`Presentation`.

- हम फ़ॉन्ट की एक सूची परिभाषित करते हैं (`fontNameExcludeList`) जिसे हम HTML में एम्बेडिंग से बाहर करना चाहते हैं। यह फ़ाइल आकार को कम करने के लिए कैलीबरी और एरियल जैसे सामान्य फ़ॉन्ट को बाहर करने के लिए उपयोगी है।

-  हम इसका एक उदाहरण बनाते हैं`EmbedAllFontsHtmlController` और फ़ॉन्ट बहिष्करण सूची को इसमें पास करें।

-  हम बनाते हैं`HtmlOptions` और एक कस्टम HTML फ़ॉर्मेटर का उपयोग करके सेट करें`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- अंत में, हम प्रेजेंटेशन को निर्दिष्ट विकल्पों के साथ HTML के रूप में सहेजते हैं।

## जावा स्लाइड्स में मूल फ़ॉन्ट्स को संरक्षित करने के साथ प्रेजेंटेशन को HTML में परिवर्तित करने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// डिफ़ॉल्ट प्रस्तुति फ़ॉन्ट को बाहर निकालें
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके मूल फ़ॉन्ट को संरक्षित करते हुए PowerPoint प्रेजेंटेशन को HTML में कैसे परिवर्तित किया जाए। यह तब उपयोगी होता है जब आप अपनी प्रस्तुतियों को वेब पर साझा करते समय उनकी दृश्य निष्ठा बनाए रखना चाहते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे डाउनलोड करूं?

आप Aspose वेबसाइट से Java के लिए Aspose.Slides डाउनलोड कर सकते हैं। मिलने जाना[यहाँ](https://downloads.aspose.com/slides/java/) नवीनतम संस्करण प्राप्त करने के लिए.

### क्या मैं बहिष्कृत फ़ॉन्ट की सूची को अनुकूलित कर सकता हूँ?

 हाँ, आप इसे अनुकूलित कर सकते हैं`fontNameExcludeList` आपकी आवश्यकताओं के अनुसार विशिष्ट फ़ॉन्ट को शामिल करने या बाहर करने के लिए सरणी।

### क्या यह विधि पीपीटी जैसे पुराने पावरपॉइंट प्रारूपों के लिए काम करती है?

यह कोड उदाहरण PPTX फ़ाइलों के लिए डिज़ाइन किया गया है। यदि आपको पुरानी पीपीटी फ़ाइलों को परिवर्तित करने की आवश्यकता है, तो आपको कोड में समायोजन करने की आवश्यकता हो सकती है।

### मैं HTML आउटपुट को और कैसे अनुकूलित कर सकता हूँ?

 आप अन्वेषण कर सकते हैं`HtmlOptions` HTML आउटपुट के विभिन्न पहलुओं, जैसे स्लाइड आकार, छवि गुणवत्ता और बहुत कुछ को अनुकूलित करने के लिए क्लास।