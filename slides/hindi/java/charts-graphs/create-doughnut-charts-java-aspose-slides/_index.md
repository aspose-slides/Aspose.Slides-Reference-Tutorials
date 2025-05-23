---
"date": "2025-04-17"
"description": "Aspose.Slides के साथ जावा में शानदार डोनट चार्ट बनाना सीखें। यह व्यापक गाइड आरंभीकरण, डेटा कॉन्फ़िगरेशन और प्रस्तुतियों को सहेजने को कवर करती है।"
"title": "Aspose.Slides का उपयोग करके जावा में डोनट चार्ट बनाएं एक व्यापक गाइड"
"url": "/hi/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides का उपयोग करके जावा में डोनट चार्ट बनाएं: एक चरण-दर-चरण मार्गदर्शिका

## परिचय

आज के डेटा-संचालित वातावरण में, जानकारी को प्रभावी ढंग से विज़ुअलाइज़ करना समझ और जुड़ाव को बढ़ाने के लिए महत्वपूर्ण है। जबकि प्रोग्रामेटिक रूप से पेशेवर चार्ट बनाना चुनौतीपूर्ण लग सकता है, खासकर जावा के साथ, यह गाइड आपको आसानी से डोनट चार्ट बनाने के लिए जावा के लिए Aspose.Slides का उपयोग करने के बारे में बताएगा।

इन चरणों का पालन करके, डेवलपर्स को प्रेजेंटेशन स्लाइडों में हेरफेर करने और डेटा विज़ुअलाइज़ेशन को सहजता से एकीकृत करने का व्यावहारिक अनुभव प्राप्त होगा।

**चाबी छीनना:**
- Aspose.Slides Java का उपयोग करके एक प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें।
- चार्ट डेटा कॉन्फ़िगर करें और मौजूदा श्रृंखला या श्रेणियों का प्रबंधन करें.
- अपने चार्ट के लिए श्रृंखला और श्रेणियां जोड़ें और अनुकूलित करें।
- डेटा बिंदुओं को प्रभावी ढंग से प्रारूपित और प्रदर्शित करें।
- अपनी प्रस्तुति को विभिन्न प्रारूपों में आसानी से सहेजें।

कार्यान्वयन में उतरने से पहले, सुनिश्चित करें कि आपके पास आरंभ करने के लिए आवश्यक सभी चीजें मौजूद हैं।

## आवश्यक शर्तें

इस ट्यूटोरियल का अनुसरण करने के लिए, सुनिश्चित करें कि आपके पास ये हैं:

- **आवश्यक पुस्तकालय:**
  - Aspose.Slides Java संस्करण 25.4 या बाद के संस्करण के लिए।
  
- **पर्यावरण सेटअप:**
  - आपके सिस्टम पर JDK 16 या उच्चतर संस्करण स्थापित है।
  - इंटेलीज आईडिया, एक्लिप्स या नेटबीन्स जैसा कोई आईडीई।

- **ज्ञान पूर्वापेक्षाएँ:**
  - जावा प्रोग्रामिंग अवधारणाओं की बुनियादी समझ।
  - मावेन या ग्रेडेल परियोजनाओं में निर्भरताओं के प्रबंधन से परिचित होना।

## Java के लिए Aspose.Slides सेट अप करना

Aspose.Slides को अपने प्रोजेक्ट में एकीकृत करने के लिए, अपने बिल्ड टूल के आधार पर इन चरणों का पालन करें:

**मावेन सेटअप:**
अपने में निम्नलिखित निर्भरता जोड़ें `pom.xml` फ़ाइल:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**ग्रेडेल सेटअप:**
अपने कार्यक्रम में निम्नलिखित को शामिल करें `build.gradle` फ़ाइल:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**प्रत्यक्षत: डाउनलोड:**
वैकल्पिक रूप से, नवीनतम संस्करण को सीधे यहां से डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

### लाइसेंस प्राप्त करना

