---
date: '2026-03-18'
description: जावा में Aspose.Slides के साथ क्लस्टर्ड कॉलम चार्ट बनाना, चार्ट जोड़ना,
  रंग सेट करना और प्रस्तुति को PPTX के रूप में सहेजना सीखें। कोड उदाहरणों के साथ चरण‑दर‑चरण
  गाइड।
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: Java में Aspose.Slides के साथ क्लस्टर्ड कॉलम चार्ट कैसे बनाएं
url: /hi/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java में Aspose.Slides के साथ क्लस्टर्ड कॉलम चार्ट कैसे बनाएं

## परिचय
दृश्यात्मक रूप से आकर्षक डेटा प्रतिनिधित्व बनाना प्रभावशाली व्यावसायिक प्रस्तुतियों के लिए आवश्यक है, और प्रोग्रामेटिक रूप से **क्लस्टर्ड कॉलम चार्ट कैसे बनाएं** सीखने से आप मैन्युअल काम के कई घंटे बचा सकते हैं। इस ट्यूटोरियल में आप देखेंगे **चार्ट कैसे जोड़ें**, स्वचालित रूप से **रंग सेट करें**, और अंत में **Aspose.Slides for Java** का उपयोग करके **प्रेजेंटेशन को PPTX के रूप में सहेजें**। हम सब कुछ चरण-दर-चरण बताएंगे—लाइब्रेरी सेटअप से लेकर चार्ट जोड़ने, सीरीज़ फ़िल रंग कस्टमाइज़ करने, और फ़ाइल को सहेजने तक।

### आप क्या हासिल करेंगे
- Aspose.Slides for Java को इंस्टॉल और कॉन्फ़िगर करें  
- **क्लस्टर्ड कॉलम चार्ट बनाएं** एक नई प्रस्तुति में  
- स्वचालित रूप से सीरीज़ फ़िल रंग लागू करें (**how to set colors**)  
- **प्रेजेंटेशन को PPTX के रूप में सहेजें** डिस्क पर (**how to save presentation**)  

चार्ट बनाना शुरू करने से पहले चलिए आवश्यक पूर्वापेक्षाएँ पूरी करते हैं।

## त्वरित उत्तर
- **मुख्य क्लास क्या है?** `Presentation` from `com.aspose.slides`  
- **मैं चार्ट कैसे जोड़ूं?** Use `addChart(ChartType.ClusteredColumn, …)` on a slide’s shape collection (**how to add chart**)  
- **क्या मैं रंग स्वचालित रूप से सेट कर सकता हूँ?** Yes, call `setAutomaticSeriesColor(true)` on each series (**how to set colors**)  
- **सहेजने के लिए कौन सा फॉर्मेट उपयोग किया जाता है?** `SaveFormat.Pptx` (PowerPoint) (**save presentation as pptx**)  
- **क्या मुझे लाइसेंस चाहिए?** परीक्षण के लिए ट्रायल काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है  

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास आवश्यक उपकरण और ज्ञान है:

### आवश्यक लाइब्रेरी और निर्भरताएँ
आपको Aspose.Slides for Java लाइब्रेरी की आवश्यकता होगी। सुनिश्चित करें कि आप संस्करण 25.4 का उपयोग कर रहे हैं जिसमें JDK16 समर्थन है।

### पर्यावरण सेटअप आवश्यकताएँ
आपके विकास पर्यावरण को Java (अधिमानतः JDK16) का समर्थन करना चाहिए और Maven या Gradle का उपयोग करके प्रोजेक्ट बनाना सक्षम होना चाहिए।

### ज्ञान पूर्वापेक्षाएँ
बेसिक Java प्रोग्रामिंग, Maven/Gradle के माध्यम से लाइब्रेरीज़ के साथ काम करने, और PowerPoint प्रस्तुतियों की समझ होना लाभदायक होगा।

