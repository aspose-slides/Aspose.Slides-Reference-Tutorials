---
title: ज्यामिति आकृतियों में संयुक्त ऑब्जेक्ट बनाएँ
linktitle: ज्यामिति आकृतियों में संयुक्त ऑब्जेक्ट बनाएँ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: इस विस्तृत ट्यूटोरियल के साथ Aspose.Slides for Java का उपयोग करके ज्यामिति आकृतियों में समग्र ऑब्जेक्ट बनाना सीखें। Java डेवलपर्स के लिए बिल्कुल सही।
type: docs
weight: 20
url: /hi/java/java-powerpoint-shape-formatting-geometry/create-composite-objects-geometry-shapes-powerpoint/
---
## परिचय
नमस्ते! क्या आपने कभी जावा का उपयोग करके अपने पावरपॉइंट प्रेजेंटेशन में आश्चर्यजनक और जटिल आकृतियाँ बनाना चाहा है? खैर, आप सही जगह पर हैं। इस ट्यूटोरियल में, हम ज्यामिति आकृतियों में समग्र ऑब्जेक्ट बनाने के लिए शक्तिशाली Aspose.Slides for Java लाइब्रेरी में गोता लगाएँगे। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह चरण-दर-चरण मार्गदर्शिका आपको कुछ ही समय में प्रभावशाली परिणाम प्राप्त करने में मदद करेगी। शुरू करने के लिए तैयार हैं? चलिए शुरू करते हैं!
## आवश्यक शर्तें
इससे पहले कि हम कोड में प्रवेश करें, आपको कुछ चीजों की आवश्यकता होगी:
- जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके मशीन पर JDK 1.8 या उच्चतर संस्करण स्थापित है।
- एकीकृत विकास वातावरण (आईडीई): इंटेलीज आईडीईए या एक्लिप्स जैसा आईडीई आपके जीवन को आसान बना देगा।
-  Aspose.Slides for Java: आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/) या इसे अपने प्रोजेक्ट में शामिल करने के लिए Maven का उपयोग करें।
- जावा का बुनियादी ज्ञान: यह ट्यूटोरियल मानता है कि आपको जावा की बुनियादी समझ है।
## पैकेज आयात करें
सबसे पहले, आइए Aspose.Slides for Java के साथ आरंभ करने के लिए आवश्यक पैकेजों को आयात करें।
```java
import com.aspose.slides.*;

```

मिश्रित ऑब्जेक्ट बनाना जटिल लग सकता है, लेकिन इसे प्रबंधनीय चरणों में तोड़कर, आप पाएंगे कि यह जितना आप सोचते हैं उससे कहीं ज़्यादा आसान है। हम एक पावरपॉइंट प्रेजेंटेशन बनाएंगे, एक आकृति जोड़ेंगे, और फिर मिश्रित आकृति बनाने के लिए कई ज्यामिति पथों को परिभाषित और लागू करेंगे।
## चरण 1: अपना प्रोजेक्ट सेट करें
 कोई भी कोड लिखने से पहले, अपना जावा प्रोजेक्ट सेट अप करें। अपने IDE में एक नया प्रोजेक्ट बनाएँ और Aspose.Slides for Java को शामिल करें। आप Maven का उपयोग करके लाइब्रेरी जोड़ सकते हैं या JAR फ़ाइल को डाउनलोड कर सकते हैं।[Aspose.Slides डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
### Maven का उपयोग करके अपने प्रोजेक्ट में Aspose.Slides जोड़ना
 यदि आप Maven का उपयोग कर रहे हैं, तो अपने में निम्नलिखित निर्भरता जोड़ें`pom.xml` फ़ाइल:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace with the latest version -->
</dependency>
```
## चरण 2: प्रस्तुति आरंभ करें
अब, चलिए एक नया पावरपॉइंट प्रेजेंटेशन बनाते हैं। हम इसे इनिशियलाइज़ करके शुरू करेंगे।`Presentation` कक्षा।
```java
// आउटपुट फ़ाइल नाम
String resultPath = "Your Output Directory" +  "GeometryShapeCompositeObjects.pptx";
Presentation pres = new Presentation();
```
## चरण 3: एक नया आकार बनाएँ
इसके बाद, हम अपनी प्रस्तुति की पहली स्लाइड में एक नया आयताकार आकार जोड़ेंगे।
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## चरण 4: पहला ज्यामिति पथ परिभाषित करें
 हम अपनी मिश्रित आकृति का पहला भाग एक बनाकर परिभाषित करेंगे`GeometryPath` और उसमें अंक जोड़ना।
```java
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.moveTo(0, 0);
geometryPath0.lineTo(shape.getWidth(), 0);
geometryPath0.lineTo(shape.getWidth(), shape.getHeight() / 3);
geometryPath0.lineTo(0, shape.getHeight() / 3);
geometryPath0.closeFigure();
```
## चरण 5: दूसरा ज्यामिति पथ परिभाषित करें
इसी प्रकार, हमारी मिश्रित आकृति के दूसरे भाग को परिभाषित करें।
```java
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.moveTo(0, shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight());
geometryPath1.lineTo(0, shape.getHeight());
geometryPath1.closeFigure();
```
## चरण 6: ज्यामिति पथों को संयोजित करें
दो ज्यामिति पथों को संयोजित करें और उन्हें आकार पर सेट करें।
```java
shape.setGeometryPaths(new GeometryPath[]{geometryPath0, geometryPath1});
```
## चरण 7: प्रेजेंटेशन सहेजें
अंत में, अपनी प्रस्तुति को एक फ़ाइल में सेव करें।
```java
String resultPath = "Your Output Directory" + "GeometryShapeCompositeObjects.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## चरण 8: संसाधनों को साफ़ करें
सुनिश्चित करें कि आप प्रस्तुति में प्रयुक्त सभी संसाधनों को जारी करें।
```java
if (pres != null) pres.dispose();
```
## निष्कर्ष
और अब आपका काम हो गया! आपने Aspose.Slides for Java का उपयोग करके सफलतापूर्वक एक समग्र आकृति बना ली है। प्रक्रिया को सरल चरणों में विभाजित करके, आप आसानी से जटिल आकृतियाँ बना सकते हैं और अपनी प्रस्तुतियों को बेहतर बना सकते हैं। अद्वितीय डिज़ाइन बनाने के लिए विभिन्न ज्यामिति पथों के साथ प्रयोग करते रहें।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java जावा में पावरपॉइंट प्रस्तुतियों को बनाने, उनमें हेरफेर करने और परिवर्तित करने के लिए एक शक्तिशाली लाइब्रेरी है।
### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?
 आप इसे Maven का उपयोग करके स्थापित कर सकते हैं या JAR फ़ाइल को डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/slides/java/).
### क्या मैं व्यावसायिक परियोजनाओं में Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
 हां, लेकिन आपको लाइसेंस खरीदना होगा। आप अधिक जानकारी यहां पा सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/buy).
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मुझे अधिक दस्तावेज और सहायता कहां मिल सकती है?
 इसकी जाँच पड़ताल करो[प्रलेखन](https://reference.aspose.com/slides/java/) और[सहयता मंच](https://forum.aspose.com/c/slides/11).