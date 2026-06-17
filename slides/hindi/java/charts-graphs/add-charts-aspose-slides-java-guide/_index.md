---
date: '2026-06-03'
description: जानें कैसे aspose slides maven dependency के साथ charts जोड़ें, डेटा
  लेबल कॉन्फ़िगर करें, और Java प्रस्तुतियों में डायनेमिक charts उत्पन्न करें.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: प्रस्तुतियों में Charts जोड़ें और कॉन्फ़िगर
  करें Aspose.Slides for Java का उपयोग करके'
url: /hi/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: प्रस्तुतियों में चार्ट जोड़ें और कॉन्फ़िगर करें Aspose.Slides for Java का उपयोग करके

## परिचय
The **aspose slides maven dependency** Java डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint फ़ाइलें बनाने, संशोधित करने और समृद्ध करने की अनुमति देता है बिना PowerPoint को खोले। कई व्यावसायिक और शैक्षणिक परिदृश्यों में, मैन्युअल रूप से चार्ट डालना समय‑साध्य और त्रुटिप्रवण होता है। यह ट्यूटोरियल आपको चरण‑दर‑चरण दिखाता है कि कैसे एक बबल चार्ट जोड़ें, डेटा लेबल को वर्कशीट सेल्स से बाइंड करें, और परिणाम को सहेजें—सभी **aspose slides maven dependency** का उपयोग करके एक साफ़, दोहराने योग्य तरीके से।

**आप क्या सीखेंगे**
- aspose slides maven dependency के साथ चार्ट कैसे जोड़ें
- Maven या Gradle का उपयोग करके Java प्रोजेक्ट सेटअप करना
- मौजूदा प्रस्तुति लोड करना और बबल चार्ट सम्मिलित करना
- सेल रेफ़रेंसेज़ का उपयोग करके डेटा लेबल कॉन्फ़िगर करना (डेटा लेबल चार्ट जोड़ें)
- अपडेटेड फ़ाइल को बाद में वितरण के लिए सहेजना
- डायनेमिक चार्ट जेनरेशन और प्रेजेंटेशन चार्ट वर्कफ़्लो बनाने जैसे वास्तविक‑विश्व उपयोग केस

## त्वरित उत्तर
- **कौन सा Maven आर्टिफैक्ट चार्ट क्षमताएँ जोड़ता है?** `com.aspose:aspose-slides:25.4` (or latest)  
- **क्या मैं डेटा लेबल को Excel‑स्टाइल सेल्स से बाइंड कर सकता हूँ?** हाँ – `ChartDataLabel` को `setDataLabelFormat` और सेल रेफ़रेंसेज़ के साथ उपयोग करें।  
- **क्या उत्पादन के लिए लाइसेंस आवश्यक है?** पूरा लाइसेंस मूल्यांकन वाटरमार्क को हटाता है और सभी सुविधाओं को अनलॉक करता है।  
- **क्या यह Java 11+ पर काम करेगा?** बिल्कुल; लाइब्रेरी Java 8 से लेकर Java 21 तक संगत है।  
- **कितने चार्ट प्रकार समर्थित हैं?** 70 से अधिक अलग-अलग चार्ट प्रकार, जिसमें बबल, रडार, और स्टॉक चार्ट शामिल हैं।

## aspose slides maven dependency क्या है?
**aspose slides maven dependency** एक Maven‑संगत पैकेज है जो Java में PowerPoint (PPTX, PPT, ODP) फ़ाइलें बनाने और संपादित करने के लिए पूर्ण‑विशेषताओं वाला API प्रदान करता है। इस डिपेंडेंसी को अपने `pom.xml` या `build.gradle` में जोड़कर आप 70 से अधिक चार्ट प्रकार, 150+ स्लाइड लेआउट, और शैप्स, एनीमेशन, तथा मेटाडेटा को बिना Office स्थापित किए मैनिपुलेट करने की क्षमता प्राप्त करते हैं।

