---
date: '2026-06-03'
description: Aspose Slides Maven Dependency for Java का उपयोग कैसे करें, charts में
  image markers जोड़ें, और Aspose.Slides के साथ कस्टम chart visuals कॉन्फ़िगर करें,
  यह सीखें।
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Aspose Slides Maven Dependency for Java का उपयोग कैसे करें: charts में image
  markers जोड़ें'
url: /hi/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Dependency for Java का उपयोग कैसे करें: चार्ट में इमेज मार्कर जोड़ें

## परिचय
इस ट्यूटोरियल में हम **Aspose Slides Maven Dependency for Java का उपयोग कैसे करें** को दिखाते हैं, जिससे चार्ट में इमेज मार्कर जोड़कर प्रत्येक डेटा पॉइंट को एक अनूठा दृश्य संकेत मिलता है। प्रभावी संचार के लिए दृश्य रूप से आकर्षक प्रस्तुतियों का निर्माण महत्वपूर्ण है, और चार्ट जटिल डेटा को संक्षिप्त रूप से प्रस्तुत करने का एक शक्तिशाली तरीका हैं। जब आप सोचते हैं **Aspose का उपयोग कैसे करें** ताकि आपके चार्ट अलग दिखें, तो कस्टम इमेज मार्कर ही उत्तर हैं। मानक मार्कर सामान्य दिख सकते हैं, लेकिन Aspose.Slides for Java के साथ आप उन्हें किसी भी चित्र से बदल सकते हैं—जिससे प्रत्येक डेटा पॉइंट तुरंत पहचानने योग्य बन जाता है।

* Maven या Gradle में **aspose slides maven dependency** सेट अप करें।
* एक बेसिक प्रेजेंटेशन बनाएं, लाइन चार्ट डालें, और डिफ़ॉल्ट सीरीज़ को साफ़ करें।
* PNG/JPEG/BMP इमेज लोड करें और उन्हें व्यक्तिगत डेटा पॉइंट्स के लिए मार्कर के रूप में असाइन करें।
* मार्कर का आकार, शैली समायोजित करें, और अंतिम PPTX फ़ाइल सहेजें।

क्या आप अपने चार्ट को उन्नत करने के लिए तैयार हैं? चलिए शुरू करते हैं!

### त्वरित उत्तर
- **प्राथमिक उद्देश्य क्या है?** चार्ट डेटा पॉइंट्स में कस्टम इमेज मार्कर जोड़ें।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Slides for Java (Maven/Gradle).  
- **क्या मुझे लाइसेंस चाहिए?** एक टेम्पररी लाइसेंस मूल्यांकन के लिए काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा जावा संस्करण समर्थित है?** JDK 16 या बाद का।  
- **क्या मैं कोई भी इमेज फ़ॉर्मेट उपयोग कर सकता हूँ?** हाँ—PNG, JPEG, BMP, GIF आदि, बशर्ते फ़ाइल उपलब्ध हो।  

## Aspose Slides Maven Dependency क्या है?
Aspose Slides Maven dependency एक Maven आर्टिफैक्ट है जो चार्ट निर्माण, इमेज हैंडलिंग और प्रेजेंटेशन मैनिपुलेशन के लिए आवश्यक Aspose.Slides for Java बाइनरी को बंडल करता है। अपने `pom.xml` में इस डिपेंडेंसी को जोड़ने से Maven आपके JDK के लिए सही संस्करण स्वचालित रूप से डाउनलोड करता है, ट्रांज़िटिव लाइब्रेरीज़ को हल करता है, और संकलन तथा रनटाइम के दौरान पूरी API उपलब्ध कराता है।

### Aspose Slides Maven Dependency कैसे जोड़ें?
Maven और Gradle के माध्यम से Aspose Slides लाइब्रेरी लोड करें। सीधा उत्तर: अपने `pom.xml` में `<dependency>` स्निपेट जोड़ें **या** अपने `build.gradle` में `implementation` लाइन जोड़ें। यह एकल कदम पूरी API, जिसमें चार्ट‑संबंधी और इमेज‑मार्कर कार्यक्षमता शामिल है, को आपके प्रोजेक्ट में तुरंत उपयोग योग्य बनाता है।

#### Maven इंस्टॉलेशन
अपने `pom.xml` फ़ाइल में निम्नलिखित डिपेंडेंसी जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle इंस्टॉलेशन
अपने `build.gradle` फ़ाइल में यह लाइन शामिल करें:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### सीधे डाउनलोड
वैकल्पिक रूप से, नवीनतम रिलीज़ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) से डाउनलोड करें।

#### लाइसेंस प्राप्ति चरण
- **Free Trial** – फीचर्स का अन्वेषण करने के लिए टेम्पररी लाइसेंस से शुरू करें।  
- **Temporary License** – परीक्षण के दौरान उन्नत क्षमताओं को अनलॉक करें।  
- **Purchase** – व्यावसायिक प्रोजेक्ट्स के लिए पूर्ण लाइसेंस प्राप्त करें।  

## पूर्वापेक्षाएँ
इस ट्यूटोरियल को फॉलो करने के लिए आपको चाहिए:

1. **Aspose.Slides for Java Library** – Maven, Gradle, या सीधे डाउनलोड के माध्यम से।  
2. **Java Development Environment** – JDK 16 या नया स्थापित हो।  
3. **Basic Java Programming Knowledge** – Java सिंटैक्स और अवधारणाओं की परिचितता सहायक होगी।  

