---
title: जावा के साथ पावरपॉइंट में स्मार्टआर्ट आकार शैली बदलें
linktitle: जावा के साथ पावरपॉइंट में स्मार्टआर्ट आकार शैली बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ Java का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt शैलियों को बदलने का तरीका जानें। अपनी प्रस्तुतियों को बेहतर बनाएँ।
weight: 23
url: /hi/java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
जावा विकास की दुनिया में, शक्तिशाली प्रस्तुतियाँ बनाना अक्सर एक आवश्यकता होती है। चाहे वह व्यावसायिक पिचों के लिए हो, शैक्षिक उद्देश्यों के लिए हो, या केवल जानकारी साझा करने के लिए हो, पावरपॉइंट प्रस्तुतियाँ एक सामान्य माध्यम हैं। हालाँकि, कभी-कभी पावरपॉइंट द्वारा प्रदान की जाने वाली डिफ़ॉल्ट शैलियाँ और प्रारूप हमारी ज़रूरतों को पूरी तरह से पूरा नहीं कर सकते हैं। यहीं पर Aspose.Slides for Java काम आता है।
Aspose.Slides for Java एक मजबूत लाइब्रेरी है जो जावा डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों के साथ काम करने की अनुमति देती है। यह कई तरह की सुविधाएँ प्रदान करता है, जिसमें आकृतियों, शैलियों, एनिमेशन और बहुत कुछ में हेरफेर करने की क्षमता शामिल है। इस ट्यूटोरियल में, हम एक विशिष्ट कार्य पर ध्यान केंद्रित करेंगे: जावा का उपयोग करके PowerPoint प्रस्तुतियों में स्मार्टआर्ट आकार शैली को बदलना।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, आपके पास कुछ पूर्व-आवश्यकताएं होनी चाहिए:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK इंस्टॉल है। आप Oracle वेबसाइट से नवीनतम संस्करण डाउनलोड और इंस्टॉल कर सकते हैं।
2. Aspose.Slides for Java लाइब्रेरी: आपको अपने प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी को डाउनलोड करके शामिल करना होगा। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): जावा विकास के लिए अपना पसंदीदा IDE चुनें। IntelliJ IDEA, Eclipse, या NetBeans लोकप्रिय विकल्प हैं।

## पैकेज आयात करें
कोडिंग शुरू करने से पहले, आइए अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। ये पैकेज हमें Aspose.Slides कार्यक्षमताओं के साथ सहजता से काम करने में सक्षम बनाएंगे।
```java
import com.aspose.slides.*;
```
## चरण 1: प्रस्तुति लोड करें
सबसे पहले, हमें उस पावरपॉइंट प्रेजेंटेशन को लोड करना होगा जिसे हम संशोधित करना चाहते हैं।
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## चरण 2: आकृतियों के माध्यम से आगे बढ़ें
इसके बाद, हम प्रस्तुति की पहली स्लाइड के अंदर प्रत्येक आकृति पर नजर डालेंगे।
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## चरण 3: स्मार्टआर्ट प्रकार की जाँच करें
प्रत्येक आकृति के लिए, हम जाँच करेंगे कि क्या यह स्मार्टआर्ट आकृति है।
```java
if (shape instanceof ISmartArt)
```
## चरण 4: स्मार्टआर्ट पर कास्ट करें
 यदि आकृति स्मार्टआर्ट है, तो हम इसे कास्ट करेंगे`ISmartArt` इंटरफेस।
```java
ISmartArt smart = (ISmartArt) shape;
```
## चरण 5: शैली जांचें और बदलें
इसके बाद हम स्मार्टआर्ट की वर्तमान शैली की जांच करेंगे और यदि आवश्यक हुआ तो उसमें बदलाव करेंगे।
```java
if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
{
    smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
}
```
## चरण 6: प्रस्तुति सहेजें
अंत में, हम संशोधित प्रस्तुति को एक नई फ़ाइल में सहेज लेंगे।
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि Java और Aspose.Slides for Java लाइब्रेरी का उपयोग करके PowerPoint प्रस्तुतियों में SmartArt आकृति शैली को कैसे बदला जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपनी प्रस्तुति आवश्यकताओं के अनुरूप SmartArt आकृतियों की उपस्थिति को आसानी से अनुकूलित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अन्य Java लाइब्रेरीज़ के साथ Aspose.Slides for Java का उपयोग कर सकता हूँ?
हां, आपके अनुप्रयोगों की कार्यक्षमता बढ़ाने के लिए Aspose.Slides for Java को अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत किया जा सकता है।
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से Aspose.Slides for Java का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Java के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 आप यहाँ जाकर Aspose.Slides for Java के लिए समर्थन प्राप्त कर सकते हैं[मंच](https://forum.aspose.com/c/slides/11).
### क्या मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
 हां, आप Aspose.Slides for Java के लिए एक अस्थायी लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं Aspose.Slides for Java के लिए विस्तृत दस्तावेज़ कहां पा सकता हूं?
 आप Java के लिए Aspose.Slides के लिए विस्तृत दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
