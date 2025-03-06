---
title: जावा स्लाइड्स में SVG इमेज ऑब्जेक्ट को आकृतियों के समूह में बदलें
linktitle: जावा स्लाइड्स में SVG इमेज ऑब्जेक्ट को आकृतियों के समूह में बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java Slides में SVG छवियों को आकृतियों के समूह में परिवर्तित करना सीखें। कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 13
url: /hi/java/image-handling/convert-svg-image-object-into-group-of-shapes-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## जावा स्लाइड्स में SVG इमेज ऑब्जेक्ट को आकृतियों के समूह में बदलने का परिचय

इस व्यापक गाइड में, हम यह पता लगाएंगे कि Aspose.Slides for Java API का उपयोग करके Java Slides में SVG इमेज ऑब्जेक्ट को आकृतियों के समूह में कैसे बदला जाए। यह शक्तिशाली लाइब्रेरी डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों में हेरफेर करने में सक्षम बनाती है, जिससे यह छवियों को संभालने सहित विभिन्न कार्यों के लिए एक मूल्यवान उपकरण बन जाता है।

## आवश्यक शर्तें

इससे पहले कि हम कोड और चरण-दर-चरण निर्देशों में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

अब जब हमने सब कुछ सेट कर लिया है, तो चलिए शुरू करते हैं।

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

आरंभ करने के लिए, आपको अपने जावा प्रोजेक्ट के लिए आवश्यक लाइब्रेरीज़ आयात करने की आवश्यकता है। Java के लिए Aspose.Slides को शामिल करना सुनिश्चित करें।

```java
import com.aspose.slides.*;
```

## चरण 2: प्रस्तुति लोड करें

 इसके बाद, आपको SVG इमेज ऑब्जेक्ट वाली पावरपॉइंट प्रेजेंटेशन लोड करनी होगी।`"Your Document Directory"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "image.pptx");
```

## चरण 3: SVG छवि पुनः प्राप्त करें

अब, आइए PowerPoint प्रेजेंटेशन से SVG इमेज ऑब्जेक्ट प्राप्त करें। हम मान लेंगे कि SVG इमेज पहली स्लाइड पर है और उस स्लाइड पर पहली आकृति है।

```java
try
{
    PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
```

## चरण 4: SVG छवि को आकृतियों के समूह में बदलें

SVG इमेज के साथ, अब हम इसे आकृतियों के समूह में बदल सकते हैं। यह स्लाइड में एक नया समूह आकार जोड़कर और स्रोत SVG इमेज को हटाकर प्राप्त किया जा सकता है।

```java
    if (svgImage != null)
    {
        // SVG छवि को आकृतियों के समूह में बदलें
        IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes()
                .addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                        pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());

        // प्रस्तुति से स्रोत SVG छवि हटाएँ
        pres.getSlides().get_Item(0).getShapes().remove(pFrame);
    }
```

## चरण 5: संशोधित प्रस्तुति को सहेजें

एक बार जब आप SVG छवि को आकृतियों के समूह में सफलतापूर्वक परिवर्तित कर लें, तो संशोधित प्रस्तुति को एक नई फ़ाइल में सहेजें।

```java
    pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
}
finally
{
    pres.dispose();
}
```

बधाई हो! अब आप सीख चुके हैं कि Aspose.Slides for Java API का उपयोग करके Java Slides में SVG छवि ऑब्जेक्ट को आकृतियों के समूह में कैसे परिवर्तित किया जाए।

## जावा स्लाइड्स में SVG इमेज ऑब्जेक्ट को आकृतियों के समूह में बदलने के लिए पूरा स्रोत कोड

```java
        // दस्तावेज़ निर्देशिका का पथ.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "image.pptx");
        try
        {
            PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
            if (svgImage != null)
            {
                // SVG छवि को आकृतियों के समूह में बदलें
                IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes().
                        addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                                pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());
                // प्रस्तुति से स्रोत SVG छवि हटाएँ
                pres.getSlides().get_Item(0).getShapes().remove(pFrame);
            }
            pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
        }
        finally
        {
            pres.dispose();
        }
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने जावा और Aspose.Slides for Java लाइब्रेरी का उपयोग करके PowerPoint प्रेजेंटेशन के भीतर SVG इमेज ऑब्जेक्ट को आकृतियों के समूह में बदलने की प्रक्रिया का पता लगाया। यह कार्यक्षमता गतिशील सामग्री के साथ आपकी प्रस्तुतियों को बढ़ाने के लिए कई संभावनाएँ खोलती है।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं Aspose.Slides का उपयोग करके अन्य छवि प्रारूपों को आकृतियों के समूह में परिवर्तित कर सकता हूँ?

हां, Aspose.Slides सिर्फ़ SVG ही नहीं, बल्कि कई इमेज फ़ॉर्मेट को सपोर्ट करता है। आप PNG, JPEG और दूसरे फ़ॉर्मेट को PowerPoint प्रेजेंटेशन में आकृतियों के समूह में बदल सकते हैं।

### क्या Aspose.Slides पावरपॉइंट प्रस्तुतियों को स्वचालित करने के लिए उपयुक्त है?

बिल्कुल! Aspose.Slides पावरपॉइंट प्रस्तुतियों को स्वचालित करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है, जिससे यह प्रोग्रामेटिक रूप से स्लाइड बनाने, संपादित करने और हेरफेर करने जैसे कार्यों के लिए एक मूल्यवान उपकरण बन जाता है।

### क्या Java के लिए Aspose.Slides का उपयोग करने के लिए कोई लाइसेंसिंग आवश्यकताएं हैं?

हां, Aspose.Slides को व्यावसायिक उपयोग के लिए वैध लाइसेंस की आवश्यकता होती है। आप Aspose वेबसाइट से लाइसेंस प्राप्त कर सकते हैं। हालाँकि, यह मूल्यांकन उद्देश्यों के लिए निःशुल्क परीक्षण प्रदान करता है।

### क्या मैं परिवर्तित आकृतियों के स्वरूप को अनुकूलित कर सकता हूँ?

ज़रूर! आप अपनी आवश्यकताओं के अनुसार परिवर्तित आकृतियों की उपस्थिति, आकार और स्थिति को अनुकूलित कर सकते हैं। Aspose.Slides आकार हेरफेर के लिए व्यापक API प्रदान करता है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
