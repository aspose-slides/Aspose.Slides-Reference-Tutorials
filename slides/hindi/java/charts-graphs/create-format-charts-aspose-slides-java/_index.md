---
date: '2026-08-27'
description: Aspose.Slides का उपयोग करके Java में ग्रिड लाइन्स वाले चार्ट को कैसे
  जोड़ें, अक्षों और शीर्षकों को फ़ॉर्मेट करें, और एक पॉलिश्ड PowerPoint लाइन चार्ट
  को एक्सपोर्ट करना सीखें।
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: Aspose.Slides का उपयोग करके Java में ग्रिड लाइन्स वाले चार्ट को कैसे
  जोड़ें, अक्षों और शीर्षकों को फ़ॉर्मेट करें, और एक पॉलिश्ड PowerPoint लाइन चार्ट
  को एक्सपोर्ट करना सीखें।
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: Aspose.Slides for Java का उपयोग करके चार्ट में ग्रिड लाइन्स कैसे जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: Aspose.Slides for Java का उपयोग करके चार्ट में ग्रिड लाइन्स कैसे जोड़ें
url: /hi/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java के साथ चार्ट में ग्रिड लाइन्स कैसे जोड़ें

## परिचय
यदि आपको प्रोग्रामेटिक रूप से PowerPoint प्रस्तुति में **ग्रिड लाइन्स चार्ट** जोड़ने की आवश्यकता है, तो Aspose.Slides for Java आपको एक साफ़, पूरी‑फ़ीचर वाली API प्रदान करता है। चाहे आप त्रैमासिक व्यवसाय समीक्षा, शैक्षणिक व्याख्यान, या डेटा‑आधारित बिक्री डेक तैयार कर रहे हों, आप एक लाइन चार्ट बना सकते हैं, प्रत्येक दृश्य तत्व को अनुकूलित कर सकते हैं, और परिणाम को सेकंडों में सहेज सकते हैं—बिना PowerPoint को मैन्युअल रूप से खोले।

## त्वरित उत्तर
- **जावा में चार्ट बनाने वाली लाइब्रेरी कौन सी है?** Aspose.Slides for Java.
- **इस गाइड में कौन सा चार्ट प्रकार कवर किया गया है?** A line chart with markers and grid lines.
- **क्या नमूना चलाने के लिए लाइसेंस की आवश्यकता है?** A free temporary license works for evaluation; a commercial license is required for production.
- **मैं कौन सा IDE उपयोग कर सकता हूँ?** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans.
- **चार्ट तत्वों को कैसे फ़ॉर्मेट किया जाता है?** Using fluent API calls for titles, axes, grid lines, legends, and background colors.

## Aspose.Slides का उपयोग करके जावा में ग्रिड लाइन्स चार्ट कैसे जोड़ें
एक नया `Presentation` लोड करें, एक स्लाइड डालें, एक लाइन चार्ट जोड़ें, और फिर वर्टिकल एक्सिस पर मेजर ग्रिड लाइन्स सक्षम करें – यह सब दस से कम कोड लाइनों में। यह सीधा उत्तर आपको आवश्यक सटीक क्रम दिखाता है, ताकि आप कॉपी‑पेस्ट करके तुरंत एक पूरी तरह फ़ॉर्मेट किया हुआ चार्ट देख सकें।

### परिभाषा एंकर
`Presentation` Aspose.Slides की मुख्य क्लास है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करती है; सभी स्लाइड‑स्तर के ऑपरेशन इस ऑब्जेक्ट से शुरू होते हैं।

## लाइन चार्ट क्या है और Aspose.Slides क्यों उपयोग करें?
एक लाइन चार्ट डेटा पॉइंट्स की श्रृंखला को सीधी रेखाओं से जोड़ता है, जिससे समय के साथ रुझान तुरंत दिखाई देते हैं। Aspose.Slides **50 से अधिक चार्ट प्रकार** का समर्थन करता है और **प्रति श्रृंखला 10,000 डेटा पॉइंट्स** तक बिना noticeable slowdown के संभाल सकता है, जिससे बड़े डेटा सेट के लिए एंटरप्राइज़‑ग्रेड प्रदर्शन मिलता है।

