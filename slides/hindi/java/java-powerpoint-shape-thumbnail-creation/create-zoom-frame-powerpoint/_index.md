---
title: पावरपॉइंट में ज़ूम फ़्रेम बनाएँ
linktitle: पावरपॉइंट में ज़ूम फ़्रेम बनाएँ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint में आकर्षक ज़ूम फ़्रेम बनाने का तरीका जानें। अपनी प्रस्तुतियों में इंटरैक्टिव तत्व जोड़ने के लिए हमारी मार्गदर्शिका का पालन करें।
weight: 17
url: /hi/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
आकर्षक पावरपॉइंट प्रेजेंटेशन बनाना एक कला है, और कभी-कभी, सबसे छोटी-छोटी चीज़ें भी बहुत बड़ा अंतर ला सकती हैं। ऐसी ही एक विशेषता है ज़ूम फ़्रेम, जो आपको विशिष्ट स्लाइड या छवियों में ज़ूम करने की अनुमति देता है, जिससे एक गतिशील और इंटरैक्टिव प्रेजेंटेशन बनता है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint में ज़ूम फ़्रेम बनाने की प्रक्रिया के बारे में बताएँगे।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- एक एकीकृत विकास वातावरण (IDE) जैसे कि IntelliJ IDEA या Eclipse.
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
## पैकेज आयात करें
आरंभ करने के लिए, आपको अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करने की आवश्यकता है। ये आयात इस ट्यूटोरियल के लिए आवश्यक Aspose.Slides कार्यक्षमताओं तक पहुँच प्रदान करेंगे।
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## चरण 1: प्रस्तुतिकरण सेट करना
सबसे पहले, हमें एक नई प्रस्तुति बनानी होगी और उसमें कुछ स्लाइडें जोड़नी होंगी।
```java
// आउटपुट फ़ाइल नाम
String resultPath = "ZoomFramePresentation.pptx";
// स्रोत छवि का पथ
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    // प्रस्तुति में नई स्लाइड जोड़ें
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## चरण 2: स्लाइड पृष्ठभूमि को अनुकूलित करना
हम पृष्ठभूमि रंग जोड़कर अपनी स्लाइडों को दृश्यात्मक रूप से विशिष्ट बनाना चाहते हैं।
### दूसरी स्लाइड के लिए पृष्ठभूमि सेट करना
```java
    // दूसरी स्लाइड के लिए पृष्ठभूमि बनाएँ
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // दूसरी स्लाइड के लिए टेक्स्ट बॉक्स बनाएँ
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### तीसरी स्लाइड के लिए पृष्ठभूमि सेट करना
```java
    // तीसरी स्लाइड के लिए पृष्ठभूमि बनाएं
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // तीसरी स्लाइड के लिए टेक्स्ट बॉक्स बनाएं
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## चरण 3: ज़ूम फ़्रेम जोड़ना
अब, प्रेजेंटेशन में ज़ूम फ़्रेम जोड़ें। हम एक ज़ूम फ़्रेम को स्लाइड पूर्वावलोकन के साथ और दूसरे को कस्टम इमेज के साथ जोड़ेंगे।
### स्लाइड पूर्वावलोकन के साथ ज़ूम फ़्रेम जोड़ना
```java
    // स्लाइड पूर्वावलोकन के साथ ज़ूमफ़्रेम ऑब्जेक्ट जोड़ें
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### कस्टम छवि के साथ ज़ूम फ़्रेम जोड़ना
```java
    // कस्टम छवि के साथ ज़ूमफ़्रेम ऑब्जेक्ट जोड़ें
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## चरण 4: ज़ूम फ़्रेम को अनुकूलित करना
अपने ज़ूम फ्रेम्स को अलग दिखाने के लिए, हम उनके स्वरूप को अनुकूलित करेंगे।
### दूसरे ज़ूम फ़्रेम को अनुकूलित करना
```java
    // zoomFrame2 ऑब्जेक्ट के लिए ज़ूम फ़्रेम प्रारूप सेट करें
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### पहले ज़ूम फ़्रेम के लिए पृष्ठभूमि छिपाना
```java
    // ज़ूमफ़्रेम1 ऑब्जेक्ट के लिए पृष्ठभूमि न दिखाएँ
    zoomFrame1.setShowBackground(false);
```
## चरण 5: प्रस्तुति को सहेजना
अंत में, हम अपनी प्रस्तुति को निर्दिष्ट पथ पर सेव कर देते हैं।
```java
    // प्रस्तुति सहेजें
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint में ज़ूम फ़्रेम बनाना आपके प्रेजेंटेशन की अन्तरक्रियाशीलता और सहभागिता को महत्वपूर्ण रूप से बढ़ा सकता है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप आसानी से स्लाइड पूर्वावलोकन और कस्टम इमेज दोनों को ज़ूम फ़्रेम के रूप में जोड़ सकते हैं, उन्हें अपनी प्रस्तुति की थीम के अनुसार अनुकूलित कर सकते हैं। प्रस्तुतिकरण का आनंद लें!
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, पावरपॉइंट प्रस्तुतियों को प्रोग्रामेटिक रूप से बनाने और उनमें बदलाव करने के लिए एक शक्तिशाली API है।
### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?
 आप Java के लिए Aspose.Slides को यहाँ से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/slides/java/) और इसे अपने प्रोजेक्ट की निर्भरताओं में जोड़ें.
### क्या मैं ज़ूम फ़्रेम के स्वरूप को अनुकूलित कर सकता हूँ?
हां, Aspose.Slides आपको ज़ूम फ्रेम्स के विभिन्न गुणों को अनुकूलित करने की अनुमति देता है, जैसे लाइन शैली, रंग और पृष्ठभूमि दृश्यता।
### क्या ज़ूम फ्रेम्स में छवियाँ जोड़ना संभव है?
बिल्कुल! आप इमेज फ़ाइलों को पढ़कर और उन्हें प्रेजेंटेशन में जोड़कर ज़ूम फ़्रेम में कस्टम इमेज जोड़ सकते हैं।
### मैं और अधिक उदाहरण और दस्तावेज कहां पा सकता हूं?
 आप यहाँ पर विस्तृत दस्तावेज और उदाहरण पा सकते हैं।[Aspose.Slides for Java दस्तावेज़न पृष्ठ](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
