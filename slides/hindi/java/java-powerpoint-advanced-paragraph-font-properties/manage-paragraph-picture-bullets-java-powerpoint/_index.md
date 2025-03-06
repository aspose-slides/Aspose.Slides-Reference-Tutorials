---
title: जावा पावरपॉइंट में पैराग्राफ पिक्चर बुलेट प्रबंधित करें
linktitle: जावा पावरपॉइंट में पैराग्राफ पिक्चर बुलेट प्रबंधित करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में कस्टम पिक्चर बुलेट जोड़ने का तरीका जानें। सहज एकीकरण के लिए इस विस्तृत, चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 11
url: /hi/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
आधुनिक व्यावसायिक दुनिया में आकर्षक और आकर्षक प्रस्तुतियाँ बनाना एक महत्वपूर्ण कौशल है। जावा डेवलपर्स पावरपॉइंट स्लाइड्स में कस्टमाइज़्ड पिक्चर बुलेट्स के साथ अपनी प्रस्तुतियों को बेहतर बनाने के लिए Aspose.Slides का लाभ उठा सकते हैं। यह ट्यूटोरियल आपको चरण दर चरण प्रक्रिया के माध्यम से मार्गदर्शन करेगा, यह सुनिश्चित करते हुए कि आप आत्मविश्वास से अपनी प्रस्तुतियों में पिक्चर बुलेट्स जोड़ सकते हैं।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- जावा डेवलपमेंट किट (JDK) स्थापित
- एकीकृत विकास वातावरण (IDE) जैसे कि एक्लिप्स या इंटेलीज आईडिया
- Aspose.Slides for Java लाइब्रेरी
- जावा प्रोग्रामिंग का बुनियादी ज्ञान
- बुलेट चित्र के लिए छवि फ़ाइल
 Aspose.Slides for Java लाइब्रेरी डाउनलोड करने के लिए, यहां जाएं[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/) दस्तावेज़ीकरण के लिए, जाँच करें[प्रलेखन](https://reference.aspose.com/slides/java/).
## पैकेज आयात करें
सबसे पहले, सुनिश्चित करें कि आपने अपने प्रोजेक्ट के लिए आवश्यक पैकेज आयात किए हैं। अपनी जावा फ़ाइल की शुरुआत में निम्नलिखित आयात जोड़ें:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
आइये इस प्रक्रिया को प्रबंधनीय चरणों में विभाजित करें।
## चरण 1: अपनी प्रोजेक्ट निर्देशिका सेट करें
अपने प्रोजेक्ट के लिए एक नई डायरेक्टरी बनाएँ। इस डायरेक्टरी में आपकी जावा फ़ाइल, Aspose.Slides लाइब्रेरी और बुलेट के लिए इमेज फ़ाइल होगी।
```java
String dataDir = "Your Document Directory";
```
## चरण 2: प्रस्तुति आरंभ करें
 का एक नया उदाहरण आरंभ करें`Presentation` क्लास. यह ऑब्जेक्ट आपके पावरपॉइंट प्रेजेंटेशन का प्रतिनिधित्व करता है.
```java
Presentation presentation = new Presentation();
```
## चरण 3: पहली स्लाइड तक पहुंचें
प्रस्तुति की पहली स्लाइड तक पहुँचें। स्लाइड शून्य-अनुक्रमित हैं, इसलिए पहली स्लाइड इंडेक्स 0 पर है।
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 4: बुलेट छवि लोड करें
वह छवि लोड करें जिसे आप बुलेट के लिए उपयोग करना चाहते हैं। यह छवि आपकी प्रोजेक्ट निर्देशिका में रखी जानी चाहिए।
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## चरण 5: स्लाइड में ऑटोशेप जोड़ें
स्लाइड में एक ऑटोशेप जोड़ें। शेप में कस्टम बुलेट पॉइंट के साथ टेक्स्ट शामिल होगा।
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## चरण 6: टेक्स्ट फ़्रेम तक पहुँचें
ऑटोशेप के पैराग्राफ़ में परिवर्तन करने के लिए उसके टेक्स्ट फ़्रेम तक पहुँचें।
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## चरण 7: डिफ़ॉल्ट पैराग्राफ़ हटाएँ
टेक्स्ट फ़्रेम में स्वचालित रूप से जोड़े गए डिफ़ॉल्ट पैराग्राफ़ को हटाएँ।
```java
textFrame.getParagraphs().removeAt(0);
```
## चरण 8: नया पैराग्राफ़ बनाएँ
एक नया पैराग्राफ़ बनाएँ और उसका टेक्स्ट सेट करें। इस पैराग्राफ़ में कस्टम पिक्चर बुलेट्स होंगे।
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## चरण 9: बुलेट शैली और छवि सेट करें
पहले लोड की गई कस्टम छवि का उपयोग करने के लिए बुलेट शैली सेट करें।
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## चरण 10: बुलेट की ऊंचाई समायोजित करें
यह सुनिश्चित करने के लिए कि बुलेट प्रस्तुति में अच्छी दिखे, इसकी ऊंचाई निर्धारित करें।
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## चरण 11: पैराग्राफ को टेक्स्ट फ़्रेम में जोड़ें
नव निर्मित पैराग्राफ को ऑटोशेप के टेक्स्ट फ्रेम में जोड़ें।
```java
textFrame.getParagraphs().add(paragraph);
```
## चरण 12: प्रस्तुति सहेजें
अंत में, प्रस्तुति को PPTX और PPT फ़ाइल दोनों के रूप में सहेजें।
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## निष्कर्ष
 और अब यह आपके लिए है! इन चरणों का पालन करके, आप आसानी से Aspose.Slides for Java का उपयोग करके अपने PowerPoint प्रस्तुतियों में कस्टम पिक्चर बुलेट जोड़ सकते हैं। यह शक्तिशाली लाइब्रेरी आपको पेशेवर और आकर्षक प्रस्तुतियाँ बनाने में मदद करने के लिए कई सुविधाएँ प्रदान करती है।[प्रलेखन](https://reference.aspose.com/slides/java/)अधिक उन्नत सुविधाओं और अनुकूलन विकल्पों के लिए.
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो जावा डेवलपर्स को प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और हेरफेर करने की अनुमति देती है।
### क्या मैं चित्र बुलेट्स के लिए किसी भी छवि का उपयोग कर सकता हूँ?
हां, आप चित्र बुलेट्स के लिए किसी भी छवि का उपयोग कर सकते हैं, बशर्ते वह आपकी प्रोजेक्ट निर्देशिका से सुलभ हो।
### क्या मुझे Java के लिए Aspose.Slides का उपयोग करने के लिए लाइसेंस की आवश्यकता है?
 Aspose.Slides for Java को पूर्ण कार्यक्षमता के लिए लाइसेंस की आवश्यकता होती है। आप यहाँ से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/) या पूर्ण लाइसेंस खरीदें[यहाँ](https://purchase.aspose.com/buy).
### क्या मैं एक ऑटोशेप में विभिन्न बुलेट शैलियों के साथ कई पैराग्राफ जोड़ सकता हूँ?
हां, आप प्रत्येक पैराग्राफ को अलग-अलग बनाकर और कॉन्फ़िगर करके एक ही ऑटोशेप में विभिन्न बुलेट शैलियों वाले कई पैराग्राफ जोड़ सकते हैं।
### मुझे और अधिक उदाहरण और समर्थन कहां मिल सकता है?
 आप अधिक उदाहरण यहां पा सकते हैं[प्रलेखन](https://reference.aspose.com/slides/java/) और Aspose समुदाय से समर्थन प्राप्त करें[मंचों](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
