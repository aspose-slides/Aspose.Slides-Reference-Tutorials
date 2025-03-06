---
title: स्लाइड में आकृति खोजें
linktitle: स्लाइड में आकृति खोजें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ PowerPoint स्लाइड में आसानी से आकृतियाँ ढूँढ़ें। सहज कोडिंग अनुभव के लिए हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 14
url: /hi/java/java-powerpoint-shape-formatting-geometry/find-shape-slide-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
क्या आप पावरपॉइंट स्लाइड्स में से खास आकृतियाँ ढूँढ़ने के लिए इधर-उधर भटकते-भटकते थक गए हैं? कल्पना करें कि आप कोड की कुछ ही पंक्तियों के साथ इस प्रक्रिया को आसानी से स्वचालित कर पाएँ। अपनी प्रेजेंटेशन फ़ाइलों में आकृतियाँ ढूँढ़ने के लिए Aspose.Slides for Java का उपयोग करने के बारे में हमारी विस्तृत गाइड में आपका स्वागत है। इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके स्लाइड में आकृतियाँ ढूँढ़ने के लिए आवश्यक चरणों को विभाजित करेंगे, जिसमें आपके परिवेश को सेट करने से लेकर कोड चलाने तक शामिल है।
## आवश्यक शर्तें
इससे पहले कि हम कोड में उतरें, आइए सुनिश्चित करें कि आपके पास वह सब कुछ है जो आपको चाहिए:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपकी मशीन पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: लाइब्रेरी को यहां से डाउनलोड करें[एस्पोज रिलीज](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (आईडीई): इंटेलीज आईडिया या एक्लिप्स जैसे आईडीई से कोडिंग आसान हो जाएगी।
4. पावरपॉइंट फ़ाइल: एक .pptx फ़ाइल जहाँ आप आकृति ढूँढना चाहते हैं।
## पैकेज आयात करें
सबसे पहले, आपको अपने जावा प्रोजेक्ट में आवश्यक Aspose.Slides पैकेज आयात करने होंगे। सुनिश्चित करें कि Aspose.Slides for Java आपके प्रोजेक्ट निर्भरताओं में जोड़ा गया है।
```java
import com.aspose.slides.IShape;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;

import java.io.File;
```
## चरण 1: प्रोजेक्ट निर्देशिका बनाएँ
आपको अपनी प्रोजेक्ट फ़ाइलों को संग्रहीत करने के लिए एक निर्देशिका की आवश्यकता है। यह कदम आपके प्रोजेक्ट को व्यवस्थित रखने के लिए महत्वपूर्ण है।
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## चरण 2: प्रेजेंटेशन फ़ाइल लोड करें
यहां, आप प्रेजेंटेशन क्लास को इंस्टैंसिएट करेंगे जो आपकी पावरपॉइंट फ़ाइल का प्रतिनिधित्व करता है।
```java
Presentation p = new Presentation(dataDir + "FindingShapeInSlide.pptx");
```
## चरण 3: स्लाइड पुनः प्राप्त करें
प्रेजेंटेशन से पहली स्लाइड प्राप्त करें। यह वह जगह है जहाँ आप आकृति की खोज करेंगे।
```java
ISlide slide = p.getSlides().get_Item(0);
```
## चरण 4: आकृति का वैकल्पिक पाठ परिभाषित करें
पावरपॉइंट में आकृतियों में वैकल्पिक टेक्स्ट हो सकता है। आप जिस आकृति को ढूँढना चाहते हैं उसे पहचानने के लिए आप इस टेक्स्ट का इस्तेमाल कर सकते हैं।
```java
String altText = "Shape1";
```
## चरण 5: आकृति खोज विधि को क्रियान्वित करें
स्लाइड में आकृतियों के माध्यम से पुनरावृत्ति करने और निर्दिष्ट वैकल्पिक पाठ वाली आकृति को खोजने के लिए एक विधि बनाएं।
```java
public static IShape findShape(ISlide slide, String alttext) {
    for (int i = 0; i < slide.getShapes().size(); i++) {
        if (slide.getShapes().get_Item(i).getAlternativeText().compareTo(alttext) == 0)
            return slide.getShapes().get_Item(i);
    }
    return null;
}
```
## चरण 6: आकृति खोज तर्क को क्रियान्वित करें
आकृति ढूंढने के लिए आपके द्वारा बनाई गई विधि को कॉल करें और यदि मिल जाए तो उसका नाम प्रिंट करें।
```java
IShape shape = findShape(slide, altText);
if (shape != null) {
    System.out.println("Shape Name: " + shape.getName());
}
```
## चरण 7: प्रेजेंटेशन ऑब्जेक्ट को हटाएँ
अंत में, सुनिश्चित करें कि आप संसाधनों को मुक्त करने के लिए प्रेजेंटेशन ऑब्जेक्ट को हटा दें।
```java
if (p != null) p.dispose();
```
## निष्कर्ष
और अब यह हो गया! अब आप सीख चुके हैं कि Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में आकृति कैसे ढूँढ़ी जाती है। इन चरणों का पालन करके, आप प्रस्तुतियों में आकृतियों को ढूँढ़ने के थकाऊ काम को स्वचालित कर सकते हैं, जिससे आपका समय और प्रयास बचेगा।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और हेरफेर करने की अनुमति देती है।
### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?
 इसे यहाँ से डाउनलोड करें[Aspose रिलीज़ पेज](https://releases.aspose.com/slides/java/) और इसे अपनी परियोजना की निर्भरताओं में शामिल करें.
### क्या मैं Aspose.Slides को अन्य फ़ाइल स्वरूपों के साथ उपयोग कर सकता हूँ?
हां, Aspose.Slides .ppt, .pptx, .odp, आदि सहित विभिन्न फ़ाइल स्वरूपों का समर्थन करता है।
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण प्राप्त कर सकते हैं[Aspose का निःशुल्क परीक्षण पृष्ठ](https://releases.aspose.com/).
### मुझे Aspose.Slides के लिए समर्थन कहां मिल सकता है?
 आप यहां पर सहायता पा सकते हैं[Aspose स्लाइड्स फ़ोरम](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