## चार्ट ऑटोमेशन के लिए aspose slides maven dependency क्यों उपयोग करें?
Aspose.Slides मानक सर्वर हार्डवेयर पर एक सेकंड से कम समय में हजारों स्लाइड डेक्स को प्रोसेस करता है, **70+ चार्ट प्रकार** का समर्थन करता है, और पूरी फ़ाइल को मेमोरी में लोड किए बिना **10,000 स्लाइड** तक की प्रस्तुतियों को रेंडर कर सकता है। ये मापनीय क्षमताएँ इसे एंटरप्राइज़‑ग्रेड डायनेमिक चार्ट जेनरेशन के लिए आदर्श बनाती हैं, जहाँ प्रदर्शन और स्केलेबिलिटी अनिवार्य हैं।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK)** 8 या नया (Java 11+ अनुशंसित)।  
- **Maven** 3.6+ **या** **Gradle** 6+.  
- **Aspose.Slides for Java** लाइब्रेरी (aspose slides maven dependency, संस्करण 25.4 या बाद का)।  
- Java कलेक्शन्स और फ़ाइल I/O की बुनियादी परिचितता।  
- यदि आप कोड को ट्रायल अवधि के बाद चलाने की योजना बनाते हैं तो एक इवैल्यूएशन या पूर्ण लाइसेंस फ़ाइल (`license.json`)।

## Aspose.Slides का उपयोग करके स्लाइड में चार्ट कैसे जोड़ें?
लक्षित प्रस्तुति लोड करें, इच्छित स्लाइड पर एक नया चार्ट शेप बनाएं, और चार्ट प्रकार निर्दिष्ट करें (इस उदाहरण में बबल)। लाइब्रेरी को रेफ़रेंस करने के बाद पूरी प्रक्रिया **तीन संक्षिप्त कोड लाइनों** में की जा सकती है, जिससे यह तेज़ प्रोटोटाइपिंग और प्रोडक्शन पाइपलाइन के लिए उपयुक्त बनता है।

### चरण 1: aspose slides maven dependency जोड़ें
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
These snippets pull the full Aspose.Slides API—including chart support—directly from Maven Central.

### चरण 2: प्रस्तुति लोड करें और बबल चार्ट सम्मिलित करें
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### चरण 3: चार्ट की डेटा सीरीज़ और लेबल कॉन्फ़िगर करें
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### चरण 4: संशोधित प्रस्तुति सहेजें
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## सेल रेफ़रेंसेज़ का उपयोग करके डेटा लेबल कैसे कॉन्फ़िगर करें?
डेटा लेबल को बाहरी सेल मानों से बाइंड किया जा सकता है, जो Excel की “Link to Cell” सुविधा को प्रतिबिंबित करता है। यह तरीका हार्ड‑कोडेड मानों को समाप्त करता है और **डायनेमिक चार्ट जेनरेशन** को सक्षम बनाता है जहाँ लेबल सामग्री मूल डेटा में बदलाव के साथ स्वचालित रूप से अपडेट होती है। प्रत्येक लेबल को एक विशिष्ट वर्कबुक सेल से लिंक करके, आप सुनिश्चित करते हैं कि स्रोत डेटा में कोई भी परिवर्तन तुरंत प्रस्तुति में परिलक्षित हो, जिससे रखरखाव प्रयास कम होता है और पुरानी जानकारी के जोखिम को न्यूनतम किया जाता है।

### सीधा उत्तर
`chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` को कॉल करें और एक `DataLabelFormat` पास करें जो सेल एड्रेस जैसे `"Sheet1!A2"` को रेफ़रेंस करता हो। Aspose.Slides रनटाइम पर रेफ़रेंस को हल करता है, और सेल का वर्तमान मान चार्ट लेबल में डालता है।

### कदम‑दर‑कदम
1. जिस सीरीज़ को आप लेबल करना चाहते हैं उसे पहचानें।  
2. प्रत्येक डेटा पॉइंट के लिए `IDataLabel` ऑब्जेक्ट प्राप्त करें।  
3. `CellReference` के लिए कॉन्फ़िगर किए गए `DataLabelFormat` के साथ `setDataLabelFormat` का उपयोग करें।  
4. वैकल्पिक रूप से फ़ॉन्ट, रंग, और डिस्प्ले विकल्पों को कस्टमाइज़ करें।

