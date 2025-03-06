---
title: पावरपॉइंट में आकृति क्रम बदलें
linktitle: पावरपॉइंट में आकृति क्रम बदलें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: इस चरण-दर-चरण ट्यूटोरियल के साथ Aspose.Slides for Java का उपयोग करके PowerPoint में आकार क्रम को बदलना सीखें। अपने प्रेजेंटेशन कौशल को सहजता से बढ़ाएँ।
weight: 15
url: /hi/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
दिखने में आकर्षक और अच्छी तरह से संरचित प्रस्तुतियाँ बनाना एक कठिन काम हो सकता है। हालाँकि, सही उपकरणों और तकनीकों के साथ, आप इसे काफी आसान बना सकते हैं। Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो आपको PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से हेरफेर और प्रबंधित करने में मदद करती है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में आकार क्रम बदलने के चरणों के बारे में बताएँगे।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके मशीन पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं।[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java लाइब्रेरी: यहां से नवीनतम संस्करण डाउनलोड करें[Aspose.Slides for Java डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (आईडीई): कोडिंग के लिए इंटेलीज आईडीईए या एक्लिप्स जैसे आईडीई का उपयोग करें।
4. प्रस्तुति फ़ाइल: एक पावरपॉइंट फ़ाइल तैयार रखें जिसे आप संशोधित करना चाहते हैं।
## पैकेज आयात करें
आरंभ करने के लिए, आपको Aspose.Slides लाइब्रेरी से आवश्यक पैकेज आयात करने होंगे। ये आयात आपको प्रस्तुतियों, स्लाइडों और आकृतियों के साथ काम करने की अनुमति देंगे।
```java
import com.aspose.slides.*;

```
इस गाइड में, हम बेहतर समझ और कार्यान्वयन में आसानी के लिए आकार क्रम बदलने की प्रक्रिया को कई चरणों में विभाजित करेंगे।
## चरण 1: प्रस्तुति लोड करें
 सबसे पहले, आपको उस पावरपॉइंट प्रेजेंटेशन फ़ाइल को लोड करना होगा जिसके साथ आप काम करना चाहते हैं। इस चरण में आरंभीकरण शामिल है`Presentation` क्लास में अपनी पावरपॉइंट फ़ाइल का पथ लिखें।
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## चरण 2: इच्छित स्लाइड तक पहुंचें
एक बार प्रस्तुति लोड हो जाने के बाद, उस स्लाइड तक पहुँचें जहाँ आप आकृतियों को पुनः क्रमित करना चाहते हैं। स्लाइड्स को 0 से शुरू करके अनुक्रमित किया जाता है, इसलिए पहली स्लाइड तक पहुँचने के लिए, इंडेक्स 0 का उपयोग करें।
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## चरण 3: स्लाइड में आकृतियाँ जोड़ें
इसके बाद, स्लाइड में आकृतियाँ जोड़ें। प्रदर्शन के लिए, हम स्लाइड में एक आयत और एक त्रिभुज आकृति जोड़ेंगे।
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## चरण 4: आकृतियों को पुनः क्रमित करें
 अब, स्लाइड पर आकृतियों को पुनः क्रमित करें।`reorder` विधि आपको स्लाइड के आकृति संग्रह के भीतर आकृति के लिए नई स्थिति निर्दिष्ट करने की अनुमति देती है।
```java
slide.getShapes().reorder(2, shp3);
```
## चरण 5: संशोधित प्रस्तुति को सहेजें
आकृतियों को पुनः क्रमित करने के बाद, संशोधित प्रस्तुति को एक नई फ़ाइल में सहेजें। यह सुनिश्चित करता है कि आपकी मूल फ़ाइल अपरिवर्तित रहे।
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## चरण 6: संसाधनों को साफ करें
अंत में, संसाधनों को मुक्त करने के लिए प्रस्तुति ऑब्जेक्ट को हटा दें।
```java
if (presentation1 != null) presentation1.dispose();
```
## निष्कर्ष
इन चरणों का पालन करके, आप आसानी से Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में आकृतियों के क्रम को बदल सकते हैं। यह शक्तिशाली लाइब्रेरी PowerPoint प्रस्तुतियों से जुड़े कई कार्यों को सरल बनाती है, जिससे आप प्रोग्रामेटिक रूप से स्लाइड बना और उनमें हेरफेर कर सकते हैं। चाहे आप प्रस्तुतियों के निर्माण को स्वचालित कर रहे हों या आपको केवल बल्क परिवर्तन करने की आवश्यकता हो, Aspose.Slides for Java एक अमूल्य उपकरण है।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक जावा एपीआई है, जो माइक्रोसॉफ्ट पावरपॉइंट का उपयोग किए बिना पावरपॉइंट प्रस्तुतियों को बनाने और उनमें हेरफेर करने के लिए उपयोग किया जाता है।
### क्या मैं अन्य Java IDE के साथ Aspose.Slides for Java का उपयोग कर सकता हूँ?
हां, आप इसे किसी भी जावा आईडीई जैसे इंटेलीज आईडीईए, एक्लिप्स या नेटबीन्स के साथ उपयोग कर सकते हैं।
### क्या Aspose.Slides for Java सभी PowerPoint प्रारूपों के साथ संगत है?
हां, Aspose.Slides for Java PPT, PPTX और अन्य PowerPoint प्रारूपों का समर्थन करता है।
### मैं Java के लिए Aspose.Slides का निःशुल्क परीक्षण कैसे प्राप्त कर सकता हूँ?
 आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[Aspose.Slides for Java डाउनलोड पृष्ठ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java पर अधिक दस्तावेज़ कहां पा सकता हूं?
 आप विस्तृत दस्तावेज यहाँ पा सकते हैं[Aspose.Slides for Java दस्तावेज़न पृष्ठ](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
