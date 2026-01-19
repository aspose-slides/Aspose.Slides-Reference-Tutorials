---
date: '2026-01-19'
description: Aspose.Slides for Java का उपयोग करके PowerPoint में लेजेंड जोड़ना और
  डायनेमिक डोनट चार्ट बनाना सीखें। कोड उदाहरणों के साथ चरण‑दर‑चरण गाइड।
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: लेजेंड पावरपॉइंट चार्ट जोड़ें – Aspose.Slides for Java के साथ डायनेमिक डोनट
  चार्ट बनाएं
url: /hi/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java का उपयोग करके PowerPoint में डायनामिक डोनट चार्ट लेजेंड कैसे जोड़ Aspose.S प्रेजेंटेशन को इनिशियलाइज़ करने, चार्ट इन्सर्ट करने, डेटा पॉइंट्स कॉन्फ़िगर करने, लेबल कस्टमाइज़ करने, और अंत में फ़ाइल सेव करने की प्रक्रिया को चरण‑बद्ध तरीके आपके पास एक पूरी तरह कार्यशील PowerPoint होगा जो न केवल डेटा दिखाता है बल्कि स्पष्ट लेजेंड और पॉलिश्ड डेटा लेबल्स भी शामिल करता है।

**आप क्या सीखेंगे:**
- Aspose.Sl अपनी स्लाइड्स में डोनट चार्ट जोड़ने के लिए चरण‑दर‑चरण गंट्स, **add data labels chart**, कॉन्फ़िगर करना और लेजेंड प्रॉपर्टीज़ कस्टमाइज़ करना  
- हाई फ़िडेलिटी के साथ संशोधित प्रेजेंटेशन को सेव करना  

आइए देखें कि आप इन फीचर्स का उपयोग करके अपनी प्रेजेंटेशन को कैसे बेहतर बना सकते हैं। शुरू करने से पहले सुनिश्चित करें कि आप बेसिक Java सिंटैक्स से परिचित हैं।

## त्वरित उत्तर
- **मुख्य लाइब्रेरी कौन सी है?** Aspose.Slides for Java  
- **क्या मैं डोनट चार्ट में लेजेंड जोड़ सकता हूँ?** हाँ – चार्ट की लेजेंड और सीरीज़ सेटिंग्स का उपयोग करें  
- **क्या लाइसेंस की जरूरत है?** डेवलपमेंट के लिए ट्रायल काम करता है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है  
- **कौन सा Java संस्करण सपोर्टेड है?** उदाहरण JDK 16 (classifier jdk16) का उपयोग करता है  
- **मैं कितनी डेटा सीरीज़ बना सकता हूँ?** सैंपल 15 सीरीज़ तक लूप करता है, लेकिन आप अपनी आवश्यकता अनुसार समायोजित कर सकते हैं  

## डोनट चार्ट क्या है और लेजेंड क्यों जोड़ें?
डोनट चार्ट पाई चार्ट का एक वैरिएंट है जिसमें मध्य में खाली जगह होती है, जो भाग‑से‑सम्पूर्ण संबंध दिखाने के साथ अतिरिक्त जानकारी के लिए स्थान प्रदान करता है। लेजेंड जोड़ने से दर्शकों को रंगों को श्रेणियों से जल्दी मैप करने में मदद मिलती है, जिससे पढ़ने में आसानी बढ़ती है—विशेषकर जब आपके पास कई सीरीज़ हों।

## पूर्वापेक्षाएँ
- Java प्रोग्रामिंग का बेसिक ज्ञान।  
- IntelliJ IDEA या Eclipse जैसे IDE।  
- डिपेंडेंसी मैनेजमेंट के लिए Maven या Gradle।  
- वैध Aspose.Slides for Java लाइसेंस (फ्री ट्रायल उपलब्ध)।

## Aspose.Slides for Java सेटअप करना
अपने बिल्ड टूल के अनुसार डिपेंडेंसी फॉर्मेट चुनें।

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

यदि आप JAR सीधे डाउनलोड करना पसंद करते हैं, तो [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) पेज पर जाएँ।

### लाइसेंस प्राप्त करना
आप Aspose.Slides की सुविधाओं को एक्सप्लोर करने के लिए फ्री ट्रायल से शुरू कर सकते हैं। विस्तारित उपयोग के लिए लाइसेंस खरीदें या [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/) से टेम्पररी लाइसेंस अनुरोध करें। अपने वातावरण को सेटअप करने और एप्लिकेशन में Aspose.Slides को इनिशियलाइज़ करने के लिए दिए गए निर्देशों का पालन करें।

