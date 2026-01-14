---
date: '2026-01-14'
description: Aspose.Slides for Java का उपयोग करके चार्ट को Excel में निर्यात करना
  और प्रस्तुतियों में पाई चार्ट स्लाइड जोड़ना सीखें। कोड के साथ चरण‑दर‑चरण मार्गदर्शिका।
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Aspose.Slides Java के साथ चार्ट को Excel में निर्यात करें
url: /hi/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Export Chart to Excel Using Aspose.Slides for Java

**Aspose.Slides for Java के साथ डेटा विज़ुअलाइज़ेशन तकनीकों में महारत हासिल करें**

आज के डेटा‑ड्रिवेन परिदृश्य में, अपने Java एप्लिकेशन से **export chart to excel** सीधे करने की क्षमता स्थिर PowerPoint विज़ुअल्स को पुन: उपयोग योग्य, विश्लेषण योग्य डेटा सेट में बदल सकती है। चाहे आपको रिपोर्ट बनानी हो, एनालिटिक्स पाइपलाइन को फ़ीड करना हो, या बस बिज़नेस यूज़र्स को Excel में चार्ट डेटा एडिट करने देना हो, Aspose.Slides इसे सरल बनाता है। यह ट्यूटोरियल आपको एक चार्ट बनाने, पाई चार्ट स्लाइड जोड़ने, और उस चार्ट डेटा को Excel वर्कबुक में एक्सपोर्ट करने की प्रक्रिया दिखाता है।

**आप क्या सीखेंगे:**
- प्रेजेंटेशन फ़ाइलों को आसानी से लोड और मैनीपुलेट करना
- **Add pie chart slide** और अन्य चार्ट प्रकारों को स्लाइड्स में जोड़ना
- **Export chart to excel** (चार्ट से Excel जेनरेट करना) के लिए डाउनस्ट्रीम एनालिसिस
- एक एक्सटर्नल वर्कबुक पाथ सेट करके **embed chart in presentation** और डेटा को सिंक्रनाइज़ रखना

चलिए शुरू करते हैं!

## Quick Answers
- **What is the primary purpose?** PowerPoint स्लाइड से Excel फ़ाइल में चार्ट डेटा एक्सपोर्ट करना।  
- **Which library version is required?** Aspose.Slides for Java 25.4 या बाद का संस्करण।  
- **Do I need a license?** मूल्यांकन के लिए फ्री ट्रायल काम करता है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **Can I add a pie chart slide?** हाँ – ट्यूटोरियल में दिखाया गया है कि कैसे Pie chart जोड़ें।  
- **Is Java 16 minimum?** हाँ, JDK 16 या उससे ऊपर की सलाह दी जाती है।

## How to export chart to excel using Aspose.Slides?
चार्ट डेटा को Excel में एक्सपोर्ट करना इतना सरल है जितना कि प्रेजेंटेशन लोड करना, एक चार्ट बनाना, और फिर चार्ट की वर्कबुक स्ट्रीम को फ़ाइल में लिखना। नीचे दिए गए चरण पूरे प्रोसेस को कवर करते हैं, प्रोजेक्ट सेटअप से लेकर अंतिम वेरिफिकेशन तक।

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित तैयार हैं:

### Required Libraries and Versions
- **Aspose.Slides for Java** संस्करण 25.4 या बाद का

### Environment Setup Requirements
- Java Development Kit (JDK) 16 या उससे ऊपर
- IntelliJ IDEA या Eclipse जैसे कोड एडिटर या IDE

### Knowledge Prerequisites
- बेसिक Java प्रोग्रामिंग स्किल्स
- Maven या Gradle बिल्ड सिस्टम की परिचितता

## Setting Up Aspose.Slides for Java
Aspose.Slides का उपयोग शुरू करने के लिए इसे Maven या Gradle के माध्यम से अपने प्रोजेक्ट में शामिल करें।

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