## संशोधित प्रस्तुति कैसे सहेजें?
सेव करना एक सिंगल‑मेथड कॉल है जो इन‑मेमोरी `Presentation` ऑब्जेक्ट को फ़ाइल पाथ या आउटपुट स्ट्रीम में लिखता है। आप उपयुक्त `SaveFormat` एन्‍युम पास करके आउटपुट फॉर्मेट (PPTX, PDF, ODP) भी चुन सकते हैं। यह ऑपरेशन परिणाम को सीधे डिस्क पर स्ट्रीम करता है, और जब `Presentation` इंस्टेंस बंद हो जाता है या स्कोप से बाहर हो जाता है तो सभी नेटिव रिसोर्सेज़ स्वचालित रूप से रिलीज़ हो जाते हैं, जिससे बड़े डेक्स के लिए भी मेमोरी उपयोग कम रहता है।

### सीधा उत्तर
`presentation.save("output.pptx", SaveFormat.Pptx)` को कॉल करें; लाइब्रेरी परिणाम को सीधे डिस्क पर स्ट्रीम करती है, और जब `Presentation` इंस्टेंस बंद हो जाता है या स्कोप से बाहर हो जाता है तो सभी नेटिव रिसोर्सेज़ स्वचालित रूप से रिलीज़ हो जाते हैं।

## व्यावहारिक अनुप्रयोग
1. **व्यावसायिक रिपोर्ट्स:** डेटाबेस डंप से स्वचालित रूप से त्रैमासिक बिक्री चार्ट जेनरेट करें।  
2. **शैक्षणिक लेक्चर:** प्रत्येक क्लास सत्र के लिए लाइव रिसर्च डेटा को लेक्चर स्लाइड्स में पुल करें।  
3. **सेल्स पिचेज़:** क्लाइंट‑स्पेसिफिक परफॉर्मेंस डैशबोर्ड तुरंत बनाएं।  
4. **प्रोजेक्ट मैनेजमेंट:** डायनेमिक डेटा लेबल्स के साथ गैंट‑स्टाइल टाइमलाइन को विज़ुअलाइज़ करें।  
5. **मार्केटिंग एनालिटिक्स:** प्रेजेंटेशन में कैंपेन KPI एम्बेड करें जो नए मेट्रिक्स आने पर अपडेट होते हैं।

## प्रदर्शन विचार
- **मेमोरी मैनेजमेंट:** नेटीव मेमोरी को तुरंत मुक्त करने के लिए try‑with‑resources या स्पष्ट `presentation.dispose()` का उपयोग करें।  
- **बड़े डेटा सेट:** जब 10,000 से अधिक डेटा पॉइंट्स को हैंडल कर रहे हों, तो `ChartDataWorkbook` के माध्यम से चार्ट डेटा पॉप्युलेट करें ताकि पूरे डेटा सेट को Java ऑब्जेक्ट्स में लोड करने से बचा जा सके।  
- **थ्रेड सुरक्षा:** प्रत्येक थ्रेड को अपना `Presentation` इंस्टेंस उपयोग करना चाहिए; API साझा ऑब्जेक्ट्स के बीच थ्रेड‑सेफ़ नहीं है।  

## सामान्य समस्याएँ और समाधान
**समस्या:** “License file not found.”  
**समाधान:** `license.json` को क्लासपाथ में रखें और किसी भी API उपयोग से पहले `License license = new License(); license.setLicense("license.json");` को कॉल करें।  

**समस्या:** “Chart appears blank after saving.”  
**समाधान:** सुनिश्चित करें कि चार्ट का डेटा वर्कबुक प्रस्तुति के साथ सहेजा गया है (`presentation.getCharts().setDataWorkbook(chartWorkbook);`)।  

