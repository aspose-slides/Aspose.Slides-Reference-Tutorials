---
date: '2026-08-06'
description: Aspose.Slides for Java का उपयोग करके legend font color बदलना और chart
  legend text संशोधित करना सीखें। chart legends को जल्दी से customize करने के लिए
  step‑by‑step निर्देशों का पालन करें।
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Aspose.Slides for Java के साथ legend font color बदलना और chart legend
  text संशोधित करना सीखें। यह गाइड आपको सटीक steps और best practices दिखाता है।
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Aspose.Slides for Java में legend font color कैसे बदलें
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Aspose.Slides for Java में legend font color कैसे बदलें
url: /hi/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java में लेजेंड फ़ॉन्ट रंग कैसे बदलें

## परिचय
यदि आपको चार्ट में **legend font color** बदलने की आवश्यकता है, तो Aspose.Slides for Java आपको प्रत्येक legend entry पर पूर्ण नियंत्रण देता है। यह ट्यूटोरियल आपको legend टेक्स्ट स्टाइल को कस्टमाइज़ करने, बोल्ड या इटैलिक फ़ॉन्ट लागू करने, और सॉलिड रंग सेट करने के माध्यम से ले जाता है ताकि आपके चार्ट बिल्कुल वही दिखें जैसा आप चाहते हैं। इस गाइड के अंत तक आप chart legend टेक्स्ट को आत्मविश्वास के साथ संशोधित कर सकेंगे और इन बदलावों को किसी भी मौजूदा प्रस्तुति में एकीकृत कर सकेंगे।

**आप क्या सीखेंगे**
- प्रोग्रामेटिक रूप से **legend font color** बदलने का तरीका।
- **chart legend text** को बदलने के तरीके जैसे बोल्ड, इटैलिक, और आकार।
- एक प्रस्तुति में कई चार्ट्स पर बदलाव लागू करने के टिप्स।
- इन चरणों को बड़े ऑटोमेशन वर्कफ़्लो में एकीकृत करने का तरीका।

## त्वरित उत्तर
- **क्या मैं एकल legend entry का रंग बदल सकता हूँ?** हाँ – एंट्री को उसके इंडेक्स से एक्सेस करें और fill format को सॉलिड रंग पर सेट करें।  
- **क्या इन APIs का उपयोग करने के लिए लाइसेंस चाहिए?** उत्पादन के लिए एक अस्थायी या भुगतान लाइसेंस आवश्यक है; मूल्यांकन के लिए एक फ्री ट्रायल काम करता है।  
- **कौन सा Java संस्करण समर्थित है?** Aspose.Slides for Java 25.4+ JDK 16 और उससे नए संस्करणों के साथ काम करता है।  
- **क्या बदलाव अन्य chart तत्वों को प्रभावित करेंगे?** नहीं, legend फ़ॉर्मेटिंग डेटा सीरीज़ स्टाइलिंग से अलग है।  
- **क्या बैच प्रोसेसिंग संभव है?** बिल्कुल – स्लाइड्स और चार्ट्स के माध्यम से लूप करके पूरे डेक में समान legend सेटिंग्स लागू करें।

## legend फ़ॉन्ट रंग बदलना क्या है?
`change legend font color` का अर्थ है Aspose.Slides API का उपयोग करके chart की legend entries के टेक्स्ट रंग को प्रोग्रामेटिक रूप से सेट करना। यह ऑपरेशन legend की दृश्य उपस्थिति को अपडेट करता है बिना मूल डेटा को बदले।

## chart legends को कस्टमाइज़ क्यों करें?
Aspose.Slides **50+ इनपुट और आउटपुट फॉर्मेट** को सपोर्ट करता है और **500+ स्लाइड्स** वाली प्रस्तुतियों को 200 MB से कम मेमोरी उपयोग के साथ संभाल सकता है। legends को कस्टमाइज़ करने से पठनीयता बढ़ती है, ब्रांड रंग मजबूत होते हैं, और प्रमुख डेटा पॉइंट्स उभर कर दिखते हैं—विशेषकर व्यावसायिक या शैक्षणिक डेक्स में जहाँ दृश्य स्पष्टता निर्णय‑निर्धारण को प्रेरित करती है।