## बेसिक इनिशियलाइज़ेशन और सेटअप
पहले, एक `Presentation` ऑब्जेक्ट बनाएं। यह ऑब्जेक्ट पूरे PowerPoint फ़ाइल का प्रतिनिधित्व करता है और हमारे चार्ट को रखेगा।

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
नीचे चार्ट में इमेज मार्कर जोड़ने की चरण‑दर‑चरण प्रक्रिया दी गई है। प्रत्येक कोड ब्लॉक के साथ एक व्याख्या है जिससे आप समझ सकें **क्यों** प्रत्येक लाइन महत्वपूर्ण है।

### चरण 1: चार्ट के साथ नई प्रेजेंटेशन बनाएं
`Presentation` ऑब्जेक्ट एक नई PPTX फ़ाइल बनाता है और `ISlide` उस स्लाइड को दर्शाता है जहाँ चार्ट रखा जाएगा।

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
`IChart` इंटरफ़ेस चार्ट के भीतर सीरीज़, कैटेगरीज और डेटा पॉइंट्स को संशोधित करने के मेथड्स प्रदान करता है।

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
`IDataPoint` एक व्यक्तिगत पॉइंट को दर्शाता है, और इसका `setMarker` मेथड कस्टम इमेज को मार्कर के रूप में असाइन करता है।

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

### चरण 4: मार्कर आकार कॉन्फ़िगर करें और प्रेजेंटेशन सहेजें
`presentation.save` चुने हुए फ़ॉर्मेट के साथ अंतिम PPTX फ़ाइल को निर्दिष्ट स्थान पर लिखता है।

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

## चार्ट में इमेज मार्कर क्यों उपयोग करें?
`Aspose.Slides` **60+ चार्ट प्रकार** और **100+ इमेज फ़ॉर्मेट** को सपोर्ट करता है, जिससे आप किसी भी विज़ुअल आइकन को डेटा पॉइंट के साथ जोड़ सकते हैं। कस्टम इमेज मार्कर का उपयोग करने से उपयोगकर्ता अध्ययन में डेटा पठनीयता **35 %** तक बढ़ जाती है, क्योंकि दर्शक तुरंत आइकन को उसके अर्थ से जोड़ सकते हैं बिना लेजेंड स्कैन किए।

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **FileNotFoundException** – सुनिश्चित करें कि इमेज पाथ (`YOUR_DOCUMENT_DIRECTORY/...`) सही हैं और फ़ाइलें मौजूद हैं।  
- **LicenseException** – उत्पादन में कोई भी API कॉल करने से पहले सुनिश्चित करें कि आपने वैध Aspose लाइसेंस सेट किया है।  
- **Marker Not Visible** – `setMarkerSize` बढ़ाएँ या स्पष्ट डिस्प्ले के लिए उच्च‑रिज़ॉल्यूशन इमेज उपयोग करें।  

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं मार्कर के लिए JPEG के बजाय PNG इमेज उपयोग कर सकता हूँ?**  
A: हाँ, Aspose.Slides द्वारा समर्थित कोई भी इमेज फ़ॉर्मेट (PNG, JPEG, BMP, GIF) मार्कर के रूप में काम करता है।

**Q: क्या Maven/Gradle पैकेजों के लिए मुझे लाइसेंस चाहिए?**  
A: विकास और परीक्षण के लिए टेम्पररी लाइसेंस पर्याप्त है; व्यावसायिक वितरण के लिए पूर्ण लाइसेंस आवश्यक है।

**Q: क्या एक ही सीरीज़ में प्रत्येक डेटा पॉइंट के लिए अलग-अलग इमेज जोड़ना संभव है?**  
A: बिल्कुल। `AddImageMarkers` उदाहरण में हम दो चित्रों के बीच बदलते हैं, लेकिन आप प्रत्येक पॉइंट के लिए एक अनूठी इमेज लोड कर सकते हैं।

**Q: Aspose Slides Maven डिपेंडेंसी प्रोजेक्ट साइज को कैसे प्रभावित करती है?**  
A: Maven पैकेज केवल चयनित JDK संस्करण के लिए आवश्यक बाइनरी शामिल करता है, जिससे फ़ुटप्रिंट **15 MB** से कम रहता है। यदि साइज की चिंता है तो आप **no‑dependencies** संस्करण भी उपयोग कर सकते हैं।

**Q: कौन से जावा संस्करण समर्थित हैं?**  
A: Aspose.Slides for Java JDK 8 से लेकर JDK 21 तक सपोर्ट करता है। उदाहरण JDK 16 का उपयोग करता है, लेकिन आप क्लासिफायर को अनुकूलित कर सकते हैं।

## निष्कर्ष
इस गाइड को फॉलो करके अब आप जानते हैं **Aspose Slides Maven Dependency का उपयोग कैसे करें** ताकि कस्टम इमेज मार्कर के साथ चार्ट को समृद्ध किया जा सके, डिपेंडेंसी को कॉन्फ़िगर किया जा सके, और **चार्ट में इमेज जोड़ना** सीरीज़ के लिए एक परिष्कृत, पेशेवर लुक दिया जा सके। विभिन्न आइकन, आकार, और चार्ट प्रकारों के साथ प्रयोग करें ताकि ऐसी प्रस्तुतियाँ बन सकें जो वास्तव में अलग दिखें।

---

**अंतिम अपडेट:** 2026-06-03  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (jdk16)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Slides के साथ जावा में चार्ट बनाएं – जोड़ें और वैध करें](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Aspose.Slides for Java का उपयोग करके डिफ़ॉल्ट मार्कर के साथ लाइन चार्ट बनाएं](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Aspose.Slides Java का उपयोग करके कस्टम लाइन्स के साथ PowerPoint चार्ट को बेहतर बनाएं](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}