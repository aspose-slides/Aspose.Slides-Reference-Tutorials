---
date: '2026-02-17'
description: Aspose.Slides for Java का उपयोग करके PowerPoint में डोनट चार्ट बनाना
  सीखें और प्रोग्रामेटिकली चार्ट डेटा पॉइंट्स जोड़ें। आसान चरणों और कोड उदाहरणों का
  पालन करें।
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Aspose.Slides for Java के साथ PowerPoint में डोनट चार्ट बनाएं
url: /hi/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

 produce final content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java के साथ डोनट चार्ट PowerPoint बनाएं

## परिचय
प्रभावशाली प्रस्तुतियों को बनाने के लिए अक्सर केवल टेक्स्ट और इमेज से अधिक की आवश्यकता होती है; चार्ट डेटा को प्रभावी ढंग से विज़ुअलाइज़ करके कहानी कहने को काफी बढ़ा सकते हैं। हालांकि, कई डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint फ़ाइलों में डायनामिक चार्ट फीचर इंटीग्रेट करने में कठिनाई होती है। यह ट्यूटोरियल दिखाता है कि कैसे **डोनट चार्ट PowerPoint बनाएं** Aspose.Slides for Java का उपयोग करके—एक शक्तिशाली टूल जो लचीलापन और उपयोग में आसान होने को मिलाता है।

**आप क्या सीखेंगे:**
- Aspose.Slides for Java का उपयोग करके प्रेजेंटेशन को इनिशियलाइज़ कैसे करें
- अपने स्लाइड्स में डोनट चार्ट जोड़ने के लिए स्टेप‑बाय‑स्टेप गाइड
- डेटा पॉइंट्स को कॉन्फ़िगर करना और लेबल प्रॉपर्टीज़ को कस्टमाइज़ करना
- संशोधित प्रेजेंटेशन को उच्च फ़िडेलिटी के साथ सेव करना

आइए देखें कि आप इन फीचर्स का उपयोग करके अपनी प्रस्तुतियों को कैसे बेहतर बना सकते हैं। शुरू करने से पहले, सुनिश्चित करें कि आप बुनियादी Java प्रोग्रामिंग अवधारणाओं से परिचित हैं।

## त्वरित उत्तर
- **डोनट चार्ट PowerPoint बनाने वाली लाइब्रेरी कौन सी है?** Aspose.Slides for Java
- **क्या मैं प्रोग्रामेटिक रूप से चार्ट डेटा पॉइंट्स जोड़ सकता हूँ?** हाँ, चार्ट API का उपयोग करके
- **प्रोडक्शन के लिए लाइसेंस चाहिए?** एक वैध Aspose.Slides लाइसेंस आवश्यक है
- **कौन से Java संस्करण समर्थित हैं?** Java 8 और बाद के (JDK 16 classifier दिखाया गया)
- **मैं कितनी सीरीज़ जोड़ सकता हूँ?** उदाहरण में अधिकतम 15 सीरीज़ जोड़ी गई हैं, लेकिन आप आवश्यकता अनुसार समायोजित कर सकते हैं

## PowerPoint में डोनट चार्ट क्या है?
डोनट चार्ट पाई चार्ट का एक वैरिएशन है जिसमें मध्य में एक खाली हिस्सा होता है, जिससे आप कई डेटा सीरीज़ को एक कॉम्पैक्ट, दृश्य रूप से आकर्षक तरीके से प्रदर्शित कर सकते हैं। यह भाग‑से‑पूरे संबंध दिखाने के लिए आदर्श है जबकि डिज़ाइन साफ़ रहता है।

## Aspose.Slides for Java का उपयोग करके डोनट चार्ट क्यों बनाएं?
- **पूर्ण नियंत्रण** चार्ट की उपस्थिति, डेटा और लेआउट पर, PowerPoint खोले बिना
- **कोई COM इंटरऑप नहीं** – Java को सपोर्ट करने वाले किसी भी प्लेटफ़ॉर्म पर काम करता है
- **उच्च प्रदर्शन** बड़े डेक बनाने या वेब सर्विसेज़ के साथ इंटीग्रेट करने के लिए
- **समृद्ध कस्टमाइज़ेशन** जैसे एक्सप्लोजन, होल साइज, स्लाइस एंगल्स, और लेबल फ़ॉर्मेटिंग

## पूर्वापेक्षाएँ
- Java प्रोग्रामिंग का बुनियादी ज्ञान।
- IntelliJ IDEA या Eclipse जैसे IDE।
- डिपेंडेंसी मैनेजमेंट के लिए Maven या Gradle।
- वैध Aspose.Slides for Java लाइसेंस (फ्री ट्रायल उपलब्ध)।

## Aspose.Slides for Java सेटअप करना
अपने प्रोजेक्ट के अनुसार उपयुक्त डिपेंडेंसी मैनेजर चुनें।

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

यदि आप सीधे डाउनलोड करना पसंद करते हैं, तो [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) पेज पर जाएँ।

### लाइसेंस प्राप्ति
आप Aspose.Slides की सुविधाओं को एक्सप्लोर करने के लिए फ्री ट्रायल से शुरू कर सकते हैं। विस्तारित उपयोग के लिए, लाइसेंस खरीदें या [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/) से एक टेम्पररी लाइसेंस अनुरोध करें। अपने पर्यावरण को सेटअप करने और एप्लिकेशन में Aspose.Slides को इनिशियलाइज़ करने के लिए प्रदान किए गए निर्देशों का पालन करें।

