---
title: पावरपॉइंट में ज्यामिति आकार में खंड जोड़ें
linktitle: पावरपॉइंट में ज्यामिति आकार में खंड जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: इस विस्तृत, चरण-दर-चरण मार्गदर्शिका के साथ Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में ज्यामिति आकृतियों में खंड जोड़ना सीखें।
type: docs
weight: 19
url: /hi/java/java-powerpoint-shape-formatting-geometry/add-segment-geometry-shape-powerpoint/
---
## परिचय
आकर्षक और गतिशील प्रस्तुतियाँ बनाना एक चुनौती हो सकती है, खासकर जब आप कस्टम आकार और डिज़ाइन जोड़ना चाहते हैं। यहीं पर Aspose.Slides for Java काम आता है। यह शक्तिशाली API आपको PowerPoint फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देता है, जिससे आपको जटिल ज्यामितीय आकृतियों और खंडों को आसानी से जोड़ने की सुविधा मिलती है। इस ट्यूटोरियल में, हम आपको बताएंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में ज्यामिति आकृतियों में खंड कैसे जोड़ें। चाहे आप एक डेवलपर हों जो प्रस्तुतियों के निर्माण को स्वचालित करना चाहते हैं या बस कोई ऐसा व्यक्ति जो कोडिंग में गोता लगाना पसंद करता है, यह मार्गदर्शिका आपके लिए व्यापक संसाधन होगी।
## आवश्यक शर्तें
इससे पहले कि हम चरण-दर-चरण मार्गदर्शिका में उतरें, कुछ पूर्व-आवश्यकताएं हैं जो आपके पास होनी चाहिए:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके मशीन पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं।[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: आपको Aspose.Slides for Java लाइब्रेरी डाउनलोड करनी होगी। आप इसे यहाँ से प्राप्त कर सकते हैं[वेबसाइट](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (आईडीई): इंटेलीज आईडीईए, एक्लिप्स या नेटबीन्स जैसे आईडीई कोडिंग को आसान और अधिक कुशल बना देंगे।
4. जावा का बुनियादी ज्ञान: इस ट्यूटोरियल का अनुसरण करने के लिए जावा प्रोग्रामिंग से परिचित होना आवश्यक है।
## पैकेज आयात करें
सबसे पहले, आपको Aspose.Slides से आवश्यक पैकेज आयात करने की आवश्यकता है। यह आपको PowerPoint प्रस्तुतियों को बनाने और उनमें हेरफेर करने के लिए आवश्यक सभी कार्यक्षमताओं तक पहुँचने की अनुमति देगा।
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
स्पष्टता और समझने में आसानी सुनिश्चित करने के लिए आइए ज्यामिति आकृतियों में खंडों को जोड़ने की प्रक्रिया को विस्तृत चरणों में विभाजित करें।
## चरण 1: एक नई प्रस्तुति बनाएँ
इस चरण में, हम Aspose.Slides का उपयोग करके एक नया पावरपॉइंट प्रेजेंटेशन बनाएंगे।
```java
Presentation pres = new Presentation();
try {
    // आपका कोड यहाँ
} finally {
    if (pres != null) pres.dispose();
}
```
 एक नया प्रेजेंटेशन बनाना उतना ही सरल है जितना कि`Presentation` क्लास। यह मेमोरी में एक नई पावरपॉइंट फ़ाइल आरंभ करता है जिसे आप हेरफेर कर सकते हैं।
## चरण 2: ज्यामिति आकार जोड़ें
इसके बाद, हम प्रेजेंटेशन की पहली स्लाइड में एक नया आकार जोड़ेंगे। इस उदाहरण के लिए, हम एक आयत जोड़ेंगे।
```java
GeometryShape shape = (GeometryShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
यहां, हम निर्देशांक (100, 100) पर 200 की चौड़ाई और 100 की ऊंचाई के साथ एक आयत आकार जोड़ रहे हैं।
## चरण 3: आकृति का ज्यामिति पथ प्राप्त करें
अब, हमें उस आकृति का ज्यामिति पथ प्राप्त करना होगा जिसे हमने अभी जोड़ा है। यह पथ आकृति की रूपरेखा को दर्शाता है।
```java
IGeometryPath geometryPath = shape.getGeometryPaths()[0];
```
`getGeometryPaths` विधि आकृति से जुड़े पथों की एक सरणी लौटाती है। चूँकि हम एक सरल आकृति के साथ काम कर रहे हैं, इसलिए हम पहले पथ तक सीधे पहुँच सकते हैं।
## चरण 4: ज्यामिति पथ में खंड जोड़ें
आकृति को संशोधित करने के लिए, हम इसके ज्यामिति पथ में नए खंड जोड़ सकते हैं। इस मामले में, हम दो रेखाखंड जोड़ेंगे।
```java
geometryPath.lineTo(100, 50, 1);
geometryPath.lineTo(100, 50, 4);
```
`lineTo` विधि ज्यामिति पथ में एक रेखाखंड जोड़ती है। पैरामीटर रेखा के अंत बिंदु और खंड के प्रकार को निर्दिष्ट करते हैं।
## चरण 5: संपादित ज्यामिति पथ को आकृति पर वापस असाइन करें
ज्यामिति पथ को संशोधित करने के बाद, हमें इसे वापस आकृति में निर्दिष्ट करना होगा।
```java
shape.setGeometryPath(geometryPath);
```
यह आकृति को नए ज्यामिति पथ के साथ अद्यतन करता है, जो हमारे द्वारा किए गए परिवर्तनों को दर्शाता है।
## चरण 6: प्रेजेंटेशन सहेजें
अंत में, प्रस्तुति को फ़ाइल में सहेजें.
```java
String resultPath = "GeometryShapeAddSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
वह पथ निर्दिष्ट करें जहाँ आप प्रस्तुति को सहेजना चाहते हैं और प्रारूप (इस मामले में PPTX) निर्दिष्ट करें।
## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में ज्यामिति आकृतियों में खंड जोड़ना एक सीधी प्रक्रिया है जो आपकी स्लाइड्स की दृश्य अपील को काफी हद तक बढ़ा सकती है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अनुकूलित आकृतियाँ बना सकते हैं और प्रोग्रामेटिक रूप से अपनी प्रस्तुतियों में जटिल विवरण जोड़ सकते हैं। चाहे आप प्रस्तुतियों के निर्माण को स्वचालित कर रहे हों या कोड के साथ प्रयोग कर रहे हों, Aspose.Slides for Java आपको काम को कुशलतापूर्वक पूरा करने के लिए आवश्यक उपकरण प्रदान करता है।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, पावरपॉइंट प्रस्तुतियों को प्रोग्रामेटिक रूप से बनाने, संशोधित करने और हेरफेर करने के लिए एक शक्तिशाली API है।
### क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
नहीं, Aspose.Slides for Java को खास तौर पर Java के साथ इस्तेमाल के लिए डिज़ाइन किया गया है। हालाँकि, Aspose .NET और Python जैसी दूसरी भाषाओं के लिए भी इसी तरह के API देता है।
### क्या Aspose.Slides for Java निःशुल्क है?
 Aspose.Slides for Java एक सशुल्क लाइब्रेरी है, लेकिन आप इसे डाउनलोड कर सकते हैं[मुफ्त परीक्षण](https://releases.aspose.com/) इसकी विशेषताओं का परीक्षण करने के लिए।
### Aspose.Slides का उपयोग करके मैं किसी प्रस्तुति में किस प्रकार की आकृतियाँ जोड़ सकता हूँ?
आप आयत, दीर्घवृत्त, रेखाएँ और कस्टम ज्यामिति आकृतियों सहित विभिन्न आकृतियाँ जोड़ सकते हैं।
### मैं Java के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 आप यहाँ से सहायता प्राप्त कर सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) जहां आप प्रश्न पूछ सकते हैं और समुदाय और डेवलपर्स से सहायता प्राप्त कर सकते हैं।