---
date: '2026-09-02'
description: Aspose.Slides for Java का उपयोग करके PowerPoint में फ़नल चार्ट बनाना
  सीखें। यह चरण-दर-चरण गाइड चार्ट डेटा सेट करने, रंगों को अनुकूलित करने और प्रस्तुति
  को निर्यात करने को कवर करता है।
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Aspose.Slides for Java का उपयोग करके PowerPoint में फ़नल चार्ट बनाना
  सीखें। यह गाइड डेटा सेटअप, रंग अनुकूलन, और अंतिम प्रस्तुति को निर्यात करने की प्रक्रिया
  को समझाता है।
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Aspose.Slides for Java के साथ PowerPoint में फ़नल चार्ट बनाएं
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Aspose.Slides for Java के साथ PowerPoint में फ़नल चार्ट बनाएं
url: /hi/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint में Aspose.Slides for Java के साथ फ़नल चार्ट निर्माण में महारत हासिल करना

## परिचय
आकर्षक प्रस्तुतियों का निर्माण एक कला है जो डेटा विज़ुअलाइज़ेशन, डिज़ाइन और कहानी कहने को मिलाती है। एक शक्तिशाली विज़ुअल जो कई‑स्तरीय प्रक्रिया को तुरंत स्पष्ट करता है वह फ़नल चार्ट है। चाहे आपको बिक्री पाइपलाइन, रूपांतरण प्रवाह, या उत्पादन बाधा को दर्शाना हो, एक अच्छी तरह से डिज़ाइन किया गया फ़नल चार्ट कच्चे आंकड़ों को सहज कथा में बदल देता है। इस ट्यूटोरियल में आप सीखेंगे कि कैसे **create funnel chart** को PowerPoint में प्रोग्रामेटिकली Aspose.Slides for Java का उपयोग करके बनाएं, उसका डेटा कॉन्फ़िगर करें, प्रत्येक खंड का रंग अनुकूलित करें, और तैयार डेक को निर्यात करें।

**आप क्या सीखेंगे**
- Maven या Gradle प्रोजेक्ट में Aspose.Slides for Java जोड़ने का तरीका  
- `Presentation` ऑब्जेक्ट को इंस्टैंशिएट करने और उसकी स्लाइड्स तक पहुँचने का तरीका  
- फ़नल चार्ट सम्मिलित करने, श्रेणियों को परिभाषित करने, और सीरीज़ डेटा भरने का तरीका  
- प्रत्येक फ़नल स्लाइस को सॉलिड फ़िल या ब्रांड‑विशिष्ट रंगों से स्टाइल करने का तरीका  
- प्रस्तुति को PPTX फ़ाइल के रूप में सहेजने या स्लाइड को इमेज के रूप में निर्यात करने का तरीका  

## त्वरित उत्तर
- **जावा डेटा विज़ुअलाइज़ेशन के लिए मुख्य लाइब्रेरी कौन सी है?** Aspose.Slides for Java.  
- **PowerPoint में फ़नल चार्ट कैसे बनाते हैं?** लक्ष्य स्लाइड पर `slide.addChart(ChartType.Funnel, …)` कॉल करें।  
- **कौन सा API चार्ट का डेटा स्रोत सेट करता है?** `IChartDataWorkbook` को `chart.getChartData()` के साथ उपयोग करें।  
- **क्या आप प्रत्येक फ़नल खंड के रंग को अनुकूलित कर सकते हैं?** हाँ—`FillFormat.setFillType(FillType.Solid)` सेट करें और `java.awt.Color` असाइन करें।  
- **उत्पादन उपयोग के लिए लाइसेंस की आवश्यकता है क्या?** व्यावसायिक तैनाती के लिए खरीदा गया Aspose.Slides लाइसेंस आवश्यक है।  

