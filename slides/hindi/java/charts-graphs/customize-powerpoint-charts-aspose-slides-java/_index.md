---
date: '2026-09-07'
description: Java का उपयोग करके Aspose Slides चार्ट में कस्टम लाइन्स जोड़ना सीखें।
  चरण‑दर‑चरण गाइड PowerPoint चार्ट को बेहतर बनाता है ताकि डेटा विज़ुअलाइज़ेशन स्पष्ट
  हो सके।
keywords:
- aspose slides chart
- customize PowerPoint charts
- add custom lines to charts Java
lastmod: '2026-09-07'
og_description: Java का उपयोग करके Aspose Slides चार्ट में कस्टम लाइन्स जोड़ना सीखें।
  यह गाइड स्पष्ट डेटा विज़ुअलाइज़ेशन के लिए चरण‑दर‑चरण कस्टमाइज़ेशन दिखाता है।
og_image_alt: Developer guide showing custom line addition to an Aspose Slides chart
  in Java
og_title: Java में Aspose Slides चार्ट में कस्टम लाइन्स कैसे जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  headline: How to add custom lines to an Aspose Slides chart in Java
  type: TechArticle
- description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  name: How to add custom lines to an Aspose Slides chart in Java
  steps:
  - name: create a presentation object
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a single PowerPoint file in memory.
  - name: add a clustered column chart
    text: Insert a clustered column chart on the first slide at coordinates (100,
      100) with a width of 500 px and a height of 400 px.
  - name: add an auto‑shape line to the chart
    text: Add a line shape to the chart’s `userShapes` collection, which stores custom
      drawing objects. `userShapes` is a collection that holds custom shapes drawn
      directly on a chart, allowing you to overlay lines, arrows, or other annotations.
  - name: customize line properties
    text: Set the line’s fill type to solid, change its color to red, and optionally
      adjust thickness or dash style.
  - name: save the presentation
    text: Persist the modified presentation to disk.
  type: HowTo
- questions:
  - answer: '`Presentation` represents a PowerPoint file in memory.'
    question: What is the main class for creating a presentation?
  - answer: '`slide.getShapes().addChart(...)` creates a chart object.'
    question: Which method adds a chart to a slide?
  - answer: Use `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`.
    question: How do you draw a line on a chart?
  - answer: Yes—set the line’s fill to a solid red `Color.RED`.
    question: Can I set the line color to red?
  - answer: A full license removes evaluation limits; a trial works for testing.
    question: Do I need a license for production use?
  type: FAQPage
tags:
- aspose slides
- chart customization
- java presentation
title: Java में Aspose Slides चार्ट में कस्टम लाइन्स कैसे जोड़ें
url: /hi/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में Aspose Slides चार्ट में कस्टम लाइनों को जोड़ने का तरीका

## परिचय

इस ट्यूटोरियल में आप जावा का उपयोग करके **aspose slides chart** में कस्टम लाइनों को जोड़ना सीखेंगे। कस्टम लाइनों से आप थ्रेशहोल्ड, ट्रेंड या प्रमुख डेटा पॉइंट्स को हाइलाइट कर सकते हैं, जिससे साधारण चार्ट एक शक्तिशाली विज़ुअल कहानी बन जाता है। गाइड के अंत तक आप अपने प्रोजेक्ट में Aspose.Slides को इंटीग्रेट कर पाएँगे, चार्ट पर लाइनों को ड्रॉ कर पाएँगे, और उनकी उपस्थिति को अधिकतम प्रभाव के लिए फाइन‑ट्यून कर पाएँगे।

**आप क्या सीखेंगे**
- Aspose.Slides for Java को इंस्टॉल और लाइसेंस करने का तरीका
- चार्ट पर कस्टम लाइन ड्रॉ करने के सटीक चरण
- लाइन को स्टाइल करने के तरीके (रंग, मोटाई, डैश स्टाइल)
- वास्तविक दुनिया के परिदृश्य जहाँ कस्टम लाइनों से डेटा संचार में सुधार होता है

