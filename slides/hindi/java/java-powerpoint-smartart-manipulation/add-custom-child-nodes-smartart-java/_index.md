---
"description": "Aspose.Slides के साथ Java का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt में कस्टम चाइल्ड नोड्स जोड़ने का तरीका जानें। पेशेवर ग्राफ़िक्स के साथ अपनी स्लाइड्स को आसानी से बेहतर बनाएँ।"
"linktitle": "जावा का उपयोग करके स्मार्टआर्ट में कस्टम चाइल्ड नोड्स जोड़ें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा का उपयोग करके स्मार्टआर्ट में कस्टम चाइल्ड नोड्स जोड़ें"
"url": "/hi/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके स्मार्टआर्ट में कस्टम चाइल्ड नोड्स जोड़ें

## परिचय
स्मार्टआर्ट पावरपॉइंट में एक शक्तिशाली सुविधा है जो उपयोगकर्ताओं को जल्दी और आसानी से पेशेवर दिखने वाले ग्राफ़िक्स बनाने की अनुमति देती है। इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides के साथ जावा का उपयोग करके स्मार्टआर्ट में कस्टम चाइल्ड नोड्स कैसे जोड़ें।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
2. Aspose.Slides for Java: Aspose.Slides for Java को यहां से डाउनलोड और इंस्टॉल करें [यहाँ](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
```
## चरण 1: प्रस्तुति लोड करें
उस पावरपॉइंट प्रेजेंटेशन को लोड करें जहां आप स्मार्टआर्ट में कस्टम चाइल्ड नोड्स जोड़ना चाहते हैं:
```java
String dataDir = "Your Document Directory";
// इच्छित प्रस्तुति लोड करें
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## चरण 2: स्लाइड में स्मार्टआर्ट जोड़ें
अब, स्लाइड में स्मार्टआर्ट जोड़ें:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## चरण 3: स्मार्टआर्ट आकार को स्थानांतरित करें
स्मार्टआर्ट आकृति को नए स्थान पर ले जाएं:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## चरण 4: आकार की चौड़ाई बदलें
स्मार्टआर्ट आकृति की चौड़ाई बदलें:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## चरण 5: आकृति की ऊंचाई बदलें
स्मार्टआर्ट आकृति की ऊंचाई बदलें:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## चरण 6: आकृति को घुमाएँ
स्मार्टआर्ट आकृति को घुमाएँ:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## चरण 7: प्रस्तुति सहेजें
अंत में, संशोधित प्रस्तुति को सहेजें:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Slides के साथ Java का उपयोग करके SmartArt में कस्टम चाइल्ड नोड्स कैसे जोड़ें। इन चरणों का पालन करके, आप अपने प्रेजेंटेशन को कस्टमाइज़्ड ग्राफ़िक्स के साथ बेहतर बना सकते हैं, जिससे वे अधिक आकर्षक और पेशेवर बन सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides for Java का उपयोग करके विभिन्न प्रकार के स्मार्टआर्ट लेआउट जोड़ सकता हूँ?
हां, Aspose.Slides for Java विभिन्न स्मार्टआर्ट लेआउट का समर्थन करता है, जिससे आप अपनी प्रस्तुति आवश्यकताओं के लिए सबसे उपयुक्त लेआउट चुन सकते हैं।
### क्या Aspose.Slides for Java PowerPoint के विभिन्न संस्करणों के साथ संगत है?
Aspose.Slides for Java को PowerPoint के विभिन्न संस्करणों के साथ सहजता से काम करने के लिए डिज़ाइन किया गया है, जो सभी प्लेटफार्मों पर संगतता और स्थिरता सुनिश्चित करता है।
### क्या मैं स्मार्टआर्ट आकृतियों के स्वरूप को प्रोग्रामेटिक रूप से अनुकूलित कर सकता हूँ?
बिल्कुल! Aspose.Slides for Java के साथ, आप अपनी डिज़ाइन प्राथमिकताओं के अनुरूप SmartArt आकृतियों की उपस्थिति, आकार, रंग और लेआउट को प्रोग्रामेटिक रूप से अनुकूलित कर सकते हैं।
### क्या Aspose.Slides for Java दस्तावेज़ीकरण और समर्थन प्रदान करता है?
हां, आप Aspose वेबसाइट पर व्यापक दस्तावेज पा सकते हैं और सामुदायिक सहायता फ़ोरम तक पहुंच सकते हैं।
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
हां, आप खरीदारी करने से पहले इसकी विशेषताओं और क्षमताओं का पता लगाने के लिए वेबसाइट से Aspose.Slides for Java का निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}