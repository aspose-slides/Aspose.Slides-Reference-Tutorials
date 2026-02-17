---
date: '2026-02-17'
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में पाई
  चार्ट कैसे जोड़ें, सीखें। पेशेवर पाई चार्ट बनाने और अनुकूलित करने के लिए इस चरण‑दर‑चरण
  गाइड का पालन करें।
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Aspose.Slides for Java के साथ PowerPoint में पाई चार्ट कैसे जोड़ें
url: /hi/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint में Aspose.Slides for Java का उपयोग करके पाई चार्ट बनाएं और कस्टमाइज़ करें

## परिचय

क्या आप अपने PowerPoint प्रस्तुतियों में डेटा को प्रभावी ढंग से विज़ुअलाइज़ करने में संघर्ष कर रहे हैं? **PowerPoint में पाई चार्ट** स्लाइड जोड़ने से कच्चे आंकड़ों को तुरंत स्पष्ट दृश्य कहानी में बदला जा सकता है। Aspose.Slides for Java के साथ, आप प्रोग्रामेटिकली **PowerPoint में पाई चार्ट** फ़ाइलें जोड़ सकते हैं, जिससे आपको डिज़ाइन और डेटा पर पूरी नियंत्रण मिलता है, बिना PowerPoint को मैन्युअली खोले। इस ट्यूटोरियल में हम पूरी प्रक्रिया—लाइब्रेरी सेटअप से लेकर व्यक्तिगत डेटा पॉइंट को कस्टमाइज़ करने तक—परिचित कराएंगे, ताकि आप मिनटों में पॉलिश्ड, डेटा‑ड्रिवन स्लाइड्स दे सकें।

### त्वरित उत्तर
- **मुझे कौन सी लाइब्रेरी चाहिए?** Aspose.Slides for Java (नवीनतम संस्करण)।  
- **क्या मैं PowerPoint इंस्टॉल किए बिना चार्ट बना सकता हूँ?** हाँ, API पूरी तरह ऑफ़लाइन काम करता है।  
- **कौन सा Java संस्करण आवश्यक है?** JDK 16 या बाद का संस्करण अनुशंसित है।  
- **स्लाइस का रंग कैसे बदलें?** डेटा पॉइंट पर `setFillType` और `setSolidFillColor` मेथड्स का उपयोग करें।  
- **क्या लाइसेंस अनिवार्य है?** विकास के लिए ट्रायल काम करता है; स्थायी लाइसेंस मूल्यांकन सीमाओं को हटा देता है।

### आप क्या सीखेंगे
- Java के साथ प्रोग्रामेटिकली **PowerPoint में पाई चार्ट** कैसे जोड़ें।  
- स्लाइस एक्सप्लोजन, रंग और अन्य विज़ुअल प्रॉपर्टीज़ को कस्टमाइज़ करने के तरीके।  
- बड़े प्रेजेंटेशन को संभालते समय रिसोर्स मैनेजमेंट और परफ़ॉर्मेंस के लिए बेस्ट प्रैक्टिसेज़।

## Aspose.Slides for Java का उपयोग करके PowerPoint में पाई चार्ट क्यों जोड़ें?
कोड से सीधे पाई चार्ट एम्बेड करने से आप अपडेटेड रिपोर्ट्स जेनरेट कर सकते हैं, मासिक डैशबोर्ड्स को ऑटोमेट कर सकते हैं, या ऑन‑द‑फ़्लाई पर्सनलाइज़्ड स्लाइड डेक बना सकते हैं। यह मैन्युअल कॉपी‑पेस्ट त्रुटियों को समाप्त करता है, प्रस्तुतियों में स्थिरता सुनिश्चित करता है, और मौजूदा Java बैक‑एंड्स के साथ सुगमता से इंटीग्रेट होता है।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

- **Aspose.Slides for Java लाइब्रेरी** – ट्यूटोरियल संस्करण 25.4 (लेखन समय पर नवीनतम रिलीज) का संदर्भ देता है।  
- एक संगत **Java Development Kit (JDK)** – JDK 16+ पसंदीदा है।  
- **Maven** या **Gradle** की बुनियादी जानकारी, ताकि डिपेंडेंसी मैनेजमेंट किया जा सके।  

## Aspose.Slides for Java सेटअप करना

शुरू करने के लिए, अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी शामिल करें।

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