## इम्प्लीमेंटेशन गाइड
नीचे एक पूर्ण वॉकथ्रू दिया गया है। प्रत्येक कोड ब्लॉक को उसके आने से पहले समझाया गया है, ताकि आप ठीक‑ठीक जान सकें कि क्या होेंटेशन इनिशियलाइज़ करें
पहले, मौजूदा PPTX लोड करें या नया बनाएं। यह चरण प्रेजेंटेशन ऑब्जेक्ट सेट करता है जो चार्ट को रखेगा।

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### डोनट चार्ट जोड़ें
अब हम स्लाइड में डोनट चार्ट जोड़ते हैं। `ChartType.Doughnut` सही विज़ुअल बनाता है, और हम डिफ़ॉल्ट लेजेंड को बंद कर देते हैं क्योंकि हम बाद में इसे कस्टमाइज़ करेंगे।

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### डेटा पॉइंट्स और लेबल्स कॉन्फ़िगर करें
अगले चरण में हम कैटेगरीज पॉप्युलेट करते हैं, प्रत्येक सीरीज़ के लिए डेटा पॉइंट्स जोड़ते हैं, और **add data labels chart** करते हैं। लेबल कस्टमाइज़ेशन यह भी दिखाता है कि कैसे प्रत्येक कैटेगरी में अंतिम सीरीज़ के बगल में लेजेंड‑जैसी डिस्क्रिप्शन पोज़िशन की जाए।

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### प्रेजेंटेशन सेव करें
अंत में, बदलावों को नई PPTX फ़ाइल में सहेजें।

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## डोनट चार्ट में PowerPoint चार्ट लेजेंड क्यों जोड़ें?
- **स्पष्टता:** लेजेंड रंगों को श्रेणियों से मैप करता है बिना चार्ट एरिया को भीड़भाड़ किए।  
- **स्केलेबिलिटी:** जब आपके पास कई सीरीज़ हों (जैसे ऊपर लूप में), लेजेंड स्लाइड को पढ़ने योग्य बनाता है।  
- **प्रोफ़ेशनल लुक:** पॉलिश्ड‑ग्रेड प्रेजेंटेशन बनता है **मार्केट एन शेयर विज़ुअलाइज़ करें और लेजेंड से प्रत्येक प्रतिस्पर्धी्पॉन्स को स्पष्ट कैटेगरी नामों के साथ प्रस्तुत करें।

आप डेटाबेस, CSV फ़ाइलों या वेब सर्विसेज़ से डेटा खींचकर लूप में फीड कर सकते हैं और चार्ट को ऑन‑द‑फ्लाई जेनरेट कर सकते हैं।

## प्रदर्शन संबंधी विचार
- लंबी‑चलने वाली एप्लिकेशन्स में `Presentation` ऑब्जेक्ट्स को तुरंत डिस्पोज़ करें (`pres.dispose()`)।  
- यदि मेमोरी प्रेशर दिखे तो सीरीज़ की संख्या सीमित रखें; प्रत्येक सीरीज़ ओवरहेड जोड़ती है।  
- बड़े डेटासेट्स पॉप्युलेट करते समय एक ही `IChartDataWorkbook` को री‑यूज़ करें।

## सामान्य समस्याएँ औराइज़ करें। |
|ेस से टकरा सकता है। | `lbl.setX()` / `lbl.setY()` समायोजित करें या `DoughnutHoleSize` बढ़ाएँ। |
| रंग लागू नहीं हो रहा | Fill टाइप `Solid` सेट नहीं है। | सुनिश्चित करें `dataPoint.getFormat().getFill().setFillType(FillType.Solid)`। |

 प्रश्न

**प्रश्न में उपयोग कर सकता हूँ?**  
उत्तर: हाँ, लेकिन आपको वैध कमर्शियल लाइसेंस चाहिए। मूल्यांकन के लिए फ्री ट्रायल उपलब्ध है।

**प्रश्न: डिसेबल किए गए लेजेंड को फिर से कैसे एनेबल करूँ?**  
उत्तर: `chart.setLegend(true);` कॉल करें और वैकल्पिक रूप से `chart.getLegend().setPosition(LegendPosition.Right);` से पोज़िशन सेट करें।

**प्रश्न: क्या लेज्न: क्या मैं डेटाब को चार्ट से बाइंड करर्कबुक सेल्स पॉप्युलेट करें, और चार्ट नवीनतम वैल्यूज़ को दर्शाएगा।

**प्रश्न: क्या Aspose.Slides डोनट के अलावा अन्य चार्ट टाइप्स सपोर्ट करता है?**  
उत्तर: यह पूरी रेंज के चार्ट टाइप्स सपोर्ट करता है—pie, bar, line, scatter आदि। सिर्फ `ChartType.Doughnut` को इच्छित एनोम के साथ बदलें।

---

**अंतिम अपडेट:** 2026-01-19  
**टेस्टेड विथ:** Aspose.Slides 25.4 (JDK 16)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}