## Aspose.Slides for Java का उपयोग करके डोनट चार्ट PowerPoint कैसे बनाएं
नीचे एक पूर्ण, स्टेप‑बाय‑स्टेप गाइड दिया गया है। प्रत्येक कोड ब्लॉक के पहले उसका विवरण दिया गया है, ताकि आप ठीक-ठीक समझ सकें कि क्या हो रहा है।

### चरण 1: प्रेजेंटेशन को इनिशियलाइज़ करें
पहले, मौजूदा PPTX लोड करें या नया बनाएं। यह आगे के संशोधनों के लिए स्लाइड कलेक्शन तैयार करता है।

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### चरण 2: स्लाइड में डोनट चार्ट जोड़ें
हम चार्ट शेप जोड़ते हैं, किसी भी डिफ़ॉल्ट सीरीज़/कैटेगरी को साफ़ करते हैं, और बेसिक विज़ुअल प्रॉपर्टीज़ सेट करते हैं।

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

### चरण 3: चार्ट डेटा पॉइंट्स जोड़ें और लेबल कस्टमाइज़ करें
यहाँ हम कैटेगरी भरते हैं, प्रत्येक सीरीज़ के लिए डेटा पॉइंट्स जोड़ते हैं, और लेबल की उपस्थिति को फाइन‑ट्यून करते हैं। यही वह जगह है जहाँ **add chart data points** कीवर्ड काम आता है।

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

### चरण 4: अपडेटेड प्रेजेंटेशन को सेव करें
अंत में, बदलावों को एक नई PPTX फ़ाइल में सहेजें।

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## व्यावहारिक अनुप्रयोग
- **वित्तीय रिपोर्ट्स:** बजट आवंटन या खर्च विभाजन को विज़ुअलाइज़ करें।
- **बाजार विश्लेषण:** प्रतिस्पर्धियों के बीच मार्केट‑शेयर वितरण दिखाएँ।
- **सर्वे परिणाम:** श्रेणीबद्ध सर्वे डेटा को कॉम्पैक्ट रूप में प्रस्तुत करें।
- **डैशबोर्ड जनरेशन:** डेटाबेस क्वेरीज़ के साथ मिलाकर लाइव‑अपडेटिंग स्लाइड्स बनाएं।

## प्रदर्शन संबंधी विचार
- **संसाधनों को डिस्पोज़ करें**: समाप्त होने पर `pres.dispose()` कॉल करें ताकि नेटिव मेमोरी मुक्त हो सके।
- **चार्ट की संख्या सीमित रखें**: सैकड़ों चार्ट जोड़ने से मेमोरी उपयोग बढ़ सकता है; आवश्यकता होने पर बैच‑प्रोसेस करें।
- **स्ट्रीमिंग का उपयोग करें**: बड़े डेटा सेट के लिए, इन‑मेमोरी एरेज़ के बजाय स्ट्रीम से सीधे वर्कबुक भरें।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| **चार्ट खाली दिख रहा है** | डेटा सेल्स सही ढंग से पॉपुलेट नहीं हुए हैं | जांचें कि `workBook.getCell(...)` सही रो/कॉलम इंडेक्स को रेफ़र कर रहा है। |
| **लेबल ओवरलैप** | सीमित स्थान में बहुत अधिक कैटेगरी | `DoughnutHoleSize` बढ़ाएँ या `FirstSliceAngle` को समायोजित करें। |
| **OutOfMemoryError** | डिस्पोज़ किए बिना बड़ी प्रस्तुतियाँ | सेव करने के बाद `pres.dispose()` कॉल करें और JVM हीप साइज बढ़ाने पर विचार करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Slides for Java को व्यावसायिक एप्लिकेशन्स में उपयोग कर सकता हूँ?**  
**उत्तर:** हाँ, लेकिन आपको एक वैध व्यावसायिक लाइसेंस चाहिए। मूल्यांकन के लिए फ्री ट्रायल उपलब्ध है।

**प्रश्न: मैं 15 से अधिक सीरीज़ कैसे जोड़ सकता हूँ?**  
**उत्तर:** “Add Doughnut Chart” चरण में लूप लिमिट बढ़ाएँ और सुनिश्चित करें कि आपके डेटा वर्कबुक में पर्याप्त रो हों।

**प्रश्न: क्या निर्माण के बाद डोनट होल साइज बदलना संभव है?**  
**उत्तर:** हाँ, सेव करने से पहले किसी भी समय `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` कॉल करें।

**प्रश्न: क्या मैं चार्ट को PPTX के बजाय इमेज के रूप में एक्सपोर्ट कर सकता हूँ?**  
**उत्तर:** बिल्कुल। `chart.getImage()` का उपयोग करें और लौटाए गए `java.awt.image.BufferedImage` को अपनी पसंदीदा फ़ॉर्मेट में सेव करें।

**प्रश्न: क्या Aspose.Slides एनीमेटेड चार्ट्स को सपोर्ट करता है?**  
**उत्तर:** एनीमेशन `ISlide.getTimeline()` API के माध्यम से जोड़ी जा सकती है, हालांकि यह ट्यूटोरियल के दायरे से बाहर है।

## निष्कर्ष
अब आपके पास Aspose.Slides for Java के साथ **डोनट चार्ट PowerPoint** फ़ाइलें बनाने की एक पूर्ण, प्रोडक्शन‑रेडी विधि है, जिसमें **चार्ट डेटा पॉइंट्स जोड़ना**, लेबल कस्टमाइज़ करना, और प्रदर्शन संबंधी विचारों को संभालना शामिल है। विभिन्न रंगों, डेटा स्रोतों, और चार्ट प्रकारों के साथ प्रयोग करें ताकि आपकी प्रस्तुतियाँ वास्तव में अलग दिखें।

---

**अंतिम अपडेट:** 2026-02-17  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}