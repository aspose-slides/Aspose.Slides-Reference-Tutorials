---
title: जावा स्लाइड्स में इनवर्ट फिल कलर चार्ट सेट करें
linktitle: जावा स्लाइड्स में इनवर्ट फिल कलर चार्ट सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके जावा स्लाइड चार्ट के लिए इनवर्ट फ़िल रंग सेट करना सीखें। इस चरण-दर-चरण मार्गदर्शिका और स्रोत कोड के साथ अपने चार्ट विज़ुअलाइज़ेशन को बढ़ाएं।
type: docs
weight: 22
url: /hi/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

## जावा स्लाइड्स में इनवर्ट फिल कलर चार्ट सेट करने का परिचय

इस ट्यूटोरियल में, हम दिखाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में चार्ट के लिए इनवर्ट फिल कलर कैसे सेट करें। जब आप किसी विशिष्ट रंग के साथ चार्ट में नकारात्मक मानों को हाइलाइट करना चाहते हैं तो भरण रंग को उलटना एक उपयोगी सुविधा है। हम इसे प्राप्त करने के लिए चरण-दर-चरण निर्देश और स्रोत कोड प्रदान करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

1. जावा लाइब्रेरी के लिए Aspose.Slides स्थापित।
2. जावा विकास पर्यावरण की स्थापना।

## चरण 1: एक प्रेजेंटेशन बनाएं

सबसे पहले, हमें अपना चार्ट जोड़ने के लिए एक प्रेजेंटेशन बनाना होगा। प्रेजेंटेशन बनाने के लिए आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: एक चार्ट जोड़ें

इसके बाद, हम प्रेजेंटेशन में एक क्लस्टर्ड कॉलम चार्ट जोड़ेंगे। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## चरण 3: चार्ट डेटा सेट करें

अब, श्रृंखला और श्रेणियों सहित चार्ट डेटा सेट करें:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// नई श्रृंखला और श्रेणियां जोड़ना
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## चरण 4: श्रृंखला डेटा पॉप्युलेट करें

अब, आइए चार्ट के लिए श्रृंखला डेटा भरें:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## चरण 5: इनवर्ट फिल कलर सेट करें

चार्ट श्रृंखला के लिए इनवर्ट फ़िल रंग सेट करने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

उपरोक्त कोड में, हम नकारात्मक मानों के लिए रंग को उल्टा करने के लिए श्रृंखला सेट करते हैं और उल्टे भरण के लिए रंग निर्दिष्ट करते हैं।

## चरण 6: प्रस्तुति सहेजें

अंत में, प्रस्तुति को चार्ट के साथ सहेजें:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में सेट इनवर्ट फिल कलर चार्ट के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// नई श्रृंखला और श्रेणियां जोड़ना
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// पहली चार्ट श्रृंखला लें और श्रृंखला डेटा पॉप्युलेट करें।
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने आपको दिखाया है कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में चार्ट के लिए इनवर्ट फिल कलर कैसे सेट करें। यह सुविधा आपको अपने चार्ट में नकारात्मक मानों को एक विशिष्ट रंग के साथ उजागर करने की अनुमति देती है, जिससे आपका डेटा अधिक जानकारीपूर्ण हो जाता है।

## अक्सर पूछे जाने वाले प्रश्न

इस अनुभाग में, हम जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में एक चार्ट के लिए इनवर्ट फिल रंग सेट करने से संबंधित कुछ सामान्य प्रश्नों को संबोधित करेंगे।

### मैं जावा के लिए Aspose.Slides कैसे स्थापित करूं?

 आप अपने जावा प्रोजेक्ट में Aspose.Slides JAR फ़ाइलों को शामिल करके Java के लिए Aspose.Slides इंस्टॉल कर सकते हैं। आप लाइब्रेरी को यहां से डाउनलोड कर सकते हैं[जावा डाउनलोड पेज के लिए Aspose.Slides](https://releases.aspose.com/slides/java/). अपने विशिष्ट विकास परिवेश के लिए दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

### क्या मैं चार्ट श्रृंखला में उल्टे भरण के लिए रंग अनुकूलित कर सकता हूँ?

हां, आप चार्ट श्रृंखला में उल्टे भरण के लिए रंग को अनुकूलित कर सकते हैं। दिए गए कोड उदाहरण में,`series.getInvertedSolidFillColor().setColor(Color.RED)` लाइन उल्टे भरण के लिए रंग को लाल पर सेट करती है। आप प्रतिस्थापित कर सकते हैं`Color.RED` अपनी पसंद के किसी अन्य रंग के साथ.

### मैं जावा के लिए Aspose.Slides में चार्ट प्रकार को कैसे संशोधित कर सकता हूं?

 आप चार्ट प्रकार को बदलकर संशोधित कर सकते हैं`ChartType` प्रेजेंटेशन में चार्ट जोड़ते समय पैरामीटर। कोड उदाहरण में, हमने उपयोग किया`ChartType.ClusteredColumn` . आप उपयुक्त निर्दिष्ट करके अन्य चार्ट प्रकार जैसे लाइन चार्ट, बार चार्ट, पाई चार्ट इत्यादि का पता लगा सकते हैं`ChartType` एनम मान.

### मैं चार्ट में एकाधिक डेटा शृंखला कैसे जोड़ूं?

 किसी चार्ट में एकाधिक डेटा श्रृंखला जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`chart.getChartData().getSeries().add(...)` प्रत्येक श्रृंखला के लिए विधि जिसे आप जोड़ना चाहते हैं। अपने चार्ट को एकाधिक श्रृंखलाओं से भरने के लिए प्रत्येक श्रृंखला के लिए उचित डेटा बिंदु और लेबल प्रदान करना सुनिश्चित करें।

### क्या चार्ट उपस्थिति के अन्य पहलुओं को अनुकूलित करने का कोई तरीका है?

हाँ, आप जावा के लिए Aspose.Slides का उपयोग करके चार्ट उपस्थिति के विभिन्न पहलुओं को अनुकूलित कर सकते हैं, जिसमें अक्ष लेबल, शीर्षक, किंवदंतियाँ और बहुत कुछ शामिल हैं। चार्ट तत्वों और स्वरूप को अनुकूलित करने पर विस्तृत मार्गदर्शन के लिए दस्तावेज़ देखें।

### क्या मैं चार्ट को विभिन्न स्वरूपों में सहेज सकता हूँ?

 हाँ, आप Java के लिए Aspose.Slides का उपयोग करके चार्ट को विभिन्न स्वरूपों में सहेज सकते हैं। दिए गए कोड उदाहरण में, हमने प्रेजेंटेशन को PPTX फ़ाइल के रूप में सहेजा है। आप अलग-अलग उपयोग कर सकते हैं`SaveFormat` आपकी आवश्यकताओं के आधार पर इसे पीडीएफ, पीएनजी, या एसवीजी जैसे अन्य प्रारूपों में सहेजने के विकल्प।