मूल्यांकन सीमाओं के बिना Aspose.Slides का उपयोग करने के लिए:
- **मुफ्त परीक्षण:** संपूर्ण सुविधाओं का लाभ उठाने के लिए अस्थायी लाइसेंस से शुरुआत करें।
- **अस्थायी लाइसेंस:** के माध्यम से एक प्राप्त करें [Aspose वेबसाइट](https://purchase.aspose.com/temporary-license/).
- **खरीदना:** निरंतर उपयोग के लिए खरीदने पर विचार करें।

अपने जावा अनुप्रयोग में अपना लाइसेंस लागू करें:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## कार्यान्वयन मार्गदर्शिका

### प्रस्तुति और चार्ट आरंभ करना

#### अवलोकन
प्रस्तुति ऑब्जेक्ट को आरंभीकृत करके और पहली स्लाइड में डोनट चार्ट जोड़कर आरंभ करें।

**चरण 1: प्रस्तुति आरंभ करें**
मौजूदा PPTX फ़ाइल लोड करें या नई फ़ाइल बनाएँ:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**चरण 2: डोनट चार्ट जोड़ें**
निर्दिष्ट निर्देशांक पर पहली स्लाइड पर एक चार्ट बनाएं:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### चार्ट डेटा वर्कबुक को कॉन्फ़िगर करना और मौजूदा श्रृंखला/श्रेणियों को साफ़ करना

#### अवलोकन
चार्ट डेटा कार्यपुस्तिका को कॉन्फ़िगर करें और किसी भी पूर्व-मौजूद श्रृंखला या श्रेणियों को हटाएँ।

**चरण 1: चार्ट डेटा वर्कबुक तक पहुँचें**
अपने चार्ट से जुड़ी कार्यपुस्तिका पुनः प्राप्त करें:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**चरण 2: मौजूदा श्रृंखला और श्रेणियाँ साफ़ करें**
सुनिश्चित करें कि कोई अवशिष्ट डेटा बिंदु न हो:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### चार्ट में श्रृंखला जोड़ना

#### अवलोकन
अपने चार्ट को अनेक श्रृंखलाओं से भरें, जिनमें से प्रत्येक को उपस्थिति और व्यवहार के लिए अनुकूलित किया गया हो।

**चरण 1: क्रमिक रूप से श्रृंखला जोड़ें**
श्रृंखला जोड़ने के लिए सूचकांकों के माध्यम से लूप करें:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // श्रृंखला को अनुकूलित करें
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### चार्ट में श्रेणियाँ और डेटा बिंदु जोड़ना

#### अवलोकन
श्रेणियाँ कॉन्फ़िगर करें और लेबल के लिए विशिष्ट स्वरूपण के साथ डेटा बिंदु जोड़ें.

**चरण 1: श्रेणियाँ जोड़ें**
प्रत्येक श्रेणी के लिए सूचकांकों को लूप करें:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**चरण 2: प्रत्येक श्रृंखला में डेटा बिंदु जोड़ें**
वर्तमान श्रेणी के लिए प्रत्येक श्रृंखला को दोहराएँ:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // डेटा बिंदु प्रारूप सेटिंग
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // अंतिम श्रृंखला के लिए लेबल स्वरूपण
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // प्रदर्शन विकल्प समायोजित करें
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // लेबल स्थिति समायोजित करें
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### प्रस्तुति को सहेजना

#### अवलोकन
एक बार जब आप अपना चार्ट कॉन्फ़िगर कर लें, तो प्रस्तुति को निर्दिष्ट निर्देशिका में सहेजें।

**चरण 1: प्रस्तुति सहेजें**
उपयोग `save` परिवर्तन लिखने की विधि:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

अब आप सीख चुके हैं कि Aspose.Slides का उपयोग करके जावा में डोनट चार्ट कैसे बनाएं और कस्टमाइज़ करें। ये चरण आपके प्रस्तुतियों में परिष्कृत डेटा विज़ुअलाइज़ेशन को एकीकृत करने के लिए एक आधार प्रदान करते हैं।

**अगले कदम:**
- Aspose.Slides में उपलब्ध विभिन्न चार्ट प्रकारों के साथ प्रयोग करें।
- अपनी ब्रांडिंग आवश्यकताओं के अनुरूप रंग, फ़ॉन्ट और शैली जैसे अतिरिक्त अनुकूलन विकल्पों का अन्वेषण करें।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}