## Aspose.Slides for Java सेटअप करना
अपने प्रोजेक्ट में Aspose.Slides को इंटीग्रेट करने के लिए नीचे दिए गए सेटअप निर्देशों का पालन करें:

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
जो सीधे डाउनलोड पसंद करते हैं, वे [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) पर जाएँ।

### लाइसेंस प्राप्ति चरण
- **Free Trial**: फीचर्स का पता लगाने के लिए एक मुफ्त ट्रायल से शुरू करें।  
- **Temporary License**: बिना सीमाओं के परीक्षण के लिए एक टेम्पररी लाइसेंस प्राप्त करें।  
- **Purchase**: निरंतर उपयोग के लिए पूर्ण लाइसेंस खरीदें।

**Basic Initialization and Setup**  
Aspose.Slides को इस प्रकार इनिशियलाइज़ करें:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## क्लस्टर्ड कॉलम चार्ट कैसे जोड़ें
चार्ट जोड़ना पहला कार्यात्मक कदम है। यह सेक्शन **चार्ट कैसे जोड़ें** API का उपयोग करके समझाता है।

### फ़ीचर 1: क्लस्टर्ड कॉलम चार्ट बनाएं
आइए Aspose.Slides for Java का उपयोग करके एक क्लस्टर्ड कॉलम चार्ट बनाते हैं। यह फ़ीचर आपको आसानी से अपने स्लाइड्स में दृश्यात्मक आकर्षक चार्ट जोड़ने की अनुमति देता है।

#### Overview
इस सेक्शन में, हम एक नई प्रस्तुति इनिशियलाइज़ करेंगे और पहले स्लाइड में एक क्लस्टर्ड कॉलम चार्ट डालेंगे।

**Step 1: प्रस्तुति को इनिशियलाइज़ करें**  
PowerPoint फ़ाइलों के साथ काम शुरू करने के लिए एक `Presentation` ऑब्जेक्ट बनाएं:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**Step 2: क्लस्टर्ड कॉलम चार्ट जोड़ें**  
निर्दिष्ट निर्देशांक (100, 50) और आकार (600 × 400) पर चार्ट जोड़ें:
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**Step 3: संसाधनों को साफ़ करें**  
स्मृति लीक से बचने के लिए हमेशा संसाधनों को डिस्पोज़ करें:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## चार्ट के लिए रंग कैसे सेट करें
स्वचालित रूप से सीरीज़ फ़िल रंग लागू करके दृश्य आकर्षण बढ़ाएँ (**how to set colors**).

### फ़ीचर 2: स्वचालित सीरीज़ फ़िल रंग सेट करें
एक सुसंगत लुक के लिए प्रत्येक चार्ट की सीरीज़ का रंग स्वचालित रूप से सेट करें।

#### Overview
एक सुसंगत लुक के लिए प्रत्येक चार्ट की सीरीज़ का रंग स्वचालित रूप से सेट करें।

**Step 1: चार्ट तक पहुँचें और सीरीज़ पर इटरेट करें**  
चार्ट बनाने के बाद, उसे एक्सेस करें और उसकी सीरीज़ पर इटरेट करें:
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**Step 2: संसाधन प्रबंधन**  
काम पूरा होने पर प्रेजेंटेशन ऑब्जेक्ट को डिस्पोज़ करें:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## प्रेजेंटेशन को PPTX के रूप में कैसे सहेजें
एक बार चार्ट शानदार दिखे, तो आप फ़ाइल को सहेजना चाहेंगे (**how to save presentation**).

### फ़ीचर 3: प्रेजेंटेशन को डिस्क पर सहेजें
अंत में, Aspose.Slides का उपयोग करके अपने काम को आसानी से सहेजें।

#### Overview
अपनी संपादित प्रस्तुतियों को इच्छित फॉर्मेट और स्थान पर सहेजें।