## त्वरित उत्तर
- **प्रेजेंटेशन बनाने के लिए मुख्य क्लास कौन सी है?** `Presentation` मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करता है।  
- **कौन सा मेथड स्लाइड में चार्ट जोड़ता है?** `slide.getShapes().addChart(...)` एक चार्ट ऑब्जेक्ट बनाता है।  
- **चार्ट पर लाइन कैसे ड्रॉ करें?** `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)` का उपयोग करें।  
- **क्या मैं लाइन का रंग लाल सेट कर सकता हूँ?** हाँ—लाइन की फ़िल को सॉलिड रेड `Color.RED` पर सेट करें।  
- **क्या प्रोडक्शन उपयोग के लिए लाइसेंस चाहिए?** पूर्ण लाइसेंस मूल्यांकन सीमाओं को हटाता है; ट्रायल परीक्षण के लिए काम करता है।  

`ShapeType.Line` एक enum वैल्यू है जो Aspose.Slides को लाइन‑शेप्ड ऑटो‑शेप बनाने के लिए बताती है।

## Aspose Slides चार्ट क्या है?

एक **Aspose Slides चार्ट** एक प्रोग्रामेबल चार्ट ऑब्जेक्ट है जो PowerPoint स्लाइड के भीतर रहता है, जिससे आप पूरी तरह से Java कोड से चार्ट जेनरेट, मॉडिफ़ाई और स्टाइल कर सकते हैं। यह कई चार्ट प्रकारों (कॉलम, बार, लाइन, पाई आदि) को सपोर्ट करता है, सीरीज़, एक्सिस, लेजेंड पर पूर्ण नियंत्रण देता है, और इमेज व कस्टम शैप्स जैसे अन्य स्लाइड एलिमेंट्स के साथ संयोजित किया जा सकता है, जिससे यह ऑटोमेटेड रिपोर्टिंग और डायनेमिक प्रेजेंटेशन के लिए उपयुक्त बनता है।

## Aspose Slides चार्ट में कस्टम लाइनों को क्यों जोड़ें?

कस्टम लाइनों से आप चार्ट को सटीक विज़ुअल क्यूज़ के साथ एनोटेट कर सकते हैं। Aspose.Slides **50+ इनपुट और आउटपुट फ़ॉर्मैट्स** को सपोर्ट करता है और **सैकड़ों स्लाइड्स** वाले प्रेजेंटेशन को सामान्य डेवलपमेंट मशीन पर **150 MB RAM** से कम उपयोग करके प्रोसेस कर सकता है, जिससे यह बड़े‑स्केल रिपोर्टिंग के लिए आदर्श है।

## पूर्वापेक्षाएँ

- **Aspose.Slides for Java** – संस्करण 25.4 (या बाद का)  
- **JDK 16+** – कोई भी नवीनतम Java रनटाइम  
- IntelliJ IDEA या Eclipse जैसे IDE  
- बेसिक Java ज्ञान और PowerPoint अवधारणाओं की परिचितता  

### आवश्यक लाइब्रेरी
- Aspose.Slides for Java (Version 25.4)

### पर्यावरण सेटअप
- JDK 16 या नया इंस्टॉल करें  
- डिपेंडेंसी मैनेज करने के लिए Maven या Gradle का उपयोग करें (नीचे उदाहरण)।  

## Aspose.Slides for Java सेटअप करना

निम्नलिखित बिल्ड टूल्स में से किसी एक के साथ लाइब्रेरी को अपने प्रोजेक्ट में जोड़ें।

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

मैन्युअल डाउनलोड के लिए, नवीनतम पैकेज के लिए [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) पर जाएँ।

### लाइसेंस प्राप्ति
- **फ़्री ट्रायल:** खरीदारी के बिना परीक्षण शुरू करें।  
- **टेम्पररी लाइसेंस:** वॉटरमार्क के बिना विस्तारित मूल्यांकन के लिए उपयोग करें।  
- **फुल लाइसेंस:** प्रोडक्शन वर्कलोड के लिए सभी फीचर अनलॉक करें।  

अपने कोड में लाइसेंस को इस प्रकार इनिशियलाइज़ करें:
```java
License license = new License();
license.setLicense("path_to_license.lic");
```  

