---
"date": "2025-04-17"
"description": "Aspose.Slides for Java का उपयोग करके सटीक फ़ॉर्मेटिंग के साथ PowerPoint स्लाइड को कस्टम SVG के रूप में निर्यात करना सीखें। यह मार्गदर्शिका सेटअप, अनुकूलन और व्यावहारिक अनुप्रयोगों को कवर करती है।"
"title": "Aspose.Slides for Java का उपयोग करके PowerPoint PPTX को कस्टम SVG में निर्यात करें&#58; एक चरण-दर-चरण मार्गदर्शिका"
"url": "/hi/java/presentation-operations/export-pptx-to-svg-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java के लिए Aspose.Slides का उपयोग करके PowerPoint PPTX को कस्टम SVG में निर्यात करें: एक चरण-दर-चरण मार्गदर्शिका

आज के डिजिटल परिदृश्य में, प्रस्तुतियों को अक्सर ऐसे प्रारूपों की आवश्यकता होती है जो पारंपरिक से परे हों। चाहे वह वेब डेवलपमेंट के लिए हो या डेटा विज़ुअलाइज़ेशन के लिए, कस्टम SVG निर्यात दृश्य अपील और कार्यक्षमता को काफी हद तक बढ़ा सकता है। यह मार्गदर्शिका आपको दिखाएगी कि Aspose.Slides for Java का उपयोग करके स्वरूपण पर सटीक नियंत्रण के साथ PowerPoint स्लाइड को SVG फ़ाइलों के रूप में कैसे निर्यात किया जाए।

## आप क्या सीखेंगे
- SVG विशेषताओं में हेरफेर करें `ISvgShapeAndTextFormattingController`.
- निर्यात के दौरान SVG तत्वों की विशिष्ट पहचान करें.
- Java के लिए Aspose.Slides को सेट अप और कॉन्फ़िगर करें।
- कस्टम SVG के रूप में प्रस्तुतियों को निर्यात करने के व्यावहारिक अनुप्रयोग।
- जटिल प्रस्तुतियों के लिए प्रदर्शन अनुकूलन युक्तियाँ.

आइए Aspose.Slides for Java में प्रवेश करने से पहले आवश्यक पूर्वावश्यकताओं को कवर करके शुरुआत करें।

## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास:
- **जावा डेवलपमेंट किट (JDK)**आपकी मशीन पर संस्करण 8 या उच्चतर स्थापित है।
- **जावा के लिए Aspose.Slides**: पावरपॉइंट प्रेजेंटेशन को मैनिपुलेट करने और एक्सपोर्ट करने के लिए आवश्यक। इंस्टॉलेशन विवरण नीचे दिए गए हैं।
- **आईडीई/संपादक**: IntelliJ IDEA, Eclipse, या VSCode जैसा कोई पसंदीदा वातावरण.

### आवश्यक लाइब्रेरी और निर्भरताएँ
अपनी परियोजना में निर्भरता के रूप में Aspose.Slides को शामिल करें:

#### मावेन
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### ग्रैडल
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
वैकल्पिक रूप से, नवीनतम संस्करण यहाँ से डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

### लाइसेंस प्राप्ति चरण
1. **मुफ्त परीक्षण**: Aspose से निःशुल्क परीक्षण लाइसेंस डाउनलोड करें।
2. **अस्थायी लाइसेंस**: मूल्यांकन सीमाओं के बिना विस्तारित परीक्षण के लिए एक अस्थायी लाइसेंस का अनुरोध करें।
3. **खरीदना**: उत्पादन उपयोग के लिए पूर्ण लाइसेंस खरीदें।

अपना परिवेश सेट अप करने और लाइसेंस प्राप्त करने के बाद, Aspose.Slides को निम्न के साथ आरंभ करें:
```java
License license = new License();
license.setLicense("path_to_your_license_file");
```
हमारा सेटअप पूरा होने के बाद, आइए कस्टम SVG निर्यात कार्यक्षमता को लागू करने के लिए आगे बढ़ें।

