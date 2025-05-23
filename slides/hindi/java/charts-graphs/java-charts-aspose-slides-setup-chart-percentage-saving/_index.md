---
"date": "2025-04-17"
"description": "Aspose.Slides का उपयोग करके Java प्रस्तुतियों में प्रतिशत लेबल वाले चार्ट बनाना, उन्हें अनुकूलित करना और सहेजना सीखें। आज ही अपने प्रस्तुति कौशल को बेहतर बनाएँ!"
"title": "Aspose.Slides का उपयोग करके जावा प्रस्तुतियों में चार्ट बनाएं और अनुकूलित करें"
"url": "/hi/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides का उपयोग करके जावा प्रस्तुतियों में चार्ट बनाएं और अनुकूलित करें

## परिचय
आकर्षक प्रस्तुतियाँ बनाने में अक्सर सिर्फ़ टेक्स्ट से ज़्यादा शामिल होता है; इसके लिए गतिशील चार्ट की ज़रूरत होती है जो जानकारी को प्रभावी ढंग से व्यक्त करते हैं। अगर आप Aspose.Slides का उपयोग करके परिष्कृत चार्ट सुविधाओं के साथ अपने जावा-आधारित प्रस्तुतियों को बेहतर बनाना चाहते हैं, तो यह ट्यूटोरियल आपके लिए है। हम आपको प्रस्तुति बनाने, चार्ट जोड़ने और कॉन्फ़िगर करने, योग की गणना करने, प्रतिशत लेबल प्रदर्शित करने और अपने काम को सहेजने के बारे में मार्गदर्शन करेंगे - ये सब बस कुछ आसान चरणों में।

**आप क्या सीखेंगे:**
- Aspose.Slides for Java का उपयोग करके चार्ट के साथ प्रस्तुतियाँ कैसे बनाएँ और अनुकूलित करें
- चार्ट में श्रेणी योग की गणना करना
- चार्ट पर प्रतिशत लेबल के रूप में डेटा प्रदर्शित करना
- उन्नत चार्ट सुविधाओं के साथ प्रस्तुतियाँ सहेजना

आइये, आरंभ करने से पहले उन पूर्वापेक्षाओं पर नजर डालें जिनकी आपको आवश्यकता है।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **जावा डेवलपमेंट किट (JDK)**: संस्करण 8 या उच्चतर.
- **आईडीई**जैसे कि IntelliJ IDEA, Eclipse, या कोई भी Java समर्थित IDE.
- **Aspose.Slides for Java लाइब्रेरी**यह प्रस्तुति सुविधाओं को संभालने के लिए महत्वपूर्ण है।

### आवश्यक लाइब्रेरी और संस्करण
आपको Java के लिए Aspose.Slides की आवश्यकता होगी। इसे अपने प्रोजेक्ट में शामिल करने का तरीका यहां बताया गया है:

**मावेन:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**ग्रेडेल:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