## जावा डेटा विज़ुअलाइज़ेशन क्या है?
जावा डेटा विज़ुअलाइज़ेशन वह अभ्यास है जिसमें कच्चे डेटा को सीधे जावा एप्लिकेशन से चार्ट, ग्राफ़ या इंटरैक्टिव ग्राफ़िक्स में परिवर्तित किया जाता है। Aspose.Slides for Java एक प्रमुख लाइब्रेरी है जो डेवलपर्स को 100 से अधिक चार्ट प्रकार—फ़नल चार्ट सहित—बिना मैन्युअली PowerPoint लॉन्च किए उत्पन्न करने की सुविधा देती है, 500 स्लाइड तक की प्रस्तुतियों का समर्थन करती है जबकि मेमोरी उपयोग कम रखती है।

## PowerPoint में फ़नल चार्ट क्यों उपयोग करें?
फ़नल चार्ट क्रमिक चरणों में ड्रॉप‑ऑफ़ दरों को तुरंत उजागर करते हैं, जिससे वे बिक्री पाइपलाइन, रूपांतरण विश्लेषण, या प्रक्रिया दक्षता समीक्षाओं के लिए आदर्श बनते हैं। Aspose.Slides आपको लेआउट, खंड रंग, और डेटा लेबल पर पिक्सेल‑परफेक्ट नियंत्रण देता है, ताकि आप ब्रांड स्थिरता बनाए रख सकें और PowerPoint UI में चार्ट संपादित करने के मैन्युअल प्रयास से बच सकें।

## पूर्वापेक्षाएँ (H2)

### आवश्यक लाइब्रेरी, संस्करण, और निर्भरताएँ
Aspose.Slides for Java को अपने प्रोजेक्ट में लागू करने के लिए, उपयुक्त Maven या Gradle कोऑर्डिनेट्स शामिल करें। यह लाइब्रेरी Java 8‑21 के साथ काम करती है और कोई बाहरी नेटिव निर्भरताएँ नहीं चाहिए।

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

