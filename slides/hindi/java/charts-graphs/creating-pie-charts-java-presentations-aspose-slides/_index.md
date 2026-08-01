---
date: '2026-08-01'
description: Aspose Slides लाइसेंस का उपयोग करके Java प्रस्तुतियों में pie charts
  बनाने और अनुकूलित करने का तरीका सीखें। pie chart डेटा को कॉन्फ़िगर करने और chart
  slides को कुशलतापूर्वक जोड़ने के लिए step‑by‑step निर्देशों का पालन करें।
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Aspose Slides लाइसेंस का उपयोग करके Java प्रस्तुतियों में pie charts
  बनाने और अनुकूलित करने का तरीका सीखें। pie chart डेटा को कॉन्फ़िगर करने और chart
  slides को कुशलतापूर्वक जोड़ने के लिए step‑by‑step निर्देशों का पालन करें।
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Aspose Slides लाइसेंस के साथ Java में Pie Charts बनाएं
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Aspose Slides लाइसेंस के साथ Java में Pie Charts बनाएं
url: /hi/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides का उपयोग करके जावा प्रस्तुतियों में पाई चार्ट कैसे बनाएं

## परिचय

यदि आपको पेशेवर‑दिखावट वाली प्रस्तुतियाँ बनानी हैं, **एक Aspose Slides लाइसेंस** आपको प्रोग्रामेटिक रूप से चार्ट बनाने और स्टाइल करने की शक्ति देता है। इस गाइड में आप सीखेंगे कि पाई चार्ट कैसे बनाएं, उसका डेटा कैसे कॉन्फ़िगर करें, और उसे जावा स्लाइड डेक में एम्बेड करें—बिना Microsoft PowerPoint पर निर्भर हुए। हम सेटअप, कोड फ्लो, और सर्वोत्तम‑प्रैक्टिस टिप्स के माध्यम से चलेंगे ताकि आप मिनटों में परिष्कृत विज़ुअल रिपोर्ट प्रदान कर सकें।

**आप क्या सीखेंगे:**
- वैध लाइसेंस के साथ जावा के लिए Aspose.Slides सेटअप करना
- पाई चार्ट बनाने और कस्टमाइज़ करने के चरण
- पाई चार्ट डेटा को कॉन्फ़िगर करने और चार्ट स्लाइड्स जोड़ने का तरीका
- सामान्य समस्याएँ और प्रदर्शन ट्रिक्स

आइए शुरू करते हैं यह पुष्टि करके कि आपका वातावरण तैयार है।

## त्वरित उत्तर
- **Aspose Slides लाइसेंस क्या सक्षम करता है?** पूर्ण‑विशेषताओं वाला चार्ट निर्माण, PDF/HTML में निर्यात, और वॉटरमार्क हटाना।  
- **कौन सा जावा संस्करण आवश्यक है?** JDK 16 या नया।  
- **क्या मुझे Maven या Gradle की आवश्यकता है?** दोनों में से कोई भी काम करता है; लाइब्रेरी दोनों के माध्यम से उपलब्ध है।  
- **पाई चार्ट कितने डेटा पॉइंट्स रख सकता है?** 10 000 पॉइंट्स तक, बिना मेमोरी समस्याओं के।  
- **क्या मैं स्लाइड को इमेज के रूप में निर्यात कर सकता हूँ?** हाँ – PNG, JPEG, SVG, और अधिक समर्थित हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:
- **आवश्यक लाइब्रेरीज़:** Aspose.Slides for Java (संस्करण 25.4 या बाद) – यह संस्करण नवीनतम फ़ाइल फ़ॉर्मेट और प्रदर्शन अनुकूलन का समर्थन करता है।
- **पर्यावरण सेटअप:** JDK 16+ स्थापित और आपके IDE या बिल्ड सिस्टम में कॉन्फ़िगर किया हुआ।
- **बुनियादी ज्ञान:** Java, Maven या Gradle, और ऑब्जेक्ट‑ओरिएंटेड प्रोग्रामिंग अवधारणाओं से परिचित होना।

## जावा के लिए Aspose.Slides सेटअप करना
जावा के लिए Aspose.Slides का उपयोग करने के लिए, इसे अपने प्रोजेक्ट में शामिल करें। यहाँ सबसे सामान्य बिल्ड टूल्स के साथ डिपेंडेंसी जोड़ने का तरीका है:

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

