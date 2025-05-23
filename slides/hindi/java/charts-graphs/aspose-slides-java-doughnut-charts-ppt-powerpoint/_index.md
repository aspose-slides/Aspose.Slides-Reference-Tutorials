---
"date": "2025-04-17"
"description": "PowerPoint में गतिशील डोनट चार्ट बनाने के लिए Aspose.Slides for Java का उपयोग करना सीखें। आसानी से अनुसरण किए जाने वाले चरणों और कोड उदाहरणों के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।"
"title": "Java के लिए Aspose.Slides का उपयोग करके PowerPoint में डायनामिक डोनट चार्ट बनाएं"
"url": "/hi/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java के लिए Aspose.Slides का उपयोग करके PowerPoint में डायनामिक डोनट चार्ट बनाएं

## परिचय
आकर्षक प्रस्तुतियाँ बनाने के लिए अक्सर सिर्फ़ टेक्स्ट और छवियों से ज़्यादा की ज़रूरत होती है; चार्ट डेटा को प्रभावी ढंग से विज़ुअलाइज़ करके कहानी कहने को काफ़ी हद तक बढ़ा सकते हैं। हालाँकि, कई डेवलपर्स प्रोग्रामेटिक रूप से PowerPoint फ़ाइलों में डायनेमिक चार्ट सुविधाओं को एकीकृत करने के लिए संघर्ष करते हैं। यह ट्यूटोरियल दिखाता है कि PowerPoint में डोनट चार्ट बनाने के लिए Aspose.Slides for Java का उपयोग कैसे करें - एक शक्तिशाली टूल जो लचीलापन और उपयोग में आसानी को जोड़ता है।

**आप क्या सीखेंगे:**
- Java के लिए Aspose.Slides का उपयोग करके किसी प्रेजेंटेशन को कैसे आरंभ करें
- अपनी स्लाइड में डोनट चार्ट जोड़ने के लिए चरण-दर-चरण मार्गदर्शिका
- डेटा बिंदुओं को कॉन्फ़िगर करना और लेबल गुणों को अनुकूलित करना
- संशोधित प्रस्तुति को उच्च निष्ठा के साथ सहेजना

आइए जानें कि आप अपनी प्रस्तुतियों को बेहतर बनाने के लिए इन सुविधाओं का लाभ कैसे उठा सकते हैं। शुरू करने से पहले, सुनिश्चित करें कि आप बुनियादी जावा प्रोग्रामिंग अवधारणाओं से परिचित हैं।

## आवश्यक शर्तें
इस ट्यूटोरियल का प्रभावी ढंग से पालन करने के लिए, सुनिश्चित करें कि आपके पास ये हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- एक एकीकृत विकास वातावरण (IDE) जैसे कि IntelliJ IDEA या Eclipse.
- निर्भरता प्रबंधन के लिए Maven या Gradle स्थापित किया गया है।
- Aspose.Slides for Java लाइसेंस मान्य है। आप इसकी विशेषताओं का परीक्षण करने के लिए निःशुल्क परीक्षण प्राप्त कर सकते हैं।

## Java के लिए Aspose.Slides सेट अप करना
अपने प्रोजेक्ट में Aspose.Slides को शामिल करके शुरुआत करें। अपनी पसंद के अनुसार Maven और Gradle में से चुनें:

**मावेन**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**ग्रैडल**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

यदि आप सीधे डाउनलोड करना पसंद करते हैं, तो यहां जाएं [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/) पृष्ठ.

