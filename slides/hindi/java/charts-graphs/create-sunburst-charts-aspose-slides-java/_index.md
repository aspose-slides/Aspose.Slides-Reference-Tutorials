---
date: '2026-07-03'
description: जावा में Aspose.Slides का उपयोग करके Sunburst Charts को चरण-दर-चरण बनाना
  सीखें, PowerPoint प्रस्तुतियों के लिए पूर्ण अनुकूलन विकल्पों के साथ।
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: जावा में Aspose.Slides का उपयोग करके Sunburst Charts कैसे बनाएं
url: /hi/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# जावा में Aspose.Slides का उपयोग करके सनबर्स्ट चार्ट कैसे बनाएं

## परिचय
आज के डेटा‑ड्रिवन प्रस्तुतियों में, **सनबर्स्ट कैसे बनाएं** विज़ुअलाइज़ेशन जल्दी से बनाना आपके स्लाइड्स को अलग बना सकता है। यह ट्यूटोरियल आपको Aspose.Slides for Java के साथ सनबर्स्ट चार्ट बनाने की पूरी प्रक्रिया दिखाता है, प्रोजेक्ट सेटअप से लेकर अंतिम एक्सपोर्ट तक, ताकि आप जावा इकोसिस्टम से बाहर निकले बिना प्रभावशाली पदानुक्रमित डेटा ग्राफ़िक्स प्रदान कर सकें।

## त्वरित उत्तर
- **PowerPoint फ़ाइल के लिए मुख्य क्लास क्या है?** `Presentation` – यह मेमोरी में पूरे PPTX को दर्शाता है।  
- **बुनियादी सनबर्स्ट के लिए कितनी लाइनों का कोड चाहिए?** लाइब्रेरी रेफ़रेंस करने के बाद आमतौर पर 5–7 लाइनों की आवश्यकता होती है।  
- **कौन‑कौन से आउटपुट फ़ॉर्मेट सपोर्टेड हैं?** PPTX, PDF, PNG, SVG, और HTML।  
- **क्या मैं व्यक्तिगत सेगमेंट को स्टाइल कर सकता हूँ?** हाँ – फ़िल कलर, बॉर्डर, और डेटा लेबल पूरी तरह कस्टमाइज़ेबल हैं।  
- **प्रोडक्शन के लिए लाइसेंस चाहिए?** परीक्षण के लिए फ्री इवैल्यूएशन चलती है; डिप्लॉयमेंट के लिए कमर्शियल लाइसेंस आवश्यक है।

## सनबर्स्ट चार्ट क्या है?
सनबर्स्ट चार्ट पदानुक्रमित डेटा को समकेंद्रित रिंग्स के रूप में दर्शाता है, जहाँ प्रत्येक रिंग पदानुक्रम के एक स्तर का प्रतिनिधित्व करती है। यह दर्शकों को एक नज़र में पैरेंट‑चाइल्ड संबंध समझने में मदद करता है, जिससे यह ऑर्गेनाइज़ेशन चार्ट, टैक्सोनॉमी डिस्प्ले, और मल्टी‑लेवल मेट्रिक्स के लिए आदर्श बन जाता है। यह विशेष रूप से प्रोडक्ट लाइन्स, जियोग्राफिक रीजन, या ऑर्गेनाइज़ेशन स्ट्रक्चर जैसी मल्टी‑लेवल कैटेगरीज को दिखाने में उपयोगी है, जिससे दर्शक समग्र वितरण और प्रत्येक सेगमेंट के भीतर विस्तृत ब्रेकडाउन दोनों देख सकते हैं।

## सनबर्स्ट चार्ट के लिए Aspose.Slides क्यों उपयोग करें?
Aspose.Slides **30+ चार्ट टाइप्स** को सपोर्ट करता है, **500 MB** तक की फ़ाइलों को बिना पूरे डॉक्यूमेंट को मेमोरी में लोड किए प्रोसेस करता है, और **300 DPI** पर ग्राफ़िक्स रेंडर करता है जिससे आउटपुट क्रिस्टल‑क्लियर रहता है। ये मापनीय क्षमताएँ बड़े प्रेजेंटेशन में भी तेज़ जेनरेशन और हाई‑क्वालिटी विज़ुअल्स सुनिश्चित करती हैं। अतिरिक्त रूप से, लाइब्रेरी थ्रेड‑सेफ़ ऑपरेशन्स प्रदान करती है और लोकप्रिय जावा बिल्ड टूल्स के साथ सहजता से इंटीग्रेट होती है, जिससे यह डेस्कटॉप और सर्वर‑साइड दोनों पर बड़े पैमाने पर प्रेजेंटेशन जेनरेशन के लिए उपयुक्त बनती है।

