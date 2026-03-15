---
date: '2026-03-15'
description: Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में क्लस्टर्ड
  कॉलम चार्ट कैसे जोड़ें, सीखें, जिसमें चार्ट को स्लाइड में जोड़ने और Java में कुशलतापूर्वक
  PowerPoint स्लाइड बनाने के चरण शामिल हैं।
keywords:
- Aspose.Slides for Java
- PowerPoint Charts
- Java PowerPoint Automation
title: Aspose.Slides Java का उपयोग करके PPT में क्लस्टर्ड कॉलम चार्ट जोड़ें
url: /hi/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java का उपयोग करके PPT में क्लस्टर्ड कॉलम चार्ट जोड़ें

## परिचय
इस गाइड में आप Aspose.Slides for Java के साथ प्रोग्रामेटिकली PowerPoint प्रस्तुति में **क्लस्टर्ड कॉलम चार्ट** जोड़ेंगे। चाहे आप व्यापार रिपोर्ट, शैक्षणिक डेक या मार्केटिंग डेक बना रहे हों, चार्ट निर्माण को स्वचालित करने से समय बचता है और स्थिरता सुनिश्चित होती है। हम लाइब्रेरी सेटअप, स्लाइड बनाना, चार्ट जोड़ना, लाइन स्टाइल और गोल कोनों को लागू करना, और अंत में फ़ाइल सहेजना दिखाएंगे। अंत तक आप **स्लाइड में चार्ट जोड़ने** और यहां तक कि **Java‑आधारित PowerPoint स्लाइड बनाने** के पूरे वर्कफ़्लो में सहज होंगे।

### त्वरित उत्तर
- **शुरुआत करने के लिए मुख्य क्लास कौन सी है?** `Presentation`
- **कौन सा चार्ट प्रकार उपयोग किया जाता है?** `ChartType.ClusteredColumn`
- **गोल कोने कैसे सक्षम करें?** `chart.setRoundedCorners(true);`
- **सहेजने के लिए कौन सा फ़ॉर्मेट अनुशंसित है?** `SaveFormat.Pptx`
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए खरीदा गया लाइसेंस आवश्यक है।

## क्लस्टर्ड कॉलम चार्ट क्या है?
क्लस्टर्ड कॉलम चार्ट प्रत्येक श्रेणी के लिए कई डेटा सीरीज़ को बगल‑बगल समूहित करता है, जिससे विभिन्न समूहों के मानों की तुलना करना आसान हो जाता है। Aspose.Slides आपको PowerPoint खोले बिना पूरी तरह कोड में इस चार्ट प्रकार को उत्पन्न करने की सुविधा देता है।

## क्लस्टर्ड कॉलम चार्ट जोड़ने के लिए Aspose.Slides for Java का उपयोग क्यों करें?
- **पूर्ण स्वचालन** – मैन्युअल UI इंटरैक्शन की आवश्यकता नहीं।  
- **क्रॉस‑प्लेटफ़ॉर्म** – वह सभी OS पर काम करता है जो Java को सपोर्ट करता है।  
- **समृद्ध फ़ॉर्मेटिंग** – लाइन स्टाइल, फ़िल, गोल कोने और अधिक को नियंत्रित करें।  
- **कोई COM निर्भरताएँ नहीं** – Office Interop के विपरीत, यह सर्वरों पर सुरक्षित रूप से चलता है।

## पूर्वापेक्षाएँ
- **Aspose.Slides for Java** (v25.4 या नया)  
- **JDK 16** (या बाद का)  
- IntelliJ IDEA, Eclipse, या NetBeans जैसे IDE  

## Aspose.Slides for Java सेटअप करना
आप लाइब्रेरी को Maven, Gradle, या सीधे डाउनलोड द्वारा जोड़ सकते हैं।

