---
title: जावा के साथ पावरपॉइंट में भाग आयत प्राप्त करें
linktitle: जावा के साथ पावरपॉइंट में भाग आयत प्राप्त करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: इस विस्तृत, चरण-दर-चरण ट्यूटोरियल के साथ जानें कि Aspose.Slides for Java का उपयोग करके PowerPoint में भाग आयत कैसे प्राप्त करें। Java डेवलपर्स के लिए बिल्कुल सही।
weight: 12
url: /hi/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
Aspose.Slides for Java के साथ Java में गतिशील प्रस्तुतियाँ बनाना बहुत आसान है। इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके PowerPoint में भाग आयत प्राप्त करने की बारीकियों में गोता लगाएँगे। हम आपके परिवेश को सेट करने से लेकर कोड को चरण-दर-चरण तोड़ने तक सब कुछ कवर करेंगे। तो, चलिए शुरू करते हैं!
## आवश्यक शर्तें
इससे पहले कि हम कोड में प्रवेश करें, आइए सुनिश्चित करें कि आपके पास सुचारू रूप से अनुसरण करने के लिए आवश्यक सभी चीजें मौजूद हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके मशीन पर JDK 8 या उससे ऊपर का संस्करण स्थापित है।
2.  Aspose.Slides for Java: यहां से नवीनतम संस्करण डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): एक्लिप्स, इंटेलीज आईडिया, या आपकी पसंद का कोई अन्य जावा IDE.
4. जावा का बुनियादी ज्ञान: जावा प्रोग्रामिंग की समझ आवश्यक है।
## पैकेज आयात करें
सबसे पहले, आइए आवश्यक पैकेज आयात करें। इसमें Aspose.Slides और हमारे कार्य को कुशलतापूर्वक संभालने के लिए कुछ अन्य शामिल होंगे।
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## चरण 1: प्रस्तुतिकरण सेट करना
पहला कदम एक नया प्रेजेंटेशन बनाना है। यह हमारे काम का कैनवास होगा।
```java
Presentation pres = new Presentation();
```
## चरण 2: तालिका बनाना
अब, आइए अपनी प्रस्तुति की पहली स्लाइड में एक तालिका जोड़ें। इस तालिका में वे कक्ष होंगे जहाँ हम अपना पाठ जोड़ेंगे।
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## चरण 3: कक्षों में पैराग्राफ़ जोड़ना
इसके बाद, हम पैराग्राफ़ बनाएंगे और उन्हें टेबल में किसी खास सेल में जोड़ेंगे। इसमें किसी भी मौजूदा टेक्स्ट को हटाना और फिर नए पैराग्राफ़ जोड़ना शामिल है।
```java
// पैराग्राफ़ बनाएँ
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// तालिका सेल में पाठ जोड़ें
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## चरण 4: ऑटोशेप में टेक्स्ट फ़्रेम जोड़ना
अपनी प्रस्तुति को अधिक गतिशील बनाने के लिए, हम ऑटोशेप में एक टेक्स्ट फ्रेम जोड़ेंगे और उसका संरेखण सेट करेंगे।
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## चरण 5: निर्देशांक की गणना
हमें टेबल सेल के ऊपरी-बाएँ कोने के निर्देशांक प्राप्त करने की आवश्यकता है। इससे हमें आकृतियों को सटीक रूप से रखने में मदद मिलेगी।
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## चरण 6: पैराग्राफ़ और भागों में फ़्रेम जोड़ना
 का उपयोग`IParagraph.getRect()` और`IPortion.getRect()`तरीकों से, हम अपने पैराग्राफ और भागों में फ्रेम जोड़ सकते हैं। इसमें पैराग्राफ और भागों के माध्यम से पुनरावृत्ति करना, उनके चारों ओर आकृतियाँ बनाना और उनकी उपस्थिति को अनुकूलित करना शामिल है।
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## चरण 7: ऑटोशेप पैराग्राफ़ में फ़्रेम जोड़ना
इसी प्रकार, हम अपने ऑटोशेप में पैराग्राफ में फ्रेम जोड़ेंगे, जिससे प्रस्तुति का दृश्य आकर्षण बढ़ जाएगा।
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## चरण 8: प्रस्तुति को सहेजना
अंत में, हम अपनी प्रस्तुति को निर्दिष्ट पथ पर सेव करेंगे।
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## चरण 9: सफाई
संसाधनों को मुक्त करने के लिए प्रस्तुति ऑब्जेक्ट को हटाना अच्छा अभ्यास है।
```java
if (pres != null) pres.dispose();
```
## निष्कर्ष
बधाई हो! आपने सफलतापूर्वक सीख लिया है कि Java के लिए Aspose.Slides का उपयोग करके PowerPoint में भाग आयत कैसे प्राप्त करें। यह शक्तिशाली लाइब्रेरी प्रोग्रामेटिक रूप से गतिशील और नेत्रहीन आकर्षक प्रस्तुतियाँ बनाने के लिए संभावनाओं की दुनिया खोलती है। Aspose.Slides में गहराई से गोता लगाएँ और अपनी प्रस्तुतियों को और बेहतर बनाने के लिए और अधिक सुविधाएँ खोजें।
## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और हेरफेर करने की अनुमति देती है।
### क्या मैं व्यावसायिक परियोजनाओं में Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?
 हां, Aspose.Slides for Java का उपयोग व्यावसायिक परियोजनाओं में किया जा सकता है। आप यहां से लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### क्या Aspose.Slides for Java के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/slides/java/).
### मैं Java के लिए Aspose.Slides के लिए समर्थन कैसे प्राप्त कर सकता हूं?
 आप Aspose फ़ोरम से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
