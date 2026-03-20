---
date: '2026-03-20'
description: Aspose.Slides का उपयोग करके जावा प्रेजेंटेशन में चार्ट कैसे जोड़ें और
  प्रेजेंटेशन चार्ट फ़ाइलें जल्दी बनाएं, सीखें।
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Aspose.Slides के साथ जावा प्रेजेंटेशन में चार्ट कैसे जोड़ें
url: /hi/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java का उपयोग करके प्रस्तुति में चार्ट कैसे जोड़ें

## परिचय

आज की तेज़‑गति वाले व्यावसायिक माहौल में डेटा को प्रभावी ढंग से प्रस्तुत करने वाली गतिशील प्रस्तुतियों का निर्माण आवश्यक है। चाहे आप वित्तीय रिपोर्ट, मार्केटिंग डेक, या प्रोजेक्ट स्टेटस अपडेट तैयार कर रहे हों, **स्लाइड में चार्ट जोड़ना** दर्शकों की सहभागिता को काफी बढ़ा सकता है। इस ट्यूटोरियल में आप चरण‑दर‑चरण सीखेंगे कि 3D स्टैक्ड कॉलम चार्ट कैसे जोड़ें, उसके डेटा को कॉन्फ़िगर करें, और अंतिम फ़ाइल को सहेजें—सभी Aspose.Slides for Java के साथ।

### त्वरित उत्तर
- **मुख्य लाइब्रेरी कौन सी है?** Aspose.Slides for Java  
- **कौन सा चार्ट प्रकार दर्शाया गया है?** 3D स्टैक्ड कॉलम  
- **क्या मैं प्रोग्रामेटिकली प्रस्तुति चार्ट फ़ाइलें बना सकता हूँ?** हाँ, नीचे दिखाए गए API मेथड्स का उपयोग करके  
- **कौन सा Java संस्करण अनुशंसित है?** JDK 16 या बाद का  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** व्यावसायिक उपयोग के लिए एक वैध Aspose.Slides लाइसेंस आवश्यक है  

## Aspose.Slides में “चार्ट कैसे जोड़ें” क्या है?

Aspose.Slides for Java उन वस्तुओं का समृद्ध सेट प्रदान करता है जो आपको Microsoft Office के बिना PowerPoint फ़ाइलें बनाने, संपादित करने और निर्यात करने की अनुमति देता है। चार्ट जोड़ना इतना सरल है कि आप एक `Presentation` ऑब्जेक्ट बनाते हैं, एक चार्ट शैप डालते हैं, और बिल्ट‑इन वर्कबुक के माध्यम से डेटा फीड करते हैं।

## Java प्रस्तुतियों में चार्ट क्यों जोड़ें?

- **दृश्य प्रभाव:** चार्ट कच्चे आंकड़ों को तुरंत समझ में आने वाले विज़ुअल में बदल देते हैं।  
- **ऑटोमेशन:** रिपोर्ट को ऑन‑द‑फ़्लाई जनरेट करें—शेड्यूल्ड ईमेल डाइजेस्ट या डैशबोर्ड के लिए आदर्श।  
- **संगतता:** सभी जनरेटेड डेक्स में समान स्टाइलिंग और ब्रांडिंग का उपयोग करें।  
- **पोर्टेबिलिटी:** एक ही मेथड कॉल से PPTX, PDF, या इमेज में निर्यात करें।

## पूर्वापेक्षाएँ

- **लाइब्रेरी और डिपेंडेंसीज़:** Aspose.Slides for Java स्थापित होना चाहिए।  
- **पर्यावरण सेटअप:** Java पर्यावरण में काम करें (JDK 16 या बाद का अनुशंसित)।  
- **ज्ञान आधार:** बेसिक Java प्रोग्रामिंग कॉन्सेप्ट्स की परिचितता उपयोगी होगी।

## Aspose.Slides for Java सेटअप करना

### इंस्टॉलेशन