### Maven का उपयोग करके
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle का उपयोग करके
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### सीधे डाउनलोड
नवीनतम संस्करण [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

#### लाइसेंस प्राप्त करने के चरण
- **फ़्री ट्रायल** – समय सीमा के बिना सभी सुविधाओं का परीक्षण करें।  
- **अस्थायी लाइसेंस** – पूर्ण‑फ़ीचर मूल्यांकन के लिए Aspose पोर्टल से अनुरोध करें।  
- **खरीदें** – उत्पादन उपयोग के लिए स्थायी लाइसेंस प्राप्त करें।

## कार्यान्वयन गाइड

### प्रस्तुति बनाना और स्लाइड जोड़ना
#### अवलोकन
सबसे पहले, हम एक नया `Presentation` ऑब्जेक्ट बनाते हैं और नई फ़ाइल के साथ आने वाली डिफ़ॉल्ट स्लाइड प्राप्त करते हैं।

#### चरण‑दर‑चरण
**1. Presentation ऑब्जेक्ट को इनिशियलाइज़ करें**
```java
Presentation presentation = new Presentation();
```

**2. पहली स्लाइड तक पहुँचें**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. संसाधनों को डिस्पोज़ करें**
```java
if (presentation != null) presentation.dispose();
```

### स्लाइड में चार्ट जोड़ना
#### अवलोकन
अब हम अभी तैयार की गई स्लाइड में एक **क्लस्टर्ड कॉलम चार्ट** एम्बेड करते हैं।

#### चरण‑दर‑चरण
**1. Presentation ऑब्जेक्ट को इनिशियलाइज़ करें**
```java
Presentation presentation = new Presentation();
```

**2. पहली स्लाइड तक पहुँचें**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. क्लस्टर्ड कॉलम चार्ट जोड़ें**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. संसाधनों को डिस्पोज़ करें**
```java
if (presentation != null) presentation.dispose();
```

### चार्ट लाइन स्टाइल फॉर्मेट करना और गोल कोने सेट करना
#### अवलोकन
एक ठोस लाइन फ़िल, एकल लाइन स्टाइल, और गोल कोनों को लागू करके दृश्य आकर्षण बढ़ाएँ।

#### चरण‑दर‑चरण
**1. Presentation ऑब्जेक्ट को इनिशियलाइज़ करें**
```java
Presentation presentation = new Presentation();
```

**2. पहली स्लाइड तक पहुँचें**
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. क्लस्टर्ड कॉलम चार्ट जोड़ें**
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. लाइन फ़ॉर्मेट को सॉलिड फ़िल टाइप पर सेट करें**
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```

**5. सिंगल लाइन स्टाइल लागू करें**
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```

**6. चार्ट एरिया के लिए गोल कोने सक्षम करें**
```java
chart.setRoundedCorners(true);
```

**7. संसाधनों को डिस्पोज़ करें**
```java
if (presentation != null) presentation.dispose();
```

### प्रस्तुति सहेजना
#### अवलोकन
अंत में, हम प्रस्तुति को PPTX फ़ॉर्मेट में डिस्क पर लिखते हैं।

#### चरण‑दर‑चरण
**1. Presentation ऑब्जेक्ट को इनिशियलाइज़ करें**
```java
Presentation presentation = new Presentation();
```

**2. आउटपुट डायरेक्टरी और फ़ाइल नाम निर्धारित करें**
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```

**3. PPTX फ़ॉर्मेट में प्रस्तुति सहेजें**
```java
presentation.save(outputFile, SaveFormat.Pptx);
```

**4. संसाधनों को डिस्पोज़ करें**
```java
if (presentation != null) presentation.dispose();
```

## व्यावहारिक अनुप्रयोग
- **व्यापार रिपोर्ट** – गतिशील चार्ट के साथ त्रैमासिक वित्तीय डेक को स्वचालित करें।  
- **शैक्षणिक सामग्री** – डेटाबेस से डेटा खींचने वाले लेक्चर स्लाइड बनाएं।  
- **मार्केटिंग प्रस्तुति** – परिष्कृत चार्ट के साथ उत्पाद रुझानों को विज़ुअलाइज़ करें।

## प्रदर्शन संबंधी विचार
- **संसाधन प्रबंधन** – हमेशा `dispose()` कॉल करें या try‑with‑resources का उपयोग करें।  
- **मेमोरी अनुकूलन** – बड़े डेटा सेट को छोटे बैच में प्रोसेस करें।  
- **सर्वोत्तम प्रथाएँ** – संभव हो तो चार्ट सीरीज़ के लिए अपरिवर्तनीय डेटा स्ट्रक्चर को प्राथमिकता दें।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **`NullPointerException` on `getSlides()`** | स्लाइड्स तक पहुँचने से पहले यह सुनिश्चित करें कि `Presentation` ऑब्जेक्ट सफलतापूर्वक इंस्टैंशिएट किया गया है। |
| **Chart not appearing** | जांचें कि चार्ट के आयाम (x, y, width, height) स्लाइड की सीमाओं के भीतर हैं। |
| **License not applied** | `Presentation` ऑब्जेक्ट बनाने से पहले अपना लाइसेंस फ़ाइल लोड करें: `License license = new License(); license.setLicense("path/to/license.xml");` |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: Aspose.Slides का उपयोग करके विभिन्न प्रकार के चार्ट कैसे जोड़ें?**  
**उत्तर:** `ChartType.ClusteredColumn` को किसी अन्य enum वैल्यू जैसे `ChartType.Pie`, `ChartType.Line`, या `ChartType.Bar` से बदलें।

**प्रश्न: यदि मुझे कंपाइलेशन त्रुटियाँ मिलें तो क्या करें?**  
**उत्तर:** सुनिश्चित करें कि आप JDK 16 या नया उपयोग कर रहे हैं और Maven/Gradle डिपेंडेंसी ऊपर दिखाए गए संस्करण से मेल खाती है।

**प्रश्न: क्या मैं डेटाबेस से डेटा के साथ चार्ट भर सकता हूँ?**  
**उत्तर:** हाँ। चार्ट के `getChartData()` कलेक्शन तक पहुँचें, सीरीज़ और कैटेगरीज बनाएं, और रनटाइम पर प्राप्त मानों से उन्हें भरें।

**प्रश्न: बहुत बड़े प्रस्तुतियों के लिए प्रदर्शन कैसे सुधारें?**  
**उत्तर:** कार्य को कई `Presentation` इंस्टेंस में विभाजित करें, चार्ट टेम्पलेट्स को पुन: उपयोग करें, और हमेशा ऑब्जेक्ट्स को तुरंत डिस्पोज़ करें।

## निष्कर्ष
अब आपके पास Aspose.Slides for Java के साथ PowerPoint स्लाइड में **क्लस्टर्ड कॉलम चार्ट जोड़ने** के लिए एक पूर्ण, अंत‑से‑अंत रेसिपी है। अन्य चार्ट प्रकारों के साथ प्रयोग करें, लाइव डेटा स्रोतों को बाइंड करें, और इस लॉजिक को बड़े रिपोर्टिंग पाइपलाइन में एकीकृत करके अपनी प्रस्तुति वर्कफ़्लो को स्वचालित करें।

---

**अंतिम अपडेट:** 2026-03-15  
**परीक्षण किया गया:** Aspose.Slides 25.4 for Java (JDK 16)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}