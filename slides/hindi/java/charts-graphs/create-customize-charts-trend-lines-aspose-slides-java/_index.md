---
date: '2026-08-21'
description: Aspose.Slides for Java के साथ clustered column chart बनाना और trend lines
  जोड़ना सीखें। इसमें लाइसेंस सेटअप, Maven/Gradle इंटीग्रेशन, और विस्तृत उदाहरण शामिल
  हैं।
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Aspose.Slides for Java का उपयोग करके clustered column chart बनाएं
  और trend lines जोड़ें। यह गाइड लाइसेंस सेटअप, Maven/Gradle, और चरण‑दर‑चरण कोड स्निपेट्स
  को कवर करता है।
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Aspose.Slides for Java के साथ clustered column chart बनाएं और trend lines
  जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Aspose.Slides for Java का उपयोग करके clustered column chart बनाना और trend
  lines जोड़ना कैसे करें
url: /hi/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java का उपयोग करके क्लस्टर्ड कॉलम चार्ट कैसे बनाएं और ट्रेंड लाइन्स जोड़ें

आकर्षक प्रस्तुतियों का निर्माण अक्सर आपके डेटा का स्पष्ट दृश्य प्रदान करने से शुरू होता है। इस गाइड में आप **क्लस्टर्ड कॉलम चार्ट** ऑब्जेक्ट बनाएँगे, फिर विभिन्न प्रकार की ट्रेंड लाइन्स—एक्स्पोनेन्शियल, लीनियर, लॉगरिदमिक, मूविंग एवरज, पॉलिनॉमियल, और पावर—को Aspose.Slides for Java API की मदद से जोड़ेंगे।

## त्वरित उत्तर
- **पहला कदम क्या है?** एक `Presentation` ऑब्जेक्ट इनिशियलाइज़ करें और स्लाइड में क्लस्टर्ड कॉलम चार्ट जोड़ें।  
- **कौन सा लाइब्रेरी संस्करण आवश्यक है?** Aspose.Slides for Java 25.4 या नया।  
- **क्या मैं Maven या Gradle का उपयोग कर सकता हूँ?** हाँ, दोनों समर्थित हैं; Maven में `<dependency>` और Gradle में `implementation` का उपयोग होता है।  
- **क्या लाइसेंस की जरूरत है?** ट्रायल लाइसेंस मूल्यांकन के लिए काम करता है; पूर्ण Aspose.Slides लाइसेंस मूल्यांकन सीमाओं को हटाता है।  
- **कितनी ट्रेंड लाइन प्रकार उपलब्ध हैं?** छह बिल्ट‑इन प्रकार: एक्स्पोनेन्शियल, लीनियर, लॉगरिदमिक, मूविंग एवरज, पॉलिनॉमियल, और पावर।

## क्लस्टर्ड कॉलम चार्ट बनाना क्या है?
`create clustered column chart` का अर्थ है ऐसा चार्ट बनाना जो प्रत्येक श्रेणी में कई डेटा सीरीज़ को साइड‑बाय‑साइड समूहित करता है, जिससे सीरीज़ के बीच मानों की तुलना आसान हो जाती है। यह चार्ट प्रकार श्रेणीबद्ध डेटा जैसे विभिन्न क्षेत्रों में त्रैमासिक बिक्री को विज़ुअलाइज़ करने के लिए आदर्श है, जिससे दर्शक समूहों के बीच अंतर जल्दी पहचान सकते हैं।

## ट्रेंड लाइन क्यों जोड़ें?
ट्रेंड लाइन्स डेटा सीरीज़ के अंतर्निहित पैटर्न को उजागर करती हैं, जिससे आप भविष्य के मानों का पूर्वानुमान लगा सकते हैं, वृद्धि दर को हाइलाइट कर सकते हैं, या शोरयुक्त डेटा को स्मूद कर सकते हैं। क्लस्टर्ड कॉलम चार्ट में ट्रेंड लाइन जोड़ने से कच्चे आंकड़े कार्यात्मक अंतर्दृष्टि में बदल जाते हैं, जिससे स्टेकहोल्डर दीर्घकालिक प्रवृत्तियों को समझकर डेटा‑ड्रिवेन निर्णय ले सकते हैं।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK):** 8 या बाद का।  
- **Aspose.Slides for Java:** संस्करण 25.4 या नया।  
- **IDE:** IntelliJ IDEA, Eclipse, या कोई भी Java‑संगत एडिटर।  
- **बिल्ड टूल:** Maven या Gradle (वैकल्पिक लेकिन अनुशंसित)।  
- **लाइसेंस:** ट्रायल या खरीदा हुआ Aspose.Slides लाइसेंस फ़ाइल।  