## Java के लिए Aspose.Slides सेट अप करना
Aspose.Slides जावा में पावरपॉइंट प्रेजेंटेशन को संभालने के लिए एक शक्तिशाली लाइब्रेरी है। उचित सेटअप सुचारू संचालन और इसकी समृद्ध सुविधाओं तक पहुँच सुनिश्चित करता है।

### इंस्टालेशन
अपने प्रोजेक्ट में निर्भरता के रूप में Aspose.Slides जोड़ने के लिए ऊपर दिए गए Maven या Gradle निर्देशों का पालन करें।

एक बार इंस्टॉल हो जाने पर, अपना लाइसेंस लागू करके लाइब्रेरी को आरंभ करें:
```java
License license = new License();
license.setLicense("path_to_your_license_file");
```
यह सेटअप विकास के दौरान बिना किसी सीमा के Aspose.Slides की क्षमताओं का पूर्ण उपयोग करने में सक्षम बनाता है।

## कार्यान्वयन मार्गदर्शिका
हमारे परिवेश सेट के साथ, आइए कस्टम SVG स्वरूपण लागू करें और स्लाइडों को SVG फ़ाइलों के रूप में निर्यात करें।

### कस्टम SVG स्वरूपण नियंत्रक
SVG आकार और पाठ स्वरूपण के लिए एक कस्टम नियंत्रक बनाएँ `ISvgShapeAndTextFormattingController`यह निर्यातित SVG तत्वों के भीतर आईडी के हेरफेर की अनुमति देता है।

