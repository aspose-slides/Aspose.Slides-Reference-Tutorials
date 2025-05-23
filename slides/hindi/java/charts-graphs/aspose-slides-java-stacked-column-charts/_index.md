---
"date": "2025-04-17"
"description": "Aspose.Slides for Java का उपयोग करके पेशेवर प्रस्तुतिकरण बनाना सीखें। यह मार्गदर्शिका आपके परिवेश को सेट अप करने, स्टैक्ड कॉलम चार्ट जोड़ने और स्पष्टता के लिए उन्हें अनुकूलित करने के बारे में बताती है।"
"title": "Aspose.Slides के साथ जावा में स्टैक्ड कॉलम चार्ट मास्टर करें एक व्यापक गाइड"
"url": "/hi/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides के साथ जावा में स्टैक्ड कॉलम चार्ट्स में महारत हासिल करें: एक व्यापक गाइड

## परिचय

Aspose.Slides for Java की शक्ति के साथ व्यावहारिक डेटा विज़ुअलाइज़ेशन को शामिल करके अपनी प्रस्तुतियों को बेहतर बनाएँ। स्टैक्ड कॉलम चार्ट के साथ पेशेवर दिखने वाली स्लाइड बनाना आसान है, चाहे आप व्यावसायिक रिपोर्ट तैयार कर रहे हों या प्रोजेक्ट आँकड़े दिखा रहे हों।

इस ट्यूटोरियल में, हम सीखेंगे कि गतिशील प्रस्तुतियाँ बनाने और आकर्षक स्टैक्ड कॉलम चार्ट जोड़ने के लिए Aspose.Slides for Java का उपयोग कैसे करें। इस गाइड के अंत तक, आप निम्नलिखित के लिए आवश्यक कौशल से लैस हो जाएँगे:
- Aspose.Slides का उपयोग करने के लिए अपना वातावरण सेट करें
- एकदम शुरुआत से एक प्रस्तुति तैयार करें
- प्रतिशत-स्टैक्ड कॉलम चार्ट जोड़ें और कस्टमाइज़ करें
- स्पष्टता के लिए चार्ट अक्ष और डेटा लेबल को प्रारूपित करें

आइये ऐसी प्रस्तुतियाँ बनाने की कोशिश करें जो आपके दर्शकों को आकर्षित कर सकें।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- **जावा डेवलपमेंट किट (JDK):** संस्करण 8 या उच्चतर.
- **आईडीई:** कोई भी एकीकृत विकास वातावरण जैसे कि IntelliJ IDEA या Eclipse.
- **मावेन/ग्रैडल:** निर्भरता प्रबंधन के लिए (वैकल्पिक लेकिन अनुशंसित)।
- **बुनियादी जावा ज्ञान:** जावा प्रोग्रामिंग अवधारणाओं से परिचित होना।

## Java के लिए Aspose.Slides सेट अप करना
आरंभ करने के लिए, आपको अपने प्रोजेक्ट में Aspose.Slides लाइब्रेरी को शामिल करना होगा। यहाँ बताया गया है कि कैसे:

**मावेन:**
इस निर्भरता को अपने में जोड़ें `pom.xml` फ़ाइल:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**ग्रेडेल:**
इसे अपने में शामिल करें `build.gradle` फ़ाइल:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**प्रत्यक्षत: डाउनलोड:**
वैकल्पिक रूप से, नवीनतम JAR को यहां से डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

