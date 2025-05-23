---
"date": "2025-04-17"
"description": "कस्टम इमेज मार्कर जोड़कर Aspose.Slides for Java में अपने चार्ट को बेहतर बनाने का तरीका जानें। विज़ुअली अलग-अलग प्रेजेंटेशन के साथ जुड़ाव बढ़ाएँ।"
"title": "मास्टर Aspose.Slides Java&#58; चार्ट में छवि मार्कर जोड़ना"
"url": "/hi/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java में महारत हासिल करना: चार्ट में इमेज मार्कर जोड़ना

## परिचय
प्रभावी संचार के लिए आकर्षक प्रस्तुतिकरण बनाना महत्वपूर्ण है, और चार्ट जटिल डेटा को संक्षिप्त रूप से व्यक्त करने के लिए एक शक्तिशाली उपकरण हैं। मानक चार्ट मार्कर कभी-कभी आपके डेटा को अलग दिखाने में विफल हो सकते हैं। Aspose.Slides for Java के साथ, आप मार्कर के रूप में कस्टम इमेज जोड़कर अपने चार्ट को बेहतर बना सकते हैं, जिससे वे अधिक आकर्षक और जानकारीपूर्ण बन सकते हैं।

इस ट्यूटोरियल में, हम जावा में Aspose.Slides लाइब्रेरी का उपयोग करके अपने चार्ट में इमेज मार्कर को एकीकृत करने का तरीका जानेंगे। इन तकनीकों में महारत हासिल करके, आप ऐसे प्रेजेंटेशन बना पाएँगे जो अपने अनूठे विज़ुअल तत्वों के साथ ध्यान आकर्षित करेंगे।

**आप क्या सीखेंगे:**
- Java के लिए Aspose.Slides कैसे सेट करें
- एक बुनियादी प्रस्तुति और चार्ट बनाना
- चार्ट डेटा बिंदुओं में छवि मार्कर जोड़ना
- इष्टतम विज़ुअलाइज़ेशन के लिए मार्कर सेटिंग कॉन्फ़िगर करना

क्या आप अपने चार्ट को बेहतर बनाने के लिए तैयार हैं? शुरू करने से पहले आइए कुछ आवश्यक शर्तों पर नज़र डालें!

### आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए आपको निम्न की आवश्यकता होगी:
1. **Aspose.Slides for Java लाइब्रेरी**: इसे Maven या Gradle निर्भरताओं के माध्यम से प्राप्त करें या सीधे Aspose से डाउनलोड करके प्राप्त करें।
2. **जावा विकास पर्यावरण**: सुनिश्चित करें कि आपकी मशीन पर JDK 16 स्थापित है।
3. **बुनियादी जावा प्रोग्रामिंग ज्ञान**जावा सिंटैक्स और अवधारणाओं से परिचित होना लाभदायक होगा।

## Java के लिए Aspose.Slides सेट अप करना
कोड में गोता लगाने से पहले, आइए आवश्यक लाइब्रेरीज़ के साथ अपना विकास वातावरण स्थापित करें।

### मावेन स्थापना
अपने में निम्नलिखित निर्भरता जोड़ें `pom.xml` फ़ाइल:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ग्रेडेल स्थापना
इसे अपने में शामिल करें `build.gradle` फ़ाइल:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### प्रत्यक्षत: डाउनलोड
वैकल्पिक रूप से, नवीनतम रिलीज़ को यहाँ से डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

#### लाइसेंस प्राप्ति चरण
- **मुफ्त परीक्षण**Aspose.Slides सुविधाओं का पता लगाने के लिए एक अस्थायी लाइसेंस के साथ शुरू करें।
- **अस्थायी लाइसेंस**अस्थायी लाइसेंस प्राप्त करके उन्नत सुविधाओं तक पहुँच प्राप्त करें।
- **खरीदना**दीर्घकालिक उपयोग के लिए, पूर्ण लाइसेंस खरीदने पर विचार करें।

### बुनियादी आरंभीकरण और सेटअप
आरंभ करें `Presentation` स्लाइड बनाना शुरू करने के लिए ऑब्जेक्ट:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // स्लाइड और चार्ट जोड़ने के लिए आपका कोड यहां है।
    }
}
```

## कार्यान्वयन मार्गदर्शिका
अब, आइए आपके चार्ट श्रृंखला में छवि मार्कर जोड़ने की प्रक्रिया को समझें।

### चार्ट के साथ एक नया प्रेजेंटेशन बनाएं
सबसे पहले, हमें एक स्लाइड की आवश्यकता है जहां हम अपना चार्ट जोड़ सकें:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
        Presentation presentation = new Presentation();

        // संग्रह से पहली स्लाइड प्राप्त करें
        ISlide slide = presentation.getSlides().get_Item(0);

        // स्लाइड में मार्कर के साथ डिफ़ॉल्ट लाइन चार्ट जोड़ें
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### चार्ट डेटा तक पहुँचें और कॉन्फ़िगर करें
इसके बाद, हम श्रृंखला को प्रबंधित करने के लिए अपने चार्ट की डेटा वर्कशीट तक पहुंचेंगे:

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

        // मौजूदा श्रृंखला साफ़ करें और नई श्रृंखला जोड़ें
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### चार्ट डेटा बिंदुओं में छवि मार्कर जोड़ें
अब रोमांचक भाग पर आते हैं - मार्कर के रूप में चित्र जोड़ना:

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

        // मार्कर के रूप में छवियाँ लोड करें और जोड़ें
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // मार्कर के रूप में छवियों के साथ डेटा बिंदु जोड़ें
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

### चार्ट श्रृंखला मार्कर कॉन्फ़िगर करें और प्रस्तुति सहेजें
अंत में, आइए बेहतर दृश्यता के लिए मार्कर का आकार समायोजित करें और अपनी प्रस्तुति को सेव करें:

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

        // छवियों को मार्कर के रूप में लोड करें और जोड़ें (उदाहरण के लिए प्लेसहोल्डर पथ का उपयोग करें)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## निष्कर्ष
इस गाइड का पालन करके, आपने सीखा है कि कस्टम इमेज मार्कर जोड़कर Aspose.Slides for Java में अपने चार्ट को कैसे बेहतर बनाया जाए। यह तरीका आपकी प्रस्तुतियों की सहभागिता और स्पष्टता को काफी हद तक बढ़ा सकता है।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}