#### चरण 1: कस्टम नियंत्रक को परिभाषित करें
```java
import com.aspose.slides.*;

public class SvgFormattingController {
    static class CustomSvgShapeFormattingController implements ISvgShapeAndTextFormattingController {
        private int m_shapeIndex, m_portionIndex, m_tspanIndex;

        public CustomSvgShapeFormattingController(int shapeStartIndex) {
            m_shapeIndex = shapeStartIndex;
            m_portionIndex = 0;
        }

        @Override
        public void formatShape(ISvgShape svgShape, IShape shape) {
            svgShape.setId(String.format("shape-%d", m_shapeIndex++));
            m_portionIndex = m_tspanIndex = 0;
        }

        @Override
        public void formatText(ISvgTSpan svgTSpan, IPortion portion, ITextFrame textFrame) {
            int paragraphIndex = 0; 
            int portionIndex = 0;

            for (int i = 0; i < textFrame.getParagraphs().getCount(); i++) {
                portionIndex = textFrame.getParagraphs().get_Item(i).getPortions().indexOf(portion);
                if (portionIndex > -1) { paragraphIndex = i; break; }
            }

            if (m_portionIndex != portionIndex) {
                m_tspanIndex = 0;
                m_portionIndex = portionIndex;
            }

            svgTSpan.setId(String.format("paragraph-%d_portion-%d_%d", 
                                         paragraphIndex, m_portionIndex, m_tspanIndex++));
        }
    }
}
```
**स्पष्टीकरण:**
- **`formatShape`**: विशिष्ट पहचान के लिए प्रत्येक SVG आकृति को उसके सूचकांक के आधार पर एक विशिष्ट आईडी प्रदान करता है।
- **`formatText`**: टेक्स्ट स्पैन को विशिष्ट आईडी प्रदान करके टेक्स्ट फ़ॉर्मेटिंग प्रबंधित करता है (`tspan`यह पैराग्राफ और भाग सूचकांक को ट्रैक करता है, तथा विभिन्न पाठ भागों में एकरूपता बनाए रखता है।

### प्रस्तुति स्लाइड को अनुकूलित SVG प्रारूप में निर्यात करें
कस्टम नियंत्रक को परिभाषित करने के बाद, इस अनुकूलित दृष्टिकोण का उपयोग करके एक प्रस्तुति स्लाइड को SVG फ़ाइल के रूप में निर्यात करें।

#### चरण 2: SVG निर्यात कार्यक्षमता को लागू करें
```java
import com.aspose.slides.*;
import java.io.FileOutputStream;

public class SvgExporter {
    public static void main(String[] args) throws Exception {
        String pptxFileName = "YOUR_DOCUMENT_DIRECTORY/Convert_Svg_Custom.pptx";
        String outSvgFileName = "YOUR_OUTPUT_DIRECTORY/Convert_Svg_Custom.svg";

        Presentation pres = new Presentation(pptxFileName);
        try {
            SVGOptions svgOptions = new SVGOptions();
            svgOptions.setShapeFormattingController(new CustomSvgShapeFormattingController(0));

            FileOutputStream fs = new FileOutputStream(outSvgFileName);
            try {
                pres.getSlides().get_Item(0).writeAsSvg(fs, svgOptions);
            } finally {
                if (fs != null) fs.close(); 
            }
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**मुख्य कॉन्फ़िगरेशन विकल्प:**
- **`SVGOptions.setShapeFormattingController`**: निर्यात के दौरान आकार और पाठ आईडी प्रबंधित करने के लिए हमारे कस्टम SVG स्वरूपण नियंत्रक को सेट करता है।
- **फ़ाइल स्ट्रीम**: पावरपॉइंट फ़ाइल से पढ़ने और आउटपुट SVG लिखने के लिए उपयोग किया जाता है। संसाधन लीक को रोकने के लिए स्ट्रीम को उचित रूप से बंद करना सुनिश्चित करें।

### समस्या निवारण युक्तियों
1. **आईडी विवाद**यदि ओवरलैपिंग आईडी हैं, तो सुनिश्चित करें कि आपके सूचकांक सही ढंग से आरंभीकृत और बढ़ाए गए हैं।
2. **फ़ाइल नहीं मिली त्रुटियाँ**: इनपुट और आउटपुट दोनों फ़ाइलों के लिए निर्देशिका पथ की दोबारा जाँच करें।
3. **स्मृति प्रबंधन**: बड़ी प्रस्तुतियों के लिए, संसाधन-गहन संचालनों को कुशलतापूर्वक संभालने के लिए अपने JVM के हीप आकार को बढ़ाएँ।

## व्यावहारिक अनुप्रयोगों
कस्टम SVG निर्यात विभिन्न व्यावहारिक उद्देश्यों की पूर्ति करते हैं:
1. **वेब विकास**वेब परियोजनाओं में उत्तरदायी डिज़ाइन तत्वों के लिए अनुकूलित SVG का उपयोग करें, जिनके लिए CSS हेरफेर या जावास्क्रिप्ट इंटरैक्शन के लिए अद्वितीय पहचानकर्ताओं की आवश्यकता होती है।
2. **डेटा विज़ुअलाइज़ेशन**स्क्रिप्ट के माध्यम से गतिशील अद्यतन के लिए कस्टम आईडी के साथ चार्ट और आरेखों को SVG फ़ाइलों के रूप में निर्यात करके डेटा प्रस्तुतियों को बढ़ाएं।
3. **मुद्रण माध्यम**: उच्च गुणवत्ता वाली मुद्रित सामग्री के लिए प्रस्तुति सामग्री तैयार करें, प्रत्येक तत्व के स्वरूपण पर सटीक नियंत्रण सुनिश्चित करें।

## प्रदर्शन संबंधी विचार
जटिल पावरपॉइंट प्रस्तुतियों के साथ काम करते समय:
- **संसाधनों का अनुकूलन करें**: सुचारू प्रदर्शन सुनिश्चित करने और मेमोरी संबंधी समस्याओं से बचने के लिए संसाधनों का प्रभावी ढंग से प्रबंधन करें।
- **कुशल कोडिंग अभ्यास**: SVG निर्यात के दौरान प्रसंस्करण समय और संसाधन उपयोग को न्यूनतम करने के लिए कुशल कोड लिखें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}