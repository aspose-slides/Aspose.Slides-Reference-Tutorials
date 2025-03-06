---
title: जावा पावरपॉइंट में टेक्स्ट को लंबवत रूप से संरेखित करें
linktitle: जावा पावरपॉइंट में टेक्स्ट को लंबवत रूप से संरेखित करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: सहज स्लाइड फ़ॉर्मेटिंग के लिए Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में टेक्स्ट को लंबवत रूप से संरेखित करना सीखें।
weight: 10
url: /hi/java/java-powerpoint-text-alignment-formatting/vertically-align-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रेजेंटेशन में टेबल सेल के भीतर टेक्स्ट को लंबवत रूप से कैसे संरेखित किया जाए। टेक्स्ट को लंबवत रूप से संरेखित करना स्लाइड डिज़ाइन का एक महत्वपूर्ण पहलू है, यह सुनिश्चित करता है कि आपकी सामग्री साफ-सुथरी और पेशेवर रूप से प्रस्तुत की गई है। Aspose.Slides प्रोग्रामेटिक रूप से प्रस्तुतियों में हेरफेर और प्रारूपण करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है, जिससे आपको अपनी स्लाइड के हर पहलू पर पूरा नियंत्रण मिलता है।
## आवश्यक शर्तें
इस ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपकी मशीन पर JDK (जावा डेवलपमेंट किट) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- IDE (एकीकृत विकास वातावरण) जैसे कि IntelliJ IDEA या Eclipse स्थापित होना चाहिए।

## पैकेज आयात करें
ट्यूटोरियल के साथ आगे बढ़ने से पहले, अपनी जावा फ़ाइल में आवश्यक Aspose.Slides पैकेज आयात करना सुनिश्चित करें:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: अपना जावा प्रोजेक्ट सेट अप करें
सुनिश्चित करें कि आपने अपने पसंदीदा IDE में एक नया Java प्रोजेक्ट स्थापित किया है और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides लाइब्रेरी को जोड़ा है।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
 इसका एक उदाहरण बनाएं`Presentation` एक नई पावरपॉइंट प्रस्तुति के साथ काम करना शुरू करने के लिए कक्षा:
```java
Presentation presentation = new Presentation();
```
## चरण 3: पहली स्लाइड तक पहुंचें
प्रस्तुति में सामग्री जोड़ने के लिए उसकी पहली स्लाइड प्राप्त करें:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 4: तालिका आयाम परिभाषित करें और तालिका जोड़ें
अपनी तालिका के लिए स्तंभ की चौड़ाई और पंक्ति की ऊंचाई निर्धारित करें, फिर स्लाइड में तालिका का आकार जोड़ें:
```java
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};
ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## चरण 5: तालिका कक्षों में पाठ सामग्री सेट करें
तालिका में विशिष्ट पंक्तियों के लिए पाठ सामग्री सेट करें:
```java
tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
```
## चरण 6: टेक्स्ट फ़्रेम तक पहुँचें और टेक्स्ट को फ़ॉर्मेट करें
टेक्स्ट फ़्रेम तक पहुँचें और किसी विशिष्ट सेल के भीतर टेक्स्ट को फ़ॉर्मेट करें:
```java
ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);
portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## चरण 7: पाठ को लंबवत संरेखित करें
सेल के अंदर पाठ के लिए ऊर्ध्वाधर संरेखण सेट करें:
```java
ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center);
cell.setTextVerticalType(TextVerticalType.Vertical270);
```
## चरण 8: प्रस्तुति सहेजें
संशोधित प्रस्तुति को अपनी डिस्क पर निर्दिष्ट स्थान पर सहेजें:
```java
String dataDir = "Your Document Directory";
presentation.save(dataDir + "Vertical_Align_Text_out.pptx", SaveFormat.Pptx);
```
## चरण 9: संसाधनों की सफ़ाई करें
 का निपटान करें`Presentation` संसाधन जारी करने पर आपत्ति:
```java
if (presentation != null) presentation.dispose();
```

## निष्कर्ष
इन चरणों का पालन करके, आप Aspose.Slides का उपयोग करके अपने Java PowerPoint प्रस्तुतियों में तालिका कक्षों के भीतर पाठ को प्रभावी ढंग से लंबवत रूप से संरेखित कर सकते हैं। यह क्षमता आपकी स्लाइड्स की दृश्य अपील और स्पष्टता को बढ़ाती है, यह सुनिश्चित करती है कि आपकी सामग्री पेशेवर रूप से प्रस्तुत की गई है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं तालिकाओं के अलावा अन्य आकृतियों में पाठ को लंबवत संरेखित कर सकता हूँ?
हां, Aspose.Slides टेक्स्ट बॉक्स और प्लेसहोल्डर्स सहित विभिन्न आकृतियों में टेक्स्ट को लंबवत रूप से संरेखित करने के तरीके प्रदान करता है।
### क्या Aspose.Slides पाठ को क्षैतिज रूप से संरेखित करने का भी समर्थन करता है?
हां, आप Aspose.Slides द्वारा प्रदान किए गए विभिन्न संरेखण विकल्पों का उपयोग करके पाठ को क्षैतिज रूप से संरेखित कर सकते हैं।
### क्या Aspose.Slides PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides उन प्रस्तुतियों को बनाने का समर्थन करता है जो Microsoft PowerPoint के सभी प्रमुख संस्करणों के साथ संगत हैं।
### मैं Aspose.Slides के लिए और अधिक उदाहरण और दस्तावेज़ कहां पा सकता हूं?
 दौरा करना[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) व्यापक गाइड, एपीआई संदर्भ और कोड नमूनों के लिए.
### मैं Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 तकनीकी सहायता और सामुदायिक समर्थन के लिए, यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
