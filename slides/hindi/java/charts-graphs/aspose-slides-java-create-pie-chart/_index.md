---
date: '2026-07-08'
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में पाई
  चार्ट जोड़ना सीखें। पेशेवर पाई चार्ट बनाने और अनुकूलित करने के लिए इस चरण‑दर‑चरण
  गाइड का पालन करें।
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Aspose.Slides for Java का उपयोग करके PowerPoint में पाई चार्ट जोड़ें।
  यह ट्यूटोरियल दिखाता है कि प्रोग्रामेटिक रूप से पाई चार्ट कैसे उत्पन्न और अनुकूलित
  करें, स्वचालित रिपोर्टों के लिए उपयुक्त।
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Aspose.Slides for Java के साथ PowerPoint में पाई चार्ट जोड़ें – त्वरित गाइड
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Aspose.Slides for Java के साथ PowerPoint में पाई चार्ट कैसे जोड़ें
url: /hi/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java के साथ पाई चार्ट PowerPoint जोड़ें

## परिचय

यदि आपको **पाई चार्ट PowerPoint** स्लाइड्स को मैन्युअल रूप से PowerPoint खोले बिना जोड़ने की आवश्यकता है, तो आप सही जगह पर हैं। इस गाइड में हम Aspose.Slides for Java सेटअप करना, पाई चार्ट बनाना, और प्रत्येक स्लाइस को कस्टमाइज़ करना सीखेंगे—ऑटोमेटेड रिपोर्टिंग, डैशबोर्ड या व्यक्तिगत प्रस्तुतियों के लिए एकदम उपयुक्त। अंत तक आपके पास एक पुन: उपयोग योग्य Java स्निपेट होगा जो सेकंडों में एक पॉलिश्ड पाई चार्ट PowerPoint फ़ाइल जेनरेट करता है।

### त्वरित उत्तर
- **कौन सी लाइब्रेरी चार्ट बनाती है?** Aspose.Slides for Java (नवीनतम रिलीज)।  
- **क्या इसे हेड‑लेस चलाया जा सकता है?** हाँ—कोई Office इंस्टॉलेशन आवश्यक नहीं।  
- **कौन सा Java संस्करण इष्टतम है?** सर्वोत्तम प्रदर्शन और GC सुधारों के लिए JDK 16+।  
- **मैं स्लाइस को कैसे एक्सप्लोड करूँ?** `IDataPoint` पर `setExplosion` कॉल करें और पिक्सेल ऑफ़सेट सेट करें।  
- **उत्पादन के लिए लाइसेंस चाहिए?** विकास के लिए ट्रायल चल सकता है; स्थायी लाइसेंस सभी मूल्यांकन सीमाओं को हटाता है।

## Aspose.Slides for Java का उपयोग करके पाई चार्ट PowerPoint क्यों जोड़ें?

आप अपने बैक‑एंड सर्विसेज़ से सीधे अद्यतन विज़ुअल रिपोर्ट्स जेनरेट कर सकते हैं, मैन्युअल कॉपी‑पेस्ट त्रुटियों को समाप्त कर सकते हैं और ब्रांड‑संगत स्टाइलिंग की गारंटी दे सकते हैं। Aspose.Slides **70+ चार्ट प्रकार** का समर्थन करता है और **10,000+ स्लाइड्स** वाली प्रस्तुतियों को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, जिससे यह बड़े‑पैमाने पर ऑटोमेशन के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ

- **Aspose.Slides for Java** – ट्यूटोरियल संस्करण 25.4 (लेखन समय पर नवीनतम) का संदर्भ देता है।  
- **Java Development Kit** – अनुशंसित JDK 16 या नया।  
- **Maven** या **Gradle** – डिपेंडेंसी मैनेजमेंट के लिए।  

## Aspose.Slides for Java सेटअप करना

### Maven
अपने `pom.xml` फ़ाइल में यह डिपेंडेंसी जोड़ें:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
अपने `build.gradle` फ़ाइल में निम्नलिखित शामिल करें:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

