---
date: '2026-06-03'
description: Aspose.Slides for Java का उपयोग करके Excel में चार्ट निर्यात करना और
  Java में चार्ट बनाना सीखें। data visualization, business report slides, और workbook
  generation में निपुण बनें।
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Excel में चार्ट निर्यात करें और Aspose.Slides के साथ चार्ट बनाएं
url: /hi/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# एक्सेल में चार्ट निर्यात करें और Aspose.Slides के साथ चार्ट बनाएं

**Aspose.Slides for Java के साथ डेटा विज़ुअलाइज़ेशन तकनीकों में महारत हासिल करें**

आज के डेटा‑ड्रिवन परिदृश्य में, *एक्सेल में चार्ट निर्यात करना* प्रोग्रामेटिक रूप से एक ऐसी कौशल है जो कच्चे आंकड़ों को आकर्षक दृश्य कहानियों में बदल सकता है। चाहे आप एक बिज़नेस रिपोर्ट स्लाइड डेक बना रहे हों या एक इंटरैक्टिव एनालिटिक्स डैशबोर्ड, Aspose.Slides for Java आपको कोड से सीधे चार्ट उत्पन्न करने, अनुकूलित करने और निर्यात करने की शक्ति देता है। इस ट्यूटोरियल में आप सीखेंगे कि कैसे चार्ट ऑब्जेक्ट बनाएं, चार्ट डेटा को एक्सेल में निर्यात करें, और डेटा प्रबंधन को सहज बनाने के लिए चार्ट को बाहरी वर्कबुक से लिंक करें।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी चाहिए?** Aspose.Slides for Java (v25.4+).  
- **क्या मैं चार्ट डेटा को एक्सेल में निर्यात कर सकता हूँ?** हाँ – `readWorkbookStream()` का उपयोग करें और बाइट्स को *.xlsx* फ़ाइल में लिखें।  
- **कौन सा जावा संस्करण आवश्यक है?** JDK 16 या उससे ऊपर।  
- **क्या मुझे लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए स्थायी लाइसेंस आवश्यक है।  
- **कौन सा चार्ट प्रकार प्रदर्शित किया गया है?** एक Pie चार्ट, लेकिन वही तरीका Bar, Line और अन्य चार्ट प्रकारों के लिए भी काम करता है।

## Aspose.Slides for Java क्या है?
Aspose.Slides for Java एक शुद्ध‑Java API है जो डेवलपर्स को Microsoft Office के बिना PowerPoint प्रस्तुतियों को बनाने, संपादित करने और परिवर्तित करने की सुविधा देता है। यह स्लाइड मैनिपुलेशन, चार्ट जनरेशन और फ़ॉर्मेट कन्वर्ज़न के लिए क्लासेस का व्यापक सेट प्रदान करता है, जिससे स्वचालित रिपोर्टिंग समाधान संभव होते हैं। यह **50+ चार्ट प्रकार**, पूर्ण डेटा बाइंडिंग, और सीधे Excel निर्यात को सपोर्ट करता है, जिससे यह **डेटा विज़ुअलाइज़ेशन java** प्रोजेक्ट्स के लिए आदर्श बनता है।

## Aspose.Slides का उपयोग करके चार्ट बनाना और एक्सेल में निर्यात करना क्यों?
चार्ट को तेज़ और विश्वसनीय तरीके से एक्सेल में निर्यात करें। Aspose.Slides ऑफिस इंस्टॉलेशन की आवश्यकता को समाप्त करता है, **50‑से अधिक बिल्ट‑इन चार्ट स्टाइल्स** प्रदान करता है, और मानक सर्वर हार्डवेयर पर **300 MB तक की प्रस्तुतियों को 30 सेकंड से कम समय में प्रोसेस** करता है। आपको नेटिव Excel वर्कबुक जनरेशन भी मिलता है, जिससे डाउनस्ट्रीम विश्लेषक मैन्युअल कॉपी‑पेस्ट के बिना कच्चे आंकड़ों के साथ काम कर सकते हैं।

## पूर्वापेक्षाएँ
आगे बढ़ने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### आवश्यक लाइब्रेरी और संस्करण
- **Aspose.Slides for Java** संस्करण 25.4 या बाद का (JDK 16+ को सपोर्ट करता है)

### पर्यावरण सेटअप आवश्यकताएँ
- Java Development Kit (JDK) 16 या उससे ऊपर  
- IntelliJ IDEA, Eclipse या कोई भी पसंदीदा टेक्स्ट एडिटर जैसे IDE

