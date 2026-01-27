---
date: '2026-01-11'
description: Aspose Slides for Java का उपयोग कैसे करें, चार्ट में इमेज मार्कर जोड़ें,
  और कस्टम चार्ट विज़ुअल्स के लिए Aspose Slides Maven डिपेंडेंसी को कॉन्फ़िगर करना
  सीखें।
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Aspose Slides Java का उपयोग कैसे करें - चार्ट में इमेज मार्कर जोड़ें'
url: /hi/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Java का उपयोग कैसे करें: चार्ट में इमेज मार्कर जोड़ें

## परिचय
दृश्यात्मक रूप से आकर्षक प्रस्तुतियों का निर्माण प्रभावी संचार की कुंजी है, और चार्ट जटिल डेटा को संक्षिप्त रूप से प्रस्तुत करने का एक शक्तिशाली उपकरण है। जब आप सोचते हैं **how to use Aspose** कि अपने चार्ट को कैसे अलग दिखाया जाए, तो कस्टम इमेज मार्कर ही उत्तर हैं। मानक मार्कर सामान्य दिख सकते हैं, लेकिन Aspose.Slides for Java के साथ आप उन्हें किसी भी चित्र से बदल सकते हैं—जिससे प्रत्येक डेटा पॉइंट तुरंत पहचानने योग्य बन जाता है।

इस ट्यूटोरियल में, हम लाइन चार्ट में इमेज मार्कर जोड़ने की पूरी प्रक्रिया को चरण‑दर‑चरण देखेंगे, **Aspose Slides Maven dependency** सेटअप करने से लेकर इमेज लोड करने और उन्हें डेटा पॉइंट्स पर लागू करने तक। अंत तक आप **how to add markers** में सहज हो जाएंगे, **add images to chart** सीरीज़ कैसे जोड़ें, और आपके पास एक तैयार‑चलाने‑योग्य कोड नमूना होगा।

**आप क्या सीखेंगे**
- Aspose.Slides for Java को सेटअप करना (Maven/Gradle सहित)
- एक बेसिक प्रेजेंटेशन और चार्ट बनाना
- चार्ट डेटा पॉइंट्स में इमेज मार्कर जोड़ना
- बेहतर विज़ुअलाइज़ेशन के लिए मार्कर आकार और शैली को कॉन्फ़िगर करना

क्या आप अपने चार्ट को बेहतर बनाना चाहते हैं? शुरू करने से पहले चलिए आवश्यकताओं में डुबकी लगाते हैं!

### त्वरित उत्तर
- **What is the primary purpose?** चार्ट डेटा पॉइंट्स में कस्टम इमेज मार्कर जोड़ना।  
- **Which library is required?** Aspose.Slides for Java (Maven/Gradle)।  
- **Do I need a license?** मूल्यांकन के लिए एक टेम्पररी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **Which Java version is supported?** JDK 16 या उससे ऊपर।  
- **Can I use any image format?** हाँ—PNG, JPEG, BMP आदि, जब तक फ़ाइल उपलब्ध हो।

### आवश्यकताएँ
इस ट्यूटोरियल को फॉलो करने के लिए, आपको चाहिए:
1. **Aspose.Slides for Java Library** – Maven, Gradle, या सीधे डाउनलोड के माध्यम से प्राप्त करें।  
2. **Java Development Environment** – JDK 16 या नया स्थापित हो।  
3. **Basic Java Programming Knowledge** – Java सिंटैक्स और अवधारणाओं की परिचितता मददगार होगी।

## Aspose Slides Maven Dependency क्या है?
Maven डिपेंडेंसी आपके Java संस्करण के लिए सही बाइनरीज़ को खींचती है। इसे अपने `pom.xml` में जोड़ने से लाइब्रेरी कंपाइल‑टाइम और रन‑टाइम दोनों पर उपलब्ध रहती है।

