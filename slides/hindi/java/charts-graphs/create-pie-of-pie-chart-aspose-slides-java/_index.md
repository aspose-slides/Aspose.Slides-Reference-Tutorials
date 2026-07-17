---
date: '2026-07-17'
description: Aspose.Slides for Java का उपयोग करके Pie of Pie चार्ट बनाकर PowerPoint
  में चार्ट कैसे जोड़ें, सीखें। सेटअप, कोड, कस्टमाइज़ेशन, और PPTX के रूप में सहेजने
  की जानकारी शामिल है।
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Aspose.Slides for Java के साथ PowerPoint में चार्ट जोड़ें। यह गाइड
  मिनटों में Pie of Pie चार्ट को बनाने, कस्टमाइज़ करने और PPTX के रूप में सहेजने का
  तरीका दिखाता है।
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: PowerPoint में चार्ट जोड़ें – Java में Pie of Pie Chart बनाएं
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: PowerPoint में चार्ट जोड़ें – Java में Aspose.Slides के साथ Pie of Pie Chart
  बनाएं
url: /hi/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint में चार्ट जोड़ें – Aspose.Slides के साथ जावा में पाई ऑफ पाई चार्ट बनाएं

## चार्ट और ग्राफ़

### परिचय

आधुनिक डेटा‑चालित प्रस्तुतियों में, **PowerPoint में चार्ट जोड़ना** अक्सर कच्चे आंकड़ों को दृश्य अंतर्दृष्टि में बदलने का सबसे तेज़ तरीका होता है। एक सामान्य पाई चार्ट कुछ श्रेणियों के लिए उपयुक्त होता है, लेकिन जब कुछ स्लाइस बहुत छोटे होते हैं तो वे पढ़ने योग्य नहीं रहते। एक *Pie of Pie* चार्ट इस समस्या को हल करता है छोटे स्लाइस को एक द्वितीयक पाई में निकालकर, मुख्य चार्ट को साफ़ रखता है और विवरण तक पहुंच आसान बनाता है।

इस ट्यूटोरियल में आप सीखेंगे कि **PowerPoint में चार्ट कैसे जोड़ें** Aspose.Slides for Java के साथ Pie of Pie चार्ट बनाकर। हम पर्यावरण सेटअप, चार्ट निर्माण, लेबल कस्टमाइज़ेशन, स्प्लिट‑पोज़िशन ट्यूनिंग, और अंत में प्रस्तुति को PPTX फ़ाइल के रूप में सहेजने की प्रक्रिया को चरण‑दर‑चरण देखेंगे। अंत तक आप किसी भी स्लाइड डेक में परिष्कृत चार्ट एम्बेड करने के लिए तैयार होंगे।

## त्वरित उत्तर
Aspose.Slides में, `Presentation` एक PPTX फ़ाइल का प्रतिनिधित्व करता है, `ChartType.PieOfPie` Pie of Pie चार्ट चुनता है, `setShowValue(true)` लेबल पर मान दिखाता है, और `save` फ़ाइल को लिखता है।

- **PowerPoint हेरफेर के लिए मुख्य क्लास कौन सी है?** `Presentation` – यह मेमोरी में पूरी PPTX फ़ाइल का प्रतिनिधित्व करता है।  
- **कौन सा चार्ट प्रकार छोटे स्लाइस के लिए द्वितीयक पाई बनाता है?** `ChartType.PieOfPie`।  
- **प्रत्येक स्लाइस पर मान कैसे दिखाएँ?** सेट करें `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`।  
- **क्या आप फ़ाइल को सीधे PPTX के रूप में सहेज सकते हैं?** हाँ – कॉल करें `presentation.save("output.pptx", SaveFormat.Pptx)`।  
- **क्या विकास के लिए लाइसेंस की आवश्यकता है?** परीक्षण के लिए एक मुफ्त 30‑दिन का ट्रायल काम करता है; एक स्थायी लाइसेंस मूल्यांकन वॉटरमार्क को हटा देता है।

## Pie of Pie चार्ट क्या है?
एक **Pie of Pie chart** दो‑स्तरीय पाई विज़ुअलाइज़ेशन है जो एक या अधिक छोटे स्लाइस को एक अलग, लिंक्ड पाई में अलग करता है, जिससे उन्हें पढ़ना आसान हो जाता है। Aspose.Slides इस चार्ट प्रकार को बॉक्स से बाहर समर्थन देता है, जिससे आप स्प्लिट साइज, पोज़िशन, और लेबल फ़ॉर्मेटिंग को नियंत्रित कर सकते हैं।