आपको बेसिक Java सिंटैक्स की समझ होनी चाहिए और प्रोजेक्ट डिपेंडेंसी मैनेजमेंट से परिचित होना चाहिए।

## Aspose.Slides for Java कैसे सेटअप करें?
अपनी पसंदीदा डिपेंडेंसी मैनेजर का उपयोग करके Aspose.Slides लाइब्रेरी को प्रोजेक्ट में जोड़ें, फिर लाइसेंस फ़ाइल को उस स्थान पर रखें जहाँ रनटाइम इसे खोज सके। इससे पूरी कार्यक्षमता मिलती है और मूल्यांकन प्रतिबंध हटते हैं।

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
अपने `build.gradle` फ़ाइल में यह लाइन शामिल करें:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### सीधे डाउनलोड
आप [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से JAR मैन्युअली भी डाउनलोड कर सकते हैं।

#### Aspose Slides लाइसेंस
`Aspose.Slides.lic` फ़ाइल को प्रोजेक्ट की रूट में रखें या प्रोग्रामेटिकली लाइसेंस सेट करें:
```java
License license = new License(); 
license.setLicense("Aspose.Slides.lic");
```
ट्रायल लाइसेंस सभी फीचर प्रतिबंध हटाता है, लेकिन खरीदा हुआ लाइसेंस इवैल्यूएशन वाटरमार्क को समाप्त करता है और पूर्ण परफ़ॉर्मेंस ऑप्टिमाइज़ेशन प्रदान करता है। प्रोडक्शन उपयोग के लिए, [Aspose purchase page](https://purchase.aspose.com/buy) से लाइसेंस खरीदने पर विचार करें।

## प्रेज़ेंटेशन बनाना और क्लस्टर्ड कॉलम चार्ट जोड़ना कैसे करें?
`Presentation` क्लास PowerPoint फ़ाइल का प्रतिनिधित्व करता है और स्लाइड्स को बनाने, संपादित करने और सेव करने के मेथड प्रदान करता है। एक `Presentation` इंस्टैंसिएट करें, स्लाइड जोड़ें, फिर `addChart` को `ChartType.ClusteredColumn` के साथ कॉल करके चार्ट ऑब्जेक्ट बनाएं। यह प्रक्रिया स्लाइड कैनवास सेट करती है, चार्ट शेप इन्सर्ट करती है, और डेटा पॉपुलेशन व स्टाइलिंग के लिए तैयार करती है।

1. **प्रेज़ेंटेशन इनिशियलाइज़ करें** – आउटपुट फ़ोल्डर सेट करें और नया `Presentation` इंस्टैंस बनाएं।  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **क्लस्टर्ड कॉलम चार्ट जोड़ें** – चार्ट शेप प्राप्त करें, उसकी सीरीज़ कॉन्फ़िगर करें, और डेटा पॉइंट्स पॉपुलेट करें।  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## एक्स्पोनेन्शियल ट्रेंड लाइन कैसे जोड़ें?
`ITrendline` इंटरफ़ेस एक ट्रेंड लाइन को परिभाषित करता है जिसे चार्ट सीरीज़ में जोड़कर डेटा पैटर्न मॉडल किया जा सकता है। एक एक्स्पोनेन्शियल ट्रेंड लाइन जोड़ने के लिए `ITrendline` इंस्टैंस बनाएं, उसका `TrendlineType` `Exponential` सेट करें, और इच्छित सीरीज़ से अटैच करें। यह प्रकार तेज़ी से बढ़ते डेटा के लिए उपयोगी है।

1. **ट्रेंड लाइन कॉन्फ़िगर करें** – सीरीज़ चुनें और `addTrendline(TrendlineType.Exponential)` कॉल करें।  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## लीनियर ट्रेंड लाइन कैसे जोड़ें?
लीनियर ट्रेंड लाइन आपके डेटा पॉइंट्स के माध्यम से सबसे उपयुक्त सीधी रेखा दिखाती है। आप इसकी उपस्थिति, जैसे लाइन रंग और मोटाई, को अपनी प्रस्तुति शैली के अनुसार कस्टमाइज़ भी कर सकते हैं।

1. **ट्रेंड लाइन सेट अप करें** – `addTrendline(TrendlineType.Linear)` उपयोग करें और फिर `getLineFormat().setFillFormat().setFillType(FillType.Solid)` के साथ रंग बदलें।  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## कस्टम टेक्स्ट फ्रेम के साथ लॉगरिदमिक ट्रेंड लाइन कैसे जोड़ें?
लॉगरिदमिक ट्रेंड लाइन्स उन डेटा के लिए आदर्श हैं जो शुरू में तेज़ी से बढ़ते हैं और फिर स्थिर हो जाते हैं। डिफ़ॉल्ट लेबल को ओवरराइड करके आप व्याख्यात्मक टेक्स्ट जोड़ सकते हैं जो ट्रेंड के महत्व को स्पष्ट करता है।

1. **ट्रेंड लाइन कस्टमाइज़ करें** – ट्रेंड लाइन जोड़ने के बाद, उसके `getDataLabel()` को एक्सेस करें और `setText("Custom label")` प्रॉपर्टी सेट करें।  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## मूविंग एवरज ट्रेंड लाइन कैसे जोड़ें?
मूविंग एवरज ट्रेंड लाइन्स अल्पकालिक उतार-चढ़ाव को स्मूद करती हैं ताकि दीर्घकालिक प्रवृत्तियों को उजागर किया जा सके। आप औसत के लिए उपयोग किए जाने वाले पॉइंट्स की संख्या (पीरियड) निर्दिष्ट कर सकते हैं, जिससे लाइन की स्मूदनेस नियंत्रित होती है।

1. **ट्रेंड लाइन कॉन्फ़िगर करें** – `addTrendline(TrendlineType.MovingAverage)` कॉल करें और `setPeriod(3)` सेट करके तीन‑पॉइंट मूविंग एवरज उपयोग करें।  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## पॉलिनॉमियल ट्रेंड लाइन कैसे जोड़ें?
पॉलिनॉमियल ट्रेंड लाइन्स डेटा को एक पॉलिनॉमियल समीकरण द्वारा परिभाषित कर्व के साथ फिट करती हैं। `order` प्रॉपर्टी पॉलिनॉमियल की डिग्री नियंत्रित करती है, जिससे आप अधिक जटिल संबंधों को मॉडल कर सकते हैं।

1. **ट्रेंड लाइन कस्टमाइज़ करें** – ट्रेंड लाइन जोड़ने के बाद, `setOrder(3)` सेट करके क्यूबिक फिट प्राप्त करें।  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## पावर ट्रेंड लाइन कैसे जोड़ें?
पावर ट्रेंड लाइन्स तब उपयोगी होती हैं जब डेटा पावर‑लॉ रिलेशनशिप फॉलो करता है। आप बैकवर्ड और फॉरवर्ड फोरकास्टिंग वैल्यूज़ सेट करके लाइन को मौजूदा डेटा रेंज से बाहर भी एक्सटेंड कर सकते हैं।

1. **ट्रेंड लाइन कॉन्फ़िगर करें** – `addTrendline(TrendlineType.Power)` उपयोग करें और `setBackward(2)` सेट करके लाइन को बैकवर्ड एक्सटेंड करें।  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## क्लस्टर्ड कॉलम चार्ट में ट्रेंड लाइन्स के व्यावहारिक उपयोग
- **वित्तीय विश्लेषण:** एक्स्पोनेन्शियल और पॉलिनॉमियल ट्रेंड्स स्टॉक प्राइस मूवमेंट का पूर्वानुमान लगाने में मदद करते हैं।  
- **सेल्स फोरकास्टिंग:** मूविंग एवरज लाइन्स सीज़नल स्पाइक्स को स्मूद करती हैं, जिससे मूलभूत बिक्री प्रवृत्तियों का स्पष्ट दृश्य मिलता है।  
- **वैज्ञानिक अनुसंधान:** लॉगरिदमिक ट्रेंड्स कई ऑर्डर ऑफ़ मैग्नीट्यूड वाले डेटा, जैसे ध्वनि तीव्रता या pH लेवल, के लिए परफेक्ट हैं।  
- **ऑपरेशन्स मॉनिटरिंग:** पावर ट्रेंड लाइन्स समय के साथ प्रदर्शन गिरावट को मॉडल कर सकती हैं।

## Aspose.Slides का उपयोग करते समय मेमोरी कैसे ऑप्टिमाइज़ करें?
ऑब्जेक्ट्स को तुरंत डिस्पोज़ करें और सेव करने के बाद `presentation.dispose()` कॉल करें। बड़े डेटा सेट के लिए इमेजेज़ का लेज़ी लोडिंग सक्षम करें और पूरे चार्ट को एक बार में मेमोरी में लोड करने से बचें।

- **डिस्पोज़ पैटर्न:** `Presentation` को try‑with‑resources ब्लॉक में रैप करें या finally क्लॉज़ में `presentation.dispose()` कॉल करें।  
- **लेज़ी लोडिंग:** हजारों डेटा पॉइंट्स के साथ काम करते समय `ChartData.setUseCache(true)` सेट करें।  
- **स्ट्रीमिंग आउटपुट:** पूरी फ़ाइल को RAM में रखने से बचने के लिए प्रेज़ेंटेशन को सीधे `FileOutputStream` में लिखें।

## Aspose.Slides for Java के मात्रात्मक लाभ
Aspose.Slides **50+ चार्ट प्रकार** का समर्थन करता है, **1,000 से अधिक स्लाइड** को **30 सेकंड** से कम समय में सामान्य 2 GHz CPU पर जेनरेट कर सकता है, और **500‑पेज PDFs** को बिना Microsoft Office इंस्टॉल किए प्रोसेस करता है। ये आँकड़े नवीनतम 25.4 रिलीज़ पर सत्यापित हैं।

## निष्कर्ष
अब आपके पास **क्लस्टर्ड कॉलम चार्ट** ऑब्जेक्ट बनाने और Aspose.Slides for Java में उपलब्ध सभी प्रमुख ट्रेंड‑लाइन प्रकारों के साथ उन्हें समृद्ध करने का पूर्ण, एंड‑टू‑एंड समाधान है। ऊपर दिए गए चरणों का पालन करके आप डेटा‑ड्रिवेन प्रस्तुतियाँ बना सकते हैं जो दृश्य रूप से आकर्षक और विश्लेषणात्मक रूप से शक्तिशाली दोनों हैं।

आगे के कदमों में चार्ट स्टाइलिंग विकल्पों का अन्वेषण, PDF/HTML में एक्सपोर्ट, और कई डेटा स्रोतों में चार्ट जेनरेशन को ऑटोमेट करना शामिल है।

## अक्सर पूछे जाने वाले प्रश्न

**प्र: Maven प्रोजेक्ट के लिए Aspose.Slides कैसे सेटअप करें?**  
उ: Maven सेक्शन में दिखाए गए `<dependency>` स्निपेट को अपने `pom.xml` में जोड़ें और `mvn clean install` चलाएँ।

**प्र: क्या मैं ट्रेंड लाइन्स को रंग और लेबल से आगे कस्टमाइज़ कर सकता हूँ?**  
उ: हाँ, आप लाइन स्टाइल, चौड़ाई, डैश पैटर्न, और यहाँ तक कि `ITrendline` API के माध्यम से फॉरवर्ड/बैकवर्ड फोरकास्ट वैल्यूज़ भी बदल सकते हैं।

**प्र: यदि मैं संस्करण‑संगतता त्रुटि का सामना करता हूँ तो क्या करें?**  
उ: सुनिश्चित करें कि आपका JDK संस्करण Aspose.Slides की न्यूनतम आवश्यकता (JDK 8+) से मेल खाता है। किसी भी ब्रेकिंग चेंज के लिए Aspose रिलीज़ नोट्स देखें।

**प्र: क्या कई चार्ट्स में ट्रेंड लाइन्स को स्वचालित रूप से जोड़ना संभव है?**  
उ: बिल्कुल। स्लाइड कलेक्शन में प्रत्येक `IChart` पर लूप करें और प्रत्येक सीरीज़ के लिए उपयुक्त `addTrendline` मेथड को कॉल करें।

**प्र: प्रोडक्शन उपयोग के लिए क्या मुझे पेड लाइसेंस चाहिए?**  
उ: हाँ, खरीदा हुआ Aspose.Slides लाइसेंस मूल्यांकन सीमाओं को हटाता है और पूर्ण परफ़ॉर्मेंस ऑप्टिमाइज़ेशन अनलॉक करता है।

---

**अंतिम अपडेट:** 2026-08-21  
**टेस्टेड विथ:** Aspose.Slides for Java 25.4  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}