### ज्ञान पूर्वापेक्षाएँ
- बुनियादी Java प्रोग्रामिंग कौशल  
- Maven या Gradle बिल्ड टूल्स की परिचितता

## Aspose.Slides for Java सेट अप करना
अपने पसंदीदा बिल्ड सिस्टम का उपयोग करके लाइब्रेरी को प्रोजेक्ट में जोड़ें।

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

वैकल्पिक रूप से, आप [नवीनतम संस्करण सीधे डाउनलोड कर सकते हैं](https://releases.aspose.com/slides/java/)।

### लाइसेंस प्राप्त करने के चरण
Aspose.Slides एक मुफ्त ट्रायल लाइसेंस प्रदान करता है ताकि आप इसकी पूरी क्षमताओं का अन्वेषण कर सकें। आप अस्थायी लाइसेंस के लिए आवेदन कर सकते हैं या विस्तारित उपयोग के लिए खरीद सकते हैं। नीचे दिए गए चरणों का पालन करें:

1. लाइसेंस प्राप्त करने के लिए [Aspose Purchase पेज](https://purchase.aspose.com/buy) पर जाएँ।  
2. मुफ्त ट्रायल के लिए, [Releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।  
3. अस्थायी लाइसेंस के लिए [यहाँ आवेदन करें](https://purchase.aspose.com/temporary-license/)।

लाइसेंस फ़ाइल मिलने के बाद, इसे अपने Java एप्लिकेशन में इनिशियलाइज़ करें:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## चरण‑दर‑चरण गाइड

### कैसे चार्ट बनाएं – प्रस्तुति लोड करें
चार्ट जोड़ने या संशोधित करने से पहले एक मौजूदा PowerPoint फ़ाइल लोड करें।  
`Presentation` क्लास मेमोरी में PowerPoint फ़ाइल का प्रतिनिधित्व करती है, जिससे स्लाइड, शैप और चार्ट ऑब्जेक्ट्स तक पहुँच मिलती है।  
`new Presentation("input.pptx")` से फ़ाइल लोड करें, फिर `presentation.getSlides().get_Item(0)` का उपयोग करके पहली स्लाइड पर काम करें। हमेशा `finally` ब्लॉक में `presentation.dispose()` कॉल करके नेटिव रिसोर्सेज़ को रिलीज़ करें।

### कैसे चार्ट बनाएं – स्लाइड में Pie चार्ट जोड़ें
एक Pie चार्ट डालें, जो अनुपातिक डेटा दिखाने के लिए उपयुक्त है।  
`IChart` इंटरफ़ेस चार्ट मैनिपुलेशन का मुख्य प्रवेश बिंदु है; `addChart` लक्ष्य स्लाइड पर नया चार्ट बनाता है। चार्ट प्रकार (`ChartType.Pie`), X/Y निर्देशांक, और चौड़ाई/ऊँचाई प्रदान करें। निर्माण के बाद, आप `ChartData` ऑब्जेक्ट के माध्यम से शीर्षक, लेजेंड और डेटा सीरीज़ को कस्टमाइज़ कर सकते हैं।

### कैसे चार्ट को एक्सेल में निर्यात करें – चार्ट डेटा निर्यात
चार्ट डेटा को एक्सेल में निर्यात करने से विश्लेषकों को संख्याओं के साथ काम करने की सुविधा मिलती है, जिससे गहरी अंतर्दृष्टि प्राप्त होती है।  
`readWorkbookStream()` चार्ट के अंतर्निहित Excel वर्कबुक को बाइट एरे के रूप में लौटाता है। `chart.getChartData().readWorkbookStream()` को कॉल करके वर्कबुक प्राप्त करें और इस एरे को मानक Java I/O का उपयोग करके `externalWorkbook1.xlsx` नाम की फ़ाइल में लिखें। परिणामी Excel फ़ाइल में वही डेटा होगा जो चार्ट ने उपयोग किया था, आगे के विश्लेषण के लिए तैयार।

### कैसे चार्ट बनाएं – डायनेमिक डेटा के लिए बाहरी वर्कबुक सेट करें
एक चार्ट को बाहरी वर्कबुक से लिंक करें ताकि स्लाइड को पुनः बनाये बिना लाइव डेटा अपडेट हो सके।  
`setExternalWorkbook()` चार्ट को डायनेमिक डेटा अपडेट के लिए बाहरी Excel फ़ाइल से बाइंड करता है। `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` का उपयोग करके चार्ट को बाहरी फ़ाइल से बाइंड करें। जब Excel वर्कबुक संपादित की जाती है, तो अगली बार प्रस्तुति खोलने पर चार्ट स्वचालित रूप से बदलाव दर्शाता है, जिससे डायनेमिक रिपोर्टिंग परिदृश्य संभव होते हैं।

## व्यावहारिक अनुप्रयोग
Aspose.Slides विभिन्न वास्तविक‑दुनिया परिदृश्यों के लिए बहुमुखी समाधान प्रदान करता है:

1. **बिज़नेस रिपोर्ट स्लाइड्स:** आपके डेटा पाइपलाइन से स्वचालित रूप से त्रैमासिक प्रदर्शन चार्ट जनरेट करें।  
2. **शैक्षणिक प्रस्तुतियाँ:** शोध डेटा को स्पष्ट विज़ुअलाइज़ेशन में बदलें बिना मैन्युअल चार्टिंग के।  
3. **वित्तीय विश्लेषण:** ऑडिटर्स को संख्याओं की पुष्टि करने के लिए चार्ट डेटा को एक्सेल में निर्यात करें, जिससे मैन्युअल त्रुटियों में कमी आए।  
4. **मार्केटिंग एनालिटिक्स:** अभियान मीट्रिक्स को विज़ुअलाइज़ करें और सहयोगी निर्णय‑निर्धारण के लिए हितधारकों के साथ संपादन योग्य वर्कबुक साझा करें।  
5. **स्वचालित डैशबोर्ड जनरेशन:** चार्ट‑क्रिएशन API को शेड्यूल्ड जॉब्स के साथ मिलाकर हर सुबह अद्यतन स्लाइड डेक बनाएं।

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **`FileNotFoundException`** – सुनिश्चित करें कि `dataDir` एक वैध फ़ोल्डर की ओर इशारा कर रहा है और आउटपुट पाथ लिखने योग्य है।  
- **Memory leaks** – हमेशा `finally` ब्लॉक में `presentation.dispose()` कॉल करके नेटिव रिसोर्सेज़ को मुक्त करें।  
- **Chart not appearing** – सुनिश्चित करें कि स्लाइड इंडेक्स (`get_Item(0)`) मौजूदा स्लाइड से मेल खाता है, और चार्ट के आयाम स्लाइड की सीमाओं के भीतर हैं।  
- **Excel export produces empty file** – `readWorkbookStream()` कॉल करने से पहले यह पुष्टि करें कि चार्ट में वास्तव में डेटा सीरीज़ मौजूद हैं।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं उसी कोड के साथ अलग चार्ट प्रकार (जैसे Bar, Line) उपयोग कर सकता हूँ?**  
उत्तर: हाँ। `ChartType.Pie` को किसी भी अन्य `ChartType` enum मान जैसे `ChartType.Bar` या `ChartType.Line` से बदलें।

**प्रश्न: क्या चार्ट बन जाने के बाद बाहरी वर्कबुक को अपडेट किया जा सकता है?**  
उत्तर: बिल्कुल। Excel फ़ाइल को सीधे संशोधित करें; लिंक किया गया चार्ट अगली बार प्रस्तुति खोलने पर बदलाव दर्शाएगा।

**प्रश्न: क्या एक्सेल निर्यात सुविधा के लिए अलग लाइसेंस चाहिए?**  
उत्तर: नहीं। एक्सेल निर्यात क्षमता मानक Aspose.Slides for Java लाइसेंस में शामिल है।

**प्रश्न: कौन से जावा संस्करण समर्थित हैं?**  
उत्तर: Aspose.Slides for Java JDK 16 और उससे नए संस्करणों को सपोर्ट करता है; पुराने संस्करण काम कर सकते हैं लेकिन आधिकारिक रूप से परीक्षण नहीं किए गए हैं।

**प्रश्न: मैं जनरेटेड Excel वर्कबुक को PPTX फ़ाइल के अंदर कैसे एम्बेड कर सकता हूँ?**  
उत्तर: `chart.getChartData().setExternalWorkbook(null)` का उपयोग करके वर्कबुक एम्बेड करें, या डायनेमिक अपडेट के लिए बाहरी लिंक रखें।

---

**अंतिम अपडेट:** 2026-06-03  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**लेखक:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Recover Workbook Data from PowerPoint Charts Using Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [How to Update PowerPoint Chart Data Range Using Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}