वैकल्पिक रूप से, नवीनतम संस्करण सीधे [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

### लाइसेंसिंग
Aspose.Slides को बिना प्रतिबंधों के उपयोग करने के लिए:

- API का मूल्यांकन करने हेतु **नि:शुल्क ट्रायल** शुरू करें।  
- विस्तारित परीक्षण के लिए [Temporary License](https://purchase.aspose.com/temporary-license/) पेज पर **अस्थायी लाइसेंस** का अनुरोध करें।  
- पूर्ण सब्सक्रिप्शन खरीदने के लिए [Purchase page](https://purchase.aspose.com/buy) पर जाएँ।

## Aspose.Slides for Java का उपयोग करके PowerPoint में पाई चार्ट कैसे जोड़ें

नीचे चरण‑दर‑चरण गाइड है जो दिखाता है कि पाई चार्ट कैसे बनाएं और कस्टमाइज़ करें।

### चरण 1: प्रेजेंटेशन को इनिशियलाइज़ करें
पहले, एक नया `Presentation` ऑब्जेक्ट बनाएं। यह एक खाली PowerPoint फ़ाइल का प्रतिनिधित्व करता है।
```java
Presentation pres = new Presentation();
```

### चरण 2: पाई चार्ट जोड़ें
पहली स्लाइड पर पाई चार्ट इन्सर्ट करें। कोऑर्डिनेट्स (50, 50) और साइज (600 × 400) मानक 16:9 स्लाइड के लिए उपयुक्त हैं।
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### चरण 3: प्रेजेंटेशन को सेव करें
प्रेजेंटेशन को डिस्क पर लिखें। `YOUR_OUTPUT_DIRECTORY` को उस फ़ोल्डर से बदलें जहाँ आप फ़ाइल सेव करना चाहते हैं।
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### चरण 4: रिसोर्सेज़ को क्लीन अप करें
`Presentation` ऑब्जेक्ट को डिस्पोज़ करके नेटिव रिसोर्सेज़ को मुक्त करें।
```java
if (pres != null) pres.dispose();
```

## डेटा पॉइंट एक्सप्लोजन और रंग कस्टमाइज़ करना

व्यक्तिगत स्लाइस को कस्टमाइज़ करने से आपका चार्ट पढ़ने में आसान हो जाता है, विशेषकर जब आप किसी विशिष्ट वैल्यू को हाइलाइट करना चाहते हैं।

### चरण 1: मौजूदा प्रेजेंटेशन लोड करें (या अभी बनाया हुआ पुन: उपयोग करें)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### चरण 2: चार्ट और लक्ष्य डेटा पॉइंट तक पहुँचें
यहाँ हम पहली सीरीज़ के दूसरे डेटा पॉइंट (इंडेक्स 1) को प्राप्त करते हैं।
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### चरण 3: एक्सप्लोजन और रंग लागू करें
स्लाइस को दृश्य रूप से अलग करें और उसका फ़िल कलर ब्लू में बदलें।
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### चरण 4: सेव और डिस्पोज़ करें
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## व्यावहारिक उपयोग
- **सेल्स रिपोर्ट:** टॉप‑सेलिंग प्रोडक्ट्स को एक्सप्लोडेड स्लाइस के साथ हाइलाइट करें।  
- **बजट एनालिसिस:** विभागों को अलग-अलग रंग असाइन करके तेज़ विज़ुअल तुलना प्रदान करें।  
- **शैक्षणिक स्लाइड्स:** जटिल अवधारणाओं को आसानी से समझ में आने वाले चार्ट सेगमेंट्स में विभाजित करें।

## परफ़ॉर्मेंस विचार
- **ऑब्जेक्ट्स को तुरंत डिस्पोज़** करें ताकि मेमोरी लीक से बचा जा सके, विशेषकर जब लूप में कई स्लाइड्स जेनरेट कर रहे हों।  
- **हिप उपयोग को मॉनिटर** करें बड़े प्रेजेंटेशन के लिए; `Save` ओवरलोड्स जो `OutputStream` स्वीकार करते हैं, उनका उपयोग करके स्ट्रीमिंग आउटपुट पर विचार करें।  
- नवीनतम गार्बेज‑कलेक्शन सुधारों का लाभ उठाने के लिए **JDK 16+** पर टिके रहें।

## निष्कर्ष
अब आपके पास Aspose.Slides for Java का उपयोग करके **PowerPoint में पाई चार्ट** फ़ाइलें जोड़ने की पूरी, प्रोडक्शन‑रेडी वर्कफ़्लो है। विभिन्न एक्सप्लोजन दूरी, रंग, और डेटा सेट्स के साथ प्रयोग करें ताकि आपका ब्रांडिंग मेल खाए। जब आप तैयार हों, तो अन्य चार्ट प्रकार—बार, लाइन, या स्कैटर—को एक्सप्लोर करें और PowerPoint के भीतर एक पूर्ण एनालिटिक्स डैशबोर्ड बनाएं।

## अक्सर पूछे जाने वाले प्रश्न
1. **Aspose.Slides for Java का मुख्य लाभ क्या है?**  
   - यह प्रोग्रामेटिकली PowerPoint फ़ाइलों के निर्माण और मैनीपुलेशन को सरल बनाता है, और कई फीचर्स प्रदान करता है।  
2. **क्या मैं Aspose.Slides के साथ अन्य चार्ट प्रकार कस्टमाइज़ कर सकता हूँ?**  
   - बिल्कुल! Aspose.Slides बार, लाइन, और स्कैटर चार्ट सहित विभिन्न चार्ट प्रकारों को सपोर्ट करता है।  
3. **चार्ट बनाते समय कई स्लाइड्स को कैसे हैंडल करूँ?**  
   - `get_Item()` मेथड का उपयोग करके इंडेक्स द्वारा प्रत्येक स्लाइड तक पहुँचें और विभिन्न स्लाइड्स पर बदलाव लागू करें।  
4. **यदि मेरा पाई चार्ट कस्टमाइज़ करने के बाद सही नहीं दिख रहा है तो क्या करें?**  
   - `addChart()` में उपयोग किए गए कोऑर्डिनेट्स और डाइमेंशन्स की जाँच करें, यह सुनिश्चित करें कि वे आपके स्लाइड लेआउट में फिट हों।  
5. **Aspose.Slides की अधिक उन्नत सुविधाएँ कहाँ मिलेंगी?**  
   - अतिरिक्त कार्यक्षमताओं और विकल्पों के बारे में जानने के लिए [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) देखें।

## संसाधन
- **डॉक्यूमेंटेशन:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **लाइब्रेरी डाउनलोड:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **लाइसेंस खरीदें:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **नि:शुल्क ट्रायल:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **अस्थायी लाइसेंस:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **सपोर्ट फ़ोरम:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**अंतिम अपडेट:** 2026-02-17  
**टेस्टेड विथ:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}