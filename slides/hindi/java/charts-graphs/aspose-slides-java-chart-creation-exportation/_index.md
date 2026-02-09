---
date: '2026-02-09'
description: Aspose.Slides for Java का उपयोग करके चार्ट बनाना और चार्ट को Excel में
  निर्यात करना सीखें। डेटा विज़ुअलाइज़ेशन, व्यापार रिपोर्ट स्लाइड्स और वर्कबुक जनरेशन
  में निपुण बनें।
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Aspose.Slides Java के साथ चार्ट कैसे बनाएं
url: /hi/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java का उपयोग करके चार्ट कैसे बनाएं

**Aspose.Slides for Java के साथ डेटा विज़ुअलाइज़ेशन तकनीकों में महारत हासिल करें**

आज के डेटा‑ड्रिवन परिदृश्य में, *how to create chart* प्रोग्रामेटिक रूप से बनाना एक कौशल है जो कच्चे आंकड़ों को आकर्षक दृश्य कहानियों में बदल सकता है। चाहे आप एक बिजनेस रिपोर्ट स्लाइड डेक बना रहे हों या एक इंटरैक्टिव एनालिटिक्स डैशबोर्ड, Aspose.Slides for Java आपको कोड से सीधे चार्ट जेनरेट, कस्टमाइज़ और एक्सपोर्ट करने की शक्ति देता है। इस ट्यूटोरियल में आप सीखेंगे कि चार्ट ऑब्जेक्ट्स कैसे बनाएं, चार्ट डेटा को Excel में एक्सपोर्ट करें, और डेटा प्रबंधन को सहज बनाने के लिए चार्ट को बाहरी वर्कबुक से लिंक करें।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Slides for Java (v25.4+).  
- **क्या मैं चार्ट डेटा को Excel में एक्सपोर्ट कर सकता हूँ?** हाँ – `readWorkbookStream()` का उपयोग करें और बाइट्स को *.xlsx* फ़ाइल में लिखें।  
- **कौनसा Java संस्करण आवश्यक है?** JDK 16 या उससे ऊपर।  
- **क्या मुझे लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक स्थायी लाइसेंस आवश्यक है।  
- **कौनसा चार्ट प्रकार दिखाया गया है?** एक Pie चार्ट, लेकिन वही तरीका Bar, Line और अन्य चार्ट प्रकारों के लिए भी काम करता है।

## Aspose.Slides for Java क्या है?
Aspose.Slides for Java एक शुद्ध‑Java API है जो डेवलपर्स को Microsoft Office के बिना PowerPoint प्रेजेंटेशन बनाने, संपादित करने और कनवर्ट करने देता है। यह चार्ट प्रकारों, डेटा बाइंडिंग और एक्सपोर्ट क्षमताओं की पूरी रेंज को सपोर्ट करता है, जिससे यह **data visualization java** प्रोजेक्ट्स के लिए आदर्श बनता है।

## Aspose.Slides का उपयोग करके चार्ट बनाने और उसे Excel में एक्सपोर्ट करने के कारण क्या हैं?
- **कोई Office इंस्टॉलेशन नहीं** – किसी भी सर्वर या क्लाउड वातावरण में काम करता है।  
- **समृद्ध चार्ट लाइब्रेरी** – दर्जन भर चार्ट प्रकार और पूर्ण स्टाइलिंग नियंत्रण।  
- **सीधा Excel एक्सपोर्ट** – डाउनस्ट्रीम विश्लेषण के लिए बाहरी वर्कबुक जेनरेट करें।  
- **परफॉर्मेंस‑उन्मुख** – कम मेमोरी उपयोग और बड़े डेक्स के लिए तेज प्रोसेसिंग।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### आवश्यक लाइब्रेरी और संस्करण
- **Aspose.Slides for Java** संस्करण 25.4 या बाद का

### पर्यावरण सेटअप आवश्यकताएँ
- Java Development Kit (JDK) 16 या उससे ऊपर  
- IntelliJ IDEA या Eclipse जैसे IDE (या कोई भी टेक्स्ट एडिटर जो आप पसंद करें)

### ज्ञान पूर्वापेक्षाएँ
- बुनियादी Java प्रोग्रामिंग कौशल  
- Maven या Gradle बिल्ड टूल्स की परिचितता

## Aspose.Slides for Java सेटअप करना
अपने पसंदीदा बिल्ड सिस्टम का उपयोग करके लाइब्रेरी को अपने प्रोजेक्ट में जोड़ें।

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

