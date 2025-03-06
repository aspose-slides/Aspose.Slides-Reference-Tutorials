---
title: जावा का उपयोग करके PowerPoint में पैराग्राफ बुलेट जोड़ें
linktitle: जावा का उपयोग करके PowerPoint में पैराग्राफ बुलेट जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में पैराग्राफ़ बुलेट कैसे जोड़ें। यह ट्यूटोरियल आपको कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शन करता है।
weight: 15
url: /hi/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
पैराग्राफ बुलेट जोड़ने से पावरपॉइंट प्रेजेंटेशन की पठनीयता और संरचना में सुधार होता है। जावा के लिए Aspose.Slides प्रोग्रामेटिक रूप से प्रेजेंटेशन में हेरफेर करने के लिए मजबूत उपकरण प्रदान करता है, जिसमें विभिन्न बुलेट शैलियों के साथ टेक्स्ट को प्रारूपित करने की क्षमता शामिल है। इस ट्यूटोरियल में, आप सीखेंगे कि जावा कोड का उपयोग करके पावरपॉइंट स्लाइड में बुलेट पॉइंट को कैसे एकीकृत किया जाए, Aspose.Slides का लाभ उठाएं।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपके सिस्टम पर JDK (जावा डेवलपमेंट किट) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक Aspose.Slides पैकेज आयात करें:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
सबसे पहले, एक नया जावा प्रोजेक्ट बनाएं और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides for Java लाइब्रेरी जोड़ें।
## चरण 2: प्रस्तुति आरंभ करें
एक प्रस्तुति ऑब्जेक्ट आरंभ करें (`Presentation`) पर क्लिक करें.
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रस्तुतिकरण उदाहरण बनाना
Presentation pres = new Presentation();
```
## चरण 3: स्लाइड और टेक्स्ट फ़्रेम तक पहुँचें
स्लाइड तक पहुंचें (`ISlide`और उसका टेक्स्ट फ़्रेम (`ITextFrame`) जहाँ आप बुलेट जोड़ना चाहते हैं.
```java
// पहली स्लाइड तक पहुँचना
ISlide slide = pres.getSlides().get_Item(0);
// ऑटोशेप जोड़ना और उस तक पहुँचना
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// निर्मित ऑटोशेप के टेक्स्ट फ़्रेम तक पहुँचना
ITextFrame txtFrm = aShp.getTextFrame();
```
## चरण 4: बुलेट के साथ पैराग्राफ़ बनाएँ और फ़ॉर्मेट करें
पैराग्राफ़ बनाएँ (`Paragraph`) और उनकी बुलेट शैलियाँ, इंडेंटेशन और टेक्स्ट सेट करें।
```java
// पैराग्राफ़ बनाना
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// एक और पैराग्राफ़ बनाना
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## चरण 5: प्रस्तुति सहेजें
संशोधित प्रस्तुति को PowerPoint फ़ाइल में सहेजें (`PPTX`).
```java
// प्रस्तुति को PPTX फ़ाइल के रूप में लिखना
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## चरण 6: संसाधनों को साफ करें
संसाधन जारी करने के लिए प्रस्तुति ऑब्जेक्ट का निपटान करें.
```java
// प्रस्तुति ऑब्जेक्ट को हटाएँ
if (pres != null) {
    pres.dispose();
}
```

## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint में पैराग्राफ़ बुलेट जोड़ना दिए गए कोड उदाहरणों के साथ सरल है। अपनी प्रस्तुति आवश्यकताओं के अनुरूप बुलेट शैलियों और स्वरूपण को सहजता से अनुकूलित करें।

## पूछे जाने वाले प्रश्न
### क्या मैं बुलेट के रंग को अनुकूलित कर सकता हूँ?
हां, आप Aspose.Slides API का उपयोग करके बुलेट्स के लिए कस्टम रंग सेट कर सकते हैं।
### मैं नेस्टेड बुलेट्स कैसे जोड़ूं?
नेस्टिंग बुलेट्स में पैराग्राफ के भीतर पैराग्राफ जोड़ना तथा उसके अनुसार इंडेंटेशन समायोजित करना शामिल है।
### क्या मैं अलग-अलग स्लाइडों के लिए अलग-अलग बुलेट शैलियाँ बना सकता हूँ?
हां, आप प्रोग्रामेटिक रूप से विभिन्न स्लाइडों पर अद्वितीय बुलेट शैलियाँ लागू कर सकते हैं।
### क्या Aspose.Slides Java 11 के साथ संगत है?
हां, Aspose.Slides Java 11 और उच्चतर संस्करणों का समर्थन करता है।
### मैं और अधिक उदाहरण और दस्तावेज कहां पा सकता हूं?
 मिलने जाना[Aspose.Slides for Java दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) विस्तृत मार्गदर्शिका और उदाहरण के लिए.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
