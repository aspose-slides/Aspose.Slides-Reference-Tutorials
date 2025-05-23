---
"description": "दस्तावेज़ प्रबंधन क्षमताओं को बढ़ाते हुए, Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों से एम्बेडेड फ़ाइल डेटा निकालना सीखें।"
"linktitle": "PowerPoint में OLE ऑब्जेक्ट से एम्बेडेड फ़ाइल डेटा निकालें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "PowerPoint में OLE ऑब्जेक्ट से एम्बेडेड फ़ाइल डेटा निकालें"
"url": "/hi/java/java-powerpoint-animation-shape-manipulation/extract-embedded-file-data-ole-object-powerpoint/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint में OLE ऑब्जेक्ट से एम्बेडेड फ़ाइल डेटा निकालें


## परिचय
जावा प्रोग्रामिंग के क्षेत्र में, PowerPoint प्रस्तुतियों के भीतर OLE (ऑब्जेक्ट लिंकिंग और एम्बेडिंग) ऑब्जेक्ट्स से एम्बेडेड फ़ाइल डेटा निकालना एक ऐसा कार्य है जो अक्सर उठता है, विशेष रूप से दस्तावेज़ प्रबंधन या डेटा निष्कर्षण अनुप्रयोगों में। जावा के लिए Aspose.Slides प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को संभालने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके OLE ऑब्जेक्ट्स से एम्बेडेड फ़ाइल डेटा निकालने का तरीका जानेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में आगे बढ़ें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपके सिस्टम पर JDK (जावा डेवलपमेंट किट) स्थापित है।
- Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके प्रोजेक्ट में संदर्भित की गई।

## पैकेज आयात करें
सबसे पहले, सुनिश्चित करें कि आप Aspose.Slides for Java द्वारा प्रदान की गई कार्यक्षमता का उपयोग करने के लिए अपने Java प्रोजेक्ट में आवश्यक पैकेज आयात करें।
```java
import com.aspose.slides.IShape;
import com.aspose.slides.ISlide;
import com.aspose.slides.OleObjectFrame;
import com.aspose.slides.Presentation;

import java.io.FileOutputStream;
import java.io.IOException;
```

अब, आइये इस प्रक्रिया को कई चरणों में विभाजित करें:
## चरण 1: दस्तावेज़ निर्देशिका पथ प्रदान करें
```java
String dataDir = "Your Document Directory";
```
प्रतिस्थापित करें `"Your Document Directory"` आपके पावरपॉइंट प्रेजेंटेशन वाली निर्देशिका का पथ सहित।
## चरण 2: PowerPoint फ़ाइल नाम निर्दिष्ट करें
```java
String pptxFileName = dataDir + "TestOlePresentation.pptx";
```
प्रतिस्थापन सुनिश्चित करें `"TestOlePresentation.pptx"` अपनी पावरपॉइंट प्रेजेंटेशन फ़ाइल के नाम के साथ।
## चरण 3: प्रस्तुति लोड करें
```java
Presentation pres = new Presentation(pptxFileName);
```
यह पंक्ति एक नए उदाहरण को आरंभ करती है `Presentation` क्लास में, निर्दिष्ट पावरपॉइंट प्रेजेंटेशन फ़ाइल लोड करना।
## चरण 4: स्लाइड और आकृतियों के माध्यम से पुनरावृति करें
```java
for (ISlide sld : pres.getSlides()) {
    for (IShape shape : sld.getShapes()) {
```
यहां, हम प्रस्तुति के भीतर प्रत्येक स्लाइड और आकृति को दोहराते हैं।
## चरण 5: OLE ऑब्जेक्ट की जाँच करें
```java
if (shape instanceof OleObjectFrame) {
```
यह स्थिति जाँचती है कि क्या आकृति एक OLE ऑब्जेक्ट है।
## चरण 6: एम्बेडेड फ़ाइल डेटा निकालें
```java
OleObjectFrame oleFrame = (OleObjectFrame) shape;
byte[] data = oleFrame.getEmbeddedData().getEmbeddedFileData();
```
यदि आकृति एक OLE ऑब्जेक्ट है, तो हम उसका एम्बेडेड फ़ाइल डेटा निकालते हैं।
## चरण 7: फ़ाइल एक्सटेंशन निर्धारित करें
```java
String fileExtention = oleFrame.getEmbeddedData().getEmbeddedFileExtension();
```
यह पंक्ति निकाली गई एम्बेडेड फ़ाइल का फ़ाइल एक्सटेंशन पुनर्प्राप्त करती है।
## चरण 8: निकाली गई फ़ाइल को सहेजें
```java
String extractedPath = dataDir + "ExtractedObject_out" + objectnum + fileExtention;
FileOutputStream fs = new FileOutputStream(extractedPath);
fs.write(data, 0, data.length);
```
अंत में, हम निकाले गए फ़ाइल डेटा को निर्दिष्ट निर्देशिका में सहेजते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि PowerPoint प्रस्तुतियों के भीतर OLE ऑब्जेक्ट से एम्बेडेड फ़ाइल डेटा निकालने के लिए Aspose.Slides for Java का उपयोग कैसे करें। दिए गए चरणों का पालन करके, आप इस कार्यक्षमता को अपने Java अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं, दस्तावेज़ प्रबंधन क्षमताओं को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Slides सभी प्रकार के एम्बेडेड ऑब्जेक्ट्स से डेटा निकाल सकता है?
Aspose.Slides विभिन्न एम्बेडेड ऑब्जेक्ट्स से डेटा निकालने के लिए व्यापक समर्थन प्रदान करता है, जिसमें OLE ऑब्जेक्ट्स, चार्ट्स आदि शामिल हैं।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
हां, Aspose.Slides विभिन्न संस्करणों में पावरपॉइंट प्रस्तुतियों के साथ संगतता सुनिश्चित करता है, जिससे एम्बेडेड डेटा का निर्बाध निष्कर्षण सुनिश्चित होता है।
### क्या Aspose.Slides को व्यावसायिक उपयोग के लिए लाइसेंस की आवश्यकता है?
हां, Aspose.Slides के व्यावसायिक उपयोग के लिए वैध लाइसेंस की आवश्यकता है। आप Aspose से लाइसेंस प्राप्त कर सकते हैं [वेबसाइट](https://purchase.aspose.com/temporary-license/).
### क्या मैं Aspose.Slides का उपयोग करके निष्कर्षण प्रक्रिया को स्वचालित कर सकता हूँ?
बिल्कुल, Aspose.Slides एम्बेडेड फ़ाइल डेटा निकालने जैसे कार्यों को स्वचालित करने के लिए व्यापक API प्रदान करता है, जिससे कुशल और सुव्यवस्थित दस्तावेज़ प्रसंस्करण की अनुमति मिलती है।
### मैं Aspose.Slides के लिए आगे सहायता या समर्थन कहां पा सकता हूं?
किसी भी प्रश्न, तकनीकी सहायता या सामुदायिक समर्थन के लिए, आप Aspose.Slides फ़ोरम पर जा सकते हैं या दस्तावेज़ देख सकते हैं [Aspose.स्लाइड्स](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}