## पूर्वापेक्षाएँ
- Java Development Kit (JDK) 8 या नया।  
- डिपेंडेंसी मैनेजमेंट के लिए Maven या Gradle।  
- Aspose.Slides for Java (नवीनतम संस्करण)।  
- पदानुक्रमित डेटा स्ट्रक्चर की बेसिक समझ।

## सनबर्स्ट चार्ट बनाने के चरण‑दर‑चरण निर्देश?
पर्यावरण तैयार करें, चार्ट जोड़ें, पदानुक्रमित डेटा फीड करें, स्टाइल सेट करें, और फ़ाइल सेव करें – सभी कुछ सरल चरणों में। नीचे वह सटीक वर्कफ़्लो दिया गया है जिसे आप अतिरिक्त बायलरप्लेट कोड लिखे बिना फॉलो कर सकते हैं। प्रक्रिया पूरी तरह ऑटोमेटेड है, मैन्युअल UI इंटरैक्शन की आवश्यकता नहीं, और इसे बैच जॉब्स या वेब सर्विसेज़ में इंटीग्रेट करके ऑन‑डिमांड चार्ट जेनरेट किया जा सकता है।

### चरण 1: प्रोजेक्ट सेट अप करें
अपने `pom.xml` में Aspose.Slides Maven डिपेंडेंसी (या समकक्ष Gradle स्निपेट) जोड़ें। यह सभी आवश्यक बाइनरीज़ और ट्रांज़िटिव लाइब्रेरीज़ को पुल कर लेगा।

### चरण 2: प्रस्तुति लोड या बनाएं
`Presentation` Aspose.Slides का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एकल PowerPoint फ़ाइल को दर्शाता है। नई डेक के लिए `new Presentation()` से इंस्टैंशिएट करें या मौजूदा PPTX खोलने के लिए फ़ाइल पाथ पास करें।

### चरण 3: सनबर्स्ट चार्ट जोड़ें
`slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)` का उपयोग करके स्लाइड पर नया चार्ट शेप इन्सर्ट करें। यह डेटा के लिए तैयार सनबर्स्ट प्लेसहोल्डर बनाता है। `ChartType.Sunburst` स्लाइड पर चार्ट जोड़ते समय सनबर्स्ट चार्ट टाइप को निर्दिष्ट करता है।

### चरण 4: पदानुक्रमित डेटा भरें
`ChartData` चार्ट की डेटा सीरीज़ और कैटेगरीज को रखता है। चार्ट की `ChartData` कलेक्शन एक्सेस करें और ऐसी सीरीज़ व कैटेगरीज जोड़ें जो आपके पदानुक्रम को दर्शाती हों। प्रत्येक लेवल के लिए `ParentSeries` प्रॉपर्टी के माध्यम से पैरेंट‑चाइल्ड रिलेशनशिप सेट करें, जिससे चार्ट स्वचालित रूप से समकेंद्रित रिंग्स बनाता है।

### चरण 5: रूप को अनुकूलित करें
`ChartSeries` और `ChartDataPoint` ऑब्जेक्ट्स के माध्यम से सेगमेंट कलर्स, बॉर्डर स्टाइल, और डेटा लेबल को फाइन‑ट्यून करें। `ChartSeries` चार्ट में डेटा पॉइंट्स की एक श्रृंखला को दर्शाता है। `ChartDataPoint` एक व्यक्तिगत डेटा पॉइंट को दर्शाता है। आप 3‑D रोटेशन भी एनेबल कर सकते हैं या `Explode` प्रॉपर्टी सेट करके विशिष्ट स्लाइस को हाइलाइट कर सकते हैं।

### चरण 6: प्रस्तुति सहेजें
`SaveFormat` एनेम उन फ़ाइल फ़ॉर्मेट्स को परिभाषित करता है जिनमें आप प्रस्तुति को सेव कर सकते हैं। `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` कॉल करके फ़ाइल डिस्क पर लिखें। `SaveFormat` एनेम वैल्यू बदलकर आप PDF या PNG में भी एक्सपोर्ट कर सकते हैं।

