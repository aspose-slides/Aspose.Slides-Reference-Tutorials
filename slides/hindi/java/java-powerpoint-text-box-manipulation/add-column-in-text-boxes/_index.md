---
title: Java के लिए Aspose.Slides के साथ टेक्स्ट बॉक्स में कॉलम जोड़ें
linktitle: Java के लिए Aspose.Slides के साथ टेक्स्ट बॉक्स में कॉलम जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Java के लिए Aspose.Slides का उपयोग करके PowerPoint में टेक्स्ट बॉक्स में कॉलम कैसे जोड़ें। इस चरण-दर-चरण मार्गदर्शिका के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।
weight: 10
url: /hi/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java के लिए Aspose.Slides के साथ टेक्स्ट बॉक्स में कॉलम जोड़ें

## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके कॉलम जोड़कर टेक्स्ट बॉक्स को बेहतर बनाने का तरीका जानेंगे। Aspose.Slides एक शक्तिशाली जावा लाइब्रेरी है जो डेवलपर्स को Microsoft Office की आवश्यकता के बिना प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। टेक्स्ट बॉक्स में कॉलम जोड़ने से स्लाइड के भीतर सामग्री की पठनीयता और संगठन में काफी सुधार हो सकता है, जिससे आपकी प्रस्तुतियाँ अधिक आकर्षक और पेशेवर बन सकती हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपकी मशीन पर JDK (जावा डेवलपमेंट किट) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
आरंभ करने के लिए, आपको अपनी जावा फ़ाइल में आवश्यक Aspose.Slides क्लासेस आयात करने की आवश्यकता है। आप इसे इस प्रकार कर सकते हैं:
```java
import com.aspose.slides.*;
```
## चरण 1: प्रस्तुति और स्लाइड आरंभ करें
सबसे पहले, एक नया पावरपॉइंट प्रेजेंटेशन बनाएं और पहली स्लाइड को आरंभ करें।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // प्रस्तुति की पहली स्लाइड प्राप्त करें
    ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 2: ऑटोशेप (आयताकार) जोड़ें
इसके बाद, स्लाइड में Rectangle प्रकार का एक AutoShape जोड़ें।
```java
    // आयत प्रकार का एक ऑटोशेप जोड़ें
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## चरण 3: आयत में टेक्स्टफ़्रेम जोड़ें
अब, Rectangle AutoShape में एक TextFrame जोड़ें और उसका प्रारंभिक टेक्स्ट सेट करें।
```java
    // आयत में टेक्स्टफ़्रेम जोड़ें
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## चरण 4: कॉलम की संख्या निर्धारित करें
टेक्स्टफ्रेम के भीतर स्तंभों की संख्या निर्दिष्ट करें.
```java
    // TextFrame का पाठ प्रारूप प्राप्त करें
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // टेक्स्टफ़्रेम में स्तंभों की संख्या निर्दिष्ट करें
    format.setColumnCount(3);
```
## चरण 5: कॉलम स्पेसिंग समायोजित करें
टेक्स्टफ्रेम में कॉलमों के बीच अंतर निर्धारित करें।
```java
    // स्तंभों के बीच रिक्ति निर्दिष्ट करें
    format.setColumnSpacing(10);
```
## चरण 6: प्रेजेंटेशन सहेजें
अंत में, संशोधित प्रस्तुति को पावरपॉइंट फ़ाइल में सहेजें।
```java
    // निर्मित प्रस्तुति सहेजें
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष
इन चरणों का पालन करके, आप आसानी से Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में टेक्स्ट बॉक्स में कॉलम जोड़ सकते हैं। यह सुविधा आपको अपनी स्लाइड्स की संरचना और पठनीयता को बढ़ाने की अनुमति देती है, जिससे वे अधिक आकर्षक और पेशेवर बन जाती हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं किसी टेक्स्ट बॉक्स में तीन से अधिक कॉलम जोड़ सकता हूँ?
हां, आप Aspose.Slides का उपयोग करके प्रोग्रामेटिक रूप से किसी भी संख्या में कॉलम निर्दिष्ट कर सकते हैं।
### क्या Aspose.Slides Java 11 के साथ संगत है?
हां, Aspose.Slides Java 11 और उच्चतर संस्करणों का समर्थन करता है।
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या Aspose.Slides को Microsoft Office स्थापित करने की आवश्यकता है?
नहीं, Aspose.Slides को मशीन पर Microsoft Office स्थापित करने की आवश्यकता नहीं है।
### मैं Aspose.Slides for Java के बारे में अधिक दस्तावेज़ कहां पा सकता हूं?
 विस्तृत दस्तावेज उपलब्ध है[यहाँ](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