वैकल्पिक रूप से नवीनतम संस्करण सीधे [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंसिंग
Aspose.Slides को बिना सीमाओं के उपयोग करने के लिए:

- API का मूल्यांकन करने हेतु **नि:शुल्क ट्रायल** से शुरू करें।  
- विस्तारित परीक्षण के लिए [Temporary License](https://purchase.aspose.com/temporary-license/) पेज पर **अस्थायी लाइसेंस** का अनुरोध करें।  
- पूर्ण सदस्यता के लिए [Purchase page](https://purchase.aspose.com/buy) पर खरीदें।

## Aspose.Slides for Java का उपयोग करके पाई चार्ट PowerPoint कैसे जोड़ें

एक नई प्रस्तुति लोड करें, पाई चार्ट डालें, और फ़ाइल को सहेजें—सिर्फ तीन संक्षिप्त चरणों में। यह पैटर्न किसी भी आकार के डेटा सेट के लिए काम करता है और लूप में लपेटकर स्वचालित रूप से दर्जनों स्लाइड्स जेनरेट किया जा सकता है। यह हल्का है, कुछ ही कोड लाइनों की आवश्यकता है और कोई बाहरी संसाधन नहीं, जिससे यह छोटे यूटिलिटीज़ और बड़े बैच जॉब्स दोनों के लिए उपयुक्त है।

### चरण 1: प्रस्तुति को इनिशियलाइज़ करें
`Presentation` क्लास मेमोरी में एकल PowerPoint फ़ाइल का प्रतिनिधित्व करती है। एक इंस्टेंस बनाकर आपको काम करने के लिए एक नई, खाली स्लाइड डेक मिलती है।
```java
Presentation pres = new Presentation();
```

### चरण 2: पाई चार्ट जोड़ें
पहली स्लाइड पर पाई चार्ट डालें। निर्देशांक (50, 50) और आकार (600 × 400) एक मानक 16:9 लेआउट में फिट होते हैं और शीर्षकों के लिए जगह छोड़ते हैं।
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### चरण 3: प्रस्तुति सहेजें
प्रेजेंटेशन को डिस्क पर लिखें। `YOUR_OUTPUT_DIRECTORY` को उस फ़ोल्डर से बदलें जहाँ आप फ़ाइल सहेजना चाहते हैं।
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### चरण 4: संसाधनों को साफ़ करें
`Presentation` ऑब्जेक्ट को डिस्पोज़ करें ताकि नेटिव रिसोर्सेज़ मुक्त हों और मेमोरी लीक न हो।
```java
if (pres != null) pres.dispose();
```

## डेटा पॉइंट एक्सप्लोजन और रंग कैसे कस्टमाइज़ करें?

चार्ट लोड करें, लक्ष्य डेटा पॉइंट खोजें, फिर एक्सप्लोजन ऑफ़सेट और सॉलिड फ़िल कलर लागू करें। यह स्लाइस को ज़ोर देने में मदद करता है। ये समायोजन दर्शकों का ध्यान महत्वपूर्ण मानों की ओर आकर्षित करते हैं और चार्ट की समग्र पठनीयता को सुधारते हैं।

### चरण 1: मौजूदा प्रस्तुति लोड करें (या अभी बनाई गई को पुनः उपयोग करें)
`Presentation` ऑब्जेक्ट मौजूदा PowerPoint फ़ाइल को मेमोरी में लोड करता है, जिससे आप उसकी सामग्री को संशोधित कर सकते हैं।
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### चरण 2: चार्ट और लक्ष्य डेटा पॉइंट तक पहुंचें
`IDataPoint` इंटरफ़ेस चार्ट सीरीज़ में एक व्यक्तिगत डेटा पॉइंट (स्लाइस) का प्रतिनिधित्व करता है।
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### चरण 3: एक्सप्लोजन और रंग लागू करें
`setExplosion(int)` स्लाइस को चार्ट केंद्र से पिक्सेल में ऑफ़सेट करने की दूरी सेट करता है। `setExplosion(20)` से स्लाइस को दृश्य रूप से अलग करें और `setFillType(FillType.Solid)` तथा `setSolidFillColor(Color.BLUE)` से फ़िल को नीला बदलें।
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### चरण 4: सहेजें और डिस्पोज़ करें
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## व्यावहारिक उपयोग
- **सेल्स रिपोर्ट:** शीर्ष‑बेचे गए उत्पादों को एक्सप्लोडेड स्लाइस के साथ हाइलाइट करें।  
- **बजट विश्लेषण:** विभागों को अलग‑अलग रंग देकर त्वरित दृश्य तुलना प्रदान करें।  
- **शैक्षिक स्लाइड्स:** जटिल अवधारणाओं को समझने योग्य चार्ट सेगमेंट में विभाजित करें।  

## प्रदर्शन संबंधी विचार
- **ऑब्जेक्ट्स को तुरंत डिस्पोज़** करें ताकि मेमोरी लीक न हो, विशेषकर जब लूप में कई स्लाइड्स जेनरेट कर रहे हों।  
- **हीप उपयोग की निगरानी** करें; बड़े प्रेजेंटेशन के लिए `Save` ओवरलोड का उपयोग करें जो `OutputStream` स्वीकार करता है, ताकि डेटा स्ट्रीम हो और मेमोरी फुटप्रिंट कम रहे।  
- **JDK 16+** पर टिके रहें ताकि नवीनतम गार्बेज‑कलेक्शन सुधारों का लाभ मिल सके, जो 1,000‑स्लाइड डेक्स के प्रोसेसिंग समय को लगभग 30 % तक घटा सकते हैं।

## निष्कर्ष
अब आपके पास Aspose.Slides for Java का उपयोग करके **पाई चार्ट PowerPoint** फ़ाइलें जोड़ने के लिए एक पूर्ण, प्रोडक्शन‑रेडी वर्कफ़्लो है। विभिन्न एक्सप्लोजन दूरी, रंग, और डेटा सेट के साथ प्रयोग करें ताकि आपका ब्रांडिंग मेल खाए। जब तैयार हों, तो अन्य चार्ट प्रकार—बार, लाइन, या स्कैटर—को एक्सप्लोर करें और PowerPoint के भीतर एक पूर्ण एनालिटिक्स डैशबोर्ड बनाएं।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: Aspose.Slides for Java का सबसे बड़ा लाभ क्या है?**  
उत्तर: यह आपको Microsoft Office इंस्टॉल किए बिना प्रोग्रामेटिक रूप से PowerPoint फ़ाइलें बनाना, संपादित करना और रेंडर करना देता है, 70+ चार्ट प्रकार और 100 + फ़ाइल फ़ॉर्मेट्स का समर्थन करता है।

**प्रश्न: क्या मैं शून्य से PowerPoint फ़ाइल जेनरेट कर सकता हूँ?**  
उत्तर: हाँ, `Presentation` ऑब्जेक्ट को इंस्टैंशिएट करें, स्लाइड्स, चार्ट या शैप्स जोड़ें, फिर `save` कॉल करें—सब कुछ शुद्ध Java कोड में।

**प्रश्न: मैं किसी विशिष्ट पाई स्लाइस को कैसे एक्सप्लोड करूँ?**  
उत्तर: स्लाइस के लिए `IDataPoint` प्राप्त करें और `setExplosion(pixelOffset)` कॉल करें। ऑफ़सेट तय करता है कि स्लाइस कितनी दूर बाहर की ओर जाता है।

**प्रश्न: मैं कितनी स्लाइड्स बना सकता हूँ?**  
उत्तर: Aspose.Slides एक ही फ़ाइल में **10,000 स्लाइड्स** तक संभाल सकता है, बशर्ते आप आउटपुट को स्ट्रीम करें ताकि पूरी फ़ाइल मेमोरी में लोड न हो।

**प्रश्न: अधिक उन्नत चार्ट‑कस्टमाइज़ेशन उदाहरण कहाँ मिलेंगे?**  
उत्तर: विस्तृत API रेफ़रेंस और सैंपल प्रोजेक्ट्स के लिए आधिकारिक [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) देखें।

## संसाधन
- **डॉक्यूमेंटेशन:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **लाइब्रेरी डाउनलोड:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **लाइसेंस खरीदें:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **नि:शुल्क ट्रायल:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **अस्थायी लाइसेंस:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **सपोर्ट फ़ोरम:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**अंतिम अपडेट:** 2026-07-08  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create and Validate Chart Layouts in PowerPoint Using Aspose.Slides for Java | SEO-Optimized Guide](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}