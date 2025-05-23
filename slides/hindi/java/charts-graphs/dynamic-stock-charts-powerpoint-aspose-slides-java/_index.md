---
"date": "2025-04-17"
"description": "Aspose.Slides for Java का उपयोग करके PowerPoint में डायनामिक स्टॉक चार्ट बनाना और उन्हें कस्टमाइज़ करना सीखें। यह गाइड प्रस्तुतियों को आरंभ करने, डेटा श्रृंखला जोड़ने, चार्ट को फ़ॉर्मेट करने और फ़ाइलों को सहेजने के बारे में बताती है।"
"title": "Aspose.Slides for Java के साथ PowerPoint में डायनामिक स्टॉक चार्ट बनाना"
"url": "/hi/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java के साथ PowerPoint में डायनामिक स्टॉक चार्ट बनाना

## परिचय

डायनेमिक स्टॉक चार्ट को शामिल करके अपने पावरपॉइंट प्रेजेंटेशन को बेहतर बनाएँ। चाहे आप वित्तीय विश्लेषक हों, व्यावसायिक पेशेवर हों या शिक्षक हों जिन्हें डेटा रुझानों को प्रभावी ढंग से देखने की आवश्यकता हो, यह ट्यूटोरियल आपको Aspose.Slides for Java का उपयोग करके स्टॉक चार्ट बनाने और उन्हें कस्टमाइज़ करने में मार्गदर्शन करता है। इस गाइड के अंत तक, आप मौजूदा पावरपॉइंट फ़ाइलों को लोड करने, कस्टम सीरीज़ और श्रेणियों के साथ विस्तृत स्टॉक चार्ट जोड़ने, उन्हें खूबसूरती से फ़ॉर्मेट करने और अपनी बेहतर प्रस्तुति को सहेजने में सक्षम होंगे।

**आप क्या सीखेंगे:**
- Aspose.Slides के साथ जावा में प्रस्तुति आरंभ करें
- स्टॉक चार्ट जोड़ें और अनुकूलित करें
- डेटा श्रृंखला और श्रेणियाँ साफ़ करें
- व्यापक विश्लेषण के लिए नए डेटा बिंदु डालें
- चार्ट लाइनों और बार को प्रभावी ढंग से प्रारूपित करें
- अद्यतन प्रस्तुति सहेजें

क्या आप आकर्षक प्रस्तुतिकरण बनाने के लिए तैयार हैं? तो चलिए शुरू करते हैं!

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- **जावा डेवलपमेंट किट (JDK)**सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है।
- **आईडीई**जावा कोड लिखने और चलाने के लिए IntelliJ IDEA या Eclipse जैसे किसी भी IDE का उपयोग करें।
- **Aspose.Slides for Java लाइब्रेरी**इस ट्यूटोरियल के लिए Java के लिए Aspose.Slides का संस्करण 25.4 आवश्यक है।

### Java के लिए Aspose.Slides सेट अप करना

#### मावेन
Maven का उपयोग करके Aspose.Slides को अपने प्रोजेक्ट में एकीकृत करने के लिए, अपने में निम्नलिखित निर्भरता जोड़ें `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### ग्रैडल
Gradle उपयोगकर्ताओं के लिए, इसे अपने में शामिल करें `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### प्रत्यक्षत: डाउनलोड
वैकल्पिक रूप से, नवीनतम JAR को यहां से डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

**लाइसेंस अधिग्रहण**: आप निःशुल्क परीक्षण के साथ शुरुआत कर सकते हैं या अस्थायी लाइसेंस का अनुरोध कर सकते हैं। विस्तारित उपयोग के लिए, पूर्ण लाइसेंस खरीदने पर विचार करें।

## कार्यान्वयन मार्गदर्शिका

आइये प्रत्येक फीचर को चरण दर चरण समझें।

### प्रस्तुति आरंभ करें
#### अवलोकन
संशोधनों के लिए तैयार करने हेतु किसी मौजूदा पावरपॉइंट फ़ाइल को लोड करके शुरुआत करें।

#### चरण-दर-चरण मार्गदर्शिका
1. **लाइब्रेरी आयात करें**:
   
   ```java
   import com.aspose.slides.Presentation;
   ```

2. **प्रस्तुति फ़ाइल लोड करें**:
   
   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // 'प्रेस' पर ऑपरेशन करने के लिए तैयार
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### स्लाइड में स्टॉक चार्ट जोड़ें
#### अवलोकन
इस चरण में आपकी प्रस्तुति की पहली स्लाइड में स्टॉक चार्ट जोड़ना शामिल है।

3. **चार्ट जोड़ें**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### चार्ट में मौजूदा डेटा श्रृंखला और श्रेणियाँ साफ़ करें
#### अवलोकन
नए सिरे से शुरुआत करने के लिए चार्ट से किसी भी पहले से मौजूद डेटा श्रृंखला या श्रेणी को हटा दें।