## पूर्वापेक्षाएँ
- **Aspose.Slides for Java** लाइब्रेरी (Version 25.4 या बाद का)।
- Java Development Kit (JDK) 16 या उससे ऊपर।
- IntelliJ IDEA, Eclipse, या NetBeans जैसे IDE।
- निर्भरता प्रबंधन के लिए Maven या Gradle।
- बुनियादी Java प्रोग्रामिंग ज्ञान।

## Aspose.Slides for Java को सेटअप करना
अपने chart legends को कस्टमाइज़ करना शुरू करने के लिए, नीचे दिए गए तरीकों में से किसी एक का उपयोग करके लाइब्रेरी को अपने प्रोजेक्ट में जोड़ें।

### Maven
अपने `pom.xml` फ़ाइल में निम्नलिखित डिपेंडेंसी जोड़ें:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` फ़ाइल में यह लाइन शामिल करें:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### सीधे डाउनलोड
आप नवीनतम JAR भी [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/) से प्राप्त कर सकते हैं।

#### लाइसेंस प्राप्त करने के चरण
- **Free trial:** Aspose.Slides की सुविधाओं को खोजने के लिए एक फ्री ट्रायल से शुरू करें।  
- **Temporary license:** विस्तारित मूल्यांकन के लिए एक अस्थायी लाइसेंस के लिए आवेदन करें।  
- **Purchase:** पूर्ण एक्सेस के लिए, [Aspose Purchase](https://purchase.aspose.com/buy) से लाइसेंस खरीदने पर विचार करें।

#### बुनियादी इनिशियलाइज़ेशन और सेटअप
लाइब्रेरी को अपने प्रोजेक्ट में जोड़ने के बाद:
1. अपने Java एप्लिकेशन में Aspose.Slides को इनिशियलाइज़ करें।  
2. मौजूदा प्रस्तुति लोड करें या नई बनाएं।

## legend फ़ॉन्ट रंग कैसे बदलें?
legend फ़ॉन्ट रंग बदलने के लिए, प्रस्तुति लोड करें, chart ऑब्जेक्ट प्राप्त करें, उसका legend प्राप्त करें, और फिर प्रत्येक legend entry के टेक्स्ट फ़ॉर्मेट को fill type को सॉलिड सेट करके और इच्छित रंग निर्दिष्ट करके संशोधित करें। यह एकल ऑपरेशन legend टेक्स्ट रंग को तुरंत अपडेट करता है बिना पूरे स्लाइड को पुनः ड्रॉ किए। उदाहरण: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` यह तरीका किसी भी chart प्रकार के लिए काम करता है और पूरे स्लाइड को पुनः‑रेंडर करने की आवश्यकता नहीं होती।

### legend टेक्स्ट प्रॉपर्टीज़ तक पहुँच और संशोधन

#### परिभाषा एंकर
`IChart` इंटरफ़ेस स्लाइड पर एक chart ऑब्जेक्ट को दर्शाता है, और इसका `getLegend()` मेथड एक `ILegend` ऑब्जेक्ट लौटाता है जिसमें `ILegendEntry` आइटम्स का संग्रह होता है।

#### अपनी प्रस्तुति में chart जोड़ना
1. **प्रस्तुति लोड करें:**  

   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **एक clustered column chart जोड़ें:**  

   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### फ़ॉन्ट प्रॉपर्टीज़ को कस्टमाइज़ करना