`License` वह क्लास है जिसका उपयोग आपके Aspose.Slides लाइसेंस फ़ाइल को लोड और एप्लिकेशन पर लागू करने के लिए किया जाता है।

## Aspose Slides चार्ट में कस्टम लाइनों को कैसे जोड़ें?

एक प्रेजेंटेशन लोड या बनाएं, एक चार्ट इन्सर्ट करें, और फिर चार्ट की `userShapes` कलेक्शन में एक लाइन शैप जोड़ें। लाइन को पोजिशन, साइज और स्टाइल किया जा सकता है ताकि आपके रिपोर्टिंग की जरूरतों को पूरा किया जा सके। यह तरीका क्लस्टर्ड कॉलम, बार, लाइन और एरिया चार्ट्स के लिए समान रूप से काम करता है।

## इम्प्लीमेंटेशन गाइड

### चार्ट में कस्टम लाइनों को जोड़ना

#### अवलोकन
कस्टम लाइनों से विशिष्ट मानों—जैसे बजट लिमिट या टार्गेट लाइन—पर ध्यान आकर्षित किया जाता है, जिससे आपके चार्ट अधिक अंतर्दृष्टिपूर्ण बनते हैं।

#### चरण 1: प्रेजेंटेशन ऑब्जेक्ट बनाएं
`Presentation` क्लास Aspose.Slides का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एकल PowerPoint फ़ाइल का प्रतिनिधित्व करता है।  
```java
Presentation pres = new Presentation();
```  