वैकल्पिक रूप से, आप सीधे [नवीनतम संस्करण डाउनलोड कर सकते हैं](https://releases.aspose.com/slides/java/)।

### लाइसेंस प्राप्त करने के चरण
Aspose.Slides अपनी पूरी क्षमताओं को आज़माने के लिए एक मुफ्त ट्रायल लाइसेंस प्रदान करता है। आप एक अस्थायी लाइसेंस के लिए आवेदन कर सकते हैं या विस्तारित उपयोग के लिए खरीद सकते हैं। इन चरणों का पालन करें:

1. लाइसेंस प्राप्त करने के लिए [Aspose Purchase पेज](https://purchase.aspose.com/buy) पर जाएँ।  
2. मुफ्त ट्रायल के लिए, [Releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।  
3. अस्थायी लाइसेंस के लिए [यहाँ](https://purchase.aspose.com/temporary-license/) आवेदन करें।

लाइसेंस फ़ाइल मिलने के बाद, इसे अपने Java एप्लिकेशन में इनिशियलाइज़ करें:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## स्टेप‑बाय‑स्टेप गाइड

### चार्ट कैसे बनाएं – प्रेजेंटेशन लोड करें
एक मौजूदा PowerPoint फ़ाइल लोड करना पहला कदम है, जिसके बाद आप चार्ट जोड़ या संशोधित कर सकते हैं।

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

**व्याख्या:**  
- `Presentation` PowerPoint फ़ाइल को दर्शाता है।  
- हमेशा `dispose()` को कॉल करें ताकि नेटिव रिसोर्सेज़ रिलीज़ हो सकें।

### चार्ट कैसे बनाएं – स्लाइड में Pie चार्ट जोड़ें
अब हम एक Pie चार्ट डालेंगे, जो अनुपातिक डेटा दिखाने के लिए उपयुक्त है।

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

**व्याख्या:**  
- `addChart` पहले स्लाइड पर चार्ट डालता है।  
- पैरामीटर चार्ट प्रकार, X/Y स्थिति और आकार को परिभाषित करते हैं।

### चार्ट को Excel में एक्सपोर्ट करें – चार्ट डेटा एक्सपोर्ट
चार्ट डेटा को एक्सपोर्ट करने से विश्लेषकों को Excel में संख्याओं के साथ काम करने की सुविधा मिलती है, जिससे गहरी अंतर्दृष्टि प्राप्त होती है।

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

**व्याख्या:**  
- `readWorkbookStream()` चार्ट के अंतर्निहित Excel वर्कबुक को बाइट एरे के रूप में निकालता है।  
- बाइट एरे को `externalWorkbook1.xlsx` में लिखा जाता है, जिससे आपको एक तैयार‑उपयोग Excel फ़ाइल मिलती है।

### चार्ट कैसे बनाएं – डायनेमिक डेटा के लिए बाहरी वर्कबुक सेट करें
चार्ट को बाहरी वर्कबुक से लिंक करने से आप केवल Excel फ़ाइल को संपादित करके चार्ट को अपडेट कर सकते हैं।

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

**व्याख्या:**  
- `setExternalWorkbook` चार्ट को निर्दिष्ट Excel फ़ाइल से बाइंड करता है, जिससे स्लाइड को फिर से बनाये बिना लाइव डेटा अपडेट संभव होते हैं।

## व्यावहारिक अनुप्रयोग
Aspose.Slides विभिन्न वास्तविक‑दुनिया परिदृश्यों के लिए बहुमुखी समाधान प्रदान करता है:

1. **बिजनेस रिपोर्ट स्लाइड्स:** अपने डेटा पाइपलाइन से स्वचालित रूप से त्रैमासिक प्रदर्शन चार्ट जेनरेट करें।  
2. **शैक्षणिक प्रस्तुतियाँ:** शोध डेटा को स्पष्ट विज़ुअलाइज़ेशन में बदलें बिना मैन्युअल चार्टिंग के।  
3. **वित्तीय विश्लेषण:** ऑडिटर्स को संख्याओं की पुष्टि करने के लिए चार्ट डेटा को Excel में एक्सपोर्ट करें।  
4. **मार्केटिंग एनालिटिक्स:** कैम्पेन मेट्रिक्स को विज़ुअलाइज़ करें और स्टेकहोल्डर्स के साथ एडिटेबल वर्कबुक साझा करें।

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **`FileNotFoundException`** – सुनिश्चित करें कि `dataDir` एक वैध फ़ोल्डर की ओर इशारा कर रहा है और आउटपुट पाथ लिखने योग्य है।  
- **मेमोरी लीक** – नेटिव रिसोर्सेज़ को मुक्त करने के लिए हमेशा `pres.dispose()` को `finally` ब्लॉक में कॉल करें।  
- **चार्ट नहीं दिख रहा है** – सुनिश्चित करें कि स्लाइड इंडेक्स (`get_Item(0)`) वास्तव में मौजूद स्लाइड से मेल खाता है।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं उसी कोड के साथ अलग चार्ट प्रकार (जैसे Bar, Line) का उपयोग कर सकता हूँ?**  
A: हाँ। `ChartType.Pie` को किसी भी अन्य `ChartType` enum वैल्यू जैसे `ChartType.Bar` या `ChartType.Line` से बदलें।

**Q: क्या चार्ट बन जाने के बाद बाहरी वर्कबुक को अपडेट करना संभव है?**  
A: बिल्कुल। Excel फ़ाइल को सीधे संशोधित करें; लिंक किया हुआ चार्ट अगली बार प्रेजेंटेशन खोलने पर बदलावों को दर्शाएगा।

**Q: क्या Excel एक्सपोर्ट फीचर के लिए मुझे अलग लाइसेंस चाहिए?**  
A: नहीं। Excel एक्सपोर्ट क्षमता मानक Aspose.Slides for Java लाइसेंस में शामिल है।

**Q: कौनसे Java संस्करण समर्थित हैं?**  
A: Aspose.Slides for Java JDK 16 और उसके बाद के संस्करणों को सपोर्ट करता है; पहले के संस्करण काम कर सकते हैं लेकिन आधिकारिक रूप से टेस्ट नहीं किए गए हैं।

**Q: जेनरेट किए गए Excel वर्कबुक को PPTX फ़ाइल के अंदर कैसे एम्बेड करूँ?**  
A: `chart.getChartData().setExternalWorkbook(null)` का उपयोग करके वर्कबुक एम्बेड करें, या डायनेमिक अपडेट के लिए बाहरी लिंक रखें।

**अंतिम अपडेट:** 2026-02-09  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}