3. **legend entry टेक्स्ट फ़ॉर्मेट तक पहुँचें:**  
   यहाँ, `legendEntry` एक `ILegendEntry` ऑब्जेक्ट है जो chart legend में एकल एंट्री का प्रतिनिधित्व करता है।  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **विशिष्ट ऊँचाई के साथ बोल्ड और इटैलिक स्टाइल सेट करें:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **बेहतर दृश्यता के लिए fill type को सॉलिड रंग में बदलें:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### प्रस्तुति सहेजना
6. **अपने बदलाव सहेजें:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### सामान्य समस्याएँ और ट्रबलशूटिंग
- सुनिश्चित करें कि legend entry का इंडेक्स आपके chart में series क्रम से मेल खाता है।  
- यह सुनिश्चित करें कि आप ऐसी लाइब्रेरी संस्करण उपयोग कर रहे हैं जो `setSolidFillColor` को सपोर्ट करता है (version 20.9 से उपलब्ध)।

## व्यावहारिक अनुप्रयोग
legend टेक्स्ट को कस्टमाइज़ करना कई वास्तविक‑दुनिया परिदृश्यों में उपयोगी है:
1. **व्यावसायिक प्रस्तुतियाँ:** एक परिष्कृत लुक के लिए legend रंगों को कॉर्पोरेट ब्रांडिंग के साथ संरेखित करें।  
2. **शैक्षणिक सामग्री:** विरोधी legend रंगों का उपयोग करके प्रमुख डेटा सीरीज़ को हाइलाइट करें।  
3. **मार्केटिंग डेक्स:** प्रदर्शन मीट्रिक्स को बोल्ड, रंगीन legends के साथ उजागर करें ताकि स्टेकहोल्डर का ध्यान आकर्षित हो।  

आप डेटाबेस या कॉन्फ़िगरेशन फ़ाइल से रंग मान निकालकर legend अपडेट को स्वचालित भी कर सकते हैं।

## प्रदर्शन संबंधी विचार
बड़े डेक्स को प्रोसेस करते समय इन टिप्स को ध्यान में रखें:
- **प्रभावी मेमोरी प्रबंधन:** सहेजने के बाद `presentation.dispose()` कॉल करके नेटिव रिसोर्सेज़ रिलीज़ करें।  
- **केवल आवश्यक स्लाइड्स लोड करें:** यदि आपको उपसमुच्चय चाहिए तो `Presentation.load(String path, LoadOptions options)` को `LoadOptions.setLoadOnlySlideIds()` के साथ उपयोग करें।  
- **बैच प्रोसेसिंग:** प्रत्येक स्लाइड पर legend अपडेट को समूहित करें ताकि API कॉल्स की संख्या कम हो और थ्रूपुट बढ़े।

## निष्कर्ष
अब आप जानते हैं कि Aspose.Slides for Java का उपयोग करके **legend फ़ॉन्ट रंग** कैसे **बदलें** और **chart legend टेक्स्ट** कैसे **संशोधित करें**। ये कस्टमाइज़ेशन दृश्य स्पष्टता को बढ़ाते हैं और डेटा को अधिक प्रभावी ढंग से प्रस्तुत करने में मदद करते हैं। विभिन्न फ़ॉन्ट, आकार, और रंगों के साथ प्रयोग करें ताकि आपकी प्रस्तुति की स्टाइल गाइड से मेल खाए, और अन्य chart‑स्टाइलिंग फीचर्स का अन्वेषण करें ताकि वास्तव में प्रोफेशनल डेक्स बन सकें।

**अगले कदम**
- पाई और लाइन चार्ट्स पर समान legend स्टाइलिंग लागू करने का प्रयास करें।  
- पूरी तरह ब्रांडेड chart के लिए legend कस्टमाइज़ेशन को डेटा लेबल फ़ॉर्मेटिंग के साथ मिलाएँ।  

अपनी प्रस्तुतियों को उन्नत करने के लिए तैयार हैं? ऊपर दिए गए चरणों को लागू करें और तुरंत अंतर देखें!

