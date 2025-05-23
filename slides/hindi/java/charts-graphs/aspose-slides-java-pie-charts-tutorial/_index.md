---
"date": "2025-04-17"
"description": "Aspose.Slides for Java का उपयोग करके पाई चार्ट बनाना और उन्हें कस्टमाइज़ करना सीखें। यह ट्यूटोरियल सेटअप से लेकर एडवांस्ड कस्टमाइज़ेशन तक सब कुछ कवर करता है।"
"title": "Aspose.Slides के साथ जावा में पाई चार्ट बनाना एक व्यापक गाइड"
"url": "/hi/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# जावा के लिए Aspose.Slides के साथ पाई चार्ट बनाना: एक संपूर्ण ट्यूटोरियल

## परिचय
प्रभावशाली जानकारी देने के लिए गतिशील और आकर्षक प्रस्तुतिकरण बनाना महत्वपूर्ण है। Aspose.Slides for Java के साथ, आप पाई चार्ट जैसे जटिल चार्ट को अपनी स्लाइड में आसानी से एकीकृत कर सकते हैं, जिससे डेटा विज़ुअलाइज़ेशन को आसानी से बढ़ाया जा सकता है। यह व्यापक मार्गदर्शिका आपको Aspose.Slides Java का उपयोग करके पाई चार्ट बनाने और उसे अनुकूलित करने की प्रक्रिया से गुज़रेगी, जिससे आम प्रस्तुति चुनौतियों को आसानी से हल किया जा सकेगा।

**आप क्या सीखेंगे:**
- प्रस्तुति आरंभ करना और स्लाइड जोड़ना.
- अपनी स्लाइड पर पाई चार्ट बनाना और कॉन्फ़िगर करना।
- चार्ट शीर्षक, डेटा लेबल और रंग सेट करना.
- प्रदर्शन को अनुकूलित करना और संसाधनों का प्रभावी प्रबंधन करना।
- Maven या Gradle का उपयोग करके Aspose.Slides को Java परियोजनाओं में एकीकृत करना।

आइए सबसे पहले यह सुनिश्चित करें कि आपके पास आगे बढ़ने के लिए सभी आवश्यक उपकरण और ज्ञान मौजूद हैं!

## आवश्यक शर्तें
इस ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित सेटअप तैयार है:

### आवश्यक लाइब्रेरी, संस्करण और निर्भरताएँ
- **जावा के लिए Aspose.Slides**सुनिश्चित करें कि आपके पास संस्करण 25.4 या बाद का संस्करण है।
- **जावा डेवलपमेंट किट (JDK)**: संस्करण 16 या उच्चतर आवश्यक है.

### पर्यावरण सेटअप आवश्यकताएँ
- जावा स्थापित और कॉन्फ़िगर किया गया एक विकास वातावरण।
- एक एकीकृत विकास वातावरण (IDE) जैसे कि IntelliJ IDEA, Eclipse, या NetBeans.

### ज्ञान पूर्वापेक्षाएँ
- जावा प्रोग्रामिंग की बुनियादी समझ.
- निर्भरता प्रबंधन के लिए मावेन या ग्रेडेल से परिचित होना।

## Java के लिए Aspose.Slides सेट अप करना
अपने जावा प्रोजेक्ट में Aspose.Slides का उपयोग शुरू करने के लिए, आपको लाइब्रेरी को निर्भरता के रूप में जोड़ना होगा। यहां बताया गया है कि आप विभिन्न बिल्ड टूल का उपयोग करके ऐसा कैसे कर सकते हैं:

**मावेन**
इस स्निपेट को अपने में जोड़ें `pom.xml` फ़ाइल:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**ग्रैडल**
अपने कार्यक्रम में निम्नलिखित को शामिल करें `build.gradle` फ़ाइल:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**प्रत्यक्षत: डाउनलोड**
यदि आप बिल्ड टूल का उपयोग नहीं करना चाहते हैं, तो नवीनतम रिलीज़ डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

### लाइसेंस प्राप्ति चरण
- **मुफ्त परीक्षण**Aspose.Slides सुविधाओं का पता लगाने के लिए एक निःशुल्क परीक्षण के साथ शुरुआत करें।
- **अस्थायी लाइसेंस**: बिना किसी सीमा के विस्तारित उपयोग के लिए अस्थायी लाइसेंस प्राप्त करें।
- **खरीदना**यदि आपको दीर्घकालिक पहुंच की आवश्यकता है तो खरीदने पर विचार करें।

