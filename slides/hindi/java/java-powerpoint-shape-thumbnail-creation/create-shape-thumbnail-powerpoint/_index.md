---
title: पावरपॉइंट में आकृति थंबनेल बनाएं
linktitle: पावरपॉइंट में आकृति थंबनेल बनाएं
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में आकृति थंबनेल कैसे बनाएं। चरण-दर-चरण मार्गदर्शिका प्रदान की गई है।
weight: 14
url: /hi/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# पावरपॉइंट में आकृति थंबनेल बनाएं

## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में आकृति थंबनेल बनाने के बारे में जानेंगे। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint फ़ाइलों के साथ काम करने में सक्षम बनाती है, जिससे आकृति थंबनेल बनाने सहित विभिन्न कार्यों के स्वचालन की अनुमति मिलती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी डाउनलोड करके अपने प्रोजेक्ट में सेट अप करें। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
सबसे पहले, आपको Aspose.Slides की कार्यक्षमताओं का उपयोग करने के लिए अपने जावा कोड में आवश्यक पैकेज आयात करने की आवश्यकता है। अपनी जावा फ़ाइल की शुरुआत में निम्नलिखित आयात कथन शामिल करें:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## चरण 1: दस्तावेज़ निर्देशिका परिभाषित करें
```java
String dataDir = "Your Document Directory";
```
 प्रतिस्थापित करें`"Your Document Directory"` अपनी पावरपॉइंट फ़ाइल वाली निर्देशिका का पथ बताएं.
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंशिएट करें
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 एक नया उदाहरण बनाएँ`Presentation` क्लास में, आपके पावरपॉइंट फ़ाइल का पथ पैरामीटर के रूप में पास किया जाता है।
## चरण 3: आकृति थंबनेल उत्पन्न करें
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
प्रस्तुति की पहली स्लाइड से वांछित आकृति का थंबनेल पुनः प्राप्त करें।
## चरण 4: थंबनेल छवि सहेजें
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
उत्पन्न थंबनेल छवि को निर्दिष्ट फ़ाइल नाम के साथ PNG प्रारूप में डिस्क पर सहेजें।

## निष्कर्ष
अंत में, इस ट्यूटोरियल ने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में आकार थंबनेल बनाने का तरीका दिखाया। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए कोड स्निपेट का उपयोग करके, आप कुशलतापूर्वक प्रोग्रामेटिक रूप से आकार थंबनेल उत्पन्न कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं प्रस्तुति में किसी भी स्लाइड पर आकृतियों के लिए थंबनेल बना सकता हूँ?
हां, आप स्लाइड इंडेक्स को समायोजित करके किसी भी स्लाइड पर आकृतियों को लक्षित करने के लिए कोड को संशोधित कर सकते हैं।
### क्या Aspose.Slides थंबनेल सहेजने के लिए अन्य छवि प्रारूपों का समर्थन करता है?
हां, PNG के अलावा, Aspose.Slides विभिन्न छवि प्रारूपों जैसे JPEG, GIF और BMP में थंबनेल सहेजने का समर्थन करता है।
### क्या Aspose.Slides व्यावसायिक उपयोग के लिए उपयुक्त है?
 हां, Aspose.Slides व्यवसायों और संगठनों के लिए वाणिज्यिक लाइसेंस प्रदान करता है। आप यहाँ से लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या मैं खरीदने से पहले Aspose.Slides आज़मा सकता हूँ?
 बिल्कुल! आप Aspose.Slides का निःशुल्क परीक्षण संस्करण यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/) इसकी विशेषताओं और क्षमताओं का मूल्यांकन करने के लिए।
### मैं Aspose.Slides के लिए समर्थन कहां पा सकता हूं?
 यदि आपके पास कोई प्रश्न है या Aspose.Slides के साथ सहायता की आवश्यकता है, तो आप जा सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) समर्थन के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
