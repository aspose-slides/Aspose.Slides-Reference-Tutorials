---
title: जावा पावरपॉइंट में एकाधिक पैराग्राफ
linktitle: जावा पावरपॉइंट में एकाधिक पैराग्राफ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java PowerPoint प्रस्तुतियों में एकाधिक पैराग्राफ़ बनाना सीखें। कोड उदाहरणों के साथ संपूर्ण मार्गदर्शिका।
weight: 13
url: /hi/java/java-powerpoint-text-paragraph-management/multiple-paragraphs-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पावरपॉइंट में एकाधिक पैराग्राफ

## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके जावा में कई पैराग्राफ़ वाली स्लाइड बनाने का तरीका जानेंगे। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों में हेरफेर करने की अनुमति देती है, जिससे यह स्लाइड निर्माण और फ़ॉर्मेटिंग से संबंधित कार्यों को स्वचालित करने के लिए आदर्श बन जाती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- JDK (जावा डेवलपमेंट किट) स्थापित.
- IDE (एकीकृत विकास वातावरण) जैसे कि IntelliJ IDEA या Eclipse स्थापित होना चाहिए।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
## पैकेज आयात करें
अपनी जावा फ़ाइल में आवश्यक Aspose.Slides क्लासेस आयात करके प्रारंभ करें:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
सबसे पहले, अपने पसंदीदा IDE में एक नया Java प्रोजेक्ट बनाएं और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides for Java लाइब्रेरी जोड़ें।
## चरण 2: प्रस्तुति आरंभ करें
 एक उदाहरण बनाना`Presentation` ऑब्जेक्ट जो एक PowerPoint फ़ाइल का प्रतिनिधित्व करता है:
```java
// उस निर्देशिका का पथ जहाँ आप प्रस्तुति को सहेजना चाहते हैं
String dataDir = "Your_Document_Directory/";
// प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंसिएट करें
Presentation pres = new Presentation();
```
## चरण 3: स्लाइड तक पहुंचना और आकृतियाँ जोड़ना
प्रस्तुति की पहली स्लाइड तक पहुंचें और एक आयताकार आकार जोड़ें (`IAutoShape`) इसे:
```java
// पहली स्लाइड पर पहुँचें
ISlide slide = pres.getSlides().get_Item(0);
// स्लाइड में एक ऑटोशेप (आयताकार) जोड़ें
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 300, 150);
```
## चरण 4: टेक्स्टफ्रेम तक पहुंचें और पैराग्राफ बनाएं
 तक पहुंच`TextFrame` की`AutoShape` और कई पैराग्राफ बनाएं (`IParagraph`) इसके अंदर:
```java
// ऑटोशेप के टेक्स्टफ्रेम तक पहुंचें
ITextFrame tf = ashp.getTextFrame();
// विभिन्न पाठ प्रारूपों के साथ पैराग्राफ और भाग बनाएँ
IParagraph para0 = tf.getParagraphs().get_Item(0);
IPortion port01 = new Portion();
IPortion port02 = new Portion();
para0.getPortions().add(port01);
para0.getPortions().add(port02);
// अतिरिक्त पैराग्राफ़ बनाएँ
IParagraph para1 = new Paragraph();
tf.getParagraphs().add(para1);
IPortion port10 = new Portion();
IPortion port11 = new Portion();
IPortion port12 = new Portion();
para1.getPortions().add(port10);
para1.getPortions().add(port11);
para1.getPortions().add(port12);
IParagraph para2 = new Paragraph();
tf.getParagraphs().add(para2);
IPortion port20 = new Portion();
IPortion port21 = new Portion();
IPortion port22 = new Portion();
para2.getPortions().add(port20);
para2.getPortions().add(port21);
para2.getPortions().add(port22);
```
## चरण 5: टेक्स्ट और पैराग्राफ़ को फ़ॉर्मेट करें
पैराग्राफ़ के भीतर पाठ के प्रत्येक भाग को प्रारूपित करें:
```java
// पाठ और स्वरूपण सेट करने के लिए पैराग्राफ और भागों के माध्यम से पुनरावृत्ति करें
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        tf.getParagraphs().get_Item(i).getPortions().get_Item(j).setText("Portion0" + j);
        if (j == 0) {
            // प्रत्येक पैराग्राफ के पहले भाग का प्रारूप
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontBold(NullableBool.True);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontHeight(15);
        } else if (j == 1) {
            // प्रत्येक पैराग्राफ के दूसरे भाग का प्रारूप
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontItalic(NullableBool.True);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontHeight(18);
        }
    }
}
```
## चरण 6: प्रस्तुति सहेजें
अंत में, संशोधित प्रस्तुति को डिस्क पर सहेजें:
```java
// PPTX को डिस्क पर सहेजें
pres.save(dataDir + "multiParaPort_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने बताया कि प्रोग्रामेटिक रूप से कई पैराग्राफ़ वाले PowerPoint प्रेजेंटेशन बनाने के लिए Aspose.Slides for Java का उपयोग कैसे करें। यह दृष्टिकोण सीधे Java कोड से गतिशील सामग्री निर्माण और अनुकूलन की अनुमति देता है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं बाद में और पैराग्राफ जोड़ सकता हूँ या फ़ॉर्मेटिंग बदल सकता हूँ?
हां, आप Aspose.Slides की API विधियों का उपयोग करके अधिक से अधिक पैराग्राफ जोड़ सकते हैं और फ़ॉर्मेटिंग को अनुकूलित कर सकते हैं।
### मैं और अधिक उदाहरण और दस्तावेज कहां पा सकता हूं?
आप अधिक उदाहरण और विस्तृत दस्तावेज़ देख सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
### क्या Aspose.Slides PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides विभिन्न PowerPoint प्रारूपों का समर्थन करता है, जो विभिन्न संस्करणों में संगतता सुनिश्चित करता है।
### क्या मैं खरीदने से पहले Aspose.Slides को निःशुल्क आज़मा सकता हूँ?
 हां, आप निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### यदि आवश्यकता पड़े तो मैं तकनीकी सहायता कैसे प्राप्त कर सकता हूँ?
 आप Aspose.Slides समुदाय से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
