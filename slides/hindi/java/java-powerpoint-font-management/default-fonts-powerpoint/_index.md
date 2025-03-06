---
title: Java के लिए Aspose.Slides के साथ PowerPoint में डिफ़ॉल्ट फ़ॉन्ट्स
linktitle: Java के लिए Aspose.Slides के साथ PowerPoint में डिफ़ॉल्ट फ़ॉन्ट्स
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में डिफ़ॉल्ट फ़ॉन्ट सेट करना सीखें। सहजता से स्थिरता सुनिश्चित करें और दृश्य अपील बढ़ाएँ।
weight: 11
url: /hi/java/java-powerpoint-font-management/default-fonts-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
कस्टम फ़ॉन्ट के साथ PowerPoint प्रस्तुतियाँ बनाना कई परियोजनाओं में एक सामान्य आवश्यकता है। Aspose.Slides for Java डिफ़ॉल्ट फ़ॉन्ट प्रबंधित करने के लिए एक सहज समाधान प्रदान करता है, जो विभिन्न वातावरणों में एकरूपता सुनिश्चित करता है। इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में डिफ़ॉल्ट फ़ॉन्ट सेट करने की प्रक्रिया के बारे में बताएँगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है।
2.  Aspose.Slides for Java: Aspose.Slides for Java को डाउनलोड करें और इंस्टॉल करें[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. बुनियादी जावा ज्ञान: जावा प्रोग्रामिंग भाषा के मूल सिद्धांतों से परिचित होना।

## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके प्रारंभ करें:
```java
import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## चरण 1: डिफ़ॉल्ट फ़ॉन्ट सेट करें
अपने दस्तावेज़ निर्देशिका का पथ परिभाषित करें और डिफ़ॉल्ट नियमित और एशियाई फ़ॉन्ट निर्दिष्ट करने के लिए लोड विकल्प बनाएं:
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## चरण 2: प्रस्तुति लोड करें
निर्धारित लोड विकल्पों का उपयोग करके पावरपॉइंट प्रस्तुति लोड करें:
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## चरण 3: आउटपुट उत्पन्न करें
स्लाइड थंबनेल, पीडीएफ और एक्सपीएस फ़ाइलें जैसे विभिन्न आउटपुट उत्पन्न करें:
```java
try {
    // स्लाइड थंबनेल उत्पन्न करें
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // पीडीएफ उत्पन्न करें
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // XPS उत्पन्न करें
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में डिफ़ॉल्ट फ़ॉन्ट सेट करना सरल और कुशल है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप विभिन्न प्लेटफ़ॉर्म और वातावरण में फ़ॉन्ट शैलियों में एकरूपता सुनिश्चित कर सकते हैं, जिससे आपकी प्रस्तुतियों की दृश्य अपील बढ़ जाती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides for Java के साथ कस्टम फ़ॉन्ट का उपयोग कर सकता हूँ?
हां, आप Java के लिए Aspose.Slides का उपयोग करके अपनी प्रस्तुतियों में कस्टम फ़ॉन्ट निर्दिष्ट कर सकते हैं।
### क्या Aspose.Slides for Java PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides for Java, PowerPoint के विभिन्न संस्करणों का समर्थन करता है, तथा विभिन्न वातावरणों में संगतता सुनिश्चित करता है।
### मैं Java के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 आप Aspose.Slides for Java के लिए समर्थन प्राप्त कर सकते हैं[Aspose फ़ोरम](https://forum.aspose.com/c/slides/11).
### क्या मैं खरीदने से पहले Aspose.Slides for Java आज़मा सकता हूँ?
 हां, आप यहां उपलब्ध निःशुल्क परीक्षण के माध्यम से Aspose.Slides for Java का पता लगा सकते हैं[रिलीज़.aspose.com](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस कहां से प्राप्त कर सकता हूं?
 आप Aspose.Slides for Java के लिए अस्थायी लाइसेंस यहाँ से प्राप्त कर सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