### Maven इंस्टॉलेशन
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle इंस्टॉलेशन
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### डायरेक्ट डाउनलोड
वैकल्पिक रूप से, नवीनतम रिलीज़ डाउनलोड करें [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से।

#### लाइसेंस प्राप्त करने के चरण
- **Free Trial** – फीचर एक्सप्लोर करने के लिए टेम्पररी लाइसेंस से शुरू करें।  
- **Temporary License** – परीक्षण के दौरान उन्नत क्षमताओं को अनलॉक करें।  
- **Purchase** – व्यावसायिक प्रोजेक्ट्स के लिए पूर्ण लाइसेंस प्राप्त करें।

## बेसिक इनिशियलाइज़ेशन और सेटअप
First, create a `Presentation` object. This object represents the entire PowerPoint file and will hold our chart.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## इम्प्लीमेंटेशन गाइड
नीचे चार्ट में इमेज मार्कर जोड़ने की चरण‑दर‑चरण प्रक्रिया दी गई है। प्रत्येक कोड ब्लॉक के साथ एक व्याख्या है ताकि आप समझ सकें **क्यों** प्रत्येक लाइन महत्वपूर्ण है।

### चरण 1: चार्ट के साथ नई प्रेजेंटेशन बनाएं
We add a line chart with default markers to the first slide.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### चरण 2: चार्ट डेटा तक पहुँचें और कॉन्फ़िगर करें
We clear any default series and add our own series, preparing the worksheet for custom data points.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### चरण 3: चार्ट डेटा पॉइंट्स में इमेज मार्कर जोड़ें  
Here we demonstrate **how to add markers** using pictures. Replace the placeholder paths with the actual location of your images.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### चरण 4: मार्कर आकार कॉन्फ़िगर करें और प्रेजेंटेशन सेव करें  
We adjust the marker style for better visibility and write the final PPTX file.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **FileNotFoundException** – सुनिश्चित करें कि इमेज पाथ (`YOUR_DOCUMENT_DIRECTORY/...`) सही हैं और फ़ाइलें मौजूद हैं।  
- **LicenseException** – उत्पादन में कोई भी API कॉल करने से पहले वैध Aspose लाइसेंस सेट किया हुआ हो, यह सुनिश्चित करें।  
- **Marker Not Visible** – `setMarkerSize` बढ़ाएँ या स्पष्ट डिस्प्ले के लिए उच्च‑रिज़ॉल्यूशन इमेज का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं मार्कर के लिए JPEG की बजाय PNG इमेज इस्तेमाल कर सकता हूँ?**  
A: हाँ, Aspose.Slides द्वारा समर्थित कोई भी इमेज फॉर्मेट (PNG, JPEG, BMP, GIF) मार्कर के रूप में काम करता है।

**Q: क्या Maven/Gradle पैकेजों के लिए मुझे लाइसेंस चाहिए?**  
A: विकास और परीक्षण के लिए टेम्पररी लाइसेंस पर्याप्त है; व्यावसायिक वितरण के लिए पूर्ण लाइसेंस आवश्यक है।

**Q: क्या एक ही सीरीज़ में प्रत्येक डेटा पॉइंट के लिए अलग-अलग इमेज जोड़ना संभव है?**  
A: बिल्कुल। `AddImageMarkers` उदाहरण में हम दो चित्रों के बीच बदलते हैं, लेकिन आप प्रत्येक पॉइंट के लिए एक अनोखी इमेज लोड कर सकते हैं।

**Q: `aspose slides maven dependency` प्रोजेक्ट साइज को कैसे प्रभावित करता है?**  
A: Maven पैकेज केवल चयनित JDK संस्करण के लिए आवश्यक बाइनरीज़ शामिल करता है, जिससे आकार उचित रहता है। यदि साइज चिंता का विषय है तो आप **no‑dependencies** संस्करण भी उपयोग कर सकते हैं।

**Q: कौन से Java संस्करण समर्थित हैं?**  
A: Aspose.Slides for Java JDK 8 से लेकर JDK 21 तक समर्थन देता है। उदाहरण में JDK 16 उपयोग किया गया है, लेकिन आप वर्गीकरण (classifier) को उसी अनुसार बदल सकते हैं।

## निष्कर्ष
इस गाइड को फॉलो करके आप अब जानते हैं **how to use Aspose** ताकि कस्टम इमेज मार्कर के साथ चार्ट को समृद्ध किया जा सके, **Aspose Slides Maven dependency** को कैसे कॉन्फ़िगर किया जाए, और **add images to chart** सीरीज़ को कैसे जोड़ा जाए ताकि एक परिष्कृत, पेशेवर लुक मिले। विभिन्न आइकन, आकार और चार्ट प्रकारों के साथ प्रयोग करें ताकि प्रस्तुतियाँ वास्तव में अलग दिखें।

---

**अंतिम अपडेट:** 2026-01-11  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (jdk16)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}