4. **स्पष्ट डेटा**:
   
   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### चार्ट डेटा में श्रेणियाँ जोड़ें
#### अवलोकन
बेहतर डेटा विभाजन और समझ के लिए कस्टम श्रेणियां जोड़ें.

5. **श्रेणियाँ डालें**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // श्रेणियाँ जोड़ें
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### चार्ट में डेटा श्रृंखला जोड़ें
#### अवलोकन
व्यापक विश्लेषण के लिए ओपन, हाई, लो और क्लोज जैसी विभिन्न डेटा श्रृंखलाओं को एकीकृत करें।

6. **डेटा श्रृंखला जोड़ें**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // 'ओपन', 'हाई', 'लो' और 'क्लोज़' के लिए श्रृंखला जोड़ें
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### श्रृंखला में डेटा बिंदु जोड़ें
#### अवलोकन
सटीक प्रतिनिधित्व के लिए प्रत्येक श्रृंखला को विशिष्ट डेटा बिंदुओं से भरें।

7. **डेटा बिंदु डालें**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // 'ओपन' श्रृंखला में डेटा बिंदु जोड़ें
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // 'उच्च' श्रृंखला में डेटा बिंदु जोड़ें
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // 'निम्न' श्रृंखला में डेटा बिंदु जोड़ें
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // 'बंद करें' श्रृंखला में डेटा बिंदु जोड़ें
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### उच्च-निम्न रेखाओं और ऊपर/नीचे बारों को प्रारूपित करें
#### अवलोकन
बेहतर दृश्यावलोकन के लिए उच्च-निम्न रेखाओं और ऊपर/नीचे पट्टियों के स्वरूप को अनुकूलित करें।

8. **उच्च-निम्न रेखाओं को प्रारूपित करें**:
   
   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // 'बंद करें' श्रृंखला के लिए उच्च-निम्न पंक्तियों को प्रारूपित करें
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

9. **ऊपर/नीचे बार प्रदर्शित करें**:
   
   ```java
   // स्टॉक चार्ट श्रृंखला समूह के लिए ऊपर/नीचे बार प्रदर्शित करें
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### हाई-लो लाइनों पर डेटा लेबल को अनुकूलित करें
#### अवलोकन
उच्च-निम्न रेखाओं पर मान प्रदर्शित करने के लिए डेटा लेबल जोड़ें और प्रारूपित करें।

10. **ऊपर/नीचे बार पर मान दिखाएं**:
    
    ```java
    // चार्ट समूह में प्रत्येक श्रृंखला के लिए ऊपर/नीचे बार पर मान दिखाएं
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### सेट अप डाउन बार्स भरें रंग
#### अवलोकन
दृश्यात्मक अंतर को बढ़ाने के लिए ऊपर/नीचे बार के लिए एक कस्टम भरण रंग सेट करें।

11. **ऊपर/नीचे बार रंग बदलें**:
    
    ```java
    // चार्ट समूह में प्रत्येक श्रृंखला के लिए ऊपर/नीचे बार रंग बदलें
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'ओपन' श्रृंखला
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // ऊपर की पट्टियाँ सियान रंग में
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'हाई' श्रृंखला
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // गहरे समुद्री हरे रंग में डाउन बार
        }
    }
    ```

### पावरपॉइंट फ़ाइल सहेजें
#### अवलोकन
अपने परिवर्तनों को एक नई PowerPoint फ़ाइल में सहेजें.

12. **प्रस्तुति सहेजें**:
    
    ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## निष्कर्ष

बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint में गतिशील स्टॉक चार्ट सफलतापूर्वक बनाए और अनुकूलित किए हैं। यह प्रक्रिया आपके प्रस्तुतियों को आकर्षक डेटा विज़ुअलाइज़ेशन के साथ बेहतर बनाती है, जिससे आप वित्तीय जानकारी को प्रभावी ढंग से संप्रेषित कर सकते हैं। यदि आप अन्य चार्ट प्रकारों को और अधिक अनुकूलित करने या तलाशने में रुचि रखते हैं, तो व्यापक में गोता लगाने पर विचार करें [Aspose.Slides दस्तावेज़ीकरण](https://docs.aspose.com/slides/java/).

## आगे पढ़ने के लिए सामग्री और संदर्भ
- Aspose.Slides for Java प्रलेखन: Aspose.Slides की विभिन्न सुविधाओं का उपयोग करने पर विस्तृत मार्गदर्शिकाएँ देखें।
- पावरपॉइंट चार्टिंग टूल्स अवलोकन: माइक्रोसॉफ्ट पावरपॉइंट में उपलब्ध विभिन्न चार्टिंग टूल्स को समझें।
- डेटा विज़ुअलाइज़ेशन सर्वोत्तम अभ्यास: दृश्य माध्यमों के माध्यम से डेटा को प्रभावी ढंग से प्रस्तुत करना सीखें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}