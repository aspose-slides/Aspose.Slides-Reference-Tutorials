---
title: जावा के साथ पावरपॉइंट में मानक तालिकाएँ बनाएँ
linktitle: जावा के साथ पावरपॉइंट में मानक तालिकाएँ बनाएँ
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java के साथ PowerPoint में मानक तालिकाएँ बनाना सीखें। सहज अनुभव के लिए हमारी विस्तृत, चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 21
url: /hi/java/java-powerpoint-table-manipulation/create-standard-tables-powerpoint-java/
---
## परिचय
दृश्य रूप से आकर्षक पावरपॉइंट प्रेजेंटेशन बनाने में अक्सर डेटा को व्यवस्थित और स्पष्ट रूप से प्रस्तुत करने के लिए टेबल जैसे विभिन्न तत्वों को जोड़ना शामिल होता है। जावा के लिए Aspose.Slides प्रोग्रामेटिक रूप से पावरपॉइंट फ़ाइलों के साथ काम करने के लिए एक मजबूत API प्रदान करता है। यह ट्यूटोरियल आपको जावा का उपयोग करके पावरपॉइंट में मानक टेबल बनाने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा, एक सहज और व्यापक सीखने के अनुभव को सुनिश्चित करने के लिए प्रत्येक चरण को तोड़ देगा।
## आवश्यक शर्तें
कोड में गोता लगाने से पहले, आपको कुछ चीजें व्यवस्थित करनी होंगी:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपकी मशीन पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं[ओरेकल वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java लाइब्रेरी को यहाँ से डाउनलोड करें[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): IntelliJ IDEA, Eclipse, या अपनी पसंद के किसी अन्य Java IDE का उपयोग करें।
4. जावा का बुनियादी ज्ञान: जावा प्रोग्रामिंग से परिचित होना लाभदायक होगा।
## पैकेज आयात करें
आरंभ करने के लिए, आपको Aspose.Slides for Java से आवश्यक पैकेज आयात करने होंगे। इससे आपको PowerPoint प्रस्तुतियाँ बनाने और उनमें हेरफेर करने के लिए आवश्यक क्लास और विधियों तक पहुँचने की अनुमति मिलेगी।
```java
import com.aspose.slides.*;
import java.awt.*;
```
## मानक तालिकाएँ बनाने के लिए चरण-दर-चरण मार्गदर्शिका
आइए, जावा का उपयोग करके पावरपॉइंट में मानक तालिकाएं बनाने की प्रक्रिया को आसान चरणों में विभाजित करें।
## चरण 1: प्रोजेक्ट सेट अप करें
सबसे पहले, आपको अपना जावा प्रोजेक्ट सेट अप करना होगा और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides for Java लाइब्रेरी को शामिल करना होगा।
1. नया प्रोजेक्ट बनाएं: अपना IDE खोलें और एक नया जावा प्रोजेक्ट बनाएं।
2.  Aspose.Slides for Java लाइब्रेरी जोड़ें: लाइब्रेरी को यहाँ से डाउनलोड करें[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/) और इसे अपने प्रोजेक्ट के निर्माण पथ में जोड़ें.
## चरण 2: प्रस्तुति आरंभ करें
अब, आपको प्रेजेंटेशन क्लास का एक इंस्टेंस बनाना होगा, जो एक पावरपॉइंट फ़ाइल का प्रतिनिधित्व करता है।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation pres = new Presentation();
```
## चरण 3: पहली स्लाइड तक पहुंचें
प्रस्तुति की पहली स्लाइड पर पहुँचें जहाँ तालिका जोड़ी जाएगी।
```java
// पहली स्लाइड तक पहुंचें
ISlide sld = pres.getSlides().get_Item(0);
```
## चरण 4: तालिका आयाम परिभाषित करें
तालिका के लिए स्तंभों की चौड़ाई और पंक्तियों की ऊंचाई निर्धारित करें।
```java
// स्तंभों को चौड़ाई और पंक्तियों को ऊँचाई के साथ परिभाषित करें
double[] dblCols = {70, 70, 70, 70};
double[] dblRows = {70, 70, 70, 70};
```
## चरण 5: स्लाइड में तालिका जोड़ें
स्लाइड में निर्दिष्ट स्थान पर तालिका आकार जोड़ें.
```java
// स्लाइड में तालिका आकार जोड़ें
ITable tbl = sld.getShapes().addTable(100, 50, dblCols, dblRows);
```
## चरण 6: तालिका बॉर्डर को प्रारूपित करें
तालिका में प्रत्येक कक्ष को दृश्यतः आकर्षक बनाने के लिए बॉर्डर प्रारूप निर्धारित करें।
```java
// प्रत्येक सेल के लिए बॉर्डर प्रारूप सेट करें
for (IRow row : tbl.getRows()) {
    for (ICell cell : (Iterable<ICell>) row) {
        cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderTop().setWidth(5);
        cell.getCellFormat().getBorderBottom().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderBottom().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderBottom().setWidth(5);
        cell.getCellFormat().getBorderLeft().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderLeft().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderLeft().setWidth(5);
        cell.getCellFormat().getBorderRight().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderRight().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderRight().setWidth(5);
    }
}
```
## चरण 7: प्रेजेंटेशन सहेजें
अंत में, पावरपॉइंट प्रेजेंटेशन को एक फ़ाइल में सेव करें।
```java
//PPTX को डिस्क पर लिखें
pres.save(dataDir + "StandardTables_out.pptx", SaveFormat.Pptx);
```
## चरण 8: संसाधनों को साफ़ करें
संसाधनों को मुक्त करने के लिए प्रेजेंटेशन ऑब्जेक्ट को हटा दें।
```java
finally {
    if (pres != null) pres.dispose();
}
```
## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में सफलतापूर्वक एक मानक तालिका बनाई है। इस गाइड ने आपको अपने प्रोजेक्ट को सेट करने से लेकर तालिका जोड़ने और उसे फ़ॉर्मेट करने तक के प्रत्येक चरण के बारे में बताया है। Aspose.Slides के साथ, आप जटिल प्रेजेंटेशन के निर्माण को स्वचालित कर सकते हैं, जिससे आपके डेटा प्रेजेंटेशन कार्य बहुत आसान और अधिक कुशल हो जाते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली API है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने, संशोधित करने और प्रबंधित करने की अनुमति देता है।
### क्या मैं अन्य JVM भाषाओं के साथ Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
हां, Java के लिए Aspose.Slides का उपयोग अन्य JVM भाषाओं जैसे कोटलिन, स्काला और ग्रूवी के साथ किया जा सकता है।
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं।[वेबसाइट](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए लाइसेंस कैसे खरीद सकता हूं?
 आप यहां से लाइसेंस खरीद सकते हैं[Aspose खरीद पृष्ठ](https://purchase.aspose.com/buy).
### क्या Aspose.Slides for Java सभी PowerPoint प्रारूपों का समर्थन करता है?
हां, Aspose.Slides for Java सभी प्रमुख पावरपॉइंट प्रारूपों का समर्थन करता है जिसमें PPT, PPTX, PPS आदि शामिल हैं।