आप JAR को सीधे [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से भी डाउनलोड कर सकते हैं।

### पर्यावरण सेटअप आवश्यकताएँ
सुनिश्चित करें कि आपके पास JDK 8 या उससे नया स्थापित है और आपका `JAVA_HOME` सही JDK डायरेक्टरी की ओर इशारा करता है। Aspose.Slides किसी भी OS पर चलता है जो JDK को सपोर्ट करता है, जिसमें Windows, macOS, और Linux शामिल हैं।

### ज्ञान पूर्वापेक्षाएँ
जावा सिंटैक्स, ऑब्जेक्ट‑ओरिएंटेड प्रोग्रामिंग, और प्रस्तुति फ़ाइल की अवधारणा की मूलभूत परिचितता मददगार होगी, लेकिन कोड स्निपेट्स सभी अनुभव स्तर के डेवलपर्स के लिए पूरी तरह समझाए गए हैं।

## Aspose.Slides for Java सेटअप करना (H2)

1. **निर्भरता जोड़ें** – ऊपर दिए गए Maven या Gradle स्निपेट का उपयोग करें।  
2. **लाइसेंस प्राप्त करें** –  
   - **फ़्री ट्रायल** – मूल्यांकन के लिए [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/) से एक अस्थायी लाइसेंस डाउनलोड करें।  
   - **पूर्ण लाइसेंस** – [खरीद पृष्ठ](https://purchase.aspose.com/buy) के माध्यम से प्रोडक्शन लाइसेंस खरीदें।  
3. **बेसिक इनिशियलाइज़ेशन** –  

`Presentation` Aspose.Slides की कोर क्लास है जो मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करती है। यह स्लाइड्स, शैप्स, और चार्ट ऑब्जेक्ट्स तक पहुँच प्रदान करती है।

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

ऊपर दिया गया कोड एक नया `Presentation` इंस्टेंस बनाता है, जो स्लाइड मैनिपुलेशन के लिए तैयार है, और `dispose()` के साथ संसाधनों को रिलीज़ करने की गारंटी देता है।

## कार्यान्वयन मार्गदर्शिका

हम एक पूर्ण फ़नल चार्ट बनाने के लिए आवश्यक प्रत्येक फीचर को चरण-दर-चरण देखेंगे, प्रत्येक कोड प्लेसहोल्डर से पहले संक्षिप्त व्याख्यात्मक टेक्स्ट जोड़ेंगे।

### फ़ीचर 1: प्रस्तुति बनाना (H2)

#### सारांश
`Presentation` क्लास का एक इंस्टेंस बनाकर शुरू करें। यह ऑब्जेक्ट सभी बाद के ऑपरेशन्स का प्रवेश बिंदु है।

`Presentation` Aspose.Slides का टॉप‑लेवल ऑब्जेक्ट है जो स्लाइड कलेक्शन और ग्लोबल डॉक्यूमेंट सेटिंग्स रखता है।

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

यह स्निपेट एक खाली प्रस्तुति खोलता है, जिसे आप बाद में `.pptx` फ़ाइल के रूप में सहेज सकते हैं।

### फ़ीचर 2: स्लाइड में फ़नल चार्ट जोड़ना (H2)

#### सारांश
पहली स्लाइड पर फ़नल चार्ट डालें, उसका आकार निर्धारित करें, और चार्ट प्रकार सेट करें।

`ChartType.Funnel` Aspose.Slides को बार या लाइन चार्ट के बजाय फ़नल‑स्टाइल विज़ुअलाइज़ेशन रेंडर करने के लिए बताता है।

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

`addChart` कॉल चार्ट शैप बनाता है, इसे `(50, 50)` पॉइंट्स पर स्थित करता है, और इसकी चौड़ाई `500` तथा ऊँचाई `400` सेट करता है।

### फ़ीचर 3: चार्ट डेटा साफ़ करना (H2)

#### सारांश
चार्ट को भरने से पहले, टेम्पलेट में मौजूद किसी भी प्लेसहोल्डर श्रेणियों या सीरीज़ को साफ़ करें।

`chart.getChartData().getCategories().clear()` सभी मौजूदा श्रेणी प्रविष्टियों को हटाता है, जबकि `chart.getChartData().getSeries().clear()` किसी भी पूर्व‑भरी हुई सीरीज़ को हटाता है।

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

यह एक साफ़ स्लेट सुनिश्चित करता है ताकि आपका कस्टम डेटा ठीक उसी तरह दिखाई दे जैसा आप चाहते हैं।

### फ़ीचर 4: चार्ट डेटा वर्कबुक सेटअप करना (H2)

#### सारांश
`IChartDataWorkbook` ऑब्जेक्ट चार्ट को चलाने वाले कच्चे मानों को संग्रहीत करता है। इसे इनिशियलाइज़ करने से आप डेटा को सीधे सेल्स में लिख सकते हैं।

`IChartDataWorkbook` एक हल्का इन‑मे्मोरी स्प्रेडशीट है जिसे Aspose.Slides चार्ट सीरीज़ और श्रेणियों को फीड करने के लिए उपयोग करता है।

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

कोड किसी भी मौजूदा सेल्स को साफ़ करता है, वर्कबुक को नई प्रविष्टियों के लिए तैयार करता है।

### फ़ीचर 5: चार्ट में श्रेणियाँ जोड़ना (H2)

#### सारांश
फ़नल के बाएँ पक्ष पर दिखने वाले टेक्स्ट लेबल निर्धारित करें—ये आपके प्रक्रिया के प्रत्येक चरण का प्रतिनिधित्व करते हैं।

`chart.getChartData().getCategories().add()` एक नया श्रेणी ऑब्जेक्ट बनाता है जो एक विशिष्ट वर्कबुक सेल से जुड़ा होता है।

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

यहाँ हम तीन चरण जोड़ते हैं: “Prospects”, “Qualified Leads”, और “Closed Deals”.

### फ़ीचर 6: चार्ट में डेटा सीरीज़ जोड़ना (H2)

#### सारांश
फ़नल को संख्यात्मक मानों से भरें और वैकल्पिक रूप से प्रत्येक स्लाइस को एक अनूठा रंग असाइन करें।

`IDataPoint` चार्ट सीरीज़ के भीतर एक एकल डेटा पॉइंट का प्रतिनिधित्व करता है।

`chart.getChartData().getSeries().add()` एक सीरीज़ बनाता है जो संख्यात्मक डेटा पॉइंट्स रखती है; प्रत्येक `IDataPoint` अपना फ़िल रंग प्राप्त कर सकता है।

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

लूप यह दर्शाता है कि प्रत्येक पॉइंट के लिए सॉलिड फ़िल कैसे सेट करें, चाहे ब्रांड‑विशिष्ट `java.awt.Color` कॉन्स्टेंट्स का उपयोग हो या दृश्य विविधता के लिए रैंडमली जेनरेटेड रंग।

## सामान्य उपयोग केस और टिप्स (H2)

- **सेल्स पाइपलाइन रिपोर्टिंग** – प्रत्येक चरण में कितने लीड्स प्रॉस्पेक्ट से क्लोज़्ड‑वॉन तक जाते हैं, दिखाएँ।  
- **प्रक्रिया दक्षता विश्लेषण** – निर्माण चरणों में सामग्री हानि या समय देरी को विज़ुअलाइज़ करें।  
- **मार्केटिंग फ़नल समीक्षा** – अभियानों या ट्रैफ़िक स्रोतों के बीच रूपांतरण दरों की तुलना करें।  

**प्रो टिप:** रैंडम रंगों के बजाय, अपनी कंपनी के ब्रांड पैलेट (जैसे, `new Color(0, 112, 192)`) का उपयोग करें ताकि प्रस्तुति अन्य मार्केटिंग एसेट्स के साथ सुसंगत रहे।

## अक्सर पूछे जाने वाले प्रश्न (H2)

**प्रश्न: फ़नल चार्ट की अभिविन्यास कैसे बदलें?**  
उत्तर: `IChart` ऑब्जेक्ट पर `ChartOrientation` प्रॉपर्टी को `ChartOrientation.Vertical` या `ChartOrientation.Horizontal` सेट करें।

**प्रश्न: चार्ट जोड़ने के बाद स्लाइड को इमेज के रूप में निर्यात कर सकता हूँ?**  
उत्तर: हाँ—`pres.getSlides().get_Item(0).getThumbnail(1, 1)` कॉल करें और प्राप्त `java.awt.image.BufferedImage` को PNG या JPEG फ़ाइल में लिखें।

**प्रश्न: यदि मुझे तीन से अधिक श्रेणियों की आवश्यकता हो तो?**  
उत्तर: बस `chart.getChartData().getCategories().add(...)` का उपयोग करके अतिरिक्त श्रेणियाँ जोड़ें और प्रत्येक नई श्रेणी के लिए मिलते-जुलते डेटा पॉइंट्स प्रदान करें।

**प्रश्न: क्या लेजेंड को छुपाने का कोई तरीका है?**  
उत्तर: `chart.getChartTitle().setVisible(false)` और `chart.getLegend().setVisible(false)` का उपयोग करके शीर्षक और लेजेंड दोनों को विज़ुअल से हटा दें।

**प्रश्न: विकास बिल्ड्स के लिए लाइसेंस की आवश्यकता है क्या?**  
उत्तर: मूल्यांकन के लिए एक अस्थायी लाइसेंस पर्याप्त है; उत्पादन तैनाती के लिए पूर्ण व्यावसायिक लाइसेंस आवश्यक है।

---

**अंतिम अपडेट:** 2026-09-02  
**परीक्षण किया गया:** Aspose.Slides for Java 25.4 (jdk16)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Slides for Java का उपयोग करके PowerPoint में चार्ट कैसे जोड़ें: चरण‑दर‑चरण गाइड](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java का उपयोग करके PowerPoint चार्ट डेटा कैसे संपादित करें: व्यापक गाइड](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Aspose.Slides for Java का उपयोग करके PowerPoint चार्ट में एनीमेशन जोड़ें – चरण‑दर‑चरण गाइड](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}