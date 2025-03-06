---
title: पावरपॉइंट में जॉइन स्टाइल्स को फॉर्मेट करें
linktitle: पावरपॉइंट में जॉइन स्टाइल्स को फॉर्मेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके आकृतियों के लिए अलग-अलग लाइन जॉइन स्टाइल सेट करके अपने PowerPoint प्रेजेंटेशन को बेहतर बनाने का तरीका जानें। हमारे चरण-दर-चरण गाइड का पालन करें।
weight: 15
url: /hi/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
आकर्षक दिखने वाले PowerPoint प्रेजेंटेशन बनाना एक कठिन काम हो सकता है, खासकर तब जब आप हर विवरण को परफेक्ट बनाना चाहते हैं। यहीं पर Aspose.Slides for Java काम आता है। यह एक शक्तिशाली API है जो आपको प्रोग्रामेटिक रूप से प्रेजेंटेशन बनाने, हेरफेर करने और प्रबंधित करने की अनुमति देता है। आप जिन सुविधाओं का उपयोग कर सकते हैं उनमें से एक है आकृतियों के लिए अलग-अलग लाइन जॉइन स्टाइल सेट करना, जो आपकी स्लाइड्स के सौंदर्य को काफी हद तक बढ़ा सकता है। इस ट्यूटोरियल में, हम इस बात पर चर्चा करेंगे कि आप PowerPoint प्रेजेंटेशन में आकृतियों के लिए जॉइन स्टाइल सेट करने के लिए Aspose.Slides for Java का उपयोग कैसे कर सकते हैं। 
## आवश्यक शर्तें
शुरू करने से पहले, आपके पास कुछ पूर्व-आवश्यकताएं होनी चाहिए:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके मशीन पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं[ओरेकल की वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java लाइब्रेरी: आपको Aspose.Slides for Java को डाउनलोड करके अपने प्रोजेक्ट में शामिल करना होगा। आप इसे यहाँ से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): अपने जावा कोड को लिखने और निष्पादित करने के लिए IntelliJ IDEA, Eclipse, या NetBeans जैसे IDE का उपयोग करें।
4. जावा का बुनियादी ज्ञान: जावा प्रोग्रामिंग की बुनियादी समझ आपको ट्यूटोरियल का अनुसरण करने में मदद करेगी।
## पैकेज आयात करें
सबसे पहले, आपको Aspose.Slides के लिए आवश्यक पैकेज आयात करने की आवश्यकता है। यह हमारे प्रेजेंटेशन मैनीपुलेशन के लिए आवश्यक क्लासेस और मेथड्स तक पहुँचने के लिए आवश्यक है।
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## चरण 1: प्रोजेक्ट निर्देशिका सेट अप करना
आइए अपनी प्रेजेंटेशन फ़ाइलों को संग्रहीत करने के लिए एक निर्देशिका बनाकर शुरू करें। यह सुनिश्चित करता है कि हमारी सभी फ़ाइलें व्यवस्थित और आसानी से सुलभ हैं।
```java
String dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
इस चरण में, हम एक निर्देशिका पथ परिभाषित करते हैं और जाँचते हैं कि क्या यह मौजूद है। यदि यह मौजूद नहीं है, तो हम निर्देशिका बनाते हैं। यह आपकी फ़ाइलों को व्यवस्थित रखने का एक सरल लेकिन प्रभावी तरीका है।
## चरण 2: प्रस्तुति आरंभ करें
 इसके बाद, हम उदाहरण देते हैं`Presentation` क्लास, जो हमारी पावरपॉइंट फ़ाइल का प्रतिनिधित्व करता है। यह वह आधार है जिस पर हम अपनी स्लाइड और आकृतियाँ बनाएंगे।
```java
Presentation pres = new Presentation();
```
कोड की यह पंक्ति एक नई प्रस्तुति बनाती है। इसे एक खाली पावरपॉइंट फ़ाइल खोलने के रूप में सोचें जहाँ आप अपनी सारी सामग्री जोड़ेंगे।
## चरण 3: स्लाइड में आकृतियाँ जोड़ें
### पहली स्लाइड प्राप्त करें
आकृतियाँ जोड़ने से पहले, हमें अपनी प्रस्तुति में पहली स्लाइड का संदर्भ प्राप्त करना होगा। डिफ़ॉल्ट रूप से, एक नई प्रस्तुति में एक खाली स्लाइड होती है।
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### आयताकार आकृतियाँ जोड़ें
अब, आइए अपनी स्लाइड में तीन आयताकार आकृतियाँ जोड़ें। ये आकृतियाँ अलग-अलग लाइन जॉइन शैलियों को प्रदर्शित करेंगी।
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
इस चरण में, हम स्लाइड पर निर्दिष्ट स्थानों पर तीन आयत जोड़ते हैं। प्रत्येक आयत को बाद में विभिन्न जॉइन शैलियों को दिखाने के लिए अलग-अलग स्टाइल किया जाएगा।
## चरण 4: आकृतियों को स्टाइल करें
### भरण रंग सेट करें
हम चाहते हैं कि हमारे आयतों को ठोस रंग से भरा जाए। यहाँ, हम भरने के रंग के लिए काला चुनते हैं।
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### लाइन की चौड़ाई और रंग सेट करें
इसके बाद, हम प्रत्येक आयत के लिए लाइन की चौड़ाई और रंग निर्धारित करते हैं। इससे जॉइन शैलियों को दृष्टिगत रूप से अलग करने में मदद मिलती है।
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## चरण 5: जॉइन स्टाइल लागू करें
इस ट्यूटोरियल का मुख्य आकर्षण लाइन जॉइन स्टाइल सेट करना है। हम तीन अलग-अलग स्टाइल का इस्तेमाल करेंगे: मिटर, बेवल और राउंड।
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
प्रत्येक लाइन जॉइन स्टाइल आकृतियों को कोनों पर एक अनूठा रूप देता है जहाँ रेखाएँ मिलती हैं। यह विशेष रूप से अलग-अलग आरेख या चित्र बनाने के लिए उपयोगी हो सकता है।
## चरण 6: आकृतियों में पाठ जोड़ें
यह स्पष्ट करने के लिए कि प्रत्येक आकृति क्या दर्शाती है, हम प्रत्येक आयत में प्रयुक्त संयोजन शैली का वर्णन करते हुए पाठ जोड़ते हैं।
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
जब आप स्लाइड प्रस्तुत या साझा करते हैं तो पाठ जोड़ने से विभिन्न शैलियों की पहचान करने में मदद मिलती है।
## चरण 7: प्रेजेंटेशन सहेजें
अंत में, हम अपनी प्रस्तुति को निर्दिष्ट निर्देशिका में सहेज लेते हैं।
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
यह कमांड प्रस्तुति को PPTX फ़ाइल में लिखता है, जिसे आप Microsoft PowerPoint या किसी अन्य संगत सॉफ़्टवेयर के साथ खोल सकते हैं।
## निष्कर्ष
और अब यह हो गया! आपने अभी-अभी तीन आयतों वाली एक पावरपॉइंट स्लाइड बनाई है, जिनमें से प्रत्येक Aspose.Slides for Java का उपयोग करके एक अलग लाइन जॉइन स्टाइल प्रदर्शित करती है। यह ट्यूटोरियल न केवल आपको Aspose.Slides की मूल बातें समझने में मदद करता है, बल्कि यह भी दिखाता है कि अनूठी शैलियों के साथ अपनी प्रस्तुतियों को कैसे बेहतर बनाया जाए। प्रस्तुतिकरण का आनंद लें!
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, पावरपॉइंट प्रस्तुतियों को प्रोग्रामेटिक रूप से बनाने, उनमें हेरफेर करने और प्रबंधन करने के लिए एक शक्तिशाली API है।
### क्या मैं किसी भी IDE में Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, आप किसी भी Java-समर्थित IDE जैसे IntelliJ IDEA, Eclipse, या NetBeans में Aspose.Slides for Java का उपयोग कर सकते हैं।
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### पावरपॉइंट में लाइन जॉइन शैलियाँ क्या हैं?
लाइन जॉइन स्टाइल उन कोनों के आकार को संदर्भित करते हैं जहाँ दो रेखाएँ मिलती हैं। आम शैलियों में मिटर, बेवल और राउंड शामिल हैं।
### मैं Aspose.Slides for Java पर अधिक दस्तावेज़ कहां पा सकता हूं?
 आप विस्तृत दस्तावेज पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