### लाइसेंस अधिग्रहण
आप Aspose.Slides की विशेषताओं का पता लगाने के लिए निःशुल्क परीक्षण के साथ शुरुआत कर सकते हैं। विस्तारित उपयोग के लिए, लाइसेंस खरीदें या अस्थायी लाइसेंस का अनुरोध करें [Aspose की वेबसाइट](https://purchase.aspose.com/temporary-license/)अपने अनुप्रयोग में अपना वातावरण स्थापित करने और Aspose.Slides को आरंभ करने के लिए दिए गए निर्देशों का पालन करें।

## कार्यान्वयन मार्गदर्शिका
आइए Aspose.Slides for Java का उपयोग करके PowerPoint में डोनट चार्ट बनाने के लिए आवश्यक चरणों को विभाजित करें। प्रत्येक अनुभाग एक विशिष्ट सुविधा के लिए समर्पित है, जो स्पष्टता और फ़ोकस सुनिश्चित करता है।

### प्रस्तुति आरंभ करें
एक नई PowerPoint फ़ाइल लोड करके या बनाकर शुरू करें। यह चरण आपके प्रेजेंटेशन वातावरण को सेट करता है।

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// प्रारंभिक प्रस्तुति को सहेजकर सफल लोडिंग की पुष्टि करें
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### डोनट चार्ट जोड़ें
अपनी स्लाइड में डोनट चार्ट जोड़ें, इसके आयाम और स्वरूप को अनुकूलित करें।

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// श्रृंखला गुण कॉन्फ़िगर करें
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### डेटा पॉइंट और लेबल कॉन्फ़िगर करें
प्रत्येक डेटा बिंदु के स्वरूप को अनुकूलित करें और बेहतर पठनीयता के लिए लेबल कॉन्फ़िगर करें।

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
        
        // डेटा बिंदु को प्रारूपित करें
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // प्रत्येक श्रेणी में अंतिम श्रृंखला के लिए लेबल गुण अनुकूलित करें
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

### प्रस्तुति सहेजें
अपना चार्ट कॉन्फ़िगर करने के बाद, अपने परिवर्तनों को बनाए रखने के लिए प्रस्तुति को सहेजें.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## व्यावहारिक अनुप्रयोगों
डोनट चार्ट का उपयोग विभिन्न परिदृश्यों में किया जा सकता है:
- **वित्तीय रिपोर्ट:** बजट आवंटन या वित्तीय मीट्रिक्स की कल्पना करें।
- **बाज़ार विश्लेषण:** प्रतिस्पर्धियों के बीच बाजार हिस्सेदारी का वितरण दिखाएं।
- **सर्वेक्षण परिणाम:** सर्वेक्षण प्रतिक्रियाओं से प्राप्त श्रेणीबद्ध डेटा को प्रभावी ढंग से प्रस्तुत करें।

डेटाबेस और वेब अनुप्रयोगों जैसी अन्य प्रणालियों के साथ एकीकरण, वास्तविक समय के आंकड़ों के आधार पर गतिशील चार्ट निर्माण को सक्षम बनाता है।

## प्रदर्शन संबंधी विचार
इष्टतम प्रदर्शन के लिए:
- संसाधनों का तुरंत निपटान करके मेमोरी उपयोग का प्रबंधन करें।
- यदि प्रसंस्करण शक्ति को संरक्षित करना आवश्यक न हो तो चार्ट या स्लाइड की संख्या सीमित रखें।
- बड़े डेटासेट को संभालने के लिए कुशल डेटा संरचनाओं का उपयोग करें।

सर्वोत्तम प्रथाओं का पालन करने से यह सुनिश्चित होता है कि आपका अनुप्रयोग सुचारू रूप से चले, विशेष रूप से जटिल प्रस्तुतियों के साथ काम करते समय।

## निष्कर्ष
एक बार जब आप मुख्य चरणों को समझ लेते हैं, तो Aspose.Slides for Java का उपयोग करके PowerPoint में गतिशील डोनट चार्ट बनाना एक सीधी प्रक्रिया है। इस गाइड के साथ, अब आप डेटा अंतर्दृष्टि को प्रभावी ढंग से संप्रेषित करने वाले दृश्यमान आकर्षक चार्ट को एकीकृत करके अपनी प्रस्तुतियों को बेहतर बनाने के लिए सुसज्जित हैं।

Aspose.Slides की कार्यक्षमताओं को और अधिक जानने तथा इसकी क्षमताओं को गहराई से समझने के लिए, विभिन्न चार्ट प्रकारों या एनिमेशन और ट्रांजिशन जैसी उन्नत सुविधाओं के साथ प्रयोग करने पर विचार करें।

## अक्सर पूछे जाने वाले प्रश्न अनुभाग
**प्रश्न: क्या मैं व्यावसायिक अनुप्रयोगों में Aspose.Slides for Java का उपयोग कर सकता हूँ?**
उत्तर: हां, लेकिन आपको लाइसेंस प्राप्त करना होगा। आप इसकी विशेषताओं का मूल्यांकन करने के लिए निःशुल्क परीक्षण से शुरुआत कर सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}