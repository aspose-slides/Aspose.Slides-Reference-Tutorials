---
title: जावा के साथ पावरपॉइंट में टेक्स्ट फ़्रेम का एंकर सेट करें
linktitle: जावा के साथ पावरपॉइंट में टेक्स्ट फ़्रेम का एंकर सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ Java का उपयोग करके PowerPoint में टेक्स्ट फ़्रेम एंकर सेट करना सीखें। अपनी प्रस्तुतियों को बेहतर बनाएँ।
type: docs
weight: 13
url: /hi/java/java-powerpoint-text-font-customization/set-anchor-text-frame-powerpoint-java/
---
## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Slides की मदद से जावा का उपयोग करके PowerPoint प्रस्तुतियों में टेक्स्ट फ़्रेम का एंकर कैसे सेट करें। टेक्स्ट फ़्रेम को एंकर करने से आप आकृति के भीतर टेक्स्ट की स्थिति और व्यवहार को सटीक रूप से नियंत्रित कर सकते हैं, जिससे यह सुनिश्चित होता है कि आपकी स्लाइड्स दिखने में आकर्षक और प्रभावी ढंग से संरचित हैं।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/)
- जावा प्रोग्रामिंग भाषा और ऑब्जेक्ट-ओरिएंटेड अवधारणाओं की बुनियादी समझ
## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक Aspose.Slides लाइब्रेरी शामिल करें:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
सुनिश्चित करें कि आपके पास अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक जावा प्रोजेक्ट सेट अप है। सुनिश्चित करें कि Aspose.Slides JAR फ़ाइल आपके प्रोजेक्ट के बिल्ड पथ में जोड़ी गई है।
## चरण 2: एक प्रेजेंटेशन ऑब्जेक्ट बनाएँ
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
यह एक नया पावरपॉइंट प्रेजेंटेशन ऑब्जेक्ट आरंभ करता है।
## चरण 3: स्लाइड तक पहुंचें और एक आकृति जोड़ें
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
यहां, स्लाइड में विशिष्ट निर्देशांकों और आयामों पर एक आयताकार आकार जोड़ा जाता है।
## चरण 4: आकृति में टेक्स्ट फ़्रेम जोड़ें
```java
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAnchoringType(TextAnchorType.Bottom);
```
 आयताकार आकार में एक टेक्स्ट फ़्रेम जोड़ा जाता है, और इसका एंकरिंग प्रकार सेट किया जाता है`Bottom`, यह सुनिश्चित करते हुए कि पाठ आकृति के निचले भाग पर स्थित है।
## चरण 5: टेक्स्ट फ़्रेम में टेक्स्ट डालें
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
यह टेक्स्ट फ़्रेम में टेक्स्ट सामग्री जोड़ता है और फ़ॉर्मेटिंग लागू करता है, जैसे टेक्स्ट का रंग काला करना।
## चरण 6: प्रेजेंटेशन सहेजें
```java
presentation.save(dataDir + "AnchorText_out.pptx", SaveFormat.Pptx);
```
अंत में, संशोधित प्रस्तुति को अपनी डिस्क पर निर्दिष्ट स्थान पर सहेजें।

## निष्कर्ष
जावा का उपयोग करके पावरपॉइंट में टेक्स्ट फ़्रेम का एंकर सेट करना सुव्यवस्थित प्रस्तुतियाँ बनाने के लिए आवश्यक है। इन चरणों का पालन करके और जावा के लिए Aspose.Slides का लाभ उठाकर, आप अपनी स्लाइड्स की दृश्य अपील और स्पष्टता को बढ़ाने के लिए आकृतियों के भीतर टेक्स्ट पोजिशनिंग को कुशलतापूर्वक प्रबंधित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो जावा डेवलपर्स को पावरपॉइंट प्रस्तुतियों को बनाने, पढ़ने, हेरफेर करने और परिवर्तित करने की अनुमति देती है।
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 आप दस्तावेज़ तक पहुँच सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
### मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### क्या मैं Java के लिए Aspose.Slides निःशुल्क आज़मा सकता हूँ?
 हां, आप एक निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए समर्थन कहां से प्राप्त कर सकता हूं?
 आप सहायता फ़ोरम पर जा सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11) किसी भी प्रश्न या सहायता के लिए.