### लाइसेंस अधिग्रहण
आप Aspose.Slides की विशेषताओं का पता लगाने के लिए निःशुल्क परीक्षण से शुरुआत कर सकते हैं। मूल्यांकन सीमाओं को हटाने के लिए, अस्थायी या खरीदा हुआ लाइसेंस प्राप्त करने पर विचार करें।
- **मुफ्त परीक्षण:** तत्काल लागत के बिना सीमित सुविधाओं तक पहुँच प्राप्त करें।
- **अस्थायी लाइसेंस:** अनुरोध करें [Aspose की साइट](https://purchase.aspose.com/temporary-license/).
- **खरीदना:** पूर्ण पहुँच के लिए खरीद पृष्ठ पर जाएँ।

### मूल आरंभीकरण
यहां बताया गया है कि आप अपने जावा अनुप्रयोग में Aspose.Slides को कैसे आरंभ करते हैं:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
        Presentation presentation = new Presentation();
        
        // प्रस्तुति ऑब्जेक्ट पर ऑपरेशन निष्पादित करें
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## कार्यान्वयन मार्गदर्शिका

### प्रस्तुति बनाना और स्लाइड जोड़ना
**अवलोकन:**
एक प्रारंभिक स्लाइड के साथ एक सरल प्रस्तुति तैयार करके शुरुआत करें। यह आगे के सुधारों के लिए आपकी नींव है।

#### चरण 1: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // एक नया प्रस्तुतिकरण उदाहरण बनाएँ
        Presentation presentation = new Presentation();
        
        // पहली स्लाइड का संदर्भ (स्वतः निर्मित)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### चरण 2: प्रस्तुति सहेजें
```java
// प्रस्तुति को फ़ाइल में सहेजें
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### स्लाइड में प्रतिशत स्टैक्ड कॉलम चार्ट जोड़ना
**अवलोकन:**
प्रतिशत-स्टैक्ड कॉलम चार्ट जोड़कर अपनी स्लाइड को बेहतर बनाएं, जिससे डेटा की तुलना आसानी से की जा सके।

#### चरण 1: स्लाइड को आरंभ करें और एक्सेस करें
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // अगले चरण में चार्ट जोड़ने के लिए आगे बढ़ें
    }
}
```

#### चरण 2: स्लाइड में चार्ट जोड़ें
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### चार्ट अक्ष संख्या प्रारूप को अनुकूलित करना
**अवलोकन:**
बेहतर पठनीयता के लिए अपने चार्ट के ऊर्ध्वाधर अक्ष के संख्या प्रारूप को अनुकूलित करें।

#### चरण 1: चार्ट जोड़ें और एक्सेस करें
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### चरण 2: कस्टम नंबर प्रारूप सेट करें
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### चार्ट में श्रृंखला और डेटा बिंदु जोड़ना
**अवलोकन:**
अपने चार्ट को डेटा श्रृंखला से भरें, जिससे यह जानकारीपूर्ण और देखने में आकर्षक बन सके।

#### चरण 1: प्रस्तुति और चार्ट आरंभ करें
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### चरण 2: डेटा श्रृंखला जोड़ें
```java
// मौजूदा श्रृंखला साफ़ करें और नई श्रृंखलाएँ जोड़ें
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// आवश्यकतानुसार अधिक डेटा बिंदु जोड़ें
```

### स्वरूपण श्रृंखला भरण रंग
**अवलोकन:**
प्रत्येक श्रृंखला के भरण रंग को प्रारूपित करके अपने चार्ट के सौंदर्य को बढ़ाएं।

#### चरण 1: चार्ट को आरंभ करें और एक्सेस करें
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### चरण 2: भरण रंग सेट करें
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// विभिन्न रंगों वाली अन्य श्रृंखलाओं के लिए भी यही दोहराएँ
```

### डेटा लेबल का प्रारूपण
**अवलोकन:**
अपने डेटा लेबल के प्रारूप को अनुकूलित करके उन्हें अधिक पठनीय बनाएं।

#### चरण 1: चार्ट श्रृंखला और डेटा बिंदुओं तक पहुंचें
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### चरण 2: डेटा लेबल अनुकूलित करें
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## निष्कर्ष
इस गाइड का पालन करके, आपने सीखा है कि Java के लिए Aspose.Slides को कैसे सेट अप करें और प्रतिशत-स्टैक्ड कॉलम चार्ट के साथ गतिशील प्रस्तुतियाँ कैसे बनाएँ। अपनी ज़रूरतों के हिसाब से रंग और लेबल समायोजित करके अपने चार्ट को और भी कस्टमाइज़ करें।

हैप्पी कोडिंग!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}