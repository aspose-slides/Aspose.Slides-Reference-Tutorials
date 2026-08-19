---
date: '2026-07-08'
description: Aspose का उपयोग करके Java के साथ PowerPoint में doughnut chart बनाने
  का तरीका सीखें। यह चरण‑दर‑चरण मार्गदर्शिका प्रोग्रामेटिक रूप से चार्ट डेटा पॉइंट्स
  जोड़ना, लेबल्स को कस्टमाइज़ करना, और PPTX को उच्च सटीकता के साथ सहेजना दिखाती है।
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Aspose का उपयोग करके आप Java का उपयोग करके PowerPoint में doughnut
  chart बना सकते हैं। इस ट्यूटोरियल का पालन करके डेटा पॉइंट्स जोड़ें, लेबल्स को कस्टमाइज़
  करें, और PPTX को उच्च सटीकता के साथ सहेजें।
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Aspose का उपयोग कैसे करें: PowerPoint (Java) में doughnut chart बनाएं'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Aspose का उपयोग करके PowerPoint (Java) में doughnut chart कैसे बनाएं
url: /hi/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose का उपयोग करके PowerPoint (Java) में डोनट चार्ट कैसे बनाएं

## परिचय
प्रभावशाली प्रस्तुतियों को बनाने के लिए अक्सर केवल टेक्स्ट और इमेज से अधिक की आवश्यकता होती है; चार्ट डेटा को प्रभावी ढंग से विज़ुअलाइज़ करके कहानी कहने को काफी बढ़ा सकते हैं। **Aspose का उपयोग कैसे करें** चार्ट जनरेशन के लिए आपको PowerPoint खोले बिना प्रोग्रामेटिक नियंत्रण देता है। यह ट्यूटोरियल आपको डोनट चार्ट बनाने, उसके डेटा पॉइंट्स को कॉन्फ़िगर करने और हाई‑फ़िडेलिटी PPTX सेव करने की प्रक्रिया दिखाता है। आपको केवल बुनियादी Java ज्ञान और कुछ मिनटों की सेटअप समय चाहिए।

`Aspose.Slides for Java` एक Java लाइब्रेरी है जो Microsoft Office के बिना PowerPoint फ़ाइलों का निर्माण, हेरफेर और रूपांतरण सक्षम करती है।

## त्वरित उत्तर
- **PowerPoint में डोनट चार्ट बनाने वाली लाइब्रेरी कौन सी है?** Aspose.Slides for Java  
- **क्या मैं प्रोग्रामेटिक रूप से चार्ट डेटा पॉइंट्स जोड़ सकता हूँ?** हाँ, चार्ट API का उपयोग करके  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** एक वैध Aspose.Slides लाइसेंस आवश्यक है  
- **कौन से Java संस्करण समर्थित हैं?** Java 8 और उसके बाद के (JDK 16 classifier दिखाया गया है)  
- **मैं कितनी सीरीज़ जोड़ सकता हूँ?** उदाहरण में अधिकतम 15 सीरीज़ जोड़ी गई हैं, लेकिन आप आवश्यकता अनुसार समायोजित कर सकते हैं  

## PowerPoint में डोनट चार्ट क्या है?
डोनट चार्ट एक गोलाकार चार्ट है जो पाई चार्ट के समान है लेकिन इसका केंद्र खोखला होता है, जिससे एक साथ कई सीरीज़ प्रदर्शित की जा सकती हैं। यह भाग‑से‑सम्पूर्ण संबंधों पर ज़ोर देता है जबकि दृश्य लेआउट को कॉम्पैक्ट और पढ़ने में आसान रखता है।

## डोनट चार्ट बनाने के लिए Aspose.Slides for Java का उपयोग क्यों करें?
Aspose.Slides for Java 50 से अधिक इनपुट और आउटपुट फ़ॉर्मेट को संभालता है और पूरी फ़ाइल को मेमोरी में लोड किए बिना 500 MB तक की प्रस्तुतियों को जेनरेट कर सकता है। यह किसी भी Java प्लेटफ़ॉर्म पर चार्ट की उपस्थिति, डेटा और लेआउट पर पूर्ण प्रोग्रामेटिक नियंत्रण देता है, COM इंटरऑप को समाप्त करता है, और सामान्य सर्वर पर दो सेकंड से कम समय में 100 चार्ट‑समृद्ध स्लाइड्स रेंडर कर सकता है।

