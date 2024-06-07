---
title: पावरपॉइंट में टिप्पणियाँ प्रस्तुत करें
linktitle: पावरपॉइंट में टिप्पणियाँ प्रस्तुत करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में टिप्पणियाँ प्रस्तुत करना सीखें। उपस्थिति को अनुकूलित करें और कुशलतापूर्वक छवि पूर्वावलोकन बनाएँ।
type: docs
weight: 10
url: /hi/java/java-powerpoint-rendering-techniques/render-comments-powerpoint/
---
## परिचय
इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में टिप्पणियाँ प्रस्तुत करने की प्रक्रिया के बारे में जानेंगे। टिप्पणियाँ प्रस्तुत करना विभिन्न उद्देश्यों के लिए उपयोगी हो सकता है, जैसे कि टिप्पणियों के साथ प्रस्तुतियों का छवि पूर्वावलोकन बनाना।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है।
2.  Aspose.Slides for Java: Aspose.Slides for Java लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/slides/java/).
3. IDE: जावा कोड लिखने और निष्पादित करने के लिए आपको एक एकीकृत विकास वातावरण (IDE) जैसे कि इक्लिप्स या इंटेलीज आईडिया की आवश्यकता होती है।
## पैकेज आयात करें
अपने जावा कोड में आवश्यक पैकेज आयात करके प्रारंभ करें:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.*;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## चरण 1: वातावरण तैयार करें
सबसे पहले, अपने प्रोजेक्ट की निर्भरता में Aspose.Slides लाइब्रेरी को शामिल करके अपना जावा वातावरण सेट करें। आप दिए गए लिंक से लाइब्रेरी डाउनलोड करके और इसे अपने प्रोजेक्ट के बिल्ड पथ में जोड़कर ऐसा कर सकते हैं।
## चरण 2: प्रस्तुति लोड करें
उस पावरपॉइंट प्रेजेंटेशन फ़ाइल को लोड करें जिसमें वे टिप्पणियाँ हैं जिन्हें आप प्रस्तुत करना चाहते हैं।
```java
String dataDir = "path/to/your/presentation/";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```
## चरण 3: रेंडरिंग विकल्प कॉन्फ़िगर करें
टिप्पणियों को कैसे प्रस्तुत किया जाए, इसे अनुकूलित करने के लिए रेंडरिंग विकल्पों को कॉन्फ़िगर करें।
```java
IRenderingOptions renderOptions = new RenderingOptions();
renderOptions.getNotesCommentsLayouting().setCommentsAreaColor(Color.RED);
renderOptions.getNotesCommentsLayouting().setCommentsAreaWidth(200);
renderOptions.getNotesCommentsLayouting().setCommentsPosition(CommentsPositions.Right);
renderOptions.getNotesCommentsLayouting().setNotesPosition(NotesPositions.BottomTruncated);
```
## चरण 4: छवि पर टिप्पणियाँ प्रस्तुत करें
निर्दिष्ट रेंडरिंग विकल्पों का उपयोग करके टिप्पणियों को एक छवि फ़ाइल में रेंडर करें।
```java
try {
    BufferedImage image = new BufferedImage(740, 960, BufferedImage.TYPE_INT_ARGB);
    Graphics2D graphics = image.createGraphics();
    try {
        pres.getSlides().get_Item(0).renderToGraphics(renderOptions, graphics);
    } finally {
        if (graphics != null) graphics.dispose();
    }
    ImageIO.write(image, "png", new File(resultPath));
} finally {
    if (pres != null) pres.dispose();
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में टिप्पणियाँ कैसे प्रस्तुत की जाती हैं। इन चरणों का पालन करके, आप टिप्पणियों सहित प्रस्तुतियों के छवि पूर्वावलोकन उत्पन्न कर सकते हैं, जिससे आपकी PowerPoint फ़ाइलों का दृश्य प्रतिनिधित्व बेहतर हो जाता है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं एकाधिक स्लाइडों से टिप्पणियाँ प्रस्तुत कर सकता हूँ?
हां, आप प्रस्तुति में सभी स्लाइडों को दोहरा सकते हैं और प्रत्येक स्लाइड से अलग-अलग टिप्पणियां प्रस्तुत कर सकते हैं।
### क्या प्रस्तुत टिप्पणियों के स्वरूप को अनुकूलित करना संभव है?
बिल्कुल, आप अपनी पसंद के अनुसार टिप्पणी क्षेत्र के रंग, आकार और स्थिति जैसे विभिन्न मापदंडों को समायोजित कर सकते हैं।
### क्या Aspose.Slides PNG के अलावा अन्य छवि प्रारूपों में टिप्पणियां प्रस्तुत करने का समर्थन करता है?
हां, PNG के अलावा, आप जावा के ImageIO वर्ग द्वारा समर्थित अन्य छवि प्रारूपों में भी टिप्पणियाँ प्रस्तुत कर सकते हैं।
### क्या मैं टिप्पणियों को पावरपॉइंट में प्रदर्शित किए बिना प्रोग्रामेटिक रूप से प्रस्तुत कर सकता हूँ?
हां, Aspose.Slides का उपयोग करके, आप PowerPoint एप्लिकेशन खोले बिना छवियों पर टिप्पणियां प्रस्तुत कर सकते हैं।
### क्या टिप्पणियों को सीधे पीडीएफ दस्तावेज़ में प्रस्तुत करने का कोई तरीका है?
हां, Aspose.Slides सीधे पीडीएफ दस्तावेजों में टिप्पणियां प्रस्तुत करने की कार्यक्षमता प्रदान करता है, जिससे आपके दस्तावेज़ वर्कफ़्लो में सहज एकीकरण की अनुमति मिलती है।