#### चरण 2: क्लस्टर्ड कॉलम चार्ट जोड़ें
पहली स्लाइड पर (100, 100) कॉर्डिनेट्स पर 500 px चौड़ाई और 400 px ऊँचाई के साथ एक क्लस्टर्ड कॉलम चार्ट इन्सर्ट करें।  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 400);
```  

#### चरण 3: चार्ट में ऑटो‑शेप लाइन जोड़ें
चार्ट की `userShapes` कलेक्शन में एक लाइन शैप जोड़ें, जो कस्टम ड्राइंग ऑब्जेक्ट्स को स्टोर करती है।  
```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(
    ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```  

`userShapes` एक कलेक्शन है जो सीधे चार्ट पर ड्रॉ की गई कस्टम शैप्स को रखता है, जिससे आप लाइनों, एरोज़ या अन्य एनोटेशन को ओवरले कर सकते हैं।

#### चरण 4: लाइन प्रॉपर्टीज़ को कस्टमाइज़ करें
लाइन की फ़िल टाइप को सॉलिड सेट करें, उसका रंग लाल करें, और वैकल्पिक रूप से मोटाई या डैश स्टाइल को समायोजित करें।  
```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```  

#### चरण 5: प्रेजेंटेशन सहेजें
बदलाव किए गए प्रेजेंटेशन को डिस्क पर सहेजें।  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/" + "AddCustomLines.pptx", SaveFormat.Pptx);
```  

### Presentation क्लास के साथ काम करना
`Presentation` क्लास मेथड्स प्रदान करता है जो PowerPoint फ़ाइलों को लोड, बनाना और सहेजना, साथ ही व्यक्तिगत स्लाइड्स और शैप्स तक पहुँच प्रदान करता है।

### ट्रबलशूटिंग टिप्स
- `save` में उपयोग किए गए फ़ाइल पाथ को लिखने योग्य होने की जाँच करें; विश्वसनीयता के लिए एब्सोल्यूट पाथ का उपयोग करें।  
- यदि चार्ट नहीं दिख रहा है, तो X/Y कॉर्डिनेट्स को दोबारा जांचें और सुनिश्चित करें कि स्लाइड इंडेक्स सही है।  

## व्यावहारिक अनुप्रयोग

कस्टम लाइनों का उपयोग विशेष रूप से निम्नलिखित में उपयोगी है:
1. **वित्तीय रिपोर्ट** – बजट कैप या प्रॉफिट टार्गेट को हाइलाइट करें।  
2. **सेल्स डैशबोर्ड** – त्रैमासिक बिक्री लक्ष्य के लिए लाइन ड्रॉ करें।  
3. **हेल्थकेयर एनालिटिक्स** – रोगी के वाइटल साइन ट्रेंड में महत्वपूर्ण थ्रेशहोल्ड को मार्क करें।  

आप थ्रेशहोल्ड वैल्यूज़ को डेटाबेस या API से खींचकर लाइन प्लेसमेंट को ऑटोमेट भी कर सकते हैं, जिससे रीयल‑टाइम रिपोर्टिंग संभव होती है।

## प्रदर्शन संबंधी विचार

- जब काम समाप्त हो जाए तो `presentation.dispose()` के साथ `Presentation` ऑब्जेक्ट्स को डिस्पोज़ करें ताकि नेटिव मेमोरी मुक्त हो सके।  
- फ़ाइल साइज को नियंत्रित रखने के लिए मध्यम इमेज और चार्ट रिज़ॉल्यूशन (जैसे 150 dpi) का उपयोग करें।  
- डेवलपमेंट के दौरान, टेम्पररी लाइसेंस मूल्यांकन वॉटरमार्क को हटाता है जबकि पूरी API एक्सेस प्रदान करता है।

## निष्कर्ष

आप अब जानते हैं कि जावा में **aspose slides chart** में कस्टम लाइनों को कैसे जोड़ें, जिससे आपको चार्ट एनोटेशन और विज़ुअल इम्प्रेशन पर पूर्ण नियंत्रण मिलता है। विभिन्न लाइन स्टाइल्स, पोजिशन और चार्ट टाइप्स के साथ प्रयोग करें ताकि डेटा तुरंत संवादित करने वाली रिपोर्ट्स बन सकें।

## अक्सर पूछे जाने वाले प्रश्न

**Q1: क्या मैं कस्टम लाइनों का रंग बदल सकता हूँ?**  
हाँ, `SolidFillColor` प्रॉपर्टी को किसी भी इच्छित `java.awt.Color` पर सेट करके लाइन का रंग कस्टमाइज़ कर सकते हैं।

**Q2: क्या Aspose.Slides सभी Java IDEs के साथ संगत है?**  
हाँ, जब तक आपका IDE Maven या Gradle को सपोर्ट करता है, आप बिना किसी समस्या के Aspose.Slides को इंटीग्रेट कर सकते हैं।

**Q3: कस्टम लाइनों को जोड़ने के लिए कौन से चार्ट टाइप सपोर्टेड हैं?**  
कस्टम लाइनों को क्लस्टर्ड कॉलम, बार, लाइन, एरिया और पाई चार्ट सहित कई अन्य चार्ट टाइप्स में जोड़ा जा सकता है।

**Q4: प्रेजेंटेशन सेव करने में समस्याओं का समाधान कैसे करें?**  
सुनिश्चित करें कि आउटपुट डायरेक्टरी मौजूद है, फ़ाइल पाथ सही है, और एप्लिकेशन के पास लिखने की अनुमति है।

**Q5: ट्रायल लाइसेंस उपयोग करने पर कोई सीमाएँ हैं?**  
ट्रायल में वॉटरमार्क जोड़ सकता है और कुछ प्रीमियम फीचर्स को सीमित कर सकता है; टेम्पररी या फुल लाइसेंस इन बाधाओं को हटाता है।

## संसाधन
- **डॉक्यूमेंटेशन**: [Aspose.Slides Java Documentation](https://reference.aspose.com/slides/java/)  
- **डाउनलोड**: [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)  
- **खरीदें**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **फ़्री ट्रायल**: [Get a Free Trial](https://releases.aspose.com/slides/java/)  
- **टेम्पररी लाइसेंस**: [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)  
- **सपोर्ट**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**अंतिम अपडेट:** 2026-09-07  
**टेस्टेड विद:** Aspose.Slides for Java 25.4  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose Slides Java में कस्टमाइज़्ड चार्ट ट्रेंड लाइन्स बनाएं](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)
- [Aspose.Slides for Java का उपयोग करके PowerPoint चार्ट डेटा को एडिट करने का व्यापक गाइड](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Aspose.Slides for Java का उपयोग करके PowerPoint में चार्ट एक्सिस टाइटल्स को रोटेट करने का स्टेप-बाय-स्टेप गाइड](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}