## Aspose.Slides के साथ PowerPoint में चार्ट क्यों जोड़ें?
Aspose.Slides Microsoft Office स्थापित किए बिना PowerPoint फ़ाइलें जनरेट, एडिट और रेंडर कर सकता है। यह **50+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करता है, सामान्य सर्वर हार्डवेयर पर **500 स्लाइड** तक की प्रस्तुतियों को एक सेकंड से कम समय में प्रोसेस करता है, और **पूर्ण API नियंत्रण** प्रदान करता है चार्ट स्टाइलिंग, डेटा लेबल और लेआउट पर—स्वचालित रिपोर्टिंग पाइपलाइन के लिए एकदम उपयुक्त।

## पूर्वापेक्षाएँ

- **Java Development Kit (JDK) 16+** स्थापित है।  
- **IntelliJ IDEA**, **Eclipse**, या **NetBeans** जैसे IDE।  
- निर्भरता प्रबंधन के लिए Maven या Gradle (नीचे के अनुभाग देखें)।  
- जावा का बुनियादी ज्ञान और प्रोजेक्ट निर्माण की परिचितता।

## Aspose.Slides for Java सेटअप करना

### इंस्टॉलेशन जानकारी

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Direct Download:** आप नवीनतम संस्करण यहाँ से डाउनलोड कर सकते हैं: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)।

### लाइसेंस प्राप्त करने के चरण
- **Free Trial:** सभी सुविधाओं को आज़माने के लिए 30‑दिन का ट्रायल शुरू करें।  
- **Temporary License:** विस्तारित मूल्यांकन के लिए एक अस्थायी कुंजी का अनुरोध करें।  
- **Purchase:** उत्पादन उपयोग के लिए स्थायी लाइसेंस प्राप्त करें ताकि मूल्यांकन वॉटरमार्क हट जाएँ।

### बुनियादी आरंभिककरण और सेटअप
`Presentation` PowerPoint फ़ाइलें बनाने के लिए मुख्य ऑब्जेक्ट है, और `Chart` स्लाइड के भीतर एक चार्ट आकार का प्रतिनिधित्व करता है।

```java
Presentation presentation = new Presentation();
```  

यह एक खाली प्रस्तुति बनाता है जो स्लाइड्स और चार्ट्स के लिए तैयार है।

## कार्यान्वयन गाइड

### Aspose.Slides for Java का उपयोग करके PowerPoint में चार्ट कैसे जोड़ें?
एक नया `Presentation` लोड करें, एक स्लाइड जोड़ें, और `PieOfPie` प्रकार का `Chart` डालें। API कॉल श्रृंखला संक्षिप्त है: चार्ट बनाएं, सीरीज़ डेटा भरें, लेबल दृश्यता समायोजित करें, द्वितीयक पाई का आकार कॉन्फ़िगर करें, और अंत में सहेजें। पूरी प्रक्रिया आमतौर पर 20 लाइनों के कोड से कम में फिट होती है, जिससे यह स्वचालित रिपोर्ट जनरेशन के लिए आदर्श बनती है।

### 'Pie of Pie' चार्ट बनाना

#### अवलोकन
हम पहली स्लाइड पर एक Pie of Pie चार्ट बनाएँगे, सबसे छोटे स्लाइस को अलग करेंगे, और प्रत्येक भाग को उसके मान के साथ लेबल करेंगे।

#### चरण 1: Presentation क्लास का एक इंस्टेंस बनाएं
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
यह सभी बाद की स्लाइड्स और चार्ट्स के लिए कंटेनर को आरंभ करता है।

#### चरण 2: पहली स्लाइड पर 'Pie of Pie' चार्ट जोड़ें
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
यहाँ हम `ChartType.PieOfPie` निर्दिष्ट करते हैं और स्लाइड कैनवास पर चार्ट की स्थिति (X, Y) और आकार (चौड़ाई, ऊँचाई) निर्धारित करते हैं।

#### चरण 3: सीरीज़ के लिए डेटा लेबल को मान दिखाने के लिए सेट करें
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
`showValue` को सक्षम करने से प्रत्येक स्लाइस अपना संख्यात्मक मान दिखाता है, जो त्वरित डेटा व्याख्या के लिए आवश्यक है।

#### चरण 4: द्वितीयक पाई का आकार और प्रतिशत द्वारा विभाजन कॉन्फ़िगर करें
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
ये विकल्प आपको तय करने देते हैं कि चार्ट का कितना हिस्सा द्वितीयक पाई को आवंटित किया जाए और कौन से स्लाइस प्रतिशत थ्रेशहोल्ड के आधार पर स्थानांतरित किए जाएँ।

