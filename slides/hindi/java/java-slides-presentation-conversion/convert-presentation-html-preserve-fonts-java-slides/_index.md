---
title: जावा स्लाइड्स में मूल फ़ॉन्ट को संरक्षित रखते हुए प्रेजेंटेशन को HTML में परिवर्तित करना
linktitle: जावा स्लाइड्स में मूल फ़ॉन्ट को संरक्षित रखते हुए प्रेजेंटेशन को HTML में परिवर्तित करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Java के लिए Aspose.Slides का उपयोग करके मूल फ़ॉन्ट को संरक्षित करते हुए PowerPoint प्रस्तुतियों को HTML में परिवर्तित करें।
weight: 14
url: /hi/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में मूल फ़ॉन्ट को संरक्षित रखते हुए प्रेजेंटेशन को HTML में परिवर्तित करने का परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके मूल फ़ॉन्ट को संरक्षित करते हुए PowerPoint प्रेजेंटेशन (PPTX) को HTML में कैसे परिवर्तित किया जाए। इससे यह सुनिश्चित होगा कि परिणामी HTML मूल प्रेजेंटेशन के स्वरूप से काफ़ी मिलता-जुलता हो।

## चरण 1: प्रोजेक्ट की स्थापना
इससे पहले कि हम कोड में उतरें, आइए सुनिश्चित करें कि आपके पास आवश्यक सेटअप मौजूद है:

1. Aspose.Slides for Java डाउनलोड करें: यदि आपने पहले से ऐसा नहीं किया है, तो अपने प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी को डाउनलोड करें और शामिल करें।

2. एक जावा प्रोजेक्ट बनाएं: अपने पसंदीदा IDE में एक जावा प्रोजेक्ट सेट करें, और सुनिश्चित करें कि आपके पास एक "lib" फ़ोल्डर है जहां आप Aspose.Slides JAR फ़ाइल रख सकते हैं।

3. आवश्यक कक्षाएं आयात करें: अपनी जावा फ़ाइल के आरंभ में आवश्यक कक्षाएं आयात करें:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## चरण 2: मूल फ़ॉन्ट के साथ प्रस्तुति को HTML में परिवर्तित करना

अब, आइए मूल फ़ॉन्ट को संरक्षित रखते हुए पावरपॉइंट प्रस्तुति को HTML में परिवर्तित करें:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// प्रस्तुति लोड करें
Presentation pres = new Presentation("input.pptx");

try {
    // कैलिब्री और एरियल जैसे डिफ़ॉल्ट प्रेजेंटेशन फ़ॉन्ट को बाहर रखें
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // HTML विकल्प बनाएं और कस्टम HTML फ़ॉर्मेटर सेट करें
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // प्रस्तुति को HTML के रूप में सहेजें
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // प्रस्तुति ऑब्जेक्ट का निपटान करें
    if (pres != null) pres.dispose();
}
```

इस कोड स्निपेट में:

-  हम इनपुट पावरपॉइंट प्रेजेंटेशन को लोड करते हैं`Presentation`.

- हम फ़ॉन्ट्स की एक सूची परिभाषित करते हैं (`fontNameExcludeList`जिन्हें हम HTML में एम्बेड करने से बाहर रखना चाहते हैं। यह फ़ाइल आकार को कम करने के लिए कैलिब्री और एरियल जैसे सामान्य फ़ॉन्ट को बाहर रखने के लिए उपयोगी है।

-  हम इसका एक उदाहरण बनाते हैं`EmbedAllFontsHtmlController` और फ़ॉन्ट बहिष्करण सूची को इसमें पास करें.

-  हम बनाते हैं`HtmlOptions` और एक कस्टम HTML फ़ॉर्मेटर का उपयोग करके सेट करें`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- अंत में, हम निर्दिष्ट विकल्पों के साथ प्रस्तुति को HTML के रूप में सहेजते हैं।

## जावा स्लाइड्स में मूल फ़ॉन्ट को संरक्षित करते हुए प्रेजेंटेशन को HTML में परिवर्तित करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// डिफ़ॉल्ट प्रस्तुति फ़ॉन्ट को बाहर करें
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

इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Slides for Java का उपयोग करके मूल फ़ॉन्ट को संरक्षित करते हुए PowerPoint प्रेजेंटेशन को HTML में कैसे परिवर्तित किया जाए। यह तब उपयोगी होता है जब आप वेब पर उन्हें साझा करते समय अपनी प्रस्तुतियों की दृश्य निष्ठा बनाए रखना चाहते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides कैसे डाउनलोड करूं?

 आप Aspose.Slides for Java को Aspose वेबसाइट से डाउनलोड कर सकते हैं।[यहाँ](https://downloads.aspose.com/slides/java/) नवीनतम संस्करण प्राप्त करने के लिए.

### क्या मैं बहिष्कृत फ़ॉन्ट्स की सूची को अनुकूलित कर सकता हूँ?

 हां, आप इसे अनुकूलित कर सकते हैं`fontNameExcludeList` अपनी आवश्यकताओं के अनुसार विशिष्ट फ़ॉन्ट को शामिल या बाहर करने के लिए सरणी।

### क्या यह विधि PPT जैसे पुराने पावरपॉइंट प्रारूपों के लिए काम करती है?

यह कोड उदाहरण PPTX फ़ाइलों के लिए डिज़ाइन किया गया है। यदि आपको पुरानी PPT फ़ाइलों को कनवर्ट करने की आवश्यकता है, तो आपको कोड में समायोजन करने की आवश्यकता हो सकती है।

### मैं HTML आउटपुट को और अधिक अनुकूलित कैसे कर सकता हूं?

 आप अन्वेषण कर सकते हैं`HtmlOptions` HTML आउटपुट के विभिन्न पहलुओं को अनुकूलित करने के लिए क्लास का उपयोग करें, जैसे स्लाइड का आकार, छवि गुणवत्ता, आदि।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
