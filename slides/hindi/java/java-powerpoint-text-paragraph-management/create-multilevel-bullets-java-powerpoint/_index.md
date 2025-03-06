---
title: जावा पावरपॉइंट में बहुस्तरीय बुलेट बनाएं
linktitle: जावा पावरपॉइंट में बहुस्तरीय बुलेट बनाएं
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint में मल्टीलेवल बुलेट बनाना सीखें। कोड उदाहरणों और FAQ के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 14
url: /hi/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पावरपॉइंट में बहुस्तरीय बुलेट बनाएं

## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में बहुस्तरीय बुलेट बनाने का तरीका जानेंगे। प्रस्तुतियों में संगठित और आकर्षक सामग्री बनाने के लिए बुलेट पॉइंट जोड़ना एक सामान्य आवश्यकता है। हम इस प्रक्रिया को चरण-दर-चरण पूरा करेंगे, यह सुनिश्चित करते हुए कि इस गाइड के अंत तक, आप कई स्तरों पर संरचित बुलेट पॉइंट के साथ अपनी प्रस्तुतियों को बेहतर बनाने के लिए सुसज्जित होंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित सेटअप है:
- जावा डेवलपमेंट एनवायरनमेंट: सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी: Aspose.Slides for Java को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/slides/java/).
- IDE: अपने पसंदीदा जावा इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (IDE) का उपयोग करें जैसे कि IntelliJ IDEA, Eclipse, या अन्य।
- बुनियादी ज्ञान: जावा प्रोग्रामिंग और बुनियादी पावरपॉइंट अवधारणाओं से परिचित होना उपयोगी होगा।

## पैकेज आयात करें
ट्यूटोरियल में आगे बढ़ने से पहले, आइए Aspose.Slides for Java से आवश्यक पैकेज आयात करें, जिनका उपयोग हम पूरे ट्यूटोरियल में करेंगे।
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
सबसे पहले, अपने IDE में एक नया Java प्रोजेक्ट बनाएँ और अपने प्रोजेक्ट की निर्भरता में Aspose.Slides for Java जोड़ें। सुनिश्चित करें कि आवश्यक Aspose.Slides JAR फ़ाइल आपके प्रोजेक्ट के बिल्ड पथ में शामिल है।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
```
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
एक नया प्रेजेंटेशन इंस्टेंस बनाकर शुरुआत करें। यह आपके पावरपॉइंट डॉक्यूमेंट के रूप में काम करेगा, जहाँ आप स्लाइड और कंटेंट जोड़ेंगे।
```java
Presentation pres = new Presentation();
```
## चरण 3: स्लाइड तक पहुंचें
इसके बाद, उस स्लाइड पर पहुँचें जहाँ आप मल्टीलेवल बुलेट जोड़ना चाहते हैं। इस उदाहरण के लिए, हम पहली स्लाइड के साथ काम करेंगे (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## चरण 4: टेक्स्ट फ़्रेम के साथ ऑटोशेप जोड़ें
स्लाइड में एक ऑटोशेप जोड़ें जहां आप अपना टेक्स्ट बहुस्तरीय बुलेट्स के साथ रखेंगे।
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## चरण 5: टेक्स्ट फ़्रेम तक पहुँचें
ऑटोशेप के भीतर टेक्स्ट फ़्रेम तक पहुंचें जहां आप बुलेट पॉइंट के साथ पैराग्राफ जोड़ेंगे।
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //डिफ़ॉल्ट पैराग्राफ़ साफ़ करें
```
## चरण 6: बुलेट के साथ पैराग्राफ़ जोड़ें
अलग-अलग लेवल के बुलेट वाले पैराग्राफ जोड़ें। यहां बताया गया है कि आप मल्टीलेवल बुलेट कैसे जोड़ सकते हैं:
```java
// प्रथम स्तर
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// दूसरा स्तर
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// तीसरे स्तर
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// चौथा स्तर
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## चरण 7: प्रेजेंटेशन सहेजें
अंत में, प्रस्तुति को अपनी इच्छित निर्देशिका में PPTX फ़ाइल के रूप में सहेजें।
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने बताया है कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में मल्टीलेवल बुलेट कैसे बनाएं। इन चरणों का पालन करके, आप अपनी प्रस्तुतियों की स्पष्टता और दृश्य अपील को बढ़ाते हुए, विभिन्न स्तरों पर व्यवस्थित बुलेट बिंदुओं के साथ अपनी सामग्री को प्रभावी ढंग से संरचित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं बुलेट प्रतीकों को और अधिक अनुकूलित कर सकता हूँ?
हां, आप यूनिकोड वर्णों को समायोजित करके या विभिन्न आकृतियों का उपयोग करके बुलेट प्रतीकों को अनुकूलित कर सकते हैं।
### क्या Aspose.Slides अन्य बुलेट प्रकारों का समर्थन करता है?
हां, Aspose.Slides प्रतीकों, संख्याओं और कस्टम छवियों सहित विभिन्न प्रकार के बुलेट का समर्थन करता है।
### क्या Aspose.Slides PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides ऐसी प्रस्तुतियाँ तैयार करता है जो Microsoft PowerPoint 2007 और उच्चतर संस्करणों के साथ संगत हैं।
### क्या मैं Aspose.Slides का उपयोग करके स्लाइडों के निर्माण को स्वचालित कर सकता हूँ?
हां, Aspose.Slides पावरपॉइंट प्रस्तुतियों के निर्माण, संशोधन और हेरफेर को स्वचालित करने के लिए API प्रदान करता है।
### मैं Aspose.Slides for Java के लिए समर्थन कहां से प्राप्त कर सकता हूं?
 आप Aspose.Slides समुदाय और विशेषज्ञों से सहायता प्राप्त कर सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