**समस्या:** “Data labels show “#REF!” errors.”  
**समाधान:** जांचें कि सेल रेफ़रेंस स्ट्रिंग सटीक शीट नाम और एड्रेस से मेल खाती है, और रेफ़रेंस किया गया वर्कबुक चार्ट से जुड़ा हुआ है।  

## अक्सर पूछे जाने वाले प्रश्न
**Q:** क्या मैं बबल के अलावा अन्य चार्ट प्रकार जोड़ सकता हूँ?  
**A:** हाँ, `ChartType` एन्यूमरेशन में लाइन, बार, पाई, रडार, स्टॉक, और 70 से अधिक अतिरिक्त प्रकार शामिल हैं।  

**Q:** क्या aspose slides maven dependency OpenJDK के साथ काम करता है?  
**A:** बिल्कुल; यह OpenJDK 8‑21 के साथ पूरी तरह संगत है और सभी प्रमुख ऑपरेटिंग सिस्टम पर चलता है।  

**Q:** मैं मौजूदा Excel फ़ाइल से चार्ट कैसे एम्बेड करूँ?  
**A:** `WorkbookFactory.create(new FileInputStream("data.xlsx"))` के साथ Excel वर्कबुक लोड करें, फिर सेल रेफ़रेंसेज़ सेट करने से पहले चार्ट के `ChartDataWorkbook` को उस वर्कबुक से बाइंड करें।  

**Q:** क्या प्रति स्लाइड चार्ट की संख्या पर कोई सीमा है?  
**A:** व्यावहारिक रूप से नहीं—Aspose.Slides प्रति स्लाइड दर्जनों चार्ट संभाल सकता है, केवल उपलब्ध मेमोरी द्वारा सीमित।  

**Q:** अंतिम प्रस्तुति को किस फॉर्मेट में एक्सपोर्ट कर सकता हूँ?  
**A:** PPTX, PPT, ODP, PDF, XPS, HTML, और PNG तथा JPEG जैसे इमेज फॉर्मेट भी समर्थित हैं।  

## संसाधन
- [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/) – download the latest library binaries.  
- [Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) – comprehensive API reference and guides.  
- [Aspose.Slides for Java डाउनलोड करें](https://releases.aspose.com/slides/java/) – direct download page for the Maven/Gradle packages.  
- [लाइसेंस खरीदें](https://purchase.aspose.com/buy) – obtain a full commercial license.  
- [नि:शुल्क ट्रायल](https://releases.aspose.com/slides/java/) – start with a trial to evaluate features.  
- [अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) – request a temporary key for extended evaluation.  
- [Aspose सपोर्ट फ़ोरम](https://forum.aspose.com/c/slides/11) – get help from the community and Aspose engineers.  

## निष्कर्ष
अब आपके पास **aspose slides maven dependency** का उपयोग करके Java प्रस्तुतियों में चार्ट जोड़ने, कॉन्फ़िगर करने और सहेजने के लिए एक पूर्ण, अंत‑से‑अंत गाइड है। ऊपर दिए गए चरणों का पालन करके आप चार्ट निर्माण को ऑटोमेट कर सकते हैं, डेटा लेबल को लाइव सेल वैल्यूज़ से बाइंड कर सकते हैं, और स्केल पर प्रोफेशनल‑ग्रेड डेक्स जेनरेट कर सकते हैं। अन्य चार्ट प्रकारों के साथ प्रयोग करें, एनीमेशन API को एक्सप्लोर करें, और इस वर्कफ़्लो को अपनी रिपोर्टिंग पाइपलाइन में इंटीग्रेट करें अधिकतम प्रभाव के लिए।

---  
**अंतिम अपडेट:** 2026-06-03  
**परीक्षित संस्करण:** Aspose.Slides for Java 25.4  
**लेखक:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## संबंधित ट्यूटोरियल

- [Aspose.Slides Java के साथ प्रस्तुतियों को बनाना और कॉन्फ़िगर करना: चरण‑दर‑चरण गाइड](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Aspose.Slides Maven के साथ PPTX Java बनाएं – ऑटोमेशन गाइड](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [Aspose.Slides के साथ Java में चार्ट बनाना: एक व्यापक गाइड](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}