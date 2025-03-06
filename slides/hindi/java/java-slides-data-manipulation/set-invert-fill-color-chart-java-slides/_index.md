---
title: जावा स्लाइड्स में इनवर्ट फिल कलर चार्ट सेट करें
linktitle: जावा स्लाइड्स में इनवर्ट फिल कलर चार्ट सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java Slides चार्ट के लिए इनवर्ट फिल कलर सेट करना सीखें। इस चरण-दर-चरण गाइड और स्रोत कोड के साथ अपने चार्ट विज़ुअलाइज़ेशन को बेहतर बनाएँ।
weight: 22
url: /hi/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## जावा स्लाइड्स में इनवर्ट फिल कलर चार्ट सेट करने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके Java Slides में चार्ट के लिए इनवर्ट फिल कलर सेट करने का तरीका दिखाएंगे। जब आप चार्ट में नेगेटिव वैल्यू को किसी खास रंग से हाइलाइट करना चाहते हैं, तो इनवर्ट फिल कलर एक उपयोगी फीचर है। हम इसे प्राप्त करने के लिए चरण-दर-चरण निर्देश और सोर्स कोड प्रदान करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. Aspose.Slides for Java लाइब्रेरी स्थापित की गई।
2. जावा विकास वातावरण की स्थापना.

## चरण 1: एक प्रस्तुति बनाएं

सबसे पहले, हमें अपना चार्ट जोड़ने के लिए एक प्रेजेंटेशन बनाना होगा। प्रेजेंटेशन बनाने के लिए आप निम्न कोड का उपयोग कर सकते हैं:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## चरण 2: चार्ट जोड़ें

इसके बाद, हम प्रेजेंटेशन में एक क्लस्टर्ड कॉलम चार्ट जोड़ेंगे। आप इसे इस तरह से कर सकते हैं:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## चरण 3: चार्ट डेटा सेट करें

अब, आइए श्रृंखला और श्रेणियों सहित चार्ट डेटा सेट करें:

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

## चरण 4: श्रृंखला डेटा भरें

अब, चार्ट के लिए श्रृंखला डेटा भरें:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## चरण 5: इनवर्ट भरण रंग सेट करें

चार्ट श्रृंखला के लिए उलटा भरण रंग सेट करने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

उपरोक्त कोड में, हमने ऋणात्मक मानों के लिए भरण रंग को उलटने के लिए श्रृंखला निर्धारित की है तथा उलटे भरण के लिए रंग निर्दिष्ट किया है।

## चरण 6: प्रेजेंटेशन सहेजें

अंत में, चार्ट के साथ प्रस्तुति को सहेजें:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में सेट इनवर्ट फिल कलर चार्ट के लिए पूरा स्रोत कोड

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
// पहले चार्ट श्रृंखला लें और श्रृंखला डेटा भरें।
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

इस ट्यूटोरियल में, हमने आपको Aspose.Slides for Java का उपयोग करके Java Slides में चार्ट के लिए इनवर्ट फिल कलर सेट करने का तरीका दिखाया है। यह सुविधा आपको अपने चार्ट में नकारात्मक मानों को एक विशिष्ट रंग के साथ हाइलाइट करने की अनुमति देती है, जिससे आपका डेटा अधिक दृश्यमान रूप से जानकारीपूर्ण बन जाता है।

## अक्सर पूछे जाने वाले प्रश्न

इस अनुभाग में, हम Aspose.Slides for Java का उपयोग करके Java स्लाइड्स में चार्ट के लिए इनवर्ट भरण रंग सेट करने से संबंधित कुछ सामान्य प्रश्नों को संबोधित करेंगे।

### मैं Java के लिए Aspose.Slides कैसे स्थापित करूं?

 आप अपने जावा प्रोजेक्ट में Aspose.Slides JAR फ़ाइलें शामिल करके जावा के लिए Aspose.Slides स्थापित कर सकते हैं। आप लाइब्रेरी को यहाँ से डाउनलोड कर सकते हैं[Aspose.Slides for Java डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/)अपने विशिष्ट विकास परिवेश के लिए दस्तावेज़ में दिए गए स्थापना निर्देशों का पालन करें।

### क्या मैं चार्ट श्रृंखला में उल्टे भरण के लिए रंग को अनुकूलित कर सकता हूँ?

हां, आप चार्ट श्रृंखला में उल्टे भरण के लिए रंग को अनुकूलित कर सकते हैं। दिए गए कोड उदाहरण में,`series.getInvertedSolidFillColor().setColor(Color.RED)` लाइन उल्टे भरण के लिए लाल रंग सेट करती है। आप इसे बदल सकते हैं`Color.RED` अपनी पसंद के किसी भी अन्य रंग के साथ।

### मैं Java के लिए Aspose.Slides में चार्ट प्रकार को कैसे संशोधित कर सकता हूं?

 आप चार्ट प्रकार को बदलकर संशोधित कर सकते हैं`ChartType` प्रेजेंटेशन में चार्ट जोड़ते समय पैरामीटर। कोड उदाहरण में, हमने इस्तेमाल किया`ChartType.ClusteredColumn` आप उपयुक्त चार्ट निर्दिष्ट करके अन्य चार्ट प्रकार जैसे लाइन चार्ट, बार चार्ट, पाई चार्ट आदि का पता लगा सकते हैं।`ChartType` enum मान.

### मैं एक चार्ट में एकाधिक डेटा श्रृंखला कैसे जोड़ूं?

 चार्ट में एकाधिक डेटा श्रृंखला जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`chart.getChartData().getSeries().add(...)` प्रत्येक श्रृंखला के लिए विधि जिसे आप जोड़ना चाहते हैं। अपने चार्ट को कई श्रृंखलाओं से भरने के लिए प्रत्येक श्रृंखला के लिए उपयुक्त डेटा बिंदु और लेबल प्रदान करना सुनिश्चित करें।

### क्या चार्ट के स्वरूप के अन्य पहलुओं को अनुकूलित करने का कोई तरीका है?

हां, आप Aspose.Slides for Java का उपयोग करके चार्ट की उपस्थिति के विभिन्न पहलुओं को अनुकूलित कर सकते हैं, जिसमें अक्ष लेबल, शीर्षक, लेजेंड और बहुत कुछ शामिल है। चार्ट तत्वों और उपस्थिति को अनुकूलित करने के बारे में विस्तृत मार्गदर्शन के लिए दस्तावेज़ देखें।

### क्या मैं चार्ट को विभिन्न प्रारूपों में सहेज सकता हूँ?

 हां, आप Aspose.Slides for Java का उपयोग करके चार्ट को विभिन्न प्रारूपों में सहेज सकते हैं। दिए गए कोड उदाहरण में, हमने प्रस्तुति को PPTX फ़ाइल के रूप में सहेजा है। आप अलग-अलग प्रारूपों का उपयोग कर सकते हैं`SaveFormat` आपकी आवश्यकताओं के आधार पर इसे पीडीएफ, पीएनजी या एसवीजी जैसे अन्य प्रारूपों में सहेजने के विकल्प उपलब्ध हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
