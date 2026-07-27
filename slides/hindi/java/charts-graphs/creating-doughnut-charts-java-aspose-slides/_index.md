---
date: '2026-07-27'
description: Aspose.Slides का उपयोग करके doughnut chart java कैसे बनाएं सीखें – लाइब्रेरी
  सेट अप करने, कस्टमाइज़ेबल doughnut chart जोड़ने, होल साइज समायोजित करने और प्रेजेंटेशन
  सहेजने के लिए एक त्वरित गाइड।
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Aspose.Slides का उपयोग करके doughnut chart java कैसे बनाएं सीखें –
  लाइब्रेरी सेट अप करने, कस्टमाइज़ेबल doughnut chart जोड़ने, होल साइज समायोजित करने
  और प्रेजेंटेशन सहेजने के लिए एक त्वरित गाइड।
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Aspose.Slides के साथ Doughnut Chart Java बनाएं – चरण‑दर‑चरण
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Aspose.Slides के साथ Doughnut Chart Java बनाएं – चरण‑दर‑चरण
url: /hi/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# जावा में Aspose.Slides का उपयोग करके डोनट चार्ट कैसे बनाएं

## परिचय
दृश्यात्मक रूप से आकर्षक प्रस्तुतियों का निर्माण जानकारी को प्रभावी ढंग से संप्रेषित करने के लिए आवश्यक है। **Create doughnut chart java** एक सामान्य आवश्यकता है जब आपको अनुपातिक डेटा को आधुनिक रूप में दर्शाना हो। इस ट्यूटोरियल में आप सीखेंगे कि Aspose.Slides for Java को कैसे सेटअप करें, डोनट चार्ट बनाएं, उसके होल साइज और रंगों को कस्टमाइज़ करें, और अंत में प्रस्तुति फ़ाइल को सहेजें। अंत तक आपके पास एक पुन: उपयोग योग्य पैटर्न होगा जिसे आप किसी भी जावा प्रोजेक्ट में डाल सकते हैं जो स्वचालित रूप से PowerPoint डेक बनाता है।

**आप क्या सीखेंगे:**
- Aspose.Slides for Java को सेटअप करना
- प्रस्तुतियों में डोनट चार्ट बनाना और कॉन्फ़िगर करना
- होल साइज जैसे चार्ट सौंदर्यशास्त्र को समायोजित करना
- अपने नए चार्ट के साथ प्रस्तुति को सहेजना

आइए अपने पर्यावरण को सेटअप करके शुरू करें!

## त्वरित उत्तर
- **कौन सा लाइब्रेरी डोनट चार्ट जावा बनाता है?** Aspose.Slides for Java.  
- **एक बेसिक डोनट चार्ट के लिए कितनी कोड लाइन्स चाहिए?** About 8–10 lines after the presentation is instantiated.  
- **क्या मैं होल साइज बदल सकता हूँ?** Yes, the `setHoleSize(double)` method accepts values from 0 % to 100 %.  
- **कौन से आउटपुट फॉर्मेट सपोर्टेड हैं?** PPTX, PDF, XPS, PNG, JPEG and several others (over 50 total).  
- **क्या उत्पादन के लिए लाइसेंस चाहिए?** A commercial license is required for unlimited use; a free trial works for evaluation.

## Aspose.Slides for Java क्या है?
**Aspose.Slides for Java** एक पूरी तरह से प्रबंधित API है जो डेवलपर्स को Microsoft Office के बिना PowerPoint फ़ाइलें बनाने, संशोधित करने, परिवर्तित करने और रेंडर करने में सक्षम बनाता है। यह 50 से अधिक फ़ाइल फ़ॉर्मेट को सपोर्ट करता है और हजारों स्लाइड वाली प्रस्तुतियों को कम मेमोरी उपयोग के साथ संभाल सकता है।

## प्रस्तुतियों में डोनट चार्ट क्यों उपयोग करें?
डोनट चार्ट भाग‑से‑पूरे संबंधों को दर्शाते हैं जबकि केंद्र में लेबल या छवियों के लिए जगह मुक्त करते हैं। Aspose.Slides एक सामान्य 2.5 GHz सर्वर पर **प्रति मिनट 500 स्लाइड** तक डोनट चार्ट रेंडर कर सकता है, और यह **सैकड़ों‑पृष्ठीय प्रस्तुतियों** को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस करता है, जिससे यह बड़े‑स्तर की रिपोर्टिंग समाधान के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपने ये पूर्वापेक्षाएँ पूरी कर ली हैं:

### आवश्यक लाइब्रेरी और संस्करण
Aspose.Slides for Java के साथ काम करने के लिए, इसे अपने प्रोजेक्ट में Maven या Gradle के माध्यम से शामिल करें, या सीधे डाउनलोड करें।

