---
"description": "Aspose.Slides for Java का उपयोग करके PowerPoint टेबल सेल को प्रोग्रामेटिक रूप से विभाजित, मर्ज और फ़ॉर्मेट करना सीखें। प्रेजेंटेशन डिज़ाइन में महारत हासिल करें।"
"linktitle": "जावा का उपयोग करके पावरपॉइंट तालिका में कोशिकाओं को विभाजित करें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा का उपयोग करके पावरपॉइंट तालिका में कोशिकाओं को विभाजित करें"
"url": "/hi/java/java-powerpoint-table-manipulation/split-cells-powerpoint-table-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा का उपयोग करके पावरपॉइंट तालिका में कोशिकाओं को विभाजित करें

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Slides का उपयोग करके जावा में PowerPoint टेबल में हेरफेर कैसे करें। टेबल प्रेजेंटेशन में एक मूलभूत घटक हैं, जिनका उपयोग अक्सर डेटा को प्रभावी ढंग से व्यवस्थित और प्रस्तुत करने के लिए किया जाता है। Aspose.Slides प्रोग्रामेटिक रूप से टेबल बनाने, संशोधित करने और बढ़ाने के लिए मजबूत क्षमताएं प्रदान करता है, जो डिज़ाइन और लेआउट में लचीलापन प्रदान करता है।
## आवश्यक शर्तें
इस ट्यूटोरियल को शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपकी मशीन पर JDK (जावा डेवलपमेंट किट) स्थापित है।
- Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/slides/java/).
- एकीकृत विकास वातावरण (आईडीई) जैसे कि एक्लिप्स, इंटेलीज आईडिया, या आपकी पसंद का कोई अन्य।

## पैकेज आयात करें
Aspose.Slides for Java के साथ काम करना शुरू करने के लिए, आपको अपने Java प्रोजेक्ट में आवश्यक पैकेज आयात करने होंगे:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: प्रस्तुति सेट करना
सबसे पहले, उदाहरण दें `Presentation` एक नया पावरपॉइंट प्रेजेंटेशन बनाने के लिए क्लास का उपयोग करें।
```java
// उस निर्देशिका का पथ जहाँ आप आउटपुट प्रस्तुति को सहेजना चाहते हैं
String dataDir = "Your_Document_Directory/";
// PPTX फ़ाइल का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation presentation = new Presentation();
```
## चरण 2: स्लाइड तक पहुंचना और तालिका जोड़ना
पहली स्लाइड पर पहुँचें और उसमें एक टेबल आकार जोड़ें। स्तंभों को चौड़ाई और पंक्तियों को ऊँचाई के साथ परिभाषित करें।
```java
try {
    // पहली स्लाइड तक पहुंचें
    ISlide slide = presentation.getSlides().get_Item(0);
    // स्तंभों को चौड़ाई और पंक्तियों को ऊँचाई के साथ परिभाषित करें
    double[] dblCols = {70, 70, 70, 70};
    double[] dblRows = {70, 70, 70, 70};
    // स्लाइड में तालिका आकार जोड़ें
    ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## चरण 3: प्रत्येक सेल के लिए बॉर्डर प्रारूप सेट करना
तालिका में प्रत्येक कक्ष में पुनरावृत्ति करें और बॉर्डर स्वरूपण (रंग, चौड़ाई, आदि) सेट करें।
```java
    // प्रत्येक सेल के लिए बॉर्डर प्रारूप सेट करें
    for (IRow row : table.getRows()) {
        for (ICell cell : (Iterable<ICell>) row) {
            cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
            cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
            cell.getCellFormat().getBorderTop().setWidth(5);
            // अन्य सीमाओं (नीचे, बाएं, दाएं) के लिए समान स्वरूपण सेट करें
            // ...
        }
    }
```
## चरण 4: कोशिकाओं का विलय
आवश्यकतानुसार तालिका में कक्षों को मर्ज करें। उदाहरण के लिए, कक्षों (1,1) को (2,1) में और (1,2) को (2,2) में मर्ज करें।
```java
    // कोशिकाओं (1, 1) x (2, 1) को मर्ज करना
    table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
    // कोशिकाओं (1, 2) x (2, 2) को मर्ज करना
    table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## चरण 5: कोशिकाओं को विभाजित करना
किसी विशिष्ट कक्ष को चौड़ाई के आधार पर अनेक कक्षों में विभाजित करें।
```java
    // विभाजित सेल (1, 1)
    table.get_Item(1, 1).splitByWidth(table.get_Item(2, 1).getWidth() / 2);
```
## चरण 6: प्रस्तुति को सहेजना
संशोधित प्रस्तुति को डिस्क पर सहेजें.
```java
    // PPTX को डिस्क पर लिखें
    presentation.save(dataDir + "CellSplit_out.pptx", SaveFormat.Pptx);
} finally {
    // प्रस्तुति ऑब्जेक्ट का निपटान करें
    if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint तालिकाओं को प्रोग्रामेटिक रूप से मैनिपुलेट करना, प्रस्तुतियों को कुशलतापूर्वक अनुकूलित करने का एक शक्तिशाली तरीका प्रदान करता है। इस ट्यूटोरियल का अनुसरण करके, आपने सीखा है कि कोशिकाओं को कैसे विभाजित किया जाए, कोशिकाओं को कैसे मर्ज किया जाए, और सेल बॉर्डर को गतिशील रूप से कैसे सेट किया जाए, जिससे प्रोग्रामेटिक रूप से आकर्षक प्रस्तुतियाँ बनाने की आपकी क्षमता में वृद्धि हुई है।

## अक्सर पूछे जाने वाले प्रश्न
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
आप दस्तावेज़ पा सकते हैं [यहाँ](https://reference.aspose.com/slides/java/).
### मैं Java के लिए Aspose.Slides कैसे डाउनलोड कर सकता हूँ?
आप इसे यहां से डाउनलोड कर सकते हैं [इस लिंक](https://releases.aspose.com/slides/java/).
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
हां, आप यहां से निःशुल्क परीक्षण प्राप्त कर सकते हैं [यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए समर्थन कहां से प्राप्त कर सकता हूं?
आप Aspose.Slides फ़ोरम से सहायता प्राप्त कर सकते हैं [यहाँ](https://forum.aspose.com/c/slides/11).
### क्या मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?
हां, आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं [यहाँ](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}