---
title: जावा के साथ PowerPoint में बाहरी छाया लागू करें
linktitle: जावा के साथ PowerPoint में बाहरी छाया लागू करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ Java का उपयोग करके PowerPoint में बाहरी छाया प्रभाव लागू करना सीखें। अपनी प्रस्तुतियों को गहराई और दृश्य अपील के साथ बेहतर बनाएँ।
weight: 13
url: /hi/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा के साथ PowerPoint में बाहरी छाया लागू करें

## परिचय
दिखने में आकर्षक पावरपॉइंट प्रेजेंटेशन बनाने में अक्सर आकृतियों और टेक्स्ट में कई तरह के इफ़ेक्ट जोड़ने पड़ते हैं। ऐसा ही एक इफ़ेक्ट है बाहरी छाया, जो तत्वों को अलग दिखा सकता है और आपकी स्लाइड्स में गहराई जोड़ सकता है। इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Slides के साथ Java का उपयोग करके PowerPoint में किसी आकृति पर बाहरी छाया इफ़ेक्ट कैसे लागू करें।
## आवश्यक शर्तें

इस ट्यूटोरियल को शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर जावा इंस्टॉल है। आप Oracle वेबसाइट से JDK का नवीनतम संस्करण डाउनलोड और इंस्टॉल कर सकते हैं।

2.  Aspose.Slides for Java: Aspose.Slides for Java को डाउनलोड करें और इंस्टॉल करें[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).

3. एकीकृत विकास वातावरण (IDE): कोडिंग और जावा अनुप्रयोगों को चलाने के लिए अपना पसंदीदा जावा IDE जैसे कि इक्लिप्स, इंटेलीज आईडिया, या नेटबीन्स चुनें।

4. बुनियादी जावा ज्ञान: जावा प्रोग्रामिंग भाषा के मूल सिद्धांतों और ऑब्जेक्ट-ओरिएंटेड अवधारणाओं से परिचित होना कोड उदाहरणों को समझने के लिए फायदेमंद होगा।

## पैकेज आयात करें

सबसे पहले, अपने जावा प्रोजेक्ट में Aspose.Slides और संबंधित कार्यात्मकताओं के साथ काम करने के लिए आवश्यक पैकेज आयात करें:

```java
import com.aspose.slides.*;
```

अब आइए Aspose.Slides के साथ Java का उपयोग करके PowerPoint में किसी आकृति पर बाहरी छाया प्रभाव लागू करने के लिए उदाहरण कोड को कई चरणों में विभाजित करें:

## चरण 1: अपना प्रोजेक्ट वातावरण सेट करें

अपने पसंदीदा IDE में एक नया Java प्रोजेक्ट बनाएं और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides for Java लाइब्रेरी जोड़ें।

## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें

 इसका एक उदाहरण बनाएं`Presentation` क्लास, जो एक पावरपॉइंट प्रेजेंटेशन फ़ाइल का प्रतिनिधित्व करता है.

```java
Presentation presentation = new Presentation();
```

## चरण 3: स्लाइड और आकृति जोड़ें

उस स्लाइड का संदर्भ प्राप्त करें जहां आप आकृति जोड़ना चाहते हैं, और फिर स्लाइड में एक ऑटोशेप (जैसे, आयत) जोड़ें।

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## चरण 4: आकृति को अनुकूलित करें

आकृति का भरण प्रकार 'NoFill' पर सेट करें और आकृति में पाठ जोड़ें।

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## चरण 5: पाठ को अनुकूलित करें

आकृति के पाठ गुणों तक पहुँचें और फ़ॉन्ट आकार को अनुकूलित करें.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## चरण 6: बाहरी छाया प्रभाव सक्षम करें

पाठ भाग के लिए बाहरी छाया प्रभाव सक्षम करें.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## चरण 7: छाया पैरामीटर सेट करें

बाहरी छाया प्रभाव के लिए पैरामीटर परिभाषित करें, जैसे धुंधलापन त्रिज्या, दिशा, दूरी और छाया रंग।

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## चरण 8: प्रस्तुति सहेजें

आकृति पर लागू बाहरी छाया प्रभाव के साथ संशोधित प्रस्तुति को सहेजें।

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

बधाई हो! आपने Aspose.Slides के साथ Java का उपयोग करके PowerPoint में किसी आकृति पर बाहरी छाया प्रभाव सफलतापूर्वक लागू किया है। अपनी प्रस्तुतियों में वांछित दृश्य प्रभाव प्राप्त करने के लिए विभिन्न मापदंडों के साथ प्रयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

### क्या मैं बाहरी छाया प्रभाव को आयतों के अलावा अन्य आकृतियों पर भी लागू कर सकता हूँ?
हां, आप बाहरी छाया प्रभाव को Aspose.Slides द्वारा समर्थित विभिन्न आकृतियों पर लागू कर सकते हैं, जैसे वृत्त, त्रिकोण और कस्टम आकार।

### क्या छाया का रंग और तीव्रता को अनुकूलित करना संभव है?
बिल्कुल! आपके पास छाया मापदंडों पर पूरा नियंत्रण है, जिसमें रंग, धुंधलापन त्रिज्या, दिशा और दूरी शामिल है।

### क्या मैं एक ही आकृति पर एकाधिक प्रभाव लागू कर सकता हूँ?
हां, आप अपनी प्रस्तुतियों में आकृतियों और पाठ के दृश्य आकर्षण को बढ़ाने के लिए बाहरी छाया, आंतरिक छाया, चमक और प्रतिबिंब जैसे कई प्रभावों को संयोजित कर सकते हैं।

### क्या Aspose.Slides पाठ तत्वों पर प्रभाव लागू करने का समर्थन करता है?
हां, आप न केवल आकृतियों पर बल्कि आकृतियों के भीतर अलग-अलग पाठ भागों पर भी प्रभाव लागू कर सकते हैं, जिससे आपको अपनी स्लाइडों को डिजाइन करने में व्यापक लचीलापन मिलता है।

### मैं Aspose.Slides के लिए अधिक संसाधन और समर्थन कहां पा सकता हूं?
 आप इसका संदर्भ ले सकते हैं[प्रलेखन](https://reference.aspose.com/slides/java/) विस्तृत API संदर्भों के लिए और अन्वेषण करें[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सामुदायिक समर्थन और चर्चा के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
