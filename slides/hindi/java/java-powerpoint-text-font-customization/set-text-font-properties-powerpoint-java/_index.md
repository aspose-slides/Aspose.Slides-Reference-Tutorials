---
title: जावा के साथ PowerPoint में टेक्स्ट फ़ॉन्ट गुण सेट करें
linktitle: जावा के साथ PowerPoint में टेक्स्ट फ़ॉन्ट गुण सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके PowerPoint में टेक्स्ट फ़ॉन्ट गुणधर्म सेट करना सीखें। जावा डेवलपर्स के लिए आसान, चरण-दर-चरण मार्गदर्शिका।#जावा डेवलपर्स के लिए इस चरण-दर-चरण ट्यूटोरियल के साथ जावा के लिए Aspose.Slides का उपयोग करके PowerPoint टेक्स्ट फ़ॉन्ट गुणों में हेरफेर करना सीखें।
weight: 18
url: /hi/java/java-powerpoint-text-font-customization/set-text-font-properties-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा के साथ PowerPoint में टेक्स्ट फ़ॉन्ट गुण सेट करें

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि PowerPoint प्रेजेंटेशन में प्रोग्रामेटिक रूप से विभिन्न टेक्स्ट फ़ॉन्ट गुण सेट करने के लिए Aspose.Slides for Java का उपयोग कैसे करें। हम स्लाइड में टेक्स्ट के लिए फ़ॉन्ट प्रकार, शैली (बोल्ड, इटैलिक), रेखांकन, आकार और रंग सेट करना सीखेंगे।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- आपके सिस्टम पर JDK स्थापित है.
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- एकीकृत विकास वातावरण (आईडीई) जैसे कि इंटेलीज आईडिया या एक्लिप्स की स्थापना।
## पैकेज आयात करें
सबसे पहले, सुनिश्चित करें कि आपने आवश्यक Aspose.Slides क्लासेस आयात कर ली हैं:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: अपना जावा प्रोजेक्ट सेट अप करें
अपने IDE में एक नया जावा प्रोजेक्ट बनाएं और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides लाइब्रेरी जोड़ें।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
 एक उदाहरण बनाना`Presentation` पावरपॉइंट फ़ाइलों के साथ काम करने के लिए ऑब्जेक्ट:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## चरण 3: स्लाइड तक पहुंचें और ऑटोशेप जोड़ें
पहली स्लाइड लें और उसमें एक ऑटोशेप (आयत) जोड़ें:
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
## चरण 4: टेक्स्ट को ऑटोशेप पर सेट करें
पाठ सामग्री को ऑटोशेप पर सेट करें:
```java
ITextFrame textFrame = shape.getTextFrame();
textFrame.setText("Aspose TextBox");
```
## चरण 5: फ़ॉन्ट गुण सेट करें
पाठ के भाग तक पहुँचें और विभिन्न फ़ॉन्ट गुण सेट करें:
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
// फ़ॉन्ट परिवार सेट करें
portion.getPortionFormat().setLatinFont(new FontData("Times New Roman"));
// बोल्ड सेट करें
portion.getPortionFormat().setFontBold(NullableBool.True);
// इटैलिक सेट करें
portion.getPortionFormat().setFontItalic(NullableBool.True);
// रेखांकन सेट करें
portion.getPortionFormat().setFontUnderline(TextUnderlineType.Single);
// फ़ॉन्ट आकार सेट करें
portion.getPortionFormat().setFontHeight(25);
// फ़ॉन्ट रंग सेट करें
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## चरण 6: प्रस्तुति सहेजें
संशोधित प्रस्तुति को फ़ाइल में सहेजें:
```java
presentation.save(dataDir + "SetTextFontProperties_out.pptx", SaveFormat.Pptx);
```
## चरण 7: संसाधनों की सफ़ाई करें
संसाधन जारी करने के लिए प्रस्तुति ऑब्जेक्ट का निपटान करें:
```java
if (presentation != null) {
    presentation.dispose();
}
```

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा है कि PowerPoint स्लाइड में टेक्स्ट फ़ॉन्ट गुणों को गतिशील रूप से अनुकूलित करने के लिए Aspose.Slides for Java का उपयोग कैसे करें। इन चरणों का पालन करके, आप प्रोग्रामेटिक रूप से विशिष्ट डिज़ाइन आवश्यकताओं को पूरा करने के लिए टेक्स्ट को कुशलतापूर्वक प्रारूपित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं इन फ़ॉन्ट परिवर्तनों को पावरपॉइंट स्लाइड में मौजूदा टेक्स्ट पर लागू कर सकता हूँ?
 हां, आप मौजूदा टेक्स्ट को उसके मूल स्वरूप में एक्सेस करके संशोधित कर सकते हैं।`Portion` और वांछित फ़ॉन्ट गुण लागू करना।
### मैं फ़ॉन्ट का रंग ग्रेडिएंट या पैटर्न भरण में कैसे बदल सकता हूँ?
 के बजाय`SolidFillColor` , उपयोग`GradientFillColor` या`PatternedFillColor` इसलिए।
### क्या Aspose.Slides पावरपॉइंट टेम्पलेट्स (.potx) के साथ संगत है?
हां, आप PowerPoint टेम्पलेट्स के साथ काम करने के लिए Aspose.Slides का उपयोग कर सकते हैं।
### क्या Aspose.Slides PDF प्रारूप में निर्यात का समर्थन करता है?
हां, Aspose.Slides पीडीएफ सहित विभिन्न प्रारूपों में प्रस्तुतियों को निर्यात करने की अनुमति देता है।
### मैं Aspose.Slides के लिए अधिक सहायता और समर्थन कहां पा सकता हूं?
 मिलने जाना[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) सामुदायिक सहायता और मार्गदर्शन के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