### परिभाषा एंकर
`Chart` Aspose.Slides का टॉप‑लेवल ऑब्जेक्ट है जो किसी भी चार्ट के लिए प्रयोग होता है; यह सीरीज़, कैटेगरीज, और फ़ॉर्मेटिंग जानकारी संग्रहीत करता है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK) 8+** स्थापित है।
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, आदि)।
- **Aspose.Slides for Java** लाइब्रेरी Maven या Gradle के माध्यम से जोड़ी गई (नीचे *aspose.slides maven dependency* सेक्शन देखें)।

### Maven निर्भरता (aspose.slides maven dependency)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle निर्भरता
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

वैकल्पिक रूप से, नवीनतम JAR को [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

## लाइसेंस प्राप्ति (apply aspose license)
- परीक्षण के लिए [फ़्री ट्रायल लाइसेंस](https://purchase.aspose.com/temporary-license/) पेज से **फ़्री ट्रायल लाइसेंस** प्राप्त करें।
- प्रोडक्शन डिप्लॉयमेंट के लिए [Aspose की आधिकारिक साइट](https://purchase.aspose.com/buy) से पूर्ण लाइसेंस खरीदें।

## Aspose.Slides for Java सेटअप करना
1. ऊपर दिखाए गए Maven या Gradle निर्भरता को अपने प्रोजेक्ट में जोड़ें।
2. किसी भी `Presentation` ऑब्जेक्ट को बनाने से **पहले** लाइसेंस फ़ाइल लोड करें ताकि सभी फीचर अनलॉक हो जाएँ।

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## स्टेप‑बाय‑स्टेप इम्प्लीमेंटेशन

### Step 1: आउटपुट डायरेक्टरी बनाएं (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*क्यों यह महत्वपूर्ण है:* यह सुनिश्चित करना कि फ़ोल्डर मौजूद है, बाद में प्रस्तुति सहेजते समय `FileNotFoundException` को रोकता है।

### Step 2: स्लाइड जोड़ें और लाइन चार्ट डालें
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*व्याख्या:* यह एक नई स्लाइड बनाता है और निर्दिष्ट कॉर्डिनेट्स पर **मार्कर्स के साथ लाइन चार्ट** रखता है।

### Step 3: चार्ट शीर्षक जोड़ें (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*टिप:* बोल्ड, ग्रे शीर्षक का उपयोग करने से चार्ट तुरंत पहचानने योग्य बनता है।

### Step 4: अक्षों को फ़ॉर्मेट करें और ग्रिड लाइन्स जोड़ें (add grid lines)
#### वर्टिकल एक्सिस फ़ॉर्मेटिंग
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*क्यों यह महत्वपूर्ण है:* स्पष्ट ग्रिड लाइन्स और घुमाए गए लेबल पठनीयता बढ़ाते हैं, विशेषकर जब डेटा पॉइंट्स घने हों।

#### हॉरिज़ॉन्टल एक्सिस फ़ॉर्मेटिंग
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### Step 5: लेजेंड को कस्टमाइज़ करें (add chart legend)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### Step 6: बैकग्राउंड रंग सेट करें (format chart labels)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### Step 7: प्रस्तुति सहेजें
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*परिणाम:* अब आपके पास एक PowerPoint फ़ाइल (`FormattedChart_out.pptx`) है जिसमें पूरी तरह फ़ॉर्मेट किया हुआ लाइन चार्ट है।

## व्यावहारिक अनुप्रयोग (generate line chart powerpoint)
- **बिज़नेस रिपोर्ट्स:** त्रैमासिक राजस्व रुझान को स्पष्ट ग्रिड लाइन्स के साथ दिखाएँ।
- **अकादमिक लेक्चर:** कई सत्रों में प्रयोगात्मक डेटा को विज़ुअलाइज़ करें।
- **प्रोजेक्ट प्रपोज़ल्स:** माइलस्टोन प्रगति और भविष्यवाणी वक्रों को हाइलाइट करें।
- **मार्केटिंग एनालिसिस:** कैंपेन ROI रुझानों को प्रतिस्पर्धी डेटा के साथ साइड‑बाय‑साइड प्रस्तुत करें।
- **डैशबोर्ड इंटीग्रेशन:** स्टेकहोल्डर मीटिंग्स के लिए लाइव एनालिटिक्स को PowerPoint में एक्सपोर्ट करें।

## प्रदर्शन संबंधी विचार
- **मेमोरी प्रबंधन:** सहेजने के बाद `presentation.dispose()` कॉल करें ताकि नेटिव रिसोर्सेज तुरंत रिलीज़ हो जाएँ।
- **बड़े डेटा सेट:** Aspose.Slides स्ट्रीमिंग का उपयोग करके हजारों पॉइंट्स वाले चार्ट प्रोसेस करता है, जिससे सामान्य सर्वर पर मेमोरी उपयोग 100 MB से कम रहता है।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **License not applied** | किसी भी `Presentation` ऑब्जेक्ट को इंस्टैंशिएट करने से **पहले** ट्रायल या फुल लाइसेंस लोड करें। |
| **Chart appears blank** | सुनिश्चित करें कि स्लाइड में कम से कम एक डेटा सीरीज़ है; आवश्यकता होने पर `chart.getChartData().getSeries().add(...)` के माध्यम से सीरीज़ जोड़ें। |
| **File not saved** | आउटपुट डायरेक्टरी मौजूद है यह सुनिश्चित करें (स्टेप 1 देखें)। |
| **Colors not applied** | विश्वसनीय रंग रेंडरिंग के लिए `java.awt.Color` कॉन्स्टेंट्स या `PresetColor` एनोम का उपयोग करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं लाइन चार्ट के अलावा अन्य चार्ट प्रकार बना सकता हूँ?**  
A: हाँ, Aspose.Slides बार, पाई, स्कैटर, रेडार, और 50 से अधिक अतिरिक्त चार्ट प्रकारों का समर्थन करता है।

**Q: लाइन चार्ट में कई डेटा सीरीज़ कैसे जोड़ूँ?**  
A: फ़ॉर्मेटिंग लागू करने से पहले अतिरिक्त सीरीज़ डालने के लिए `chart.getChartData().getSeries().add(...)` उपयोग करें।

**Q: क्या चार्ट को इमेज के रूप में एक्सपोर्ट करना संभव है?**  
A: बिल्कुल। स्लाइड को PNG, JPEG, या SVG में `presentation.save("slide.png", SaveFormat.Png)` के साथ रेंडर करें।

**Q: विकास के लिए क्या मुझे पेड लाइसेंस चाहिए?**  
A: मूल्यांकन के लिए फ्री टेम्पररी लाइसेंस पर्याप्त है; प्रोडक्शन उपयोग के लिए कमर्शियल लाइसेंस आवश्यक है।

**Q: कौन से जावा संस्करण समर्थित हैं?**  
A: लाइब्रेरी JDK 8 से लेकर JDK 22 तक काम करती है; Maven/Gradle निर्भरता जोड़ते समय उपयुक्त क्लासिफ़ायर (जैसे `jdk16`) चुनें।

**अंतिम अपडेट:** 2026-08-27  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**लेखक:** Aspose  

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## संबंधित ट्यूटोरियल

- [aspose slides maven निर्भरता: Aspose.Slides for Java का उपयोग करके प्रस्तुतियों में चार्ट जोड़ें और कॉन्फ़िगर करें](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [PowerPoint में चार्ट जोड़ने के लिए Aspose.Slides for Java का उपयोग: स्टेप‑बाय‑स्टेप गाइड](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose Slides Java में कस्टमाइज़्ड चार्ट ट्रेंड लाइन्स बनाएं](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}