## FAQ अनुभाग
1. **मैं legend entry के टेक्स्ट का रंग कैसे बदलूँ?**  
   legend entry के टेक्स्ट फ़ॉर्मेट पर `getFillFormat().setFillType(FillType.Solid)` उपयोग करें और फिर `setSolidFillColor(Color.YOUR_COLOR)` सेट करें।

2. **क्या मैं इन बदलावों को प्रस्तुति में सभी legends पर लागू कर सकता हूँ?**  
   हाँ – प्रत्येक स्लाइड पर इटररेट करें, प्रत्येक chart को locate करें, और लूप के भीतर उसके legend entries को अपडेट करें।

3. **क्या टेक्स्ट लंबाई के आधार पर फ़ॉन्ट आकार को डायनामिक रूप से समायोजित करना संभव है?**  
   आप `TextFrame.getTextFrameFormat().getFontHeight()` से आवश्यक आकार की गणना कर सकते हैं और `setFontHeight(double)` के माध्यम से सेट कर सकते हैं।

4. **यदि मुझे legend entry इंडेक्सिंग में समस्याएँ आती हैं तो क्या करें?**  
   दोबारा जांचें कि आप जो इंडेक्स उपयोग कर रहे हैं वह series क्रम से मेल खाता है; याद रखें कि इंडेक्स शून्य‑आधारित होते हैं।

5. **मैं अधिक Aspose.Slides उदाहरण कहाँ पा सकता हूँ?**  
   व्यापक गाइड और API रेफ़रेंसेज़ के लिए [Aspose Documentation](https://reference.aspose.com/slides/java/) देखें।

**अतिरिक्त प्रश्न‑उत्तर**

प्रश्न: क्या legend फ़ॉन्ट रंग बदलने से निर्यातित PDF फ़ाइलों पर असर पड़ता है?  
उत्तर: नहीं, रंग परिवर्तन Aspose.Slides द्वारा समर्थित सभी निर्यात फॉर्मेट्स में संरक्षित रहता है, जिसमें PDF और PPTX शामिल हैं।

प्रश्न: क्या मैं सॉलिड रंग के बजाय ग्रेडिएंट उपयोग कर सकता हूँ?  
उत्तर: हाँ – `FillType.Gradient` सेट करें और `getGradientStyle()` के माध्यम से ग्रेडिएंट स्टॉप्स कॉन्फ़िगर करें।

प्रश्न: एक chart में अधिकतम कितने legend entries हो सकते हैं?  
उत्तर: एक chart में अधिकतम 256 legend entries हो सकते हैं, जो केवल आप द्वारा जोड़े गए डेटा सीरीज़ की संख्या पर निर्भर करता है।

## संसाधन
- **Documentation:** Aspose.Slides फीचर्स के उपयोग पर व्यापक गाइड ([Link](https://reference.aspose.com/slides/java/)).  
- **Download:** Aspose.Slides for Java का नवीनतम संस्करण प्राप्त करें ([Link](https://releases.aspose.com/slides/java/)).  
- **Purchase:** पूरी क्षमताओं को अनलॉक करने के लिए लाइसेंस खरीदें ([Link](https://purchase.aspose.com/buy)).  
- **Free trial & temporary license:** फ्री ट्रायल से शुरू करें और अस्थायी लाइसेंस के लिए आवेदन करें ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Support:** Aspose के सपोर्ट फ़ोरम पर समुदाय से मदद प्राप्त करें ([Link](https://forum.aspose.com/c/slides/11)).

---

**अंतिम अपडेट:** 2026-08-06  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल
- [PowerPoint चार्ट्स को बेहतर बनाना: फ़ॉन्ट और एक्सिस कस्टमाइज़ेशन Aspose.Slides for Java के साथ](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java: डायनामिक टेक्स्ट फ्रेम्स और फ़ॉन्ट कस्टमाइज़ेशन गाइड](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Aspose.Slides for Java का उपयोग करके PowerPoint चार्ट्स को एनीमेट करें – चरण‑दर‑चरण गाइड](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}