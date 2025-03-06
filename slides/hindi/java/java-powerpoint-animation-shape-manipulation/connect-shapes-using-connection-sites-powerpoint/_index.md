---
title: PowerPoint में कनेक्शन साइट्स का उपयोग करके आकृतियाँ कनेक्ट करें
linktitle: PowerPoint में कनेक्शन साइट्स का उपयोग करके आकृतियाँ कनेक्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint में आकृतियों को जोड़ने का तरीका जानें। अपनी प्रस्तुतियों को सहजता से स्वचालित करें।
weight: 19
url: /hi/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint में कनेक्शन साइट्स का उपयोग करके आकृतियों को कैसे जोड़ा जाए। यह शक्तिशाली लाइब्रेरी हमें PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देती है, जिससे आकृतियों को जोड़ने जैसे कार्य सहज और कुशल हो जाते हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर जावा इंस्टॉल है। आप इसे डाउनलोड करके इंस्टॉल कर सकते हैं[वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java को डाउनलोड करें और इंस्टॉल करें[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): जावा विकास के लिए कोई IDE चुनें, जैसे कि IntelliJ IDEA, Eclipse, या NetBeans.

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;

```
## चरण 1: आकृति संग्रह तक पहुँचना
चयनित स्लाइड के लिए आकृति संग्रह तक पहुंचें:
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## चरण 2: कनेक्टर आकार जोड़ना
स्लाइड आकार संग्रह में कनेक्टर आकार जोड़ें:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## चरण 3: ऑटोशेप्स जोड़ना
दीर्घवृत्त और आयत जैसे स्वचालित आकार जोड़ें:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## चरण 4: आकृतियों को कनेक्टर्स से जोड़ना
आकृतियों को कनेक्टर से जोड़ें:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## चरण 5: कनेक्शन साइट इंडेक्स सेट करना
आकृतियों के लिए वांछित कनेक्शन साइट इंडेक्स सेट करें:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके PowerPoint में कनेक्शन साइट्स का उपयोग करके आकृतियों को कैसे जोड़ा जाए। इस ज्ञान के साथ, अब आप आसानी से अपने PowerPoint प्रस्तुतियों को स्वचालित और अनुकूलित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Slides for Java का उपयोग अन्य PowerPoint मैनिपुलेशन कार्यों के लिए किया जा सकता है?
हां, Aspose.Slides for Java पावरपॉइंट प्रस्तुतियों को बनाने, संपादित करने और परिवर्तित करने के लिए कार्यात्मकता की एक विस्तृत श्रृंखला प्रदान करता है।
### क्या Aspose.Slides for Java का उपयोग निःशुल्क है?
 Aspose.Slides for Java एक व्यावसायिक लाइब्रेरी है, लेकिन आप इसके फीचर्स को निःशुल्क परीक्षण के साथ देख सकते हैं।[यहाँ](https://releases.aspose.com/) प्रारंभ करना।
### यदि मुझे Aspose.Slides for Java का उपयोग करते समय कोई समस्या आती है तो क्या मुझे सहायता मिल सकती है?
 हां, आप Aspose समुदाय मंचों से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
### क्या Aspose.Slides for Java के लिए अस्थायी लाइसेंस उपलब्ध हैं?
 हां, परीक्षण और मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस उपलब्ध हैं। आप एक प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides for Java के लिए लाइसेंस कहां से खरीद सकता हूं?
आप Aspose वेबसाइट से लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