#### पर्यावरण सेटअप आवश्यकताएँ
- एक कार्यशील Java Development Kit (JDK), आदर्श रूप से संस्करण 8 या उससे ऊपर।  
- IntelliJ IDEA या Eclipse जैसे Integrated Development Environment (IDE)।

### ज्ञान पूर्वापेक्षाएँ
Java और बुनियादी प्रोग्रामिंग अवधारणाओं की परिचितता लाभदायक है। Maven या Gradle का बुनियादी ज्ञान सेटअप प्रक्रिया को सुगम बनाता है।

## Aspose.Slides for Java सेटअप करना
अपने प्रोजेक्ट में Aspose.Slides को शामिल करने के कई तरीके हैं:

**Maven:**  
अपने `pom.xml` फ़ाइल में यह डिपेंडेंसी जोड़ें:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
अपने `build.gradle` फ़ाइल में यह शामिल करें:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
वैकल्पिक रूप से, नवीनतम संस्करण [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंस प्राप्ति
- **Free Trial:** Aspose.Slides की सुविधाओं को एक्सप्लोर करने के लिए ट्रायल संस्करण डाउनलोड करके शुरू करें।  
- **Temporary License:** सीमाओं के बिना विस्तारित कार्यक्षमता के लिए एक टेम्पररी लाइसेंस प्राप्त करें।  
- **Purchase:** निरंतर उपयोग के लिए लाइसेंस खरीदना आवश्यक है।

एक बार जब आपने लाइब्रेरी सेटअप कर ली और आपका पर्यावरण तैयार हो, तो चलिए हमारे डोनट चार्ट को लागू करने की ओर बढ़ते हैं।

## जावा में डोनट चार्ट कैसे बनाएं?
एक नया `Presentation` ऑब्जेक्ट लोड करें, स्लाइड में डोनट चार्ट जोड़ें, होल साइज सेट करें, और फ़ाइल सहेजें – सभी कुछ सरल API कॉल्स में। यह तरीका आपको चार्ट डेटा, रूप-रंग और एक्सपोर्ट फ़ॉर्मेट पर पूर्ण नियंत्रण देता है, और यह सर्वर पर Microsoft PowerPoint स्थापित किए बिना काम करता है।

### Presentation ऑब्जेक्ट को इनिशियलाइज़ करना
`Presentation` क्लास Aspose.Slides का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करता है।  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
यह चरण एक खाली प्रस्तुति बनाता है जहाँ आप स्लाइड, शैप और चार्ट जोड़ सकते हैं।

### स्लाइड में डोनट चार्ट जोड़ें
`ISlide` एक एकल स्लाइड के लिए इंटरफ़ेस है; आप पहली स्लाइड प्राप्त कर सकते हैं या नई जोड़ सकते हैं।  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
मेथड `addChart` एक डोनट चार्ट बनाता है; पैरामीटर स्लाइड पर उसकी स्थिति (X, Y) और आकार (चौड़ाई, ऊँचाई) को परिभाषित करते हैं।

### डोनट होल साइज कॉन्फ़िगर करें
`Chart` `setHoleSize(double)` मेथड को उजागर करता है जिससे चार्ट की त्रिज्या के प्रतिशत के रूप में अंदरूनी रेडियस नियंत्रित किया जा सकता है।  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
होल साइज को 90 % सेट करने से चार्ट लगभग पूर्ण वृत्त जैसा दिखता है, जो बाहरी सेगमेंट को उजागर करने के लिए उपयोगी है।

### प्रस्तुति सहेजें
`presentation.save(String, SaveFormat)` चुने हुए फ़ॉर्मेट में फ़ाइल को डिस्क पर लिखता है।  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
उदाहरण परिणाम को `DoughnutHoleSize_out.pptx` के रूप में सहेजता है, लेकिन आप PDF, PNG, या 50+ सपोर्टेड फ़ॉर्मेट में से कोई भी चुन सकते हैं।

### संसाधनों को साफ़ करें
`presentation.dispose()` को कॉल करने से नेटिव संसाधन मुक्त होते हैं और मेमोरी लीक रोकते हैं, जो लंबी अवधि चलने वाले सर्वर एप्लिकेशन में विशेष रूप से महत्वपूर्ण है।  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```

## व्यावहारिक अनुप्रयोग
डोनट चार्ट बहुमुखी होते हैं। यहाँ कुछ परिदृश्य हैं जहाँ वे उत्कृष्ट होते हैं:
1. **Budget Allocation:** दिखाएँ कि बजट विभागों में कैसे वितरित किया गया है।  
2. **Survey Results:** बहु‑विकल्प उत्तरों वाले प्रश्नों के उत्तरों को विज़ुअलाइज़ करें।  
3. **Website Traffic Sources:** विभिन्न चैनलों (ऑर्गेनिक, पेड, रेफ़रल आदि) से आने वाले ट्रैफ़िक का प्रतिशत दिखाएँ।

## प्रदर्शन संबंधी विचार
Aspose.Slides के साथ काम करते समय, इष्टतम प्रदर्शन के लिए इन टिप्स पर विचार करें:
- `Presentation` ऑब्जेक्ट को जैसे ही काम खत्म हो, डिस्पोज़ करें ताकि नेटिव मेमोरी मुक्त हो सके।  
- बड़े डेटा सेट के लिए स्ट्रीम (`FileInputStream`, `ByteArrayOutputStream`) का उपयोग करें ताकि पूरी फ़ाइल को RAM में लोड करने से बचा जा सके।  
- लूप में कई स्लाइड बनाते समय चार्ट ऑब्जेक्ट को पुन: उपयोग करें ताकि ऑब्जेक्ट‑क्रिएशन ओवरहेड कम हो।

## सामान्य समस्याएँ और समाधान
- **Error while saving:** आउटपुट डायरेक्टरी मौजूद है और एप्लिकेशन के पास लिखने की अनुमति है, यह सत्यापित करें।  
- **Missing chart data:** `setHoleSize` कॉल करने से पहले चार्ट के `ChartData` कलेक्शन को भरना सुनिश्चित करें।  
- **Memory spikes:** हजारों स्लाइड वाली प्रस्तुतियों के लिए, `Presentation.setSlideSize` को छोटे आकार पर सेट करें और मध्यवर्ती स्लाइड को तुरंत डिस्पोज़ करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं अपने डोनट चार्ट सेगमेंट्स के रंग समायोजित कर सकता हूँ?**  
A: हाँ। `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` का उपयोग करें और फिर इच्छित RGB रंग निर्दिष्ट करें।

**Q: मैं अपने चार्ट में डेटा लेबल कैसे जोड़ूँ?**  
A: सेगमेंट के अंदर मान दिखाने के लिए `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` को कॉल करें।

**Q: क्या PPTX के अलावा अन्य फ़ॉर्मेट में चार्ट सहेजना संभव है?**  
A: बिल्कुल। Aspose.Slides PDF, XPS, PNG, JPEG, TIFF और कई अन्य फ़ॉर्मेट—कुल मिलाकर 50 से अधिक—को सपोर्ट करता है।

**Q: बड़ी प्रस्तुति लोड करते समय यदि अपवाद मिलता है तो मुझे क्या करना चाहिए?**  
A: `Presentation` कंस्ट्रक्टर जो स्ट्रीम स्वीकार करता है, उसे उपयोग करें और `loadOptions.setLoadFormat(LoadFormat.Pptx)` को सक्षम करें ताकि फ़ाइल को स्ट्रीम किया जा सके और मेमोरी खपत कम हो।

**Q: क्या मैं लाइव डेटा स्रोतों के साथ चार्ट अपडेट को ऑटोमेट कर सकता हूँ?**  
A: हाँ। डेटाबेस या REST API से डेटा प्राप्त करें, `ChartData` कलेक्शन को अपडेट करें, और प्रस्तुति सहेजने से पहले `chart.refresh()` को कॉल करें।

## संसाधन
- **Documentation:** विस्तृत API रेफ़रेंसेज़ देखें [Aspose.Slides for Java](https://reference.aspose.com/slides/java/) पर।  
- **Download:** नवीनतम लाइब्रेरी संस्करण प्राप्त करें [Aspose.Slides releases](https://releases.aspose.com/slides/java/) से।  
- **Purchase:** पूर्ण एक्सेस के लिए लाइसेंस खरीदें [Aspose Purchase](https://purchase.aspose.com/buy) पर।  
- **Free Trial:** उनके डाउनलोड पेज पर उपलब्ध फ्री ट्रायल के साथ Aspose.Slides को टेस्ट करें।  
- **Temporary License:** सीमाओं के बिना विस्तारित परीक्षण के लिए टेम्पररी लाइसेंस प्राप्त करें।  
- **Support:** प्रश्न हैं? सहायता के लिए [Aspose Forum](https://forum.aspose.com/c/slides/11) पर जाएँ।

---

**अंतिम अपडेट:** 2026-07-27  
**परीक्षित संस्करण:** Aspose.Slides for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल
- [जावा के लिए Aspose.Slides का उपयोग करके PowerPoint में चार्ट कैसे जोड़ें: चरण‑दर‑चरण गाइड](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [जावा में Aspose.Slides के साथ चार्ट कैसे बनाएं: एक व्यापक गाइड](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}