## सनबर्स्ट चार्ट के रंग कैसे अनुकूलित करें?
प्रत्येक `ChartDataPoint` के लिए फ़िल कलर इस प्रकार सेट करें: `point.getFillFormat().setFillType(FillType.Solid)` और फिर `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`। यह सीधा तरीका आपको कॉर्पोरेट ब्रांडिंग से मेल खाने या प्रमुख डेटा पॉइंट्स को उजागर करने की सुविधा देता है। आप ग्रेडिएंट फ़िल, ट्रांसपैरेंसी एडजस्ट, या थीम कलर्स भी लागू कर सकते हैं ताकि स्लाइड डिज़ाइन के साथ कंसिस्टेंसी बनी रहे।

## सामान्य समस्याएँ और समाधान
- **समस्या:** पदानुक्रम सपाट दिख रहा है।  
  **समाधान:** सुनिश्चित करें कि प्रत्येक चाइल्ड सीरीज़ सही ढंग से अपने `ParentSeries` को रेफ़र कर रही है। लिंक न होने पर चार्ट सभी डेटा को एक ही लेवल मान लेता है।  
- **समस्या:** एक्सपोर्टेड PNG धुंधला दिख रहा है।  
  **समाधान:** `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)` सेट करके एक्सपोर्ट DPI बढ़ाएँ।  
- **समस्या:** बड़ी PPTX फ़ाइलों से OutOfMemoryError आता है।  
  **समाधान:** `Presentation.setMemoryOptimization(true)` उपयोग करके डेटा को स्ट्रीम करें और मेमोरी उपयोग कम रखें।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न:** क्या मैं CSV फ़ाइल से सनबर्स्ट चार्ट जेनरेट कर सकता हूँ?  
**उत्तर:** हाँ। CSV पढ़ें, मेमोरी में पदानुक्रम बनाएं, और उसे चार्ट की `ChartData` कलेक्शन में फीड करें फिर सेव करें।

**प्रश्न:** क्या Aspose.Slides सनबर्स्ट चार्ट के लिए एनीमेटेड ट्रांज़िशन सपोर्ट करता है?  
**उत्तर:** करता है। स्लाइड पर `SlideShowTransition` लागू करें या चार्ट‑लेवल एनीमेशन के लिए `ChartFormat.setAnimationEnabled(true)` उपयोग करें।

**प्रश्न:** क्या चार्ट को SVG वेक्टर ग्राफ़िक के रूप में एक्सपोर्ट करना संभव है?  
**उत्तर:** बिल्कुल। `SaveFormat.Svg` के साथ प्रस्तुति को सेव करें और आपको सनबर्स्ट चार्ट का स्केलेबल वेक्टर संस्करण मिलेगा।

**प्रश्न:** एक सनबर्स्ट चार्ट अधिकतम कितने डेटा पॉइंट्स संभाल सकता है?  
**उत्तर:** Aspose.Slides एक ही सनबर्स्ट चार्ट में **10,000** डेटा पॉइंट्स तक बिना प्रदर्शन गिरावट के प्रोसेस कर सकता है।

**प्रश्न:** क्या प्रत्येक डिप्लॉयमेंट एनवायरनमेंट के लिए अलग लाइसेंस चाहिए?  
**उत्तर:** एक ही कमर्शियल लाइसेंस सभी एनवायरनमेंट (डेवलपमेंट, स्टेजिंग, प्रोडक्शन) को कवर करता है, बशर्ते लाइसेंस शर्तें मान्य हों।

## निष्कर्ष
अब आपके पास जावा में Aspose.Slides का उपयोग करके **सनबर्स्ट कैसे बनाएं** का एक पूर्ण, चरण‑दर‑चरण गाइड है। ऊपर दिया गया वर्कफ़्लो फॉलो करके आप किसी भी PowerPoint प्रस्तुति के लिए हाई‑क्वालिटी, पूरी तरह कस्टमाइज़ेबल पदानुक्रमित विज़ुअलाइज़ेशन जेनरेट कर सकते हैं।

---

**Last Updated:** 2026-07-03  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Master PowerPoint Chart Customization Using Aspose.Slides Java for Dynamic Presentations](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animate PowerPoint Chart Categories with Aspose.Slides for Java | Step‑by‑Step Guide](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}