**Step 1: आउटपुट पाथ निर्धारित करें**  
निर्दिष्ट करें कि आप फ़ाइल कहाँ सहेजना चाहते हैं:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**Step 2: प्रेजेंटेशन सहेजें**  
`Presentation` ऑब्जेक्ट की `save` मेथड का उपयोग करें:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## व्यावहारिक अनुप्रयोग
- **Financial Reports**: त्रैमासिक आय को स्पष्टता के साथ विज़ुअलाइज़ करें।  
- **Marketing Data Analysis**: आकर्षक विज़ुअल्स का उपयोग करके कैंपेन परिणाम दिखाएँ।  
- **Project Management**: टीम मीटिंग्स में माइलस्टोन और प्रगति को दृश्य रूप से ट्रैक करें।

## प्रदर्शन संबंधी विचार
Aspose.Slides के साथ काम करते समय, इन सर्वोत्तम प्रथाओं पर विचार करें:

- `Presentation` ऑब्जेक्ट्स को तुरंत डिस्पोज़ करके मेमोरी को प्रभावी ढंग से प्रबंधित करें।  
- प्रेजेंटेशन सहेजते समय फ़ाइल आकार को ऑप्टिमाइज़ करें ताकि डिस्क स्पेस बचाया जा सके।  
- चार्ट सीरीज़ के लिए कुशल डेटा स्ट्रक्चर का उपयोग करके प्रदर्शन बढ़ाएँ।

## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके **क्लस्टर्ड कॉलम चार्ट बनाना**, स्वचालित रूप से **रंग सेट करना**, और **प्रेजेंटेशन को PPTX के रूप में सहेजना** सीख लिया है। यह कौशल न केवल आपकी प्रस्तुतियों को बेहतर बनाता है बल्कि विज़ुअल डेटा प्रतिनिधित्व की प्रक्रिया को भी सरल बनाता है।

**अगले कदम:**  
अपने प्रोजेक्ट क्षमताओं को विस्तारित करने के लिए चार्ट एलिमेंट्स को कस्टमाइज़ करना, डेटा लेबल जोड़ना, या बाहरी डेटा स्रोतों के साथ इंटीग्रेशन जैसी अतिरिक्त सुविधाओं का अन्वेषण करें।

## FAQ सेक्शन
1. **मैं किसी विशिष्ट JDK संस्करण के लिए Aspose.Slides कैसे इंस्टॉल करूँ?**  
   - सेटअप सेक्शन में दिखाए अनुसार `classifier` निर्दिष्ट करके Maven/Gradle डिपेंडेंसीज़ का उपयोग करें।  

2. **अगर मेरी प्रस्तुति सही से सहेजी नहीं जा रही है तो क्या करें?**  
   - सुनिश्चित करें कि आपके पास आउटपुट डायरेक्टरी में लिखने की अनुमति है और फ़ाइल पाथ सही है।  

3. **क्या मैं Aspose.Slides for Java का उपयोग करके अन्य प्रकार के चार्ट बना सकता हूँ?**  
   - बिल्कुल! `ChartType` विकल्पों जैसे Pie, Bar, या Line चार्ट्स को एक्सप्लोर करें।  

4. **मैं अपने चार्ट में बड़े डेटा सेट को कैसे संभालूँ?**  
   - डेटा स्ट्रक्चर को ऑप्टिमाइज़ करें और विज़ुअलाइज़ करने से पहले डेटा को प्री‑प्रोसेस करने पर विचार करें।  

5. **मैं Aspose.Slides for Java के अधिक उदाहरण कहाँ पा सकता हूँ?**  
   - व्यापक गाइड्स और कोड सैंपल्स के लिए [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) पर जाएँ।  

## संसाधन
- **दस्तावेज़ीकरण**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **डाउनलोड**: [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **खरीदें**: [Buy a License](https://purchase.aspose.com/buy)  
- **Free Trial**: [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **टेम्पररी लाइसेंस**: [Request Here](https://purchase.aspose.com/temporary-license/)  
- **सपोर्ट**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-03-18  
**Tested With:** Aspose.Slides 25.4 (JDK16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}