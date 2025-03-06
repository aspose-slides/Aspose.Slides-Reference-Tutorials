---
title: जावा के साथ पावरपॉइंट में टेबल पंक्ति के अंदर टेक्स्ट को फॉर्मेट करें
linktitle: जावा के साथ पावरपॉइंट में टेबल पंक्ति के अंदर टेक्स्ट को फॉर्मेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint में टेबल पंक्तियों के अंदर टेक्स्ट को फ़ॉर्मेट करना सीखें। हमारे चरण-दर-चरण गाइड के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।
weight: 12
url: /hi/java/java-powerpoint-table-formatting-updates/format-text-inside-table-row-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा के साथ पावरपॉइंट में टेबल पंक्ति के अंदर टेक्स्ट को फॉर्मेट करें

## परिचय
प्रस्तुतियों के साथ काम करते समय, अपने दर्शकों को जोड़े रखने के लिए दृश्य रूप से आकर्षक स्लाइड बनाना आवश्यक है। टेबल पंक्तियों के अंदर टेक्स्ट को फ़ॉर्मेट करने से आपकी स्लाइड की पठनीयता और सौंदर्य में काफ़ी सुधार हो सकता है। इस ट्यूटोरियल में, हम सीखेंगे कि Java के लिए Aspose.Slides का उपयोग करके PowerPoint में टेबल पंक्ति के अंदर टेक्स्ट को कैसे फ़ॉर्मेट किया जाए।
## आवश्यक शर्तें
कोडिंग भाग में जाने से पहले, आइए सुनिश्चित करें कि आपके पास आरंभ करने के लिए आवश्यक सभी चीजें मौजूद हैं:
-  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides for Java: Aspose.Slides for Java लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[वेबसाइट](https://releases.aspose.com/slides/java/).
- एकीकृत विकास वातावरण (IDE): अपना जावा कोड लिखने और चलाने के लिए IntelliJ IDEA, Eclipse, या NetBeans जैसे IDE का उपयोग करें।

## पैकेज आयात करें
कोडिंग शुरू करने से पहले, हमें आवश्यक पैकेज आयात करने की आवश्यकता है। आप इसे इस प्रकार कर सकते हैं:
```java
import com.aspose.slides.*;
```
आइये बेहतर समझ के लिए इस प्रक्रिया को कई चरणों में विभाजित करें।
## चरण 1: प्रस्तुति लोड करें
सबसे पहले, आपको अपना पावरपॉइंट प्रेजेंटेशन लोड करना होगा। सुनिश्चित करें कि आपके पास एक प्रेजेंटेशन फ़ाइल है जिसमें पहले से ही एक टेबल जोड़ी गई है।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation(dataDir + "SomePresentationWithTable.pptx");
```
## चरण 2: पहली स्लाइड तक पहुंचें
अब, आइए प्रेजेंटेशन की पहली स्लाइड पर जाएं। यहीं पर हमें हमारी टेबल मिलेगी।
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 3: तालिका का पता लगाएँ
इसके बाद, हमें स्लाइड के अंदर टेबल को ढूँढना होगा। सरलता के लिए, मान लें कि टेबल स्लाइड पर पहली आकृति है।
```java
ITable someTable = (ITable) slide.getShapes().get_Item(0);
```
## चरण 4: पहली पंक्ति की कोशिकाओं के लिए फ़ॉन्ट की ऊँचाई निर्धारित करें
 पहली पंक्ति की कोशिकाओं के लिए फ़ॉन्ट की ऊँचाई निर्धारित करने के लिए, इसका एक उदाहरण बनाएँ`PortionFormat` और इच्छित फ़ॉन्ट ऊंचाई सेट करें.
```java
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontHeight(25f);
someTable.getRows().get_Item(0).setTextFormat(portionFormat);
```
## चरण 5: टेक्स्ट संरेखण और मार्जिन सेट करें
 पहली पंक्ति की कोशिकाओं के लिए पाठ संरेखण और दायाँ मार्जिन सेट करने के लिए, इसका एक उदाहरण बनाएँ`ParagraphFormat` और संरेखण और मार्जिन कॉन्फ़िगर करें.
```java
ParagraphFormat paragraphFormat = new ParagraphFormat();
paragraphFormat.setAlignment(TextAlignment.Right);
paragraphFormat.setMarginRight(20);
someTable.getRows().get_Item(0).setTextFormat(paragraphFormat);
```
## चरण 6: दूसरी पंक्ति की कोशिकाओं के लिए लंबवत पाठ संरेखण सेट करें
 दूसरी पंक्ति में कक्षों के लिए लंबवत पाठ संरेखण सेट करने के लिए, का एक उदाहरण बनाएँ`TextFrameFormat` और ऊर्ध्वाधर पाठ प्रकार सेट करें.
```java
TextFrameFormat textFrameFormat = new TextFrameFormat();
textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
someTable.getColumns().get_Item(0).setTextFormat(textFrameFormat);
```
## चरण 7: प्रेजेंटेशन सहेजें
अंत में, संशोधित प्रस्तुति को एक नई फ़ाइल में सहेजें।
```java
presentation.save(dataDir + "result.pptx", SaveFormat.Pptx);
```
## चरण 8: संसाधनों को साफ़ करें
संसाधनों को मुक्त करने के लिए हमेशा प्रस्तुति ऑब्जेक्ट को हटा दें।
```java
if (presentation != null) presentation.dispose();
```

## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint में टेबल पंक्तियों के अंदर टेक्स्ट को फ़ॉर्मेट करना एक सीधी प्रक्रिया है। इन चरणों का पालन करके, आप आसानी से अपनी प्रस्तुतियों की उपस्थिति को बढ़ा सकते हैं। चाहे आप फ़ॉन्ट आकार समायोजित कर रहे हों, टेक्स्ट संरेखित कर रहे हों, या लंबवत टेक्स्ट प्रकार सेट कर रहे हों, Aspose.Slides आपको पेशेवर दिखने वाली स्लाइड बनाने में मदद करने के लिए एक शक्तिशाली API प्रदान करता है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
Aspose.Slides कई प्लेटफॉर्म के लिए उपलब्ध है, जिसमें .NET और C शामिल हैं++हालाँकि, Java के लिए, आपको Aspose.Slides for Java लाइब्रेरी का उपयोग करना होगा।
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं।[वेबसाइट](https://releases.aspose.com/).
### यदि मुझे कोई समस्या आती है तो मैं सहायता कैसे प्राप्त कर सकता हूँ?
 आप उनके यहाँ जाकर Aspose समुदाय से सहायता प्राप्त कर सकते हैं[सहयता मंच](https://forum.aspose.com/c/slides/11).
### क्या मैं Aspose.Slides for Java के लिए लाइसेंस खरीद सकता हूँ?
 हां, आप यहां से लाइसेंस खरीद सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/buy).
### Aspose.Slides for Java किस फ़ाइल स्वरूप का समर्थन करता है?
Aspose.Slides for Java विभिन्न प्रकार के प्रारूपों का समर्थन करता है, जिसमें PPT, PPTX, ODP आदि शामिल हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