**बुनियादी आरंभीकरण और सेटअप**
Aspose.Slides का उपयोग शुरू करने के लिए, एक नया प्रेजेंटेशन ऑब्जेक्ट बनाकर अपने प्रोजेक्ट को आरंभ करें:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## कार्यान्वयन मार्गदर्शिका
अब आइए पाई चार्ट को जोड़ने और अनुकूलित करने की प्रक्रिया को प्रबंधनीय चरणों में विभाजित करें।

### प्रस्तुति और स्लाइड आरंभ करें
एक नया प्रेजेंटेशन सेट अप करके और पहली स्लाइड एक्सेस करके शुरू करें। चार्ट बनाने के लिए यह आपका कैनवास है:
```java
import com.aspose.slides.*;

// एक नया प्रस्तुतिकरण उदाहरण बनाएँ.
Presentation presentation = new Presentation();
// प्रस्तुति में पहली स्लाइड तक पहुंचें.
islide slides = presentation.getSlides().get_Item(0);
```

### स्लाइड में पाई चार्ट जोड़ें
डिफ़ॉल्ट डेटा सेट के साथ निर्दिष्ट स्थान पर पाई चार्ट डालें:
```java
import com.aspose.slides.*;

// स्थिति (100, 100) पर आकार (400, 400) के साथ एक पाई चार्ट जोड़ें।
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### चार्ट शीर्षक सेट करें
शीर्षक सेट करके और उसे केन्द्रित करके अपने चार्ट को अनुकूलित करें:
```java
import com.aspose.slides.*;

// पाई चार्ट में शीर्षक जोड़ें.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### श्रृंखला के लिए डेटा लेबल कॉन्फ़िगर करें
सुनिश्चित करें कि डेटा लेबल स्पष्टता के लिए मान प्रदर्शित करते हैं:
```java
import com.aspose.slides.*;

// पहली श्रृंखला पर डेटा मान दिखाएँ.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### चार्ट डेटा वर्कशीट तैयार करें
मौजूदा श्रृंखला और श्रेणियों को साफ़ करके अपने चार्ट की डेटा वर्कशीट सेट करें:
```java
import com.aspose.slides.*;

// चार्ट डेटा कार्यपुस्तिका तैयार करें.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### चार्ट में श्रेणियाँ जोड़ें
अपने पाई चार्ट के लिए श्रेणियाँ परिभाषित करें:
```java
import com.aspose.slides.*;

// नई श्रेणियाँ जोड़ें.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### श्रृंखला जोड़ें और डेटा बिंदु भरें
एक श्रृंखला बनाएं और उसमें डेटा बिंदु भरें:
```java
import com.aspose.slides.*;

// एक नई श्रृंखला जोड़ें और उसका नाम निर्धारित करें.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### श्रृंखला के रंग और बॉर्डर अनुकूलित करें
रंग सेट करके और बॉर्डर को अनुकूलित करके दृश्य अपील बढ़ाएं:
```java
import com.aspose.slides.*;

// श्रृंखला क्षेत्रों के लिए विविध रंग निर्धारित करें।
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// विभिन्न रंगों और शैलियों के साथ अन्य डेटा बिंदुओं के लिए दोहराएं।
```

### कस्टम डेटा लेबल कॉन्फ़िगर करें
प्रत्येक डेटा बिंदु के लिए लेबल को ठीक करें:
```java
import com.aspose.slides.*;

// कस्टम लेबल कॉन्फ़िगर करें.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// लेबल के लिए लीडर लाइन सक्षम करें.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### रोटेशन कोण सेट करें और प्रेजेंटेशन सहेजें
घूर्णन कोण निर्धारित करके और प्रस्तुति को सहेजकर अपने पाई चार्ट को अंतिम रूप दें:
```java
import com.aspose.slides.*;

// घूर्णन कोण सेट करें.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// प्रस्तुति को फ़ाइल में सहेजें.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, आपने Aspose.Slides for Java का उपयोग करके पाई चार्ट बनाना और उन्हें कस्टमाइज़ करना सीखा है। इन चरणों का पालन करके, आप अपने प्रेजेंटेशन को आकर्षक डेटा विज़ुअलाइज़ेशन के साथ बेहतर बना सकते हैं। यदि आपके पास कोई प्रश्न है या आपको और सहायता की आवश्यकता है, तो बेझिझक हमसे संपर्क करें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}