वैकल्पिक रूप से, आप सीधे नवीनतम संस्करण डाउनलोड कर सकते हैं [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

### पर्यावरण सेटअप
सुनिश्चित करें कि आपका विकास वातावरण JDK 8 या बाद के संस्करण का उपयोग करने के लिए कॉन्फ़िगर किया गया है और आपका IDE Maven या Gradle का उपयोग करके निर्भरताओं को प्रबंधित करने के लिए सेट किया गया है।

**लाइसेंस प्राप्ति:**
- **मुफ्त परीक्षण**परीक्षण प्रयोजनों के लिए बुनियादी सुविधाओं तक पहुंच।
- **अस्थायी लाइसेंस**: मूल्यांकन सीमाओं के बिना उन्नत सुविधाओं का परीक्षण करें।
- **खरीदना**दीर्घकालिक व्यावसायिक उपयोग के लिए, लाइसेंस खरीदने पर विचार करें।

## Java के लिए Aspose.Slides सेट अप करना
अपने जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी सेट अप करके शुरुआत करें। इसे आरंभ करने और कॉन्फ़िगर करने का तरीका यहां बताया गया है:

1. ऊपर दिखाए अनुसार Maven या Gradle के माध्यम से निर्भरता जोड़ें।
2. आवश्यक Aspose.Slides पैकेज आयात करें:
   ```java
   import com.aspose.slides.*;
   ```

3. एक नया आरंभ करें `Presentation` उदाहरण:
   ```java
   Presentation presentation = new Presentation();
   ```

यह सेटअप आपको प्रोग्रामेटिक रूप से प्रस्तुतियाँ बनाने की सुविधा देगा।

## कार्यान्वयन मार्गदर्शिका

### अपनी प्रस्तुति में चार्ट बनाएं और अनुकूलित करें

#### अवलोकन
चार्ट बनाने में आपकी प्रस्तुति को आरंभ करना, स्लाइडों तक पहुंचना, तथा प्रकार, स्थिति और आकार जैसी विशिष्ट विशेषताओं के साथ चार्ट जोड़ना शामिल है।

**चरण:**
1. **प्रेजेंटेशन इंस्टेंस बनाएं**: का एक उदाहरण बनाकर शुरू करें `Presentation` कक्षा।
2. **स्लाइड तक पहुंचें**: का उपयोग करके पहली स्लाइड पुनः प्राप्त करें `get_Item(0)`.
3. **चार्ट जोड़ें**: उपयोग `addChart()` परिभाषित आयामों के साथ निर्दिष्ट निर्देशांक पर एक स्टैक्ड कॉलम चार्ट जोड़ने के लिए।

```java
// विशेषता: चार्ट के साथ प्रस्तुति बनाएं
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### श्रेणियों के लिए कुल की गणना करें

#### अवलोकन
श्रेणी योग की गणना करने में चार्ट में प्रत्येक श्रृंखला के माध्यम से प्रत्येक श्रेणी के मानों का योग निकालना शामिल है।

**चरण:**
1. **सारणी आरंभ करें**: कुल मान रखने के लिए एक सरणी बनाएँ.
2. **श्रेणियों और श्रृंखलाओं के माध्यम से पुनरावृति करें**: सभी श्रृंखलाओं से प्रत्येक श्रेणी के लिए कुल योग एकत्रित करने के लिए नेस्टेड लूप का उपयोग करें।

```java
// विशेषता: चार्ट में श्रेणियों के लिए कुल की गणना करें
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### चार्ट पर प्रतिशत लेबल के रूप में डेटा प्रदर्शित करें

#### अवलोकन
यह सुविधा मानों को प्रतिशत के रूप में प्रदर्शित करने के लिए डेटा लेबल को कॉन्फ़िगर करने पर ध्यान केंद्रित करती है, जिससे विज़ुअलाइज़ेशन में स्पष्टता मिलती है।

**चरण:**
1. **श्रृंखला लेबल कॉन्फ़िगर करें**: लेबल गुण सेट करें, जैसे फ़ॉन्ट आकार और लेजेंड कुंजियों की दृश्यता।
2. **प्रतिशत की गणना करें**: कुल श्रेणी मूल्य के आधार पर प्रत्येक डेटा बिंदु के लिए प्रतिशत की गणना करें।
3. **लेबल टेक्स्ट सेट करें**: प्रतिशत को दो दशमलव बिंदुओं के साथ दिखाने के लिए लेबल को प्रारूपित करें।

```java
// विशेषता: चार्ट पर प्रतिशत लेबल के रूप में डेटा प्रदर्शित करें
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### चार्ट के साथ प्रस्तुति सहेजें

#### अवलोकन
अंत में, अपनी प्रस्तुति को PPTX प्रारूप में निर्दिष्ट पथ पर सहेजें।

**चरण:**
1. **सहेजने की विधि**: उपयोग `save()` विधि पर `Presentation` उदाहरण।
2. **संसाधनों का निपटान**: सुनिश्चित करें कि संसाधन सहेजने के बाद जारी किए जाएं।

```java
// विशेषता: चार्ट के साथ प्रस्तुति सहेजें
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## व्यावहारिक अनुप्रयोगों

1. **वित्तीय रिपोर्टिंग**: विभागों में राजस्व वृद्धि प्रतिशत प्रदर्शित करने के लिए चार्ट का उपयोग करें।
2. **बिक्री डेटा विश्लेषण**: स्पष्ट जानकारी के लिए प्रतिशत लेबल के साथ क्षेत्रवार बिक्री डेटा को विज़ुअलाइज़ करें।
3. **शैक्षिक प्रस्तुतियाँ**दृश्य सांख्यिकी के साथ अकादमिक प्रस्तुतियों को बेहतर बनाएं।
4. **विपणन अभियान**: अभियान प्रदर्शन मीट्रिक को आकर्षक दृश्यों के रूप में प्रदर्शित करें.
5. **व्यापार रणनीति बैठकें**रणनीतिक योजना चर्चाओं में जटिल डेटा को व्यक्त करने के लिए चार्ट का उपयोग करें।

## प्रदर्शन संबंधी विचार
- **स्मृति प्रबंधन**: बचना `Presentation` संसाधनों को मुक्त करने के लिए तुरंत कार्रवाई करें।
- **चार्ट लोडिंग अनुकूलित करें**यदि संभव हो तो केवल आवश्यक चार्ट तत्वों को ही मेमोरी में लोड करें।
- **प्रचय संसाधन**एकाधिक प्रस्तुतियों को संसाधित करते समय, संसाधन खपत को प्रभावी ढंग से प्रबंधित करने के लिए उन्हें बैचों में संभालने पर विचार करें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}