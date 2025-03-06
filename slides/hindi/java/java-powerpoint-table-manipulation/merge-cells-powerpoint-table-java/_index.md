---
title: जावा के साथ पावरपॉइंट टेबल में सेल्स मर्ज करें
linktitle: जावा के साथ पावरपॉइंट टेबल में सेल्स मर्ज करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint टेबल में सेल मर्ज करना सीखें। इस चरण-दर-चरण मार्गदर्शिका के साथ अपने प्रेजेंटेशन लेआउट को बेहतर बनाएँ।
weight: 17
url: /hi/java/java-powerpoint-table-manipulation/merge-cells-powerpoint-table-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि जावा के लिए Aspose.Slides का उपयोग करके PowerPoint तालिका के भीतर कोशिकाओं को प्रभावी ढंग से कैसे मर्ज किया जाए। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। तालिका में कोशिकाओं को मर्ज करके, आप अपनी प्रस्तुति स्लाइड के लेआउट और संरचना को अनुकूलित कर सकते हैं, जिससे स्पष्टता और दृश्य अपील बढ़ जाती है।
## आवश्यक शर्तें
इस ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- जावा प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
- आपकी मशीन पर JDK (जावा डेवलपमेंट किट) स्थापित है।
- आईडीई (एकीकृत विकास पर्यावरण) जैसे कि इंटेलीज आईडिया या एक्लिप्स।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
आरंभ करने के लिए, सुनिश्चित करें कि आपने Aspose.Slides के साथ काम करने के लिए आवश्यक पैकेज आयात कर लिए हैं:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
सबसे पहले, अपने पसंदीदा IDE में एक नया Java प्रोजेक्ट बनाएं और अपनी प्रोजेक्ट निर्भरताओं में Aspose.Slides for Java लाइब्रेरी जोड़ें।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को इंस्टैंशिएट करें
 उदाहरण प्रस्तुत करें`Presentation` आप जिस PPTX फ़ाइल के साथ काम कर रहे हैं, उसका प्रतिनिधित्व करने के लिए क्लास:
```java
Presentation presentation = new Presentation();
```
## चरण 3: स्लाइड तक पहुंचें
उस स्लाइड तक पहुँचें जहाँ आप तालिका जोड़ना चाहते हैं। उदाहरण के लिए, पहली स्लाइड तक पहुँचने के लिए:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## चरण 4: तालिका आयाम परिभाषित करें
 अपनी तालिका के लिए स्तंभ और पंक्तियाँ निर्धारित करें। स्तंभों की चौड़ाई और पंक्तियों की ऊँचाई को सारणी के रूप में निर्दिष्ट करें`double`:
```java
double[] dblCols = {70, 70, 70, 70};
double[] dblRows = {70, 70, 70, 70};
```
## चरण 5: स्लाइड में तालिका आकार जोड़ें
निर्धारित आयामों का उपयोग करके स्लाइड में तालिका आकार जोड़ें:
```java
ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## चरण 6: सेल बॉर्डर को अनुकूलित करें
तालिका में प्रत्येक सेल के लिए बॉर्डर प्रारूप सेट करें। यह उदाहरण प्रत्येक सेल के लिए 5 की चौड़ाई के साथ एक लाल ठोस बॉर्डर सेट करता है:
```java
for (IRow row : table.getRows()) {
    for (ICell cell : (Iterable<ICell>) row) {
        // सेल के प्रत्येक पक्ष के लिए बॉर्डर प्रारूप सेट करें
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
## चरण 7: तालिका में कक्षों को मर्ज करें
 तालिका में कक्षों को मर्ज करने के लिए, का उपयोग करें`mergeCells` विधि। यह उदाहरण (1, 1) से (2, 1) और (1, 2) से (2, 2) तक कोशिकाओं को मर्ज करता है:
```java
table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## चरण 8: प्रस्तुति सहेजें
अंत में, संशोधित प्रस्तुति को अपनी डिस्क पर PPTX फ़ाइल में सहेजें:
```java
String dataDir = "Your_Document_Directory_Path/";
presentation.save(dataDir + "MergeCells1_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इन चरणों का पालन करके, आपने सफलतापूर्वक सीख लिया है कि Aspose.Slides for Java का उपयोग करके PowerPoint तालिका के भीतर कोशिकाओं को कैसे मर्ज किया जाए। यह तकनीक आपको प्रोग्रामेटिक रूप से अधिक जटिल और आकर्षक प्रस्तुतिकरण बनाने की अनुमति देती है, जिससे आपकी उत्पादकता और अनुकूलन विकल्प बढ़ जाते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक जावा एपीआई है जो प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने के लिए है।
### मैं Java के लिए Aspose.Slides कैसे डाउनलोड करूं?
 आप Java के लिए Aspose.Slides को यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
### क्या मैं खरीदने से पहले Aspose.Slides for Java आज़मा सकता हूँ?
 हां, आप यहां से Aspose.Slides for Java का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 आप दस्तावेज़ पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
### मैं Java के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 आप Aspose.Slides समुदाय मंच से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