वैकल्पिक रूप से, आप सीधे [latest version को डाउनलोड कर सकते हैं](https://releases.aspose.com/slides/java/)।

### License Acquisition Steps
Aspose.Slides अपनी पूरी क्षमताओं को एक्सप्लोर करने के लिए एक फ्री ट्रायल लाइसेंस प्रदान करता है। आप एक टेम्पररी लाइसेंस के लिए अप्लाई कर सकते हैं या विस्तारित उपयोग के लिए खरीद सकते हैं। नीचे दिए गए चरणों का पालन करें:
1. अपना लाइसेंस प्राप्त करने के लिए [Aspose Purchase page](https://purchase.aspose.com/buy) पर जाएँ।  
2. फ्री ट्रायल के लिए, [Releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।  
3. टेम्पररी लाइसेंस के लिए [here](https://purchase.aspose.com/temporary-license/) अप्लाई करें।

लाइसेंस फ़ाइल मिलने के बाद, इसे अपने Java एप्लिकेशन में इनिशियलाइज़ करें:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementation Guide

### Feature 1: Load Presentation
प्रेजेंटेशन लोड करना किसी भी मैनीपुलेशन टास्क की पहली स्टेप है।

#### Overview
यह फीचर दिखाता है कि Aspose.Slides for Java का उपयोग करके मौजूदा PowerPoint फ़ाइल को कैसे लोड किया जाए।

#### Step‑by‑Step Implementation
**Load Presentation**
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
**Explanation:**  
- `Presentation` को आपके `.pptx` फ़ाइल पाथ के साथ इनिशियलाइज़ किया गया है।  
- नेटीव रिसोर्सेज़ को फ्री करने के लिए हमेशा `Presentation` ऑब्जेक्ट को डिस्पोज़ करें।

### Feature 2: Add Pie Chart Slide
चार्ट जोड़ने से डेटा प्रस्तुति में काफी सुधार हो सकता है, और कई डेवलपर्स पूछते हैं **how to add chart slide** in Java।

#### Overview
यह फीचर दिखाता है कि कैसे **pie chart slide** (क्लासिक “add pie chart slide” परिदृश्य) को प्रेजेंटेशन की पहली स्लाइड में जोड़ा जाए।

#### Step‑by‑Step Implementation
**Add Pie Chart**
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
**Explanation:**  
- `addChart` एक Pie chart इंसर्ट करता है।  
- पैरामीटर्स चार्ट टाइप और स्लाइड पर उसकी पोज़िशन/साइज़ को परिभाषित करते हैं।

### Feature 3: Generate Excel from Chart
चार्ट डेटा को एक्सपोर्ट करने से आप **generate excel from chart** करके गहरी एनालिसिस कर सकते हैं।

#### Overview
यह फीचर प्रेजेंटेशन से चार्ट डेटा को एक एक्सटर्नल Excel वर्कबुक में एक्सपोर्ट करने को दर्शाता है।

#### Step‑by‑Step Implementation
**Export Data**
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
**Explanation:**  
- `readWorkbookStream` चार्ट की वर्कबुक डेटा को एक्सट्रैक्ट करता है।  
- बाइट एरे को `FileOutputStream` का उपयोग करके `.xlsx` फ़ाइल में लिखा जाता है।

### Feature 4: Embed Chart in Presentation with External Workbook
एक चार्ट को एक्सटर्नल वर्कबुक से लिंक करने से आप **embed chart in presentation** कर सकते हैं और डेटा को सिंक्रनाइज़ रख सकते हैं।

#### Overview
यह फीचर दिखाता है कि कैसे एक एक्सटर्नल वर्कबुक पाथ सेट किया जाए ताकि चार्ट सीधे Excel फ़ाइल से पढ़/लिख सके।

#### Step‑by‑Step Implementation
**Set External Workbook Path**
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
**Explanation:**  
- `setExternalWorkbook` चार्ट को एक Excel फ़ाइल से लिंक करता है, जिससे स्लाइड को रीबिल्ड किए बिना डायनामिक अपडेट संभव होते हैं।

## Practical Applications
Aspose.Slides विभिन्न परिदृश्यों के लिए बहुमुखी समाधान प्रदान करता है:

1. **Business Reports:** Java एप्लिकेशन से सीधे चार्ट के साथ विस्तृत रिपोर्ट बनाएं।  
2. **Academic Presentations:** इंटरैक्टिव पाई चार्ट स्लाइड्स के साथ लेक्चर को बेहतर बनाएं।  
3. **Financial Analysis:** **Export chart to excel** करके गहन वित्तीय मॉडलिंग करें।  
4. **Marketing Analytics:** कैंपेन परफ़ॉर्मेंस को विज़ुअलाइज़ करें और **generate excel from chart** करके एनालिटिक्स टीम को प्रदान करें।

## Frequently Asked Questions

**Q: Can I use this approach with other chart types (e.g., Bar, Line)?**  
A: बिल्कुल। `ChartType.Pie` को किसी भी अन्य `ChartType` enum वैल्यू से बदल दें।

**Q: Do I need a separate Excel library to read the exported file?**  
A: नहीं। एक्सपोर्ट किया गया `.xlsx` फ़ाइल एक स्टैंडर्ड Excel वर्कबुक है जिसे किसी भी स्प्रेडशीट एप्लिकेशन से खोला जा सकता है।

**Q: How does the external workbook affect slide size?**  
A: एक्सटर्नल वर्कबुक को लिंक करने से PPTX फ़ाइल साइज में उल्लेखनीय वृद्धि नहीं होती; चार्ट रनटाइम पर वर्कबुक को रेफ़र करता है।

**Q: Is it possible to update the Excel data and have the slide reflect changes automatically?**  
A: हाँ। `setExternalWorkbook` कॉल करने के बाद वर्कबुक में किए गए कोई भी बदलाव अगली बार प्रेजेंटेशन खोलने पर स्लाइड में परिलक्षित होंगे।

**Q: What if I need to export multiple charts from the same presentation?**  
A: प्रत्येक स्लाइड के चार्ट कलेक्शन पर इटरेट करें, प्रत्येक के लिए `readWorkbookStream()` कॉल करें, और अलग-अलग वर्कबुक फ़ाइलों में लिखें।

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides 25.4 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}