---
"date": "2025-04-17"
"description": "Aspose.Slides for Java का उपयोग करके .NET प्रस्तुतियों में चार्ट बनाना और उन्हें कस्टमाइज़ करना सीखें। अपने प्रस्तुति डेटा विज़ुअलाइज़ेशन को बेहतर बनाने के लिए इस चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"title": "Aspose.Slides for Java&#58; .NET प्रस्तुतियों में चार्ट बनाना"
"url": "/hi/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java के लिए Aspose.Slides का उपयोग करके .NET प्रस्तुतियों में चार्ट बनाना
## परिचय
आकर्षक प्रस्तुतियाँ बनाने में अक्सर दर्शकों की समझ और जुड़ाव को बढ़ाने के लिए चार्ट जैसे विज़ुअल डेटा अभ्यावेदन को एकीकृत करना शामिल होता है। यदि आप एक डेवलपर हैं जो Aspose.Slides for Java का उपयोग करके अपने .NET प्रस्तुतियों में गतिशील, अनुकूलन योग्य चार्ट जोड़ना चाहते हैं, तो यह ट्यूटोरियल आपके लिए ही बनाया गया है। हम इस बात पर गहनता से चर्चा करेंगे कि आप प्रस्तुतियाँ कैसे आरंभ कर सकते हैं, विभिन्न चार्ट प्रकार जोड़ सकते हैं, चार्ट डेटा प्रबंधित कर सकते हैं और श्रृंखला डेटा को प्रभावी ढंग से प्रारूपित कर सकते हैं।
**आप क्या सीखेंगे:**
- अपने .NET वातावरण में Java के लिए Aspose.Slides को कैसे सेट अप और उपयोग करें।
- Aspose.Slides का उपयोग करके एक नई प्रस्तुति आरंभ करना।
- स्लाइडों में चार्ट जोड़ना और अनुकूलित करना.
- चार्ट डेटा कार्यपुस्तिकाओं का प्रबंधन करना.
- श्रृंखला डेटा को प्रारूपित करना, विशेष रूप से ऋणात्मक मानों को संभालना।
पूर्वापेक्षा अनुभाग में जाने से यह सुनिश्चित हो जाएगा कि आप आसानी से उसका अनुसरण करने के लिए पूरी तरह तैयार हैं।
## आवश्यक शर्तें
Aspose.Slides for Java के साथ चार्ट बनाने में आगे बढ़ने से पहले, आइए जानते हैं कि आपको क्या चाहिए:
### आवश्यक लाइब्रेरी और संस्करण
सुनिश्चित करें कि आपके पास निम्नलिखित निर्भरताएँ हैं:
- **जावा के लिए Aspose.Slides**: संस्करण 25.4 या बाद का.
### पर्यावरण सेटअप आवश्यकताएँ
- .NET अनुप्रयोगों का समर्थन करने वाला विकास वातावरण.
- जावा प्रोग्रामिंग अवधारणाओं की बुनियादी समझ।
### ज्ञान पूर्वापेक्षाएँ
- .NET अनुप्रयोग संदर्भ में प्रस्तुतियाँ बनाने की जानकारी।
- जावा निर्भरता और उनके प्रबंधन को समझना (मावेन/ग्रैडल)।
## Java के लिए Aspose.Slides सेट अप करना
Aspose.Slides का उपयोग शुरू करने के लिए, आपको इसे अपने प्रोजेक्ट में निर्भरता के रूप में शामिल करना होगा। यहाँ बताया गया है कि आप ऐसा कैसे कर सकते हैं:
### मावेन
अपने में निम्नलिखित निर्भरता जोड़ें `pom.xml` फ़ाइल:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### ग्रैडल
इसे अपने में शामिल करें `build.gradle` फ़ाइल:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### प्रत्यक्षत: डाउनलोड
वैकल्पिक रूप से, आप नवीनतम संस्करण यहाँ से डाउनलोड कर सकते हैं [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).
#### लाइसेंस प्राप्ति चरण
- **मुफ्त परीक्षण**: सुविधाओं का पता लगाने के लिए एक अस्थायी लाइसेंस के साथ शुरुआत करें।
- **खरीदना**व्यापक उपयोग के लिए लाइसेंस खरीदने पर विचार करें।
#### बुनियादी आरंभीकरण और सेटअप
यहां बताया गया है कि आप अपने कोड में Aspose.Slides को कैसे आरंभ करते हैं:
```java
import com.aspose.slides.Presentation;
// एक नया प्रेजेंटेशन ऑब्जेक्ट आरंभ करें
Presentation pres = new Presentation();
try {
    // आपका तर्क यहाँ...
} finally {
    if (pres != null) pres.dispose();
}
```
यह सेटअप सुनिश्चित करता है कि संसाधन प्रबंधन प्रभावी ढंग से किया जाए।
## कार्यान्वयन मार्गदर्शिका
हम आपको चरण-दर-चरण सुविधाओं के क्रियान्वयन के बारे में बताएंगे।
### प्रस्तुति आरंभ करना
**अवलोकन:**
प्रेजेंटेशन इंस्टेंस बनाना सभी आगामी कार्यों के लिए मंच तैयार करता है। यह सुविधा दिखाती है कि Aspose.Slides का उपयोग करके शुरुआत से कैसे शुरू किया जाए।
#### चरण 1: आवश्यक पैकेज आयात करें
```java
import com.aspose.slides.Presentation;
```
#### चरण 2: नया प्रेजेंटेशन ऑब्जेक्ट बनाएँ
इसे आप इस प्रकार कर सकते हैं:
```java
Presentation pres = new Presentation();
try {
    // आपका कोड तर्क यहाँ...
} finally {
    if (pres != null) pres.dispose(); // यह सुनिश्चित करता है कि संसाधन मुक्त हों
}
```
*इससे यह सुनिश्चित होता है कि उपयोग के बाद प्रस्तुति ऑब्जेक्ट का उचित तरीके से निपटान हो जाए, जिससे मेमोरी लीक को रोका जा सके।*
### स्लाइड में चार्ट जोड़ना
**अवलोकन:**
अपनी स्लाइड में चार्ट जोड़ने से डेटा विज़ुअलाइज़ेशन अधिक प्रभावी और आकर्षक बन सकता है।
#### चरण 1: आवश्यक पैकेज आयात करें
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```
#### चरण 2: प्रस्तुति आरंभ करें और चार्ट जोड़ें
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // चार्ट अनुकूलन के लिए अतिरिक्त तर्क...
} finally {
    if (pres != null) pres.dispose();
}
```
*यहां, हम निर्दिष्ट निर्देशांकों और आयामों पर पहली स्लाइड में एक क्लस्टर कॉलम चार्ट जोड़ते हैं।*
### चार्ट डेटा कार्यपुस्तिका प्रबंधित करना
**अवलोकन:**
अपने चार्ट की डेटा वर्कबुक को कुशलतापूर्वक प्रबंधित करने से आप श्रृंखलाओं और श्रेणियों को सहजता से प्रबंधित कर सकते हैं।
#### चरण 1: आवश्यक पैकेज आयात करें
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```
#### चरण 2: डेटा कार्यपुस्तिका तक पहुँचें और उसे साफ़ करें
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // मौजूदा डेटा साफ़ करें
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // आपका अनुकूलन तर्क यहाँ...
} finally {
    if (pres != null) pres.dispose();
}
```
*नई श्रृंखला और श्रेणियां जोड़ते समय कार्यपुस्तिका को साफ़ करना एक साफ़ स्लेट के साथ शुरू करने के लिए महत्वपूर्ण है।*
### चार्ट में श्रृंखला और श्रेणियाँ जोड़ना
**अवलोकन:**
यह सुविधा दिखाती है कि आप श्रृंखलाओं और श्रेणियों का प्रबंधन करके कैसे सार्थक डेटा बिंदु जोड़ सकते हैं।
#### चरण 1: श्रृंखला और श्रेणियाँ जोड़ें
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // मौजूदा श्रृंखला और श्रेणियाँ साफ़ करें
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // नई श्रृंखला और श्रेणियां जोड़ें
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // आगे अनुकूलन तर्क...
} finally {
    if (pres != null) pres.dispose();
}
```
*श्रृंखला और श्रेणियाँ जोड़ने से डेटा प्रस्तुति अधिक व्यवस्थित हो जाती है।*
### श्रृंखला डेटा भरना और स्वरूपण करना
**अवलोकन:**
अपने चार्ट को डेटा बिंदुओं से भरें और पठनीयता बढ़ाने के लिए स्वरूप को प्रारूपित करें, विशेष रूप से नकारात्मक मानों के साथ काम करते समय।
#### चरण 1: श्रृंखला डेटा भरें
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // श्रृंखला और श्रेणियाँ जोड़ें (पिछले तर्क का पुनः उपयोग करें)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // नकारात्मक मानों के लिए श्रृंखला प्रारूपित करें
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // प्रस्तुति सहेजें
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*यह अनुभाग दर्शाता है कि डेटा को कैसे पॉप्युलेट किया जाए और बेहतर विज़ुअलाइज़ेशन के लिए रंग फ़ॉर्मेटिंग कैसे लागू की जाए।*

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}