#### चरण 5: प्रस्तुति को डिस्क पर PPTX फ़ॉर्मेट में सहेजें
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro tip:** प्लेटफ़ॉर्म‑विशिष्ट विभाजकों से बचने के लिए एक पूर्ण पथ या जावा के `Paths.get()` का उपयोग करें।

## सामान्य समस्याएँ और समाधान

`License` क्लास मूल्यांकन प्रतिबंधों को हटाने के लिए एक लाइसेंस फ़ाइल लोड करता है।

- **Missing license warning:** यदि आप चार्ट पर “Evaluation Only” देखते हैं, तो सुनिश्चित करें कि आपने वैध लाइसेंस फ़ाइल `License license = new License(); license.setLicense("Aspose.Slides.lic");` के माध्यम से लागू की है।  
- **Incorrect slice split:** पुष्टि करें कि `splitBy` प्रॉपर्टी `SplitBy.Percentage` पर सेट है और `secondPieSize` 0 से 100 के बीच का मान है।  
- **Data not displaying:** पुष्टि करें कि चार्ट की सीरीज़ में कम से कम एक डेटा पॉइंट है; अन्यथा चार्ट खाली दिखेगा।

## अक्सर पूछे जाने वाले प्रश्न

`IChart` एक चार्ट ऑब्जेक्ट का प्रतिनिधित्व करता है जिसे स्लाइड में जोड़ा जा सकता है।

**प्रश्न:** क्या मैं एक ही प्रस्तुति में कई चार्ट बना सकता हूँ?  
A: हाँ, प्रत्येक स्लाइड या स्थान के लिए नया `IChart` इंस्टैंसिएट करें; API फ़ाइल प्रति असीमित चार्ट ऑब्जेक्ट की अनुमति देता है।

`SaveFormat.Pdf` PDF आउटपुट फ़ॉर्मेट को सहेजने के लिए निर्दिष्ट करता है।

**Q:** क्या Aspose.Slides PDF के रूप में सहेजने का समर्थन करता है?  
A: बिल्कुल – `presentation.save("output.pdf", SaveFormat.Pdf)` को कॉल करके वही स्लाइड डेक PDF में एक्सपोर्ट करें।

`IPortion` पाई चार्ट के व्यक्तिगत स्लाइस का प्रतिनिधित्व करता है।

**Q:** Pie of Pie चार्ट अधिकतम कितने डेटा पॉइंट संभाल सकता है?  
A: लाइब्रेरी प्रति सीरीज़ **10,000** डेटा पॉइंट तक समर्थन देती है, जो केवल उपलब्ध मेमोरी पर निर्भर है।

**Q:** क्या व्यक्तिगत स्लाइस के रंग को अनुकूलित करना संभव है?  
A: हाँ, प्रत्येक `IPortion` को `chart.getChartData().getSeries().get_Item(0).getPortions()` के माध्यम से एक्सेस करें और `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))` सेट करें।

**Q:** उत्पन्न PPTX को वेब एप्लिकेशन में कैसे एम्बेड करूँ?  
A: फ़ाइल सहेजने के बाद, इसे सीधे क्लाइंट को `HttpServletResponse` के साथ `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation` का उपयोग करके स्ट्रीम करें।

## निष्कर्ष

आपके पास अब Aspose.Slides for Java के साथ Pie of Pie चार्ट बनाकर **PowerPoint में चार्ट जोड़ने** के लिए एक पूर्ण, उत्पादन‑तैयार रेसिपी है। विभिन्न स्प्लिट थ्रेशहोल्ड, लेबल फ़ॉर्मेट और रंग योजनाओं के साथ प्रयोग करें ताकि आपके ब्रांड गाइडलाइन के अनुरूप हो सके। अगला, अन्य चार्ट प्रकार—जैसे स्टैक्ड बार या रडार—की खोज करें ताकि आपके स्वचालित स्लाइड डेक और भी समृद्ध हो सकें।

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [डायनामिक चार्ट जावा बनाएं – Aspose.Slides के लिए PowerPoint चार्ट ट्यूटोरियल्स](/slides/java/charts-graphs/)
- [Aspose.Slides for Java के साथ PowerPoint में पाई चार्ट कैसे जोड़ें](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Aspose.Slides for Java का उपयोग करके PowerPoint में चार्ट कैसे जोड़ें: चरण‑दर‑चरण गाइड](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}