Aspose.Slides को अपने प्रोजेक्ट में इंटीग्रेट करने के लिए नीचे दिए गए विकल्पों में से किसी एक का पालन करें।

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**डायरेक्ट डाउनलोड**: वैकल्पिक रूप से, नवीनतम संस्करण [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंस प्राप्त करना
- **फ्री ट्रायल:** फीचर्स का पता लगाने के लिए फ्री ट्रायल से शुरू करें।  
- **टेम्पररी लाइसेंस:** विस्तारित टेस्टिंग के लिए एक टेम्पररी लाइसेंस प्राप्त करें।  
- **खरीदें:** व्यावसायिक उपयोग के लिए पूर्ण लाइसेंस खरीदें।

इंस्टॉल होने के बाद, आप `Presentation` क्लास को इंस्टैंशिएट कर सकते हैं, जो सभी चार्ट‑संबंधित ऑपरेशन्स का एंट्री पॉइंट है।

## इम्प्लीमेंटेशन गाइड

### 3D स्टैक्ड कॉलम के साथ प्रस्तुति में चार्ट कैसे जोड़ें

#### अवलोकन
Aspose.Slides के साथ शून्य से एक प्रस्तुति बनाना सीधा है। इस सेक्शन में हम अपनी प्रस्तुति की पहली स्लाइड में 3D स्टैक्ड कॉलम चार्ट जोड़ेंगे।

**कदम:**

1. **Presentation ऑब्जेक्ट इनिशियलाइज़ करें**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
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

2. **पैरामीटर्स समझाएँ**  
   - `ChartType.StackedColumn3D`: चार्ट प्रकार निर्दिष्ट करता है।  
   - पोज़िशन और साइज `(0, 0, 500, 500)`: स्लाइड पर चार्ट कहाँ दिखेगा, यह निर्धारित करता है।

### चार्ट डेटा कॉन्फ़िगर करें

#### अवलोकन
अपने चार्ट को अर्थपूर्ण बनाने के लिए, डेटा सीरीज़ और कैटेगरीज को कॉन्फ़िगर करें। यह सेक्शन दिखाता है कि कैसे विशिष्ट डेटा पॉइंट्स को चार्ट में जोड़ें।

**कदम:**

1. **चार्ट के डेटा वर्कबुक तक पहुँचें**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### चार्ट के लिए Rotation3D प्रॉपर्टीज़ सेट करें

#### अवलोकन
3D रोटेशन प्रॉपर्टीज़ के साथ अपने चार्ट की दृश्य आकर्षण बढ़ाएँ। यह कस्टमाइज़ेशन आपको परिप्रेक्ष्य और गहराई को एडजस्ट करने की अनुमति देता है।

**कदम:**

1. **3D रोटेशन कॉन्फ़िगर करें**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **पैरामीटर्स समझाएँ**  
   - `setRightAngleAxes(true)`: एक्सिस को लंबवत सुनिश्चित करता है।  
   - रोटेशन वैल्यूज़: 3D व्यू के एंगल और डेप्थ को एडजस्ट करें।

### चार्ट में सीरीज़ डेटा भरें

#### अवलोकन
डेटा पॉइंट्स के साथ चार्ट को भरना विश्लेषण के लिए आवश्यक है। यहाँ हम अपनी चार्ट की एक सीरीज़ में विशिष्ट मान जोड़ेंगे।

**कदम:**

1. **डेटा पॉइंट्स जोड़ें**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
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

### चार्ट में सीरीज़ ओवरलैप समायोजित करें

#### अवलोकन
अपने चार्ट की उपस्थिति को फाइन‑ट्यून करने से पठनीयता में सुधार हो सकता है। यह सेक्शन बेहतर डेटा विज़ुअलाइज़ेशन के लिए ओवरलैप प्रॉपर्टी को कैसे एडजस्ट करें, बताता है।

**कदम:**

1. **सीरीज़ ओवरलैप सेट करें**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### प्रस्तुति सहेजें

#### अवलोकन
एक बार जब आपकी प्रस्तुति कॉन्फ़िगर हो जाए, तो इसे इच्छित फॉर्मेट में डिस्क पर सहेजें। यह कदम सभी बदलावों को संरक्षित करता है।

**कदम:**

1. **प्रेजेंटेशन सहेजें**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|-------|----------|
| **चार्ट फ्लैट दिख रहा है** | 3D रोटेशन सेट नहीं है | उपयुक्त X/Y वैल्यूज़ के साथ `setRotation3D` कॉल करें। |
| **डेटा नहीं दिख रहा** | वर्कबुक सेल्स लिंक नहीं हैं | सुनिश्चित करें कि `fact.getCell` सही रो/कॉलम इंडेक्स को रेफ़र कर रहा है। |
| **फ़ाइल सहेजी नहीं गई** | पाथ गलत या अनुमति नहीं है | `outputFilePath` लिखने योग्य है और फ़ोल्डर मौजूद है, यह जाँचें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं PPTX के अलावा अन्य फॉर्मेट में प्रस्तुति चार्ट फ़ाइलें जनरेट कर सकता हूँ?**  
उ: हाँ, Aspose.Slides `SaveFormat` एनेम के माध्यम से PDF, ODP, और इमेज फॉर्मेट को सपोर्ट करता है।

**प्र: विकास में कोड चलाने के लिए लाइसेंस चाहिए?**  
उ: विकास के लिए टेम्पररी या इवैल्यूएशन लाइसेंस काम करता है, लेकिन प्रोडक्शन डिप्लॉयमेंट के लिए पूर्ण लाइसेंस आवश्यक है।

**प्र: क्या एक ही स्लाइड में कई चार्ट जोड़ सकते हैं?**  
उ: बिल्कुल। विभिन्न पोज़िशन या साइज के साथ `slide.getShapes().addChart` को कई बार कॉल करें।

**प्र: चार्ट का कलर पैलेट कैसे बदलें?**  
उ: `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` का उपयोग करें और `SolidFillColor` सेट करें।

**प्र: क्या चार्ट को डेटाबेस जैसे एक्सटर्नल डेटा सोर्स से बाइंड कर सकते हैं?**  
उ: हाँ। JDBC के साथ डेटा रिट्रीव करें, फिर वर्कबुक सेल्स को प्रोग्रामेटिकली पॉप्युलेट करें और सहेजें।

## निष्कर्ष

आपने अब **Java प्रस्तुति में चार्ट कैसे जोड़ें**, उसके डेटा को कॉन्फ़िगर करना, 3D रोटेशन कस्टमाइज़ करना, सीरीज़ ओवरलैप एडजस्ट करना, और अंतिम फ़ाइल सहेजना सीख लिया है। यह ज्ञान आपको रिपोर्ट जनरेशन ऑटोमेट करने, ब्रांडिंग को सुसंगत रखने, और मैन्युअल प्रयास के बिना डेटा‑ड्रिवेन प्रस्तुतियों को डिलीवर करने में मदद करेगा। अधिक उन्नत कस्टमाइज़ेशन—जैसे लेजेंड, एक्सिस स्टाइलिंग, या थीम लागू करना—के लिए आधिकारिक दस्तावेज़ में पूरी क्षमताओं का अन्वेषण करें।

अधिक उन्नत फीचर्स और कस्टमाइज़ेशन विकल्पों के लिए, देखें [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/)।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-03-20  
**टेस्टेड विद:** Aspose.Slides for Java 25.4 (JDK 16)  
**लेखक:** Aspose