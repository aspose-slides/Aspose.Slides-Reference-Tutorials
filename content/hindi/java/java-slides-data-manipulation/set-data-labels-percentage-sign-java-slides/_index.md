---
title: जावा स्लाइड में डेटा लेबल प्रतिशत साइन सेट करें
linktitle: जावा स्लाइड में डेटा लेबल प्रतिशत साइन सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में प्रतिशत चिह्नों के साथ डेटा लेबल सेट करना सीखें। चरण-दर-चरण मार्गदर्शन और स्रोत कोड के साथ आकर्षक चार्ट बनाएं।
type: docs
weight: 17
url: /hi/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## जावा के लिए Aspose.Slides में सेट डेटा लेबल प्रतिशत साइन इन का परिचय

इस गाइड में, हम आपको जावा के लिए Aspose.Slides का उपयोग करके प्रतिशत चिह्न के साथ डेटा लेबल सेट करने की प्रक्रिया के बारे में बताएंगे। हम एक स्टैक्ड कॉलम चार्ट के साथ एक पावरपॉइंट प्रेजेंटेशन बनाएंगे और प्रतिशत प्रदर्शित करने के लिए डेटा लेबल कॉन्फ़िगर करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Slides जोड़ा गया है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: एक नई प्रस्तुति बनाएं

सबसे पहले, हम Aspose.Slides का उपयोग करके एक नई PowerPoint प्रस्तुति बनाते हैं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएं
Presentation presentation = new Presentation();
```

## चरण 2: एक स्लाइड और चार्ट जोड़ें

इसके बाद, हम प्रेजेंटेशन में एक स्लाइड और एक स्टैक्ड कॉलम चार्ट जोड़ते हैं।

```java
// स्लाइड का संदर्भ प्राप्त करें
ISlide slide = presentation.getSlides().get_Item(0);

// स्लाइड पर PercentsStackedColumn चार्ट जोड़ें
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## चरण 3: एक्सिस नंबर प्रारूप कॉन्फ़िगर करें

प्रतिशत प्रदर्शित करने के लिए, हमें चार्ट के ऊर्ध्वाधर अक्ष के लिए संख्या प्रारूप को कॉन्फ़िगर करने की आवश्यकता है।

```java
//NumberFormatLinkedToSource को गलत पर सेट करें
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## चरण 4: चार्ट डेटा जोड़ें

हम श्रृंखला और डेटा बिंदु बनाकर चार्ट में डेटा जोड़ते हैं। इस उदाहरण में, हम उनके संबंधित डेटा बिंदुओं के साथ दो श्रृंखलाएँ जोड़ते हैं।

```java
//चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// नई श्रृंखला जोड़ें
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// नई श्रृंखला जोड़ें
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## चरण 5: डेटा लेबल अनुकूलित करें

अब, आइए डेटा लेबल के स्वरूप को अनुकूलित करें।

```java
// लेबलफ़ॉर्मेट गुण सेट करना
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## चरण 6: प्रस्तुति सहेजें

अंत में, हम प्रेजेंटेशन को PowerPoint फ़ाइल में सहेजते हैं।

```java
// डिस्क पर प्रेजेंटेशन लिखें
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

इतना ही! आपने जावा के लिए Aspose.Slides का उपयोग करके प्रतिशत प्रदर्शित करने के लिए स्टैक्ड कॉलम चार्ट और कॉन्फ़िगर किए गए डेटा लेबल के साथ सफलतापूर्वक एक PowerPoint प्रस्तुति बनाई है।

## जावा स्लाइड में सेट डेटा लेबल प्रतिशत साइन के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएं
Presentation presentation = new Presentation();
// स्लाइड का संदर्भ प्राप्त करें
ISlide slide = presentation.getSlides().get_Item(0);
// स्लाइड पर PercentsStackedColumn चार्ट जोड़ें
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
//NumberFormatLinkedToSource को गलत पर सेट करें
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
//चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// नई श्रृंखला जोड़ें
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// श्रृंखला का भरण रंग सेट करना
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// लेबलफ़ॉर्मेट गुण सेट करना
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// नई श्रृंखला जोड़ें
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// भरण प्रकार और रंग सेट करना
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// डिस्क पर प्रेजेंटेशन लिखें
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस गाइड का पालन करके, आपने सीखा है कि प्रतिशत-आधारित डेटा लेबल के साथ आकर्षक प्रस्तुतियाँ कैसे बनाई जाती हैं, जो विशेष रूप से व्यावसायिक रिपोर्ट, शैक्षिक सामग्री और अन्य में जानकारी को प्रभावी ढंग से संप्रेषित करने के लिए उपयोगी हो सकती हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट श्रृंखला के रंग कैसे बदल सकता हूँ?

 आप इसका उपयोग करके चार्ट श्रृंखला का भरण रंग बदल सकते हैं`setFill` विधि जैसा कि उदाहरण में दिखाया गया है।

### क्या मैं डेटा लेबल के फ़ॉन्ट आकार को अनुकूलित कर सकता हूँ?

 हाँ, आप सेट करके डेटा लेबल के फ़ॉन्ट आकार को अनुकूलित कर सकते हैं`setFontHeight` संपत्ति जैसा कि कोड में दर्शाया गया है।

### मैं चार्ट में और श्रृंखला कैसे जोड़ सकता हूँ?

 आप इसका उपयोग करके चार्ट में अतिरिक्त श्रृंखला जोड़ सकते हैं`add` पर विधि`IChartSeriesCollection` वस्तु।
