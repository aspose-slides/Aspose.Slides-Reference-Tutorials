---
title: पावरपॉइंट में कनेक्टर लाइन कोण सेट करें
linktitle: पावरपॉइंट में कनेक्टर लाइन कोण सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में कनेक्टर लाइन कोण सेट करना सीखें। अपनी स्लाइड्स को सटीकता के साथ कस्टमाइज़ करें।
weight: 17
url: /hi/java/java-powerpoint-animation-shape-manipulation/set-connector-line-angle-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में कनेक्टर लाइनों का कोण कैसे सेट करें। कनेक्टर लाइनें आपकी स्लाइड में आकृतियों के बीच संबंधों और प्रवाह को दर्शाने के लिए आवश्यक हैं। उनके कोणों को समायोजित करके, आप यह सुनिश्चित कर सकते हैं कि आपकी प्रस्तुतियाँ आपके संदेश को स्पष्ट और प्रभावी ढंग से व्यक्त करें।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपके सिस्टम पर JDK (जावा डेवलपमेंट किट) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके प्रोजेक्ट में जोड़ दी गई। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। सुनिश्चित करें कि आपने PowerPoint कार्यक्षमताओं तक पहुँचने के लिए Aspose.Slides लाइब्रेरी शामिल की है।
```java
import com.aspose.slides.*;

```
## चरण 1: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
अपनी पावरपॉइंट फ़ाइल को लोड करने के लिए प्रेजेंटेशन ऑब्जेक्ट को आरंभीकृत करके आरंभ करें।
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
## चरण 2: स्लाइड और आकृतियों तक पहुँचें
कनेक्टर लाइनों की पहचान करने के लिए स्लाइड और उसके आकार तक पहुंचें।
```java
Slide slide = (Slide) pres.getSlides().get_Item(0);
Shape shape;
```
## चरण 3: आकृतियों के माध्यम से पुनरावृति करें
कनेक्टर लाइनों और उनके गुणों को पहचानने के लिए स्लाइड पर प्रत्येक आकृति को दोहराएं।
```java
for (int i = 0; i < slide.getShapes().size(); i++) {
    double dir = 0.0;
    shape = (Shape) slide.getShapes().get_Item(i);
    if (shape instanceof AutoShape) {
        AutoShape ashp = (AutoShape) shape;
        if (ashp.getShapeType() == ShapeType.Line) {
            // हैंडल लाइन आकार
            dir = getDirection(ashp.getWidth(), ashp.getHeight(), ashp.getFrame().getFlipH() != 0, ashp.getFrame().getFlipV() != 0);
        }
    } else if (shape instanceof Connector) {
        // हैंडल कनेक्टर आकार
        Connector ashp = (Connector) shape;
        dir = getDirection(ashp.getWidth(), ashp.getHeight(), ashp.getFrame().getFlipH() != 0, ashp.getFrame().getFlipV() != 0);
    }
    System.out.println(dir);
}
```
## चरण 4: कोण की गणना करें
कनेक्टर लाइन के कोण की गणना करने के लिए getDirection विधि को कार्यान्वित करें।
```java
public static double getDirection(float w, float h, boolean flipH, boolean flipV) {
    float endLineX = w * (flipH ? -1 : 1);
    float endLineY = h * (flipV ? -1 : 1);
    float endYAxisX = 0;
    float endYAxisY = h;
    double angle = (Math.atan2(endYAxisY, endYAxisX) - Math.atan2(endLineY, endLineX));
    if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में कनेक्टर लाइनों के कोणों में हेरफेर कैसे करें। इन चरणों का पालन करके, आप अपने डेटा और अवधारणाओं को सटीकता के साथ विज़ुअल रूप से प्रस्तुत करने के लिए अपनी स्लाइड्स को प्रभावी ढंग से अनुकूलित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अन्य Java लाइब्रेरीज़ के साथ Aspose.Slides for Java का उपयोग कर सकता हूँ?
बिल्कुल! Aspose.Slides for Java आपके प्रेजेंटेशन निर्माण और प्रबंधन अनुभव को बढ़ाने के लिए अन्य Java लाइब्रेरीज़ के साथ सहजता से एकीकृत होता है।
### क्या Aspose.Slides सरल और जटिल दोनों प्रकार के PowerPoint कार्यों के लिए उपयुक्त है?
हां, Aspose.Slides विभिन्न PowerPoint आवश्यकताओं को पूरा करने के लिए कार्यात्मकता की एक विस्तृत श्रृंखला प्रदान करता है, जिसमें बुनियादी स्लाइड मैनीपुलेशन से लेकर उन्नत फॉर्मेटिंग और एनीमेशन कार्य शामिल हैं।
### क्या Aspose.Slides सभी PowerPoint सुविधाओं का समर्थन करता है?
Aspose.Slides अधिकांश PowerPoint सुविधाओं का समर्थन करने का प्रयास करता है। हालाँकि, विशिष्ट या उन्नत कार्यक्षमताओं के लिए, दस्तावेज़ों से परामर्श करना या Aspose समर्थन तक पहुँचना अनुशंसित है।
### क्या मैं Aspose.Slides के साथ कनेक्टर लाइन शैलियों को अनुकूलित कर सकता हूं?
निश्चित रूप से! Aspose.Slides कनेक्टर लाइनों को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है, जिसमें स्टाइल, मोटाई और समापन बिंदु शामिल हैं, जिससे आप आकर्षक प्रस्तुतियाँ बना सकते हैं।
### मैं Aspose.Slides-संबंधित प्रश्नों के लिए समर्थन कहां पा सकता हूं?
 आप यहां जा सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) विकास प्रक्रिया के दौरान आपके सामने आने वाली किसी भी समस्या या प्रश्न के लिए सहायता हेतु हमसे संपर्क करें।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
