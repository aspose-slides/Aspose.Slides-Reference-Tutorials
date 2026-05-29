---
date: '2026-05-29'
description: Aspose.Slides Maven का उपयोग करके Aspose के साथ पाई चार्ट बनाना, स्लाइड
  में पाई चार्ट Java जोड़ना, और चार्ट डेटा को कस्टमाइज़ करना सीखें। Maven सेटअप और
  वास्तविक उदाहरणों के साथ चरण‑दर‑चरण गाइड।
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Aspose के साथ पाई चार्ट बनाएं – Maven के साथ प्रस्तुति में चार्ट जोड़ें
url: /hi/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java का उपयोग करके प्रस्तुति में पाई चार्ट कैसे जोड़ें

## परिचय
इस गाइड में आप **create pie chart aspose** को Aspose.Slides Maven के साथ बनाएँगे और देखेंगे कि इसे PowerPoint स्लाइड में कैसे एम्बेड किया जाता है। दृश्य रूप से आकर्षक प्रस्तुतियों का निर्माण जानकारी को प्रभावी ढंग से संप्रेषित करने के लिए अत्यंत महत्वपूर्ण है, विशेषकर जब डेटा विज़ुअलाइज़ेशन मुख्य भूमिका निभाता है। यदि आप इस प्रक्रिया को **aspose slides maven** के साथ स्वचालित करना चाहते हैं, तो आप सही जगह पर आए हैं। हम स्लाइड में एक चार्ट—विशेष रूप से पाई चार्ट—जोड़ने और इसे वास्तविक‑दुनिया के परिदृश्यों के लिए अनुकूलित करने की प्रक्रिया को चरण‑दर‑चरण देखेंगे।

### आप क्या सीखेंगे
- Java में प्रस्तुति ऑब्जेक्ट को कैसे इनिशियलाइज़ करें।  
- प्रस्तुति की पहली स्लाइड पर **add a pie chart java** कैसे जोड़ें।  
- चार्ट डेटा वर्कबुक तक पहुँच और उनमें मौजूद वर्कशीट्स को सूचीबद्ध करना।  

आइए देखें कि आप Aspose.Slides Java का उपयोग करके गतिशील चार्ट्स के साथ अपनी प्रस्तुतियों को कैसे बेहतर बना सकते हैं!

## त्वरित उत्तर
- **Maven के माध्यम से चार्ट जोड़ने वाली लाइब्रेरी कौन सी है?** aspose slides maven  
- **कौन सा चार्ट प्रकार प्रदर्शित किया गया है?** Pie chart (स्लाइड में चार्ट जोड़ें)  
- **न्यूनतम Java संस्करण क्या चाहिए?** JDK 16 या बाद का  
- **परीक्षण के लिए लाइसेंस चाहिए?** एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है  
- **Maven डिपेंडेंसी कहाँ मिल सकती है?** नीचे सेटअप सेक्शन में  

## Aspose Slides Maven क्या है?
Aspose.Slides for Java एक शक्तिशाली API है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint फ़ाइलें बनाने, संशोधित करने और रेंडर करने की सुविधा देता है। Maven पैकेज (`aspose-slides`) डिपेंडेंसी मैनेजमेंट को सरल बनाता है, जिससे आप स्लाइड्स—जैसे पाई चार्ट जोड़ना—पर ध्यान केंद्रित कर सकते हैं, बिना लो‑लेवल फ़ाइल हैंडलिंग की झंझट के।

## स्लाइड में चार्ट जोड़ने के लिए Aspose.Slides Maven का उपयोग क्यों करें?
Aspose.Slides Maven का उपयोग करके आप Java कोड से सीधे चार्ट जेनरेट कर सकते हैं, बिना मैन्युअल PowerPoint एडिटिंग के। यह चार्ट प्रकार, डेटा स्रोत और स्टाइलिंग पर पूर्ण प्रोग्रामेटिक नियंत्रण प्रदान करता है, जिससे ब्रांडिंग और सटीकता में स्थिरता आती है। Maven आर्टिफैक्ट सभी आवश्यक डिपेंडेंसी को संभालता है, बिल्ड को सरल बनाता है और CI/CD पाइपलाइन में सहज इंटीग्रेशन सक्षम करता है।

## आवश्यकताएँ
- **Aspose.Slides for Java** संस्करण 25.4 या बाद का (Maven/Gradle)।  
- JDK 16+ स्थापित हो।  
- एक IDE (IntelliJ IDEA, Eclipse, आदि)।  
- बुनियादी Java ज्ञान और Maven या Gradle की परिचितता।

## Aspose.Slides for Java सेटअप करना
पहले, Maven या Gradle के माध्यम से अपने प्रोजेक्ट में Aspose.Slides शामिल करें।

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