सीधे डाउनलोड: आप नवीनतम JAR को [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से भी डाउनलोड कर सकते हैं।

### लाइसेंस प्राप्ति
Aspose एक मुफ्त ट्रायल प्रदान करता है जो सभी सुविधाओं को अनलॉक करता है, लेकिन उत्पादन उपयोग के लिए **वैध Aspose Slides लाइसेंस** आवश्यक है ताकि मूल्यांकन वॉटरमार्क हटाए जा सकें और प्रदर्शन लाभ मिल सके। खरीद विकल्प [purchase page](https://purchase.aspose.com/buy) पर सूचीबद्ध हैं। लाइसेंस फ़ाइल प्राप्त करने के बाद, इसे एप्लिकेशन स्टार्टअप पर एक बार लोड करें:

`License` आपका Aspose.Slides लाइसेंस लोड करता है और लागू करता है।  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## कार्यान्वयन गाइड

### प्रेजेंटेशन में पाई चार्ट बनाएं और जोड़ें

#### सारांश
यह अनुभाग बताता है कि पाई चार्ट कैसे बनाएं, उसके डेटा सीरीज़ को कॉन्फ़िगर करें, और चार्ट को स्लाइड में एम्बेड करें। आप प्रस्तुति ऑब्जेक्ट को इनिशियलाइज़ करने से लेकर अंतिम फ़ाइल को सेव करने तक का पूरा प्रवाह देखेंगे।

#### चरण 1: प्रस्तुति को इनिशियलाइज़ करें  
`Presentation` Aspose.Slides का शीर्ष‑स्तरीय ऑब्जेक्ट है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करता है। एक इंस्टेंस बनाना आपको संशोधन के लिए तैयार एक खाली स्लाइड डेक देता है।

```java
demo.Presentation pres = new demo.Presentation();
```  
यह पंक्ति एक नई प्रस्तुति बनाती है जहाँ सभी बाद के परिवर्तन लागू होंगे।

#### चरण 2: स्लाइड में पाई चार्ट जोड़ें  
`Chart` वह क्लास है जो चार्ट ऑब्जेक्ट्स को समेटे हुए है, जिसमें पाई चार्ट भी शामिल हैं। स्लाइड में चार्ट जोड़ना एक ही मेथड कॉल है जो स्थिति और आकार निर्दिष्ट करता है।

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` और `yPosition` चार्ट के शीर्ष‑बाएँ कोने को सेट करते हैं।  
- `width` और `height` स्लाइड पर चार्ट के दृश्य आकार को परिभाषित करते हैं।

#### चरण 3: पाई चार्ट डेटा कॉन्फ़िगर करें  
`ChartData` चार्ट के लिए डेटा सीरीज़ रखता है।  
**मैं पाई चार्ट डेटा कैसे कॉन्फ़िगर करूँ?**  
पहले एक संक्षिप्त उत्तर दें: `ChartData` संग्रह का उपयोग करके एक सीरीज़ जोड़ें, फिर `ChartDataPoint` ऑब्जेक्ट्स को संख्यात्मक मानों और श्रेणी नामों से भरें। यह तरीका आपको 10 000 स्लाइस तक दिखाने की अनुमति देता है जबकि लेबल फ़ॉर्मेटिंग को बनाए रखता है। डेटा सेट करने के बाद, आप रंग, लेजेंड, और डेटा लेबल्स को अपने कॉर्पोरेट स्टाइल गाइड के अनुसार कस्टमाइज़ कर सकते हैं।

अब, यहाँ वह कोड है जो दो श्रेणियाँ जोड़ता है और उनके लेबल दिखाता है:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
यह स्निपेट एक डेटा सीरीज़ बनाता है, दो पॉइंट्स डालता है, और चार्ट पर श्रेणी लेबल्स को सक्षम करता है।

#### चरण 4: प्रस्तुति को सहेजें  
अंत में, अपनी पसंद के फ़ाइल फ़ॉर्मेट (PPTX, PDF, या PNG) में प्रस्तुति को सहेजें। `save` मेथड सक्रिय लाइसेंस का सम्मान करता है, जिससे कोई ट्रायल वॉटरमार्क नहीं दिखता।

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### सामान्य समस्याएँ और समाधान
- **लाइसेंस नहीं मिलने की त्रुटि:** सुनिश्चित करें कि लाइसेंस फ़ाइल पथ सही है और `License` ऑब्जेक्ट किसी भी Aspose.Slides कॉल से पहले इंस्टैंशिएट किया गया है।
- **खाली चार्ट:** जांचें कि `ChartData` सीरीज़ में कम से कम एक `ChartDataPoint` है। खाली सीरीज़ से चार्ट क्षेत्र खाली रहेगा।
- **बड़े डेटा सेट्स के साथ प्रदर्शन में गिरावट:** उपयोग न किए गए स्लाइड्स को हटाने के लिए `presentation.getSlides().removeAt(index)` का उपयोग करें और भारी प्रोसेसिंग के बाद `System.gc()` कॉल करें।

## व्यावहारिक अनुप्रयोग
- **व्यावसायिक रिपोर्ट्स:** एकल पाई चार्ट के साथ विभिन्न क्षेत्रों में बाजार हिस्सेदारी या राजस्व वितरण को विज़ुअलाइज़ करें।
- **शैक्षणिक प्रस्तुतियाँ:** सर्वेक्षण परिणाम या प्रयोगात्मक निष्कर्षों को स्पष्ट, समझने योग्य फ़ॉर्मेट में दिखाएँ।
- **प्रोजेक्ट डैशबोर्ड्स:** कार्य पूर्णता प्रतिशत या संसाधन आवंटन को तुरंत स्लाइड पर प्रदर्शित करें।

आप Aspose.Slides को JDBC के साथ भी जोड़ सकते हैं ताकि डेटाबेस से लाइव डेटा प्राप्त कर सकें, और साप्ताहिक कार्यकारी ब्रीफ़िंग्स के लिए अद्यतन चार्ट बना सकें।

## प्रदर्शन विचार
जब आप ऐसी प्रस्तुतियों से निपटते हैं जिनमें कई हाई‑रेज़ोल्यूशन इमेज या बड़े डेटा सेट होते हैं:
- `try‑with‑resources` या स्पष्ट `dispose()` कॉल्स का उपयोग करके ऑब्जेक्ट्स को तुरंत रिलीज़ करें।
- स्लाइड रिसोर्सेज की लेज़ी लोडिंग सक्षम करें ताकि मेमोरी उपयोग कम रहे।
- बैच प्रोसेसिंग के लिए, संभव हो तो एक ही `Presentation` इंस्टेंस को पुन: उपयोग करें ताकि JVM ओवरहेड कम हो।

## निष्कर्ष
अब आपके पास जावा में **Aspose Slides लाइसेंस** का उपयोग करके पाई चार्ट बनाने के लिए एक पूर्ण, प्रोडक्शन‑रेडी वर्कफ़्लो है। अतिरिक्त चार्ट प्रकार—बार, लाइन, या डोनट—के साथ प्रयोग करें ताकि अपनी स्लाइड्स को और समृद्ध बना सकें। अगला, API की एक्सपोर्ट क्षमताओं का अन्वेषण करें ताकि PDF रिपोर्ट या PNG इमेज़ स्वचालित रूप से जेनरेट कर सकें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: मैं एक ही स्लाइड में कई चार्ट कैसे जोड़ूँ?**  
A: प्रत्येक चार्ट के लिए `slide.getShapes().addChart()` कॉल करें, प्रत्येक इंस्टेंस के लिए अद्वितीय कॉर्डिनेट्स और डाइमेंशन प्रदान करें।

**Q: जावा के लिए Aspose.Slides के कुछ विकल्प क्या हैं?**  
A: Apache POI और JFreeChart सामान्य विकल्प हैं, लेकिन उनके पास Aspose की व्यापक एक्सपोर्ट विकल्प और लाइसेंस मॉडल नहीं है।

**Q: क्या मैं Aspose.Slides का उपयोग करके अपनी प्रस्तुति को अन्य फ़ॉर्मेट में बदल सकता हूँ?**  
A: हाँ—एक ही `save` कॉल से PDF, XPS, HTML, PNG, JPEG, SVG, और अधिक में निर्यात कर सकते हैं।

**Q: बड़े विकास टीम के लिए लाइसेंसिंग कैसे संभालूँ?**  
A: एक एंटरप्राइज़ लाइसेंस खरीदें जो कई डेवलपर्स और सर्वरों को कवर करता है; वॉल्यूम डिस्काउंट के लिए Aspose सेल्स से संपर्क करें।

**Q: यदि मेरे चार्ट डेटा बार‑बार अपडेट होते हैं तो क्या करूँ?**  
A: Aspose.Slides को डेटा स्रोत (जैसे SQL क्वेरी) के साथ इंटीग्रेट करें और रनटाइम पर चार्ट को पुनः बनाएं; API डायनामिक डेटा बाइंडिंग का समर्थन करता है।

## संसाधन
- **डॉक्यूमेंटेशन:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **डाउनलोड:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **खरीदें:** [Buy a License](https://purchase.aspose.com/buy)
- **फ़्री ट्रायल:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **अस्थायी लाइसेंस:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **सपोर्ट:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**अंतिम अपडेट:** 2026-08-01  
**परीक्षण किया गया:** Aspose.Slides for Java 25.4  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Slides for Java का उपयोग करके प्रस्तुतियों में चार्ट जोड़ना और कॉन्फ़िगर करना](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Aspose.Slides का उपयोग करके जावा प्रस्तुतियों में चार्ट बनाना और कस्टमाइज़ करना](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Aspose.Slides Java के साथ प्रस्तुतियों को बनाना और कॉन्फ़िगर करना: चरण‑दर‑चरण गाइड](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}