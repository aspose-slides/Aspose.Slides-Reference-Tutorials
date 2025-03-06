---
title: PowerPoint में कनेक्टर्स का उपयोग करके आकृतियाँ कनेक्ट करें
linktitle: PowerPoint में कनेक्टर्स का उपयोग करके आकृतियाँ कनेक्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ PowerPoint प्रस्तुतियों में कनेक्टर का उपयोग करके आकृतियों को कनेक्ट करना सीखें। शुरुआती लोगों के लिए चरण-दर-चरण ट्यूटोरियल।
weight: 18
url: /hi/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, हम Aspose.Slides for Java की मदद से PowerPoint प्रेजेंटेशन में कनेक्टर का उपयोग करके आकृतियों को जोड़ने का तरीका जानेंगे। आकृतियों को कुशलतापूर्वक जोड़ने और आकर्षक स्लाइड बनाने के लिए इन चरण-दर-चरण निर्देशों का पालन करें।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java डाउनलोड करके सेट अप करें। अगर आपने इसे अभी तक इंस्टॉल नहीं किया है, तो आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- एक कोड संपादक जैसे कि एक्लिप्स या इंटेलीज आईडिया।

## पैकेज आयात करें
सबसे पहले, अपने जावा प्रोजेक्ट में Aspose.Slides के साथ काम करने के लिए आवश्यक पैकेज आयात करें।
```java
import com.aspose.slides.*;

```
## चरण 1: प्रेजेंटेशन क्लास को इंस्टैंशिएट करें
 उदाहरण प्रस्तुत करें`Presentation`क्लास, जो उस PPTX फ़ाइल का प्रतिनिधित्व करता है जिस पर आप काम कर रहे हैं।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## चरण 2: आकृति संग्रह तक पहुँचें
उस चयनित स्लाइड के लिए आकृति संग्रह तक पहुँचें जहाँ आप आकृतियाँ और कनेक्टर जोड़ना चाहते हैं।
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## चरण 3: आकृतियाँ जोड़ें
स्लाइड में आवश्यक आकृतियाँ जोड़ें। इस उदाहरण में, हम एक दीर्घवृत्त और एक आयत जोड़ेंगे।
```java
// ऑटोशेप दीर्घवृत्त जोड़ें
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// ऑटोशेप आयत जोड़ें
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## चरण 4: कनेक्टर जोड़ें
स्लाइड आकार संग्रह में कनेक्टर आकार जोड़ें.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## चरण 5: आकृतियों को कनेक्टर्स से जोड़ें
आकृतियों को कनेक्टर से जोड़ें।
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## चरण 6: कनेक्टर को पुनः रूट करें
आकृतियों के बीच स्वचालित सबसे छोटा रास्ता निर्धारित करने के लिए रीरूट को कॉल करें।
```java
connector.reroute();
```
## चरण 7: प्रस्तुति सहेजें
कनेक्टर का उपयोग करके आकृतियों को जोड़ने के बाद प्रस्तुति को सहेजें.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
अंत में, प्रेजेंटेशन ऑब्जेक्ट को हटाना न भूलें।
```java
if (input != null) input.dispose();
```
अब आपने Aspose.Slides for Java का उपयोग करके PowerPoint में कनेक्टर्स का उपयोग करके आकृतियों को सफलतापूर्वक कनेक्ट कर लिया है।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java के साथ PowerPoint प्रस्तुतियों में कनेक्टर का उपयोग करके आकृतियों को कैसे जोड़ा जाए। इन सरल चरणों का पालन करके, आप अपनी प्रस्तुतियों को आकर्षक आरेखों और फ़्लोचार्ट के साथ बेहतर बना सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides for Java में कनेक्टर्स की उपस्थिति को अनुकूलित कर सकता हूं?
हां, आप अपनी प्रस्तुति आवश्यकताओं के अनुरूप कनेक्टर के विभिन्न गुणों जैसे रंग, रेखा शैली और मोटाई को अनुकूलित कर सकते हैं।
### क्या Aspose.Slides for Java PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides for Java विभिन्न PowerPoint प्रारूपों का समर्थन करता है, जिनमें PPTX, PPT, और ODP शामिल हैं।
### क्या मैं एक ही कनेक्टर से दो से अधिक आकृतियों को जोड़ सकता हूँ?
हां, आप Aspose.Slides for Java द्वारा प्रदान किए गए जटिल कनेक्टर का उपयोग करके एकाधिक आकृतियों को जोड़ सकते हैं।
### क्या Java के लिए Aspose.Slides आकृतियों में पाठ जोड़ने के लिए समर्थन प्रदान करता है?
बिल्कुल, आप आसानी से जावा के लिए Aspose.Slides का उपयोग करके आकृतियों और कनेक्टर्स में प्रोग्रामेटिक रूप से पाठ जोड़ सकते हैं।
### क्या जावा उपयोगकर्ताओं के लिए Aspose.Slides हेतु कोई सामुदायिक फोरम या सहायता चैनल उपलब्ध है?
 हां, आप Aspose.Slides फ़ोरम पर सहायक संसाधन पा सकते हैं, प्रश्न पूछ सकते हैं और अन्य उपयोगकर्ताओं के साथ जुड़ सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
