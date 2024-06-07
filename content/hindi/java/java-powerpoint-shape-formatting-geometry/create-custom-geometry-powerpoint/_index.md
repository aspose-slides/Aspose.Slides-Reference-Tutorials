---
title: पावरपॉइंट में कस्टम ज्यामिति बनाएं
linktitle: पावरपॉइंट में कस्टम ज्यामिति बनाएं
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Aspose.Slides for Java का उपयोग करके PowerPoint में कस्टम ज्यामिति आकृतियाँ कैसे बनाएँ। यह मार्गदर्शिका आपको अद्वितीय आकृतियों के साथ अपनी प्रस्तुतियों को बेहतर बनाने में मदद करेगी।
type: docs
weight: 21
url: /hi/java/java-powerpoint-shape-formatting-geometry/create-custom-geometry-powerpoint/
---
## परिचय
PowerPoint में कस्टम आकार और ज्यामिति बनाना आपके प्रस्तुतियों की दृश्य अपील को काफी हद तक बढ़ा सकता है। Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को PowerPoint फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देती है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में कस्टम ज्यामिति, विशेष रूप से एक स्टार आकार कैसे बनाया जाए। आइए गोता लगाएँ!
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है।
2. Java के लिए Aspose.Slides: Aspose.Slides लाइब्रेरी डाउनलोड और इंस्टॉल करें।
   - [Java के लिए Aspose.Slides डाउनलोड करें](https://releases.aspose.com/slides/java/)
3. आईडीई (एकीकृत विकास पर्यावरण): इंटेलीज आईडिया या एक्लिप्स जैसा एक आईडीई।
4. जावा की बुनियादी समझ: जावा प्रोग्रामिंग से परिचित होना आवश्यक है।
## पैकेज आयात करें
कोडिंग भाग में जाने से पहले, आइए आवश्यक पैकेजों को आयात करें।
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.geom.Point2D;
import java.util.ArrayList;
import java.util.List;
```
## चरण 1: प्रोजेक्ट की स्थापना
शुरू करने के लिए, अपना जावा प्रोजेक्ट सेट अप करें और अपने प्रोजेक्ट की निर्भरताओं में Aspose.Slides for Java लाइब्रेरी शामिल करें। यदि आप Maven का उपयोग कर रहे हैं, तो अपने प्रोजेक्ट में निम्न निर्भरता जोड़ें`pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>YOUR_VERSION_HERE</version>
</dependency>
```
## चरण 2: प्रस्तुति आरंभ करें
इस चरण में, हम एक नई पावरपॉइंट प्रस्तुति आरंभ करेंगे।
```java
public static void main(String[] args) throws Exception {
    // प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
    Presentation pres = new Presentation();
    try {
        // आपका कोड यहां जाएगा
    } finally {
        if (pres != null) pres.dispose();
    }
}
```
## चरण 3: स्टार ज्यामिति पथ बनाएँ
हमें एक ऐसी विधि बनाने की ज़रूरत है जो किसी तारे के आकार के लिए ज्यामिति पथ उत्पन्न करे। यह विधि बाहरी और आंतरिक त्रिज्या के आधार पर तारे के बिंदुओं की गणना करती है।
```java
private static GeometryPath createStarGeometry(float outerRadius, float innerRadius) {
    GeometryPath starPath = new GeometryPath();
    List<Point2D.Float> points = new ArrayList<>();
    int step = 72; // तारा बिंदुओं के बीच का कोण
    for (int angle = -90; angle < 270; angle += step) {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.cos(radians);
        double y = outerRadius * Math.sin(radians);
        points.add(new Point2D.Float((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.cos(radians);
        y = innerRadius * Math.sin(radians);
        points.add(new Point2D.Float((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.moveTo(points.get(0));
    for (int i = 1; i < points.size(); i++) {
        starPath.lineTo(points.get(i));
    }
    starPath.closeFigure();
    return starPath;
}
```
## चरण 4: स्लाइड में कस्टम आकार जोड़ें
इसके बाद, हम पिछले चरण में बनाए गए स्टार ज्यामिति पथ का उपयोग करके अपनी प्रस्तुति की पहली स्लाइड में एक कस्टम आकार जोड़ेंगे।
```java
// स्लाइड में कस्टम आकार जोड़ें
float R = 100, r = 50; // बाह्य और आंतरिक तारा त्रिज्या
GeometryPath starPath = createStarGeometry(R, r);
// नया आकार बनाएं
GeometryShape shape = (GeometryShape)pres.getSlides().get_Item(0).
        getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
// आकृति के लिए नया ज्यामिति पथ सेट करें
shape.setGeometryPath(starPath);
```
## चरण 5: प्रस्तुति सहेजें
अंत में, प्रस्तुति को फ़ाइल में सहेजें.
```java
// आउटपुट फ़ाइल नाम
String resultPath = "GeometryShapeCreatesCustomGeometry.pptx";
// प्रस्तुति सहेजें
pres.save(resultPath, SaveFormat.Pptx);
```

## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint में कस्टम ज्यामिति बनाना सरल है और आपकी प्रस्तुतियों में बहुत अधिक दृश्य रुचि जोड़ता है। कोड की केवल कुछ पंक्तियों के साथ, आप सितारों जैसी जटिल आकृतियाँ बना सकते हैं और उन्हें अपनी स्लाइड में एम्बेड कर सकते हैं। इस गाइड में प्रोजेक्ट को सेट अप करने से लेकर अंतिम प्रस्तुति को सहेजने तक की प्रक्रिया को चरण-दर-चरण कवर किया गया है।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो जावा डेवलपर्स को प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और प्रबंधित करने में सक्षम बनाती है।
### क्या मैं तारों के अलावा अन्य आकृतियाँ भी बना सकता हूँ?
हां, आप उनके ज्यामिति पथ को परिभाषित करके विभिन्न कस्टम आकार बना सकते हैं।
### क्या Aspose.Slides for Java निःशुल्क है?
Aspose.Slides for Java निःशुल्क परीक्षण प्रदान करता है। विस्तारित उपयोग के लिए, आपको लाइसेंस खरीदना होगा।
### क्या मुझे Aspose.Slides for Java चलाने के लिए किसी विशेष सेटअप की आवश्यकता है?
JDK को स्थापित करने और अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी को शामिल करने के अलावा किसी विशेष सेटअप की आवश्यकता नहीं है।
### मुझे Aspose.Slides के लिए समर्थन कहां मिल सकता है?
 आप यहाँ से सहायता प्राप्त कर सकते हैं[Aspose.Slides समर्थन मंच](https://forum.aspose.com/c/slides/11).