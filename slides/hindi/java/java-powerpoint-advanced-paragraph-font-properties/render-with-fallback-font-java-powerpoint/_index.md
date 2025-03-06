---
title: जावा पावरपॉइंट में फ़ॉलबैक फ़ॉन्ट के साथ रेंडर करें
linktitle: जावा पावरपॉइंट में फ़ॉलबैक फ़ॉन्ट के साथ रेंडर करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में फ़ॉलबैक फ़ॉन्ट के साथ टेक्स्ट रेंडर करना सीखें। निर्बाध कार्यान्वयन के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 13
url: /hi/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पावरपॉइंट में फ़ॉलबैक फ़ॉन्ट के साथ रेंडर करें

## परिचय
जावा में पावरपॉइंट प्रेजेंटेशन बनाना और उसमें हेरफेर करना चुनौतीपूर्ण हो सकता है, लेकिन Aspose.Slides के साथ, आप इसे कुशलतापूर्वक कर सकते हैं। एक महत्वपूर्ण विशेषता फ़ॉलबैक फ़ॉन्ट के साथ टेक्स्ट रेंडर करने की क्षमता है। यह लेख जावा के लिए Aspose.Slides का उपयोग करके अपने पावरपॉइंट स्लाइड में फ़ॉलबैक फ़ॉन्ट को लागू करने के तरीके पर एक विस्तृत, चरण-दर-चरण मार्गदर्शिका प्रदान करता है।
## आवश्यक शर्तें
कार्यान्वयन में उतरने से पहले, आइए सुनिश्चित करें कि आपके पास वह सब कुछ है जो आपको चाहिए:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है।
2.  Aspose.Slides for Java: आप इसे यहाँ से डाउनलोड कर सकते हैं[Aspose.Slides for Java डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (आईडीई): इंटेलीज आईडीईए या एक्लिप्स जैसा आईडीई आपकी विकास प्रक्रिया को अधिक सुचारू बना देगा।
4. निर्भरताएँ: अपने प्रोजेक्ट की निर्भरताओं में Aspose.Slides को शामिल करें।
## पैकेज आयात करें
सबसे पहले, हमें अपने जावा प्रोग्राम में आवश्यक पैकेजों को आयात करना होगा।
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
आइये इस प्रक्रिया को प्रबंधनीय चरणों में विभाजित करें।
## चरण 1: अपना प्रोजेक्ट सेट करें
 कोई भी कोड लिखने से पहले, सुनिश्चित करें कि आपका प्रोजेक्ट सही तरीके से सेट अप किया गया है। इसमें आपके प्रोजेक्ट में Aspose.Slides लाइब्रेरी जोड़ना शामिल है। आप लाइब्रेरी को यहाँ से डाउनलोड करके ऐसा कर सकते हैं[जावा के लिए Aspose.Slides](https://releases.aspose.com/slides/java/) और इसे अपने निर्माण पथ में जोड़ें।
## चरण 2: फ़ॉन्ट फ़ॉलबैक नियम आरंभ करें
 आपको इसका एक उदाहरण बनाने की आवश्यकता है`IFontFallBackRulesCollection` क्लास में जाकर उसमें नियम जोड़ें। ये नियम विशिष्ट यूनिकोड श्रेणियों के लिए फ़ॉन्ट फ़ॉलबैक को परिभाषित करते हैं।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// नियम संग्रह का नया उदाहरण बनाएँ
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// कई नियम बनाएं
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## चरण 3: फ़ॉलबैक नियमों को संशोधित करें
इस चरण में, हम मौजूदा फ़ॉलबैक फ़ॉन्ट्स को हटाकर और विशिष्ट यूनिकोड श्रेणियों के लिए नियमों को अद्यतन करके फ़ॉलबैक नियमों को संशोधित करेंगे।
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // लोड किए गए नियमों से फ़ॉलबैक फ़ॉन्ट "ताहोमा" को हटाने का प्रयास किया जा रहा है
    fallBackRule.remove("Tahoma");
    // निर्दिष्ट श्रेणी के लिए नियम अपडेट करें
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//सूची से कोई भी मौजूदा नियम हटाएँ
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## चरण 4: प्रस्तुति लोड करें
वह पावरपॉइंट प्रस्तुति लोड करें जिसे आप संशोधित करना चाहते हैं।
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## चरण 5: प्रेजेंटेशन को फ़ॉलबैक नियम असाइन करें
तैयार फ़ॉलबैक नियमों को प्रस्तुति के फ़ॉन्ट प्रबंधक को असाइन करें.
```java
try {
    // उपयोग के लिए तैयार नियम सूची को निर्दिष्ट करना
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // आरंभीकृत नियम संग्रह का उपयोग करके थंबनेल प्रस्तुत करना और उसे PNG में सहेजना
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## चरण 6: सहेजें और परीक्षण करें
अंत में, अपना काम सहेजें और कार्यान्वयन का परीक्षण करें ताकि यह सुनिश्चित हो सके कि सब कुछ अपेक्षित रूप से काम करता है। यदि आपको कोई समस्या आती है, तो अपने सेटअप को दोबारा जांचें और सुनिश्चित करें कि सभी निर्भरताएँ सही ढंग से जोड़ी गई हैं।
## निष्कर्ष
इस गाइड का पालन करके, आप Aspose.Slides for Java का उपयोग करके अपने PowerPoint प्रस्तुतियों में फ़ॉलबैक फ़ॉन्ट के साथ कुशलतापूर्वक टेक्स्ट रेंडर कर सकते हैं। यह प्रक्रिया सुनिश्चित करती है कि आपकी प्रस्तुतियाँ सुसंगत स्वरूपण बनाए रखें, भले ही प्राथमिक फ़ॉन्ट अनुपलब्ध हों। हैप्पी कोडिंग!
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक लाइब्रेरी है जो डेवलपर्स को जावा अनुप्रयोगों में पावरपॉइंट प्रस्तुतियाँ बनाने, संशोधित करने और प्रस्तुत करने की अनुमति देती है।
### मैं अपने प्रोजेक्ट में Aspose.Slides कैसे जोड़ूं?
 आप लाइब्रेरी को यहां से डाउनलोड कर सकते हैं[Aspose.Slides डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/) और इसे अपने प्रोजेक्ट के निर्माण पथ में जोड़ें.
### फ़ॉलबैक फ़ॉन्ट क्या हैं?
फ़ॉलबैक फ़ॉन्ट वैकल्पिक फ़ॉन्ट होते हैं जिनका उपयोग तब किया जाता है जब निर्दिष्ट फ़ॉन्ट उपलब्ध नहीं होता है या कुछ वर्णों का समर्थन नहीं करता है।
### क्या मैं एकाधिक फ़ॉलबैक नियमों का उपयोग कर सकता हूँ?
हां, आप विभिन्न यूनिकोड श्रेणियों और फ़ॉन्टों को संभालने के लिए अनेक फ़ॉलबैक नियम जोड़ सकते हैं।
### मुझे Aspose.Slides के लिए समर्थन कहां मिल सकता है?
 आप यहाँ से सहायता प्राप्त कर सकते हैं[Aspose.Slides समर्थन मंच](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