वैकल्पिक रूप से, आप Aspose की वेबसाइट से सीधे [नवीनतम रिलीज़ डाउनलोड करें](https://releases.aspose.com/slides/java/)।

### लाइसेंस प्राप्त करना
Aspose.Slides for Java परीक्षण के लिए एक मुफ्त ट्रायल और अस्थायी लाइसेंस प्रदान करता है। अनलिमिटेड प्रोडक्शन उपयोग के लिए, कृपया [खरीद पृष्ठ](https://purchase.aspose.com/buy) से लाइसेंस खरीदें।

## कार्यान्वयन गाइड
नीचे हम समाधान को दो फीचर्स में विभाजित करेंगे: पाई चार्ट जोड़ना और उसके डेटा वर्कबुक तक पहुँच।

### फीचर 1: प्रस्तुति बनाना और चार्ट जोड़ना
#### अवलोकन
यह भाग नई प्रस्तुति बनाना और पहली स्लाइड पर **add a pie chart** दिखाता है।

#### पाई चार्ट aspose कैसे बनाएं?
`Presentation` क्लास लोड करें, `ChartType.Pie` प्रकार का चार्ट जोड़ें, और फ़ाइल सहेजें। पूरी प्रक्रिया केवल तीन API कॉल्स में पूरी होती है और सामान्य 10‑स्लाइड डेक के लिए एक सेकंड से कम समय लेती है, जिससे यह स्वचालित रिपोर्ट जेनरेशन के लिए आदर्श बनती है।

#### चरण‑दर‑चरण

**चरण 1: नया प्रस्तुति ऑब्जेक्ट इनिशियलाइज़ करें**  
`Presentation` क्लास Aspose.Slides का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करता है।  
```java
Presentation pres = new Presentation();
```
*`Presentation` इंस्टेंस बनाता है जो सभी स्लाइड्स को रखेगा।*

**चरण 2: पाई चार्ट जोड़ें**  
`ChartType.Pie` Aspose को पाई चार्ट रेंडर करने के लिए बताता है।  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*कोऑर्डिनेट (50, 50) पर चौड़ाई 400 और ऊँचाई 500 के साथ पाई चार्ट रखता है।*

**चरण 3: संसाधनों को डिस्पोज़ करें**  
`dispose()` कॉल करने से नेटिव संसाधन मुक्त होते हैं और मेमोरी लीक्स से बचा जाता है।  
```java
if (pres != null) pres.dispose();
```
*नेटिव संसाधन रिलीज़ करता है; समाप्ति पर हमेशा `dispose()` कॉल करें।*

### फीचर 2: चार्ट डेटा वर्कबुक और वर्कशीट्स तक पहुँच
#### अवलोकन
चार्ट डेटा को स्टोर करने वाले अंतर्निहित वर्कबुक तक पहुँचना और उसकी वर्कशीट्स को इटररेट करना सीखें।

#### चार्ट डेटा वर्कबुक कैसे एक्सेस करें?
चार्ट से `IChartDataWorkbook` प्राप्त करें, फिर उसकी `Worksheets` कलेक्शन पर लूप चलाएँ। यह वर्कबुक Excel फ़ाइल की नकल करता है, जिससे आप प्रोग्रामेटिक रूप से डेटा सीरीज़ पढ़, संशोधित या जोड़ सकते हैं, और चार्ट रिफ्रेश होने पर तुरंत अपडेट हो जाता है।

#### चरण‑दर‑चरण

**चरण 1: (पुन: उपयोग) नया प्रस्तुति ऑब्जेक्ट इनिशियलाइज़ करें**  
*फ़ीचर 1, चरण 1 के समान।*

**चरण 2: (पुन: उपयोग) पाई चार्ट जोड़ें**  
*फ़ीचर 1, चरण 2 के समान।*

**चरण 3: चार्ट डेटा वर्कबुक प्राप्त करें**  
`IChartDataWorkbook` वह इंटरफ़ेस है जो चार्ट के आंतरिक Excel‑जैसे वर्कबुक तक रीड/राइट एक्सेस प्रदान करता है।  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*चार्ट से जुड़ा `IChartDataWorkbook` प्राप्त करता है।*

**चरण 4: वर्कशीट्स को इटररेट करें**  
`Worksheet` ऑब्जेक्ट्स वर्कबुक के भीतर व्यक्तिगत शीट्स का प्रतिनिधित्व करते हैं।  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*प्रत्येक वर्कशीट का नाम प्रिंट करता है, जिससे डेटा स्ट्रक्चर की पुष्टि होती है।*

**चरण 5: संसाधनों को डिस्पोज़ करें**  
*फ़ीचर 1, चरण 3 के समान।*

## व्यावहारिक अनुप्रयोग
- **डेटा रिपोर्टिंग:** व्यापारिक इंटेलिजेंस के लिए अद्यतन मीट्रिक्स के साथ स्वचालित स्लाइड डेक जेनरेट करें।  
- **शैक्षणिक प्रस्तुतियाँ:** मैन्युअल चार्ट निर्माण के बिना शोध परिणामों को विज़ुअलाइज़ करें।  
- **मार्केटिंग सामग्री:** उत्पाद प्रदर्शन या सर्वे परिणामों को तुरंत प्रदर्शित करें।

## प्रदर्शन संबंधी विचार
- Aspose.Slides **50+ इनपुट और आउटपुट फ़ॉर्मैट** संभाल सकता है और कई‑सौ पेज़ की प्रस्तुतियों को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है।  
- स्लाइड और चार्ट की संख्या को यथासंभव सीमित रखें; प्रत्येक चार्ट नेटिव मेमोरी खपत करता है।  
- हमेशा `dispose()` कॉल करके संसाधनों को तुरंत मुक्त करें।  
- वर्कबुक डेटा हैंडलिंग को ऑप्टिमाइज़ करें—एक ही चार्ट में बड़े डेटा सेट लोड करने से बचें।

## निष्कर्ष
हमने देखा कि **aspose slides maven** कैसे प्रोग्रामेटिक रूप से **add chart to slide** को सक्षम करता है और चार्ट के डेटा वर्कबुक के साथ कैसे काम किया जाता है। इन बिल्डिंग ब्लॉक्स के साथ आप किसी भी रिपोर्टिंग वर्कफ़्लो को स्वचालित कर सकते हैं जो एक परिष्कृत PowerPoint आउटपुट की मांग करता है।

### अगले कदम
- चार्ट स्टाइलिंग विकल्पों (रंग, लेजेंड, डेटा लेबल) का अन्वेषण करें।  
- बाहरी डेटा स्रोतों (CSV, डेटाबेस) से कनेक्ट करके चार्ट को डायनामिक रूप से पॉप्युलेट करें।  
- समृद्ध कहानी कहने के लिए एक ही प्रस्तुति में कई चार्ट प्रकारों को संयोजित करें।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: मैं Aspose.Slides for Java कैसे इंस्टॉल करूँ?**  
उत्तर: ऊपर दिखाए गए Maven या Gradle डिपेंडेंसी का उपयोग करें, या रिलीज़ पेज से लाइब्रेरी डाउनलोड करें।

**प्रश्न: Aspose.Slides की सिस्टम आवश्यकताएँ क्या हैं?**  
उत्तर: JDK 16 या बाद का; लाइब्रेरी किसी भी प्लेटफ़ॉर्म पर चलती है जो Java सपोर्ट करता है।

**प्रश्न: क्या मैं पाई चार्ट के अलावा अन्य चार्ट प्रकार जोड़ सकता हूँ?**  
उत्तर: हाँ, Aspose.Slides बार, लाइन, स्कैटर, रेडार और 20 से अधिक चार्ट प्रकारों का समर्थन करता है।

**प्रश्न: बड़े प्रस्तुतियों को कुशलता से कैसे संभालूँ?**  
उत्तर: ऑब्जेक्ट्स को तुरंत डिस्पोज़ करें, हाई‑रेज़ोल्यूशन इमेजेज़ को सीमित रखें, और मेमोरी उपयोग कम रखने के लिए चार्ट टेम्पलेट्स को पुन: उपयोग करें।

**प्रश्न: Aspose.Slides की सुविधाओं के बारे में अधिक जानकारी कहाँ मिल सकती है?**  
उत्तर: पूर्ण API रेफ़रेंस के लिए [Aspose documentation](https://reference.aspose.com/slides/java/) देखें।

**प्रश्न: व्यावसायिक उपयोग के लिए लाइसेंस आवश्यक है?**  
उत्तर: उत्पादन के लिए वैध लाइसेंस आवश्यक है; मूल्यांकन के लिए एक मुफ्त ट्रायल उपलब्ध है।

**प्रश्न: क्या Maven पैकेज में सभी चार्ट क्षमताएँ शामिल हैं?**  
उत्तर: हाँ, `aspose-slides` Maven आर्टिफैक्ट में पूर्ण चार्टिंग इंजन सम्मिलित है।

## संसाधन
- दस्तावेज़ीकरण: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)  
- डाउनलोड: [Latest Releases](https://releases.aspose.com/slides/java/)  
- खरीद और ट्रायल: [Purchase Page](https://purchase.aspose.com/buy)  
- मुफ्त ट्रायल: [Trial Downloads](https://releases.aspose.com/slides/java/)  
- अस्थायी लाइसेंस: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- सपोर्ट फ़ोरम: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**अंतिम अपडेट:** 2026-05-29  
**टेस्टेड विथ:** Aspose.Slides 25.4 for Java (jdk16)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [How to Customize Pie Chart Colors in Java with Aspose.Slides – A Complete Guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Create a Pie of Pie Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}