## पूर्वापेक्षाएँ
- Java प्रोग्रामिंग का बुनियादी ज्ञान।  
- IntelliJ IDEA या Eclipse जैसे IDE।  
- निर्भरता प्रबंधन के लिए Maven या Gradle।  
- एक वैध Aspose.Slides for Java लाइसेंस (फ़्री ट्रायल उपलब्ध)।  

## Aspose.Slides for Java सेटअप करना
अपने प्रोजेक्ट के अनुरूप डिपेंडेंसी मैनेजर चुनें।

**Maven**  
`pom.xml` में निम्नलिखित डिपेंडेंसी जोड़ें (संस्करण को नवीनतम रिलीज़ से बदलें):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
`build.gradle` में यह लाइन जोड़ें:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

यदि आप सीधे डाउनलोड करना पसंद करते हैं, तो [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) पेज पर जाएँ।

### लाइसेंस प्राप्ति
आप Aspose.Slides की सुविधाओं को आज़माने के लिए मुफ्त ट्रायल से शुरू कर सकते हैं। विस्तारित उपयोग के लिए, लाइसेंस खरीदें या [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/) से एक अस्थायी लाइसेंस अनुरोध करें। अपने वातावरण को सेटअप करने और एप्लिकेशन में Aspose.Slides को इनिशियलाइज़ करने के लिए प्रदान किए गए निर्देशों का पालन करें।

## Aspose.Slides for Java का उपयोग करके PowerPoint में डोनट चार्ट कैसे बनाएं
डोनट चार्ट बनाने के लिए, पहले `Presentation` लोड या बनाएं, `ChartType.Doughnut` प्रकार का चार्ट शेप जोड़ें, डिफ़ॉल्ट सीरीज़ को साफ़ करें, होल साइज सेट करें, और फिर चार्ट की वर्कबुक को श्रेणी नामों और संख्यात्मक मानों से भरें। अंत में, लेबल फ़ॉर्मेटिंग को समायोजित करें और PPTX सेव करें।

### चरण 1: प्रस्तुति को इनिशियलाइज़ करें
एक नई प्रस्तुति बनाएं या मौजूदा फ़ाइल खोलें ताकि स्लाइड कलेक्शन प्राप्त हो सके।

`Presentation` वह मुख्य क्लास है जो PowerPoint फ़ाइल का प्रतिनिधित्व करता है।  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### चरण 2: स्लाइड में डोनट चार्ट जोड़ें
एक चार्ट शेप डालें, डिफ़ॉल्ट सीरीज़/कैटेगरी हटाएँ, और डोनट होल साइज जैसी बुनियादी दृश्य सेटिंग्स कॉन्फ़िगर करें।

`Chart` (या चार्ट शेप) स्लाइड पर रखे गए चार्ट ऑब्जेक्ट को दर्शाता है।  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### चरण 3: चार्ट डेटा पॉइंट्स जोड़ें और लेबल कस्टमाइज़ करें
श्रेणी नाम भरें, प्रत्येक सीरीज़ के लिए डेटा पॉइंट्स जोड़ें, और लेबल फ़ॉर्मेटिंग (फ़ॉन्ट, रंग, स्थिति) को सूक्ष्म रूप से समायोजित करें। यह चरण “चार्ट डेटा पॉइंट्स जोड़ें” क्षमता को दर्शाता है।

`Workbook` चार्ट के अंतर्निहित स्प्रेडशीट डेटा तक पहुंच प्रदान करता है जहाँ सेल्स को भरना होता है।  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### चरण 4: अपडेटेड प्रस्तुति को सेव करें
परिवर्तनों को डिस्क पर नई PPTX फ़ाइल में सहेजें।

`save` चयनित फ़ॉर्मेट में प्रस्तुति को फ़ाइल में लिखता है।  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## व्यावहारिक उपयोग
- **वित्तीय रिपोर्ट्स:** बजट आवंटन या खर्च विभाजन को विज़ुअलाइज़ करना।  
- **बाजार विश्लेषण:** प्रतिस्पर्धियों के बीच मार्केट‑शेयर वितरण दिखाना।  
- **सर्वे परिणाम:** श्रेणीबद्ध सर्वे डेटा को कॉम्पैक्ट रूप में प्रस्तुत करना।  
- **डैशबोर्ड जनरेशन:** डेटाबेस क्वेरीज़ के साथ मिलाकर लाइव‑अपडेटिंग स्लाइड्स बनाना।  

## प्रदर्शन संबंधी विचार
- **संसाधन मुक्त करें:** सेव करने के बाद `pres.dispose()` कॉल करके नेटिव मेमोरी मुक्त करें।  
- **चार्ट की संख्या सीमित करें:** सैकड़ों चार्ट जोड़ने से मेमोरी उपयोग बढ़ सकता है; आवश्यकता होने पर बैच‑प्रोसेस करें।  
- **स्ट्रीमिंग का उपयोग करें:** बड़े डेटा सेट के लिए, इन‑मेमोरी एरेज़ के बजाय स्ट्रीम से सीधे वर्कबुक भरें।  

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| **चार्ट खाली दिख रहा है** | डेटा सेल्स सही ढंग से भर नहीं रहे हैं | सुनिश्चित करें कि `workBook.getCell(...)` सही पंक्ति/स्तंभ इंडेक्स को संदर्भित कर रहा है। |
| **लेबल ओवरलैप** | सीमित स्थान में बहुत अधिक श्रेणियाँ | `DoughnutHoleSize` बढ़ाएँ या `FirstSliceAngle` को समायोजित करें। |
| **OutOfMemoryError** | बिना संसाधन मुक्त किए बड़ी प्रस्तुतियाँ | सेव करने के बाद `pres.dispose()` कॉल करें और JVM हीप साइज बढ़ाने पर विचार करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Slides for Java को व्यावसायिक एप्लिकेशन्स में उपयोग कर सकता हूँ?**  
**उत्तर:** हाँ, लेकिन आपको एक वैध व्यावसायिक लाइसेंस चाहिए। मूल्यांकन के लिए एक मुफ्त ट्रायल उपलब्ध है।

**प्रश्न: मैं 15 से अधिक सीरीज़ कैसे जोड़ूँ?**  
**उत्तर:** “Add Doughnut Chart” चरण में लूप सीमा बढ़ाएँ और सुनिश्चित करें कि आपके डेटा वर्कबुक में पर्याप्त पंक्तियाँ हों।

**प्रश्न: क्या निर्माण के बाद डोनट होल साइज बदलना संभव है?**  
**उत्तर:** हाँ, सेव करने से पहले `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` कॉल करें।

**प्रश्न: क्या मैं चार्ट को PPTX के बजाय इमेज के रूप में एक्सपोर्ट कर सकता हूँ?**  
**उत्तर:** बिल्कुल। `chart.getImage()` का उपयोग करें और लौटाए गए `java.awt.image.BufferedImage` को अपनी पसंद के फ़ॉर्मेट में सहेजें।

**प्रश्न: क्या Aspose.Slides एनिमेटेड चार्ट्स को सपोर्ट करता है?**  
**उत्तर:** एनिमेशन `ISlide.getTimeline()` API के माध्यम से जोड़ी जा सकती है, हालांकि यह ट्यूटोरियल के दायरे से बाहर है।

## निष्कर्ष
अब आपके पास Aspose.Slides for Java के साथ **डोनट चार्ट PowerPoint** फ़ाइलें बनाने की एक पूर्ण, प्रोडक्शन‑रेडी विधि है, जिसमें **चार्ट डेटा पॉइंट्स जोड़ना**, लेबल कस्टमाइज़ करना, और प्रदर्शन संबंधी विचारों को संभालना शामिल है। विभिन्न रंगों, डेटा स्रोतों और चार्ट प्रकारों के साथ प्रयोग करें ताकि आपकी प्रस्तुतियाँ वास्तव में अलग दिखें।

---

**अंतिम अपडेट:** 2026-07-08  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**लेखक:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## संबंधित ट्यूटोरियल्स

- [PowerPoint में चार्ट कैसे जोड़ें Aspose.Slides for Java का उपयोग करके: चरण‑दर‑चरण गाइड](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java का उपयोग करके PowerPoint चार्ट डेटा कैसे संपादित करें: एक व्यापक गाइड](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Aspose.Slides for Java से PowerPoint में चार्ट एनिमेट करें – चरण‑दर‑चरण गाइड](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}