---
title: जावा पावरपॉइंट में फ़ॉन्ट फ़ॉलबैक सेट करें
linktitle: जावा पावरपॉइंट में फ़ॉन्ट फ़ॉलबैक सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: सुसंगत पाठ प्रदर्शन सुनिश्चित करने के लिए Aspose.Slides for Java का उपयोग करके Java PowerPoint में फ़ॉन्ट फ़ॉलबैक सेट करना सीखें।
weight: 16
url: /hi/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके Java PowerPoint प्रस्तुतियों में फ़ॉन्ट फ़ॉलबैक सेट करने की पेचीदगियों पर चर्चा करेंगे। फ़ॉन्ट फ़ॉलबैक यह सुनिश्चित करने के लिए महत्वपूर्ण हैं कि आपके प्रस्तुतियों में पाठ विभिन्न डिवाइस और ऑपरेटिंग सिस्टम पर सही ढंग से प्रदर्शित हो, तब भी जब आवश्यक फ़ॉन्ट उपलब्ध न हों।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- जावा प्रोग्रामिंग भाषा की बुनियादी समझ।
- एकीकृत विकास वातावरण (आईडीई) जैसे कि इंटेलीज आईडिया या एक्लिप्स।

## पैकेज आयात करें
सबसे पहले, अपने जावा क्लास में आवश्यक Aspose.Slides for Java पैकेज शामिल करें:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## चरण 1: फ़ॉन्ट फ़ॉलबैक नियम आरंभ करें
फ़ॉन्ट फ़ॉलबैक सेट करने के लिए, आपको ऐसे नियम परिभाषित करने होंगे जो यूनिकोड रेंज और संबंधित फ़ॉलबैक फ़ॉन्ट निर्दिष्ट करते हों। यहाँ बताया गया है कि आप इन नियमों को कैसे आरंभ कर सकते हैं:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## चरण 2: फ़ॉन्ट फ़ॉलबैक नियम लागू करें
इसके बाद, आप इन नियमों को उस प्रस्तुति या स्लाइड पर लागू करते हैं जहाँ फ़ॉन्ट फ़ॉलबैक सेट करने की आवश्यकता होती है। नीचे PowerPoint प्रस्तुति में स्लाइड पर इन नियमों को लागू करने का एक उदाहरण दिया गया है:
```java
// मान लें कि स्लाइड आपकी स्लाइड ऑब्जेक्ट है
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## निष्कर्ष
Aspose.Slides for Java का उपयोग करके Java PowerPoint प्रस्तुतियों में फ़ॉन्ट फ़ॉलबैक सेट करना विभिन्न वातावरणों में सुसंगत टेक्स्ट डिस्प्ले सुनिश्चित करने के लिए आवश्यक है। इस ट्यूटोरियल में दिखाए गए अनुसार फ़ॉलबैक नियमों को परिभाषित करके, आप उन स्थितियों को संभाल सकते हैं जहाँ विशिष्ट फ़ॉन्ट अनुपलब्ध हैं, जिससे आपकी प्रस्तुतियों की अखंडता बनी रहती है।

## अक्सर पूछे जाने वाले प्रश्न
### पावरपॉइंट प्रस्तुतियों में फ़ॉन्ट फ़ॉलबैक क्या हैं?
फ़ॉन्ट फ़ॉलबैक यह सुनिश्चित करता है कि उपलब्ध फ़ॉन्ट्स को उन फ़ॉन्ट्स के साथ प्रतिस्थापित करके पाठ सही ढंग से प्रदर्शित हो।
### मैं Java के लिए Aspose.Slides कैसे डाउनलोड कर सकता हूँ?
 आप Java के लिए Aspose.Slides को यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
### क्या Aspose.Slides for Java सभी Java IDE के साथ संगत है?
हां, Aspose.Slides for Java लोकप्रिय Java IDEs जैसे IntelliJ IDEA और Eclipse के साथ संगत है।
### क्या मुझे Aspose उत्पादों के लिए अस्थायी लाइसेंस मिल सकता है?
हां, Aspose उत्पादों के लिए अस्थायी लाइसेंस यहां से प्राप्त किए जा सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides for Java के लिए समर्थन कहां पा सकता हूं?
 Aspose.Slides for Java से संबंधित सहायता के लिए, यहां जाएं[एस्पोज फोरम](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
