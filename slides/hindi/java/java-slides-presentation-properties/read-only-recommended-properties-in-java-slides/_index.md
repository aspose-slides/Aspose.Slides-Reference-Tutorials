---
"description": "Aspose.Slides for Java का उपयोग करके Java PowerPoint प्रस्तुतियों में केवल पढ़ने के लिए अनुशंसित गुणों को सक्षम करने का तरीका जानें। बेहतर प्रस्तुति सुरक्षा के लिए स्रोत कोड उदाहरणों के साथ हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"linktitle": "जावा स्लाइड्स में केवल पढ़ने के लिए अनुशंसित गुण"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में केवल पढ़ने के लिए अनुशंसित गुण"
"url": "/hi/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में केवल पढ़ने के लिए अनुशंसित गुण


## जावा स्लाइड्स में केवल पढ़ने के लिए अनुशंसित गुण सक्षम करने का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों के लिए केवल पढ़ने के लिए अनुशंसित गुणों को सक्षम करने का तरीका जानेंगे। केवल पढ़ने के लिए अनुशंसित गुण तब उपयोगी हो सकते हैं जब आप उपयोगकर्ताओं को बिना कोई बदलाव किए प्रस्तुति देखने के लिए प्रोत्साहित करना चाहते हैं। ये गुण सुझाव देते हैं कि प्रस्तुति को केवल पढ़ने के लिए मोड में खोला जाना चाहिए। हम आपको इसे प्राप्त करने के लिए जावा स्रोत कोड के साथ एक चरण-दर-चरण मार्गदर्शिका प्रदान करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी सेट अप है। आप इसे यहाँ से डाउनलोड कर सकते हैं [Aspose.Slides for Java वेबसाइट](https://products.aspose.com/slides/java/).

## चरण 1: एक नया पावरपॉइंट प्रेजेंटेशन बनाएं

हम Aspose.Slides for Java का उपयोग करके एक नया PowerPoint प्रेजेंटेशन बनाकर शुरू करेंगे। यदि आपके पास पहले से ही एक प्रेजेंटेशन है, तो आप इस चरण को छोड़ सकते हैं।

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

उपरोक्त कोड में, हमने आउटपुट पावरपॉइंट फ़ाइल के लिए पथ परिभाषित किया है और एक नया प्रेजेंटेशन ऑब्जेक्ट बनाया है।

## चरण 2: केवल पढ़ने के लिए अनुशंसित संपत्ति सक्षम करें

अब, आइए प्रस्तुति के लिए केवल-पढ़ने के लिए अनुशंसित गुण को सक्षम करें।

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

इस कोड स्निपेट में, हम उपयोग करते हैं `getProtectionManager().setReadOnlyRecommended(true)` केवल पढ़ने के लिए अनुशंसित गुण को सेट करने की विधि `true`इससे यह सुनिश्चित होता है कि जब कोई व्यक्ति प्रस्तुति खोलेगा, तो उसे इसे केवल पढ़ने के लिए मोड में खोलने के लिए कहा जाएगा।

## चरण 3: प्रस्तुति सहेजें

अंत में, हम प्रस्तुति को केवल-पढ़ने के लिए अनुशंसित गुण को सक्षम करके सहेजते हैं।

## जावा स्लाइड्स में केवल पढ़ने के लिए अनुशंसित गुणों के लिए पूर्ण स्रोत कोड

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन के लिए Read-Only Recommended प्रॉपर्टी को कैसे सक्षम किया जाए। यह सुविधा तब मददगार हो सकती है जब आप संपादन को प्रतिबंधित करना चाहते हैं और दर्शकों को प्रेजेंटेशन को केवल पढ़ने के लिए मोड में उपयोग करने के लिए प्रोत्साहित करना चाहते हैं। आप प्रेजेंटेशन के लिए पासवर्ड सेट करके सुरक्षा को और बढ़ा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं केवल पढ़ने के लिए अनुशंसित गुण को कैसे अक्षम करूँ?

केवल पढ़ने के लिए अनुशंसित गुण को अक्षम करने के लिए, बस निम्नलिखित कोड का उपयोग करें:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### क्या मैं केवल पढ़ने के लिए अनुशंसित प्रस्तुति के लिए पासवर्ड सेट कर सकता हूँ?

हां, आप Aspose.Slides for Java का उपयोग करके Read-Only Recommended प्रेजेंटेशन के लिए पासवर्ड सेट कर सकते हैं। `setPassword` प्रेजेंटेशन के लिए पासवर्ड सेट करने की विधि। यदि पासवर्ड सेट किया गया है, तो प्रेजेंटेशन खोलने के लिए उपयोगकर्ताओं को इसे दर्ज करना होगा, यहां तक कि केवल पढ़ने के लिए मोड में भी।

```java
pres.getProtectionManager().setPassword("YourPassword");
```

प्रतिस्थापित करना याद रखें `"YourPassword"` अपने इच्छित पासवर्ड के साथ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}