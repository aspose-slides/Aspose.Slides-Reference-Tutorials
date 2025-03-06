---
title: जावा का उपयोग करके PowerPoint में टेक्स्ट बॉक्स में हाइपरलिंक जोड़ें
linktitle: जावा का उपयोग करके PowerPoint में टेक्स्ट बॉक्स में हाइपरलिंक जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint टेक्स्ट बॉक्स में हाइपरलिंक जोड़ना सीखें। Java डेवलपर्स के लिए उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 23
url: /hi/java/java-powerpoint-text-font-customization/add-hyperlink-text-box-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
आज के डिजिटल युग में, प्रभावी संचार के लिए गतिशील प्रस्तुतियाँ बनाना जो संलग्न और सूचित करती हैं, महत्वपूर्ण है। जावा डेवलपर्स अपने अनुप्रयोगों को इंटरैक्टिव सुविधाओं के साथ बढ़ाने की चाहत रखते हैं, अक्सर जावा के लिए Aspose.Slides का सहारा लेते हैं, जो एक शक्तिशाली लाइब्रेरी है जो प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों में हेरफेर करने में सक्षम बनाती है। यह ट्यूटोरियल ऐसी ही एक सुविधा पर चर्चा करता है: जावा का उपयोग करके पावरपॉइंट प्रस्तुतियों में टेक्स्ट बॉक्स में हाइपरलिंक जोड़ना। इस गाइड के अंत तक, आपको इस बात की स्पष्ट समझ हो जाएगी कि अपने जावा अनुप्रयोगों में इस कार्यक्षमता को कैसे सहजता से लागू किया जाए।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर JDK (जावा डेवलपमेंट किट) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी डाउनलोड और सेट अप की गई। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- एकीकृत विकास वातावरण (IDE) जैसे कि IntelliJ IDEA या Eclipse स्थापित होना चाहिए।

## पैकेज आयात करें
उदाहरण में आगे बढ़ने से पहले, आवश्यक पैकेजों को आयात करना सुनिश्चित करें:
```java
import com.aspose.slides.*;
import java.io.File;
```
## चरण 1: एक प्रेजेंटेशन ऑब्जेक्ट बनाएँ
सबसे पहले, एक प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंसिएट करें जो एक पावरपॉइंट प्रेजेंटेशन का प्रतिनिधित्व करता है।
```java
String dataDir = "Your Document Directory";
Presentation pptxPresentation = new Presentation();
```
## चरण 2: स्लाइड तक पहुंचें और उसे संशोधित करें
प्रस्तुतिकरण में बदलाव करने के लिए उसमें से पहली स्लाइड लें।
```java
ISlide slide = pptxPresentation.getSlides().get_Item(0);
```
## चरण 3: एक ऑटोशेप (टेक्स्ट बॉक्स) जोड़ें
निर्दिष्ट निर्देशांक पर स्लाइड में आयत प्रकार का एक ऑटोशेप जोड़ें।
```java
IShape pptxShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 150, 50);
```
## चरण 4: टेक्स्ट फ़्रेम तक पहुँचें
आकृति को ऑटोशेप में डालें और उसके टेक्स्ट फ्रेम तक पहुंचें।
```java
IAutoShape pptxAutoShape = (IAutoShape) pptxShape;
pptxAutoShape.addTextFrame("");
ITextFrame textFrame = pptxAutoShape.getTextFrame();
```
## चरण 5: टेक्स्ट फ़्रेम में टेक्स्ट जोड़ें
टेक्स्ट फ़्रेम में इच्छित टेक्स्ट सामग्री जोड़ें.
```java
textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0).setText("Aspose.Slides");
```
## चरण 6: टेक्स्ट के लिए हाइपरलिंक सेट करें
पिछले चरण में जोड़े गए पाठ भाग के लिए हाइपरलिंक सेट करें।
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
IHyperlinkManager hyperlinkManager = portion.getPortionFormat().getHyperlinkManager();
hyperlinkManager.setExternalHyperlinkClick("http://www.aspose.com");
```
## चरण 7: प्रेजेंटेशन सहेजें
संशोधित प्रस्तुति को निर्दिष्ट स्थान पर सहेजें.
```java
pptxPresentation.save(dataDir + "hLinkPPTX_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इन चरणों का पालन करके, आपने सफलतापूर्वक सीखा है कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में टेक्स्ट बॉक्स में हाइपरलिंक कैसे जोड़ें। यह क्षमता आपको अपने Java अनुप्रयोगों के भीतर गतिशील और इंटरैक्टिव सामग्री बनाने की अनुमति देती है, जिससे उपयोगकर्ता जुड़ाव और अन्तरक्रियाशीलता बढ़ती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Java के लिए Aspose.Slides का निःशुल्क उपयोग कर सकता हूँ?
 हां, आप निःशुल्क परीक्षण के साथ शुरुआत कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 विस्तृत दस्तावेज उपलब्ध है[यहाँ](https://reference.aspose.com/slides/java/).
### यदि मुझे कोई समस्या आती है तो मैं सहायता कैसे प्राप्त कर सकता हूँ?
 आप Aspose समुदाय से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
### क्या मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, अस्थायी लाइसेंस खरीदने के लिए उपलब्ध हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या Aspose.Slides अन्य जावा लाइब्रेरीज़ के साथ संगत है?
Aspose.Slides व्यापक पावरपॉइंट हेरफेर के लिए विभिन्न जावा पुस्तकालयों के साथ अच्छी तरह से एकीकृत होता है।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
