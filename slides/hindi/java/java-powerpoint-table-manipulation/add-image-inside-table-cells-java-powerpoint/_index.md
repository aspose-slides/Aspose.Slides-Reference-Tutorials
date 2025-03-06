---
title: जावा पावरपॉइंट में टेबल सेल के अंदर छवि जोड़ें
linktitle: जावा पावरपॉइंट में टेबल सेल के अंदर छवि जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके इस विस्तृत चरण-दर-चरण मार्गदर्शिका के साथ Java PowerPoint प्रस्तुतियों में तालिका कक्षों के अंदर छवियों को जोड़ने का तरीका जानें।
weight: 10
url: /hi/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
यदि आप टेबल सेल में इमेज एम्बेड करके अपने Java PowerPoint प्रेजेंटेशन को बेहतर बनाना चाहते हैं, तो आप सही जगह पर आए हैं! आज, हम Aspose.Slides for Java का उपयोग करके विस्तृत, चरण-दर-चरण मार्गदर्शिका में गोता लगाएँगे। यह ट्यूटोरियल आपको पूरी प्रक्रिया से गुजारेगा, यह सुनिश्चित करते हुए कि एक नौसिखिया भी इसका अनुसरण कर सकता है और आश्चर्यजनक परिणाम प्राप्त कर सकता है।
## आवश्यक शर्तें
आरंभ करने से पहले, आइए सुनिश्चित करें कि आपके पास वह सब कुछ है जो आपको चाहिए:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके मशीन पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं[ओरेकल की साइट](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Java के लिए Aspose.Slides: Aspose.Slides लाइब्रेरी को यहाँ से डाउनलोड करें[वेबसाइट](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): हम जावा विकास के लिए IntelliJ IDEA या Eclipse का उपयोग करने की अनुशंसा करते हैं।
4. छवि फ़ाइल: एक छवि फ़ाइल तैयार रखें जिसे आप अपने पावरपॉइंट तालिका कक्षों में एम्बेड करना चाहते हैं।
अब जब आपके पास सभी पूर्वापेक्षित शर्तें हैं, तो चलिए आवश्यक पैकेजों को आयात करने और कोड लिखने की ओर बढ़ते हैं।
## पैकेज आयात करें
सबसे पहले, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। ये पैकेज आपको Aspose.Slides और जावा की इमेज हैंडलिंग द्वारा प्रदान की गई कार्यक्षमताओं का उपयोग करने की अनुमति देंगे।
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
आइये इस उदाहरण को कई चरणों में विभाजित करें ताकि इसका अनुसरण करना आसान हो जाए।
## चरण 1: प्रस्तुति सेट करें
प्रस्तुति ऑब्जेक्ट को सेट करके और पहली स्लाइड तक पहुंचकर शुरुआत करें।
```java
// अपने दस्तावेज़ निर्देशिका का पथ निर्धारित करें
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास ऑब्जेक्ट को इंस्टैंसिएट करें
Presentation presentation = new Presentation();
```
यह कोड स्निपेट एक नई पावरपॉइंट प्रस्तुति को आरंभ करता है और उसे आगे के संशोधनों के लिए तैयार करता है।
## चरण 2: पहली स्लाइड तक पहुंचें
इसके बाद, प्रेजेंटेशन की पहली स्लाइड पर पहुँचें। यह स्लाइड वह कैनवास होगी जहाँ हम टेबल जोड़ेंगे।
```java
try {
    // पहली स्लाइड पर पहुँचें
    ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 3: तालिका आयाम परिभाषित करें
तालिका के लिए स्तंभों की चौड़ाई और पंक्तियों की ऊँचाई निर्धारित करें। यह चरण यह सुनिश्चित करने के लिए महत्वपूर्ण है कि आपकी तालिका कोशिकाओं के आयाम सही हों।
```java
    // स्तंभों को चौड़ाई और पंक्तियों को ऊँचाई के साथ परिभाषित करें
    double[] columns = {150, 150, 150, 150};
    double[] rows = {100, 100, 100, 100, 90};
```
## चरण 4: स्लाइड में तालिका जोड़ें
निर्दिष्ट आयामों का उपयोग करके स्लाइड में तालिका आकार जोड़ें।
```java
    // स्लाइड में तालिका आकार जोड़ें
    ITable table = slide.getShapes().addTable(50, 50, columns, rows);
```
## चरण 5: छवि लोड करें
वह छवि लोड करें जिसे आप टेबल सेल में एम्बेड करना चाहते हैं। सुनिश्चित करें कि छवि फ़ाइल आपकी निर्दिष्ट निर्देशिका में उपलब्ध है।
```java
    // छवि फ़ाइल को रखने के लिए BufferedImage ऑब्जेक्ट बनाएँ
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    // बिटमैप ऑब्जेक्ट का उपयोग करके IPPImage ऑब्जेक्ट बनाएँ
    IPPImage imgx = presentation.getImages().addImage(image);
```
## चरण 6: तालिका सेल में छवि जोड़ें
अब, तालिका के पहले सेल में छवि जोड़ने का समय आ गया है। भरण प्रारूप कॉन्फ़िगर करें और चित्र गुण सेट करें।
```java
    // पहले तालिका सेल में छवि जोड़ें
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## चरण 7: छवि क्रॉप समायोजित करें
यदि आवश्यक हो तो सेल के भीतर पूरी तरह से फिट होने के लिए छवि क्रॉपिंग को समायोजित करें। यह चरण सुनिश्चित करता है कि आपकी छवि बिल्कुल सही दिखती है।
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## चरण 8: प्रस्तुति सहेजें
अंत में, संशोधित प्रस्तुति को अपनी इच्छित निर्देशिका में सहेजें।
```java
    // PPTX को डिस्क पर सहेजें
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष
बस इतना ही! इन चरणों का पालन करके, आप Aspose.Slides का उपयोग करके Java PowerPoint प्रेजेंटेशन में टेबल सेल के अंदर सफलतापूर्वक छवियाँ जोड़ सकते हैं। इस गाइड में आपके वातावरण को सेट करने से लेकर अंतिम प्रेजेंटेशन को सहेजने तक सब कुछ शामिल है। मुझे उम्मीद है कि यह ट्यूटोरियल आपको अधिक आकर्षक प्रेजेंटेशन बनाने में मदद करेगा।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, जावा अनुप्रयोगों में पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और प्रबंधित करने के लिए एक शक्तिशाली API है।
### क्या Aspose.Slides के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप प्राप्त कर सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) खरीदने से पहले Aspose.Slides आज़माएँ.
### क्या मैं Aspose.Slides के साथ किसी भी छवि प्रारूप का उपयोग कर सकता हूँ?
Aspose.Slides JPEG, PNG, BMP, आदि सहित विभिन्न छवि प्रारूपों का समर्थन करता है।
### मैं अधिक विस्तृत दस्तावेज कहां पा सकता हूं?
 आप इसका संदर्भ ले सकते हैं[प्रलेखन](https://reference.aspose.com/slides/java/) अधिक विस्तृत जानकारी और उदाहरण के लिए.
### मैं Java के लिए Aspose.Slides कैसे खरीद सकता हूँ?
 आप इसे यहाँ से खरीद सकते हैं[Aspose वेबसाइट](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
