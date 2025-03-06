---
title: जावा का उपयोग करके स्मार्टआर्ट आकार रंग शैली बदलें
linktitle: जावा का उपयोग करके स्मार्टआर्ट आकार रंग शैली बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Java और Aspose.Slides के साथ PowerPoint में SmartArt आकार के रंगों को गतिशील रूप से बदलना सीखें। दृश्य अपील को सहजता से बढ़ाएँ।
weight: 20
url: /hi/java/java-powerpoint-smartart-manipulation/change-smartart-shape-color-style-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
इस ट्यूटोरियल में, हम Aspose.Slides के साथ Java का उपयोग करके SmartArt आकार रंग शैलियों को बदलने की प्रक्रिया से गुजरेंगे। SmartArt PowerPoint प्रस्तुतियों में एक शक्तिशाली सुविधा है जो नेत्रहीन आकर्षक ग्राफ़िक्स के निर्माण की अनुमति देती है। SmartArt आकृतियों की रंग शैली को बदलकर, आप अपनी प्रस्तुतियों के समग्र डिज़ाइन और दृश्य प्रभाव को बढ़ा सकते हैं। हम इस प्रक्रिया को आसान चरणों में विभाजित करेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा डेवलपमेंट एनवायरनमेंट: सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2.  Aspose.Slides for Java: Aspose.Slides for Java को डाउनलोड करें और इंस्टॉल करें[वेबसाइट](https://releases.aspose.com/slides/java/).
3. जावा का बुनियादी ज्ञान: जावा प्रोग्रामिंग भाषा की अवधारणाओं से परिचित होना उपयोगी होगा।
## पैकेज आयात करें
कोड में आगे बढ़ने से पहले, आइए आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
```
अब, आइए कोड उदाहरण को चरण-दर-चरण निर्देशों में विभाजित करें:
## चरण 1: प्रस्तुति लोड करें
सबसे पहले, हमें पावरपॉइंट प्रेजेंटेशन को लोड करना होगा जिसमें स्मार्टआर्ट आकृति शामिल है:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## चरण 2: आकृतियों के माध्यम से आगे बढ़ें
इसके बाद, हम स्मार्टआर्ट आकृतियों की पहचान करने के लिए पहली स्लाइड के अंदर प्रत्येक आकृति को देखेंगे:
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## चरण 3: स्मार्टआर्ट प्रकार की जाँच करें
प्रत्येक आकृति के लिए, हम जाँचेंगे कि क्या यह स्मार्टआर्ट आकृति है:
```java
if (shape instanceof ISmartArt)
```
## चरण 4: रंग शैली बदलें
यदि आकृति स्मार्टआर्ट आकृति है, तो हम इसकी रंग शैली बदल देंगे:
```java
ISmartArt smart = (ISmartArt) shape;
if (smart.getColorStyle() == SmartArtColorType.ColoredFillAccent1)
{
    smart.setColorStyle(SmartArtColorType.ColorfulAccentColors);
}
```
## चरण 5: प्रस्तुति सहेजें
अंत में, हम संशोधित प्रस्तुति को सहेज लेंगे:
```java
presentation.save(dataDir + "ChangeSmartArtColorStyle_out.pptx", SaveFormat.Pptx);
```
## निष्कर्ष
इन चरणों का पालन करके, आप आसानी से Aspose.Slides के साथ Java का उपयोग करके अपने PowerPoint प्रस्तुतियों में SmartArt आकार रंग शैलियों को बदल सकते हैं। अपनी प्रस्तुतियों की दृश्य अपील को बढ़ाने के लिए विभिन्न रंग शैलियों के साथ प्रयोग करें।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं केवल विशिष्ट स्मार्टआर्ट आकृतियों की रंग शैली बदल सकता हूँ?
हां, आप अपनी आवश्यकताओं के आधार पर विशिष्ट स्मार्टआर्ट आकृतियों को लक्षित करने के लिए कोड को संशोधित कर सकते हैं।
### क्या Aspose.Slides स्मार्टआर्ट के लिए अन्य हेरफेर विकल्पों का समर्थन करता है?
हां, Aspose.Slides स्मार्टआर्ट आकृतियों में हेरफेर करने के लिए विभिन्न API प्रदान करता है, जिसमें आकार बदलना, पुनः स्थिति निर्धारण करना और पाठ जोड़ना शामिल है।
### क्या मैं एकाधिक प्रस्तुतियों के लिए इस प्रक्रिया को स्वचालित कर सकता हूँ?
बिल्कुल, आप एकाधिक प्रस्तुतियों को कुशलतापूर्वक संभालने के लिए इस कोड को बैच प्रोसेसिंग स्क्रिप्ट में शामिल कर सकते हैं।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
हां, Aspose.Slides PowerPoint संस्करणों की एक विस्तृत श्रृंखला का समर्थन करता है, जो अधिकांश प्रस्तुति फ़ाइलों के साथ संगतता सुनिश्चित करता है।
### मैं Aspose.Slides-संबंधित प्रश्नों के लिए समर्थन कहां से प्राप्त कर सकता हूं?
 आप यहां जा सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) समुदाय और Aspose समर्थन कर्मचारियों से सहायता के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
