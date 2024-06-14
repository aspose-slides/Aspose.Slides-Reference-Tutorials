---
title: सीमा आकार थंबनेल बनाएँ
linktitle: सीमा आकार थंबनेल बनाएँ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके बाउंड के साथ आकार थंबनेल बनाना सीखें। यह चरण-दर-चरण ट्यूटोरियल आपको प्रक्रिया के माध्यम से मार्गदर्शन करता है।
type: docs
weight: 10
url: /hi/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---
## परिचय
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो जावा डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके सीमाओं के साथ एक आकृति की थंबनेल छवि कैसे बनाई जाए।
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2.  Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके प्रोजेक्ट में जोड़ दी गई। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
सुनिश्चित करें कि आप अपने जावा कोड में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने पसंदीदा IDE में एक नया Java प्रोजेक्ट बनाएं और अपने प्रोजेक्ट की निर्भरताओं में Aspose.Slides for Java लाइब्रेरी जोड़ें।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंशिएट करें
 एक उदाहरण बनाना`Presentation` अपनी पावरपॉइंट प्रेजेंटेशन फ़ाइल का पथ प्रदान करके ऑब्जेक्ट को चुनें।
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## चरण 3: सीमा आकार थंबनेल बनाएँ
अब, आइए प्रस्तुति से सीमाओं के साथ एक आकृति की थंबनेल छवि बनाएं।
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके किसी आकृति की थंबनेल छवि कैसे बनाई जाती है। इन चरणों का पालन करके, आप आसानी से अपने PowerPoint प्रस्तुतियों में प्रोग्रामेटिक रूप से आकृतियों के थंबनेल बना सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं किसी स्लाइड में विशिष्ट आकृतियों के लिए थंबनेल बना सकता हूँ?
हां, आप Aspose.Slides for Java का उपयोग करके स्लाइड के भीतर अलग-अलग आकृतियों तक पहुंच सकते हैं और उनके लिए थंबनेल बना सकते हैं।
### क्या Aspose.Slides for Java PowerPoint फ़ाइलों के सभी संस्करणों के साथ संगत है?
Aspose.Slides for Java विभिन्न PowerPoint फ़ाइल स्वरूपों का समर्थन करता है, जिनमें PPT, PPTX, PPS, PPSX, आदि शामिल हैं।
### क्या मैं उत्पन्न थंबनेल छवियों के स्वरूप को अनुकूलित कर सकता हूँ?
हां, आप अपनी आवश्यकताओं के अनुसार थंबनेल छवियों के गुणों, जैसे आकार और गुणवत्ता, को समायोजित कर सकते हैं।
### क्या Aspose.Slides for Java थंबनेल निर्माण के अलावा अन्य सुविधाओं का समर्थन करता है?
हां, Aspose.Slides for Java पावरपॉइंट प्रस्तुतियों के साथ काम करने के लिए व्यापक कार्यक्षमता प्रदान करता है, जिसमें स्लाइड मैनीपुलेशन, टेक्स्ट निष्कर्षण और चार्ट निर्माण शामिल है।
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).