---
"date": "2025-04-17"
"description": "Aspose.Slides का उपयोग करके Java में चार्ट के साथ गतिशील प्रस्तुतियाँ बनाना और कॉन्फ़िगर करना सीखें। प्रस्तुतियों को प्रभावी ढंग से जोड़ना, अनुकूलित करना और सहेजना सीखें।"
"title": "Aspose.Slides for Java का उपयोग करके चार्ट के साथ Java प्रस्तुतियाँ बनाएँ"
"url": "/hi/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# जावा के लिए Aspose.Slides का उपयोग करके चार्ट के साथ प्रस्तुति कैसे बनाएं और कॉन्फ़िगर करें

## परिचय

आज के तेज़-तर्रार कारोबारी माहौल में डेटा को प्रभावी ढंग से व्यक्त करने वाले गतिशील प्रस्तुतियाँ बनाना ज़रूरी है। चाहे आप वित्तीय रिपोर्ट तैयार कर रहे हों या प्रोजेक्ट मेट्रिक्स दिखा रहे हों, चार्ट जोड़ने से आपकी प्रस्तुति का प्रभाव काफ़ी हद तक बढ़ सकता है। यह ट्यूटोरियल आपको Aspose.Slides for Java का उपयोग करके 3D स्टैक्ड कॉलम चार्ट के साथ प्रस्तुति बनाने और कॉन्फ़िगर करने के बारे में मार्गदर्शन करता है, जो कि प्रोग्रामेटिक रूप से प्रस्तुतियों को संभालने के लिए डिज़ाइन की गई एक शक्तिशाली लाइब्रेरी है।

**आप क्या सीखेंगे:**
- नया प्रेजेंटेशन कैसे बनाएं
- स्लाइड में चार्ट जोड़ें और कॉन्फ़िगर करें
- चार्ट डेटा और उपस्थिति को अनुकूलित करें
- अपनी प्रस्तुति को प्रभावी ढंग से सहेजें

क्या आप जावा के साथ आकर्षक प्रस्तुतिकरण बनाने में महारत हासिल करने के लिए तैयार हैं? चलिए शुरू करते हैं!

## आवश्यक शर्तें

ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपने इन पूर्व-आवश्यकताओं को पूरा कर लिया है:

- **पुस्तकालय और निर्भरताएँ**: Aspose.Slides for Java स्थापित होना चाहिए।
- **पर्यावरण सेटअप**: जावा वातावरण में कार्य करें (JDK 16 या बाद का संस्करण अनुशंसित है)।
- **ज्ञानधार**बुनियादी जावा प्रोग्रामिंग अवधारणाओं से परिचित होना लाभदायक होगा।

## Java के लिए Aspose.Slides सेट अप करना

### इंस्टालेशन

Aspose.Slides को अपने प्रोजेक्ट में एकीकृत करने के लिए, इन चरणों का पालन करें:

**मावेन**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**ग्रैडल**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**प्रत्यक्षत: डाउनलोड**: वैकल्पिक रूप से, नवीनतम संस्करण यहाँ से डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

### लाइसेंस अधिग्रहण
- **मुफ्त परीक्षण**: सुविधाओं का पता लगाने के लिए निःशुल्क परीक्षण से शुरुआत करें।
- **अस्थायी लाइसेंस**विस्तारित परीक्षण के लिए अस्थायी लाइसेंस प्राप्त करें।
- **खरीदना**: व्यावसायिक उपयोग के लिए पूर्ण लाइसेंस प्राप्त करें।

एक बार इंस्टॉल हो जाने पर, अपने जावा वातावरण में लाइब्रेरी का एक उदाहरण बनाकर उसे आरंभ करें। `Presentation` यह आपके प्रेजेंटेशन में चार्ट और अन्य तत्वों को जोड़ने के लिए आधार तैयार करता है।

## कार्यान्वयन मार्गदर्शिका

### चार्ट के साथ प्रस्तुति बनाएं और कॉन्फ़िगर करें

#### अवलोकन
Aspose.Slides के साथ स्क्रैच से प्रेजेंटेशन बनाना बहुत आसान है। इस अनुभाग में, हम अपनी प्रेजेंटेशन की पहली स्लाइड में 3D स्टैक्ड कॉलम चार्ट जोड़ेंगे।

**चरण:**

1. **प्रस्तुति ऑब्जेक्ट आरंभ करें**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // एक नया प्रेजेंटेशन ऑब्जेक्ट आरंभ करें
           Presentation presentation = new Presentation();
           
           // प्रस्तुति में पहली स्लाइड तक पहुँचें
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // स्थिति (0,0) पर स्लाइड में 3D स्टैक्ड कॉलम चार्ट जोड़ें
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **पैरामीटर्स समझाएं**:
   - `ChartType.StackedColumn3D`: चार्ट प्रकार निर्दिष्ट करता है.
   - स्थिति और आकार `(0, 0, 500, 500)`: यह निर्धारित करता है कि चार्ट स्लाइड पर कहां दिखाई देगा।

### चार्ट डेटा कॉन्फ़िगर करें

#### अवलोकन
अपने चार्ट को सार्थक बनाने के लिए, इसकी डेटा श्रृंखला और श्रेणियों को कॉन्फ़िगर करें। यह अनुभाग दर्शाता है कि अपने चार्ट में विशिष्ट डेटा बिंदु कैसे जोड़ें।

**चरण:**

1. **चार्ट की डेटा कार्यपुस्तिका तक पहुँचें**

   ```java
   public static void configureChartData(IChart chart) {
       // चार्ट डेटा वाले वर्कशीट का इंडेक्स सेट करें
       int defaultWorksheetIndex = 0;
       
       // चार्ट की डेटा वर्कबुक तक पहुँचें
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // नामों के साथ दो श्रृंखलाएँ जोड़ें
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // तीन श्रेणियाँ जोड़ें
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### चार्ट के लिए रोटेशन3D गुण सेट करें

#### अवलोकन
3D रोटेशन गुणों के साथ अपने चार्ट की दृश्य अपील को बढ़ाएँ। यह अनुकूलन आपको परिप्रेक्ष्य और गहराई को समायोजित करने की अनुमति देता है।

**चरण:**

1. **3D रोटेशन कॉन्फ़िगर करें**

   ```java
   public static void setRotation3D(IChart chart) {
       // समकोण अक्षों को सक्षम करें और X, Y दिशाओं में घुमावों और गहराई प्रतिशत को कॉन्फ़िगर करें
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **पैरामीटर्स समझाएं**:
   - `setRightAngleAxes(true)`: यह सुनिश्चित करता है कि अक्ष लंबवत हों।
   - रोटेशन मान: 3D दृश्य के कोण और गहराई को समायोजित करता है।

### चार्ट में श्रृंखला डेटा भरें

#### अवलोकन
विश्लेषण के लिए अपने चार्ट को डेटा बिंदुओं से भरना महत्वपूर्ण है। यहाँ, हम अपने चार्ट के भीतर एक श्रृंखला में विशिष्ट मान जोड़ेंगे।

**चरण:**

1. **डेटा पॉइंट जोड़ें**

   ```java
   public static void populateSeriesData(IChart chart) {
       // दूसरे चार्ट श्रृंखला तक पहुंचें
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // निर्दिष्ट मानों के साथ बार श्रृंखला के लिए डेटा बिंदु जोड़ें
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### चार्ट में श्रृंखला ओवरलैप समायोजित करें

#### अवलोकन
अपने चार्ट की दिखावट को बेहतर बनाने से पठनीयता में सुधार हो सकता है। इस अनुभाग में बताया गया है कि बेहतर डेटा विज़ुअलाइज़ेशन के लिए ओवरलैप प्रॉपर्टी को कैसे समायोजित किया जाए।

**चरण:**

1. **सेट श्रृंखला ओवरलैप**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // चार्ट से दूसरी श्रृंखला प्राप्त करें और उसका ओवरलैप 100 पर सेट करें
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### प्रस्तुति सहेजें

#### अवलोकन
एक बार जब आपकी प्रस्तुति कॉन्फ़िगर हो जाए, तो उसे वांछित प्रारूप में डिस्क पर सहेजें। यह चरण सुनिश्चित करता है कि सभी परिवर्तन संरक्षित हैं।

**चरण:**

1. **प्रस्तुति सहेजें**

   ```java
   public static void savePresentation(Presentation presentation) {
       // संशोधित प्रस्तुति को फ़ाइल में सहेजें
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## निष्कर्ष

अब आप जान गए हैं कि Aspose.Slides for Java का उपयोग करके चार्ट के साथ प्रेजेंटेशन कैसे बनाएं और कॉन्फ़िगर करें। इस गाइड में प्रेजेंटेशन को आरंभ करना, 3D स्टैक्ड कॉलम चार्ट जोड़ना, डेटा श्रृंखला और श्रेणियों को कॉन्फ़िगर करना, रोटेशन गुण सेट करना, श्रृंखला डेटा को पॉप्युलेट करना, श्रृंखला ओवरलैप को समायोजित करना और अंतिम प्रेजेंटेशन को सहेजना शामिल है।

अधिक उन्नत सुविधाओं और अनुकूलन विकल्पों के लिए, देखें [Aspose.Slides for Java दस्तावेज़](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}