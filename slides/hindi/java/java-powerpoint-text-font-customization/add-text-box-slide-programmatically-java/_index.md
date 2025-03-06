---
title: जावा के साथ प्रोग्रामेटिक रूप से स्लाइड पर टेक्स्ट बॉक्स जोड़ें
linktitle: जावा के साथ प्रोग्रामेटिक रूप से स्लाइड पर टेक्स्ट बॉक्स जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में प्रोग्रामेटिक रूप से टेक्स्ट बॉक्स जोड़ना सीखें। इस चरण-दर-चरण मार्गदर्शिका के साथ अपनी उत्पादकता में सुधार करें।
weight: 24
url: /hi/java/java-powerpoint-text-font-customization/add-text-box-slide-programmatically-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
प्रोग्रामेटिक रूप से पावरपॉइंट प्रेजेंटेशन बनाना और उसमें हेरफेर करना, रिपोर्ट बनाने से लेकर प्रेजेंटेशन को स्वचालित करने तक कई वर्कफ़्लो को सुव्यवस्थित कर सकता है। Aspose.Slides for Java एक शक्तिशाली API प्रदान करता है जो डेवलपर्स को इन कार्यों को कुशलतापूर्वक करने की अनुमति देता है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके स्लाइड में टेक्स्ट बॉक्स जोड़ने के बारे में मार्गदर्शन करेंगे। इस ट्यूटोरियल के अंत तक, आपको इस कार्यक्षमता को अपने Java अनुप्रयोगों में एकीकृत करने के तरीके के बारे में स्पष्ट समझ होगी।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा डेवलपमेंट किट (JDK) स्थापित
- IDE (एकीकृत विकास वातावरण) जैसे कि IntelliJ IDEA या Eclipse
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/)
- जावा प्रोग्रामिंग का बुनियादी ज्ञान
## पैकेज आयात करें
सबसे पहले, कोडिंग शुरू करने के लिए Aspose.Slides और Java कोर लाइब्रेरीज़ से आवश्यक पैकेज आयात करें।
```java
import com.aspose.slides.*;
import java.io.File;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने IDE में एक नया Java प्रोजेक्ट बनाएं और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides for Java लाइब्रेरी जोड़ें। अगर आपने इसे अभी तक डाउनलोड नहीं किया है, तो इसे यहाँ से डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/java/).
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
 आरंभ करें`Presentation` ऑब्जेक्ट, जो पावरपॉइंट फ़ाइल का प्रतिनिधित्व करता है.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## चरण 3: स्लाइड तक पहुंचें और ऑटोशेप जोड़ें
प्रस्तुति से पहली स्लाइड लें और उसमें एक ऑटोशेप (आयत) जोड़ें।
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## चरण 4: ऑटोशेप में टेक्स्ट फ़्रेम जोड़ें
पाठ शामिल करने के लिए ऑटोशेप में एक पाठ फ़्रेम जोड़ें।
```java
shape.addTextFrame(" ");
ITextFrame textFrame = shape.getTextFrame();
```
## चरण 5: पाठ सामग्री सेट करें
टेक्स्ट फ़्रेम के अंदर टेक्स्ट सामग्री सेट करें.
```java
IParagraph para = textFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## चरण 6: प्रस्तुति सहेजें
संशोधित प्रस्तुति को फ़ाइल में सहेजें.
```java
pres.save(dataDir + "TextBox_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Slides का उपयोग करके किसी स्लाइड में प्रोग्रामेटिक रूप से टेक्स्ट बॉक्स जोड़ने का तरीका खोजा है। यह क्षमता डेवलपर्स को पावरपॉइंट प्रस्तुतियों के निर्माण और अनुकूलन को स्वचालित करने की अनुमति देती है, जिससे विभिन्न अनुप्रयोगों में उत्पादकता और दक्षता बढ़ती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Java के लिए Aspose.Slides आयतों के अलावा अन्य आकृतियों को भी संभाल सकता है?
हां, Aspose.Slides विभिन्न आकृतियों जैसे वृत्त, रेखाएं आदि का समर्थन करता है।
### क्या Aspose.Slides for Java बड़े पैमाने के उद्यम अनुप्रयोगों के लिए उपयुक्त है?
बिल्कुल, इसे जटिल कार्यों को कुशलतापूर्वक निपटाने के लिए डिज़ाइन किया गया है।
### मैं Aspose.Slides के लिए और अधिक उदाहरण और दस्तावेज़ कहां पा सकता हूं?
 दौरा करना[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) विस्तृत मार्गदर्शिका और उदाहरण के लिए.
### मैं परीक्षण के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 आप प्राप्त कर सकते हैं[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) Aspose से.
### क्या Aspose.Slides प्रस्तुतियों को अन्य प्रारूपों में परिवर्तित करने का समर्थन करता है?
हां, यह पीडीएफ और छवियों सहित विभिन्न प्रारूपों का समर्थन करता है।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
