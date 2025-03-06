---
title: जावा स्लाइड्स में डेटा पॉइंट पर चार्ट मार्कर विकल्प
linktitle: जावा स्लाइड्स में डेटा पॉइंट पर चार्ट मार्कर विकल्प
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: कस्टम चार्ट मार्कर विकल्पों के साथ अपने जावा स्लाइड्स को ऑप्टिमाइज़ करें। Aspose.Slides for Java का उपयोग करके डेटा पॉइंट्स को विज़ुअली बेहतर बनाना सीखें। चरण-दर-चरण मार्गदर्शन और FAQ देखें।
weight: 14
url: /hi/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में डेटा पॉइंट पर चार्ट मार्कर विकल्पों का परिचय

जब प्रभावशाली प्रस्तुतियाँ बनाने की बात आती है, तो डेटा बिंदुओं पर चार्ट मार्करों को अनुकूलित और हेरफेर करने की क्षमता सभी अंतर ला सकती है। Aspose.Slides for Java के साथ, आपके पास अपने चार्ट को गतिशील और नेत्रहीन आकर्षक तत्वों में बदलने की शक्ति है।

## आवश्यक शर्तें

इससे पहले कि हम कोडिंग भाग में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा विकास पर्यावरण
- Aspose.Slides for Java लाइब्रेरी
- जावा एकीकृत विकास वातावरण (आईडीई)
- नमूना प्रस्तुति दस्तावेज़ (उदाहरणार्थ, "Test.pptx")

## चरण 1: वातावरण की स्थापना

सबसे पहले, सुनिश्चित करें कि आपके पास आवश्यक उपकरण इंस्टॉल और तैयार हैं। अपने IDE में एक Java प्रोजेक्ट बनाएँ और Aspose.Slides for Java लाइब्रेरी को आयात करें।

## चरण 2: प्रस्तुति लोड करना

आरंभ करने के लिए, अपना नमूना प्रस्तुति दस्तावेज़ लोड करें। दिए गए कोड में, हम मानते हैं कि दस्तावेज़ का नाम "Test.pptx" है।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## चरण 3: चार्ट बनाना

अब, आइए प्रेजेंटेशन में एक चार्ट बनाएं। इस उदाहरण में हम मार्कर के साथ एक लाइन चार्ट का उपयोग करेंगे।

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## चरण 4: चार्ट डेटा के साथ काम करना

चार्ट डेटा में हेरफेर करने के लिए, हमें चार्ट डेटा वर्कबुक तक पहुँचना होगा और डेटा सीरीज़ तैयार करनी होगी। हम डिफ़ॉल्ट सीरीज़ को साफ़ करेंगे और अपना कस्टम डेटा जोड़ेंगे।

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## चरण 5: कस्टम मार्कर जोड़ना

अब रोमांचक हिस्सा आता है - डेटा पॉइंट पर मार्कर को कस्टमाइज़ करना। हम इस उदाहरण में मार्कर के रूप में छवियों का उपयोग करेंगे।

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// डेटा बिंदुओं में कस्टम मार्कर जोड़ना
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// अन्य डेटा बिंदुओं के लिए दोहराएँ
// ...

// चार्ट श्रृंखला मार्कर का आकार बदलना
series.getMarker().setSize(15);
```

## चरण 6: प्रस्तुति को सहेजना

एक बार जब आप अपने चार्ट मार्करों को अनुकूलित कर लें, तो परिवर्तनों को क्रियान्वित होते देखने के लिए प्रस्तुति को सहेजें।

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में डेटा पॉइंट पर चार्ट मार्कर विकल्पों के लिए पूर्ण स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//डिफ़ॉल्ट चार्ट बनाना
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//डिफ़ॉल्ट चार्ट डेटा वर्कशीट इंडेक्स प्राप्त करना
int defaultWorksheetIndex = 0;
//चार्ट डेटा वर्कशीट प्राप्त करना
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//डेमो श्रृंखला हटाएं
chart.getChartData().getSeries().clear();
//नई श्रृंखला जोड़ें
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//चित्र सेट करें
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//चित्र सेट करें
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//पहली चार्ट श्रृंखला लें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//वहां नया बिंदु (1:3) जोड़ें.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//चार्ट श्रृंखला मार्कर बदलना
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

Aspose.Slides for Java के साथ, आप डेटा पॉइंट्स पर चार्ट मार्कर को कस्टमाइज़ करके अपनी प्रस्तुतियों को बेहतर बना सकते हैं। यह आपको अपने दर्शकों को आकर्षित करने वाली दिखने में आकर्षक और जानकारीपूर्ण स्लाइड बनाने की अनुमति देता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं डेटा बिंदुओं के लिए मार्कर का आकार कैसे बदल सकता हूँ?

 डेटा बिंदुओं के लिए मार्कर आकार बदलने के लिए, का उपयोग करें`series.getMarker().setSize()` विधि और वांछित आकार को तर्क के रूप में प्रदान करें।

### क्या मैं छवियों को कस्टम मार्कर के रूप में उपयोग कर सकता हूँ?

 हां, आप डेटा बिंदुओं के लिए कस्टम मार्कर के रूप में छवियों का उपयोग कर सकते हैं। भरण प्रकार को इस पर सेट करें`FillType.Picture` और वह छवि प्रदान करें जिसका आप उपयोग करना चाहते हैं।

### क्या Aspose.Slides for Java गतिशील चार्ट बनाने के लिए उपयुक्त है?

बिल्कुल! Aspose.Slides for Java आपके प्रस्तुतियों में गतिशील और इंटरैक्टिव चार्ट बनाने के लिए व्यापक क्षमताएं प्रदान करता है।

### क्या मैं Aspose.Slides का उपयोग करके चार्ट के अन्य पहलुओं को अनुकूलित कर सकता हूँ?

हां, आप Aspose.Slides for Java का उपयोग करके चार्ट के विभिन्न पहलुओं को अनुकूलित कर सकते हैं, जिसमें शीर्षक, अक्ष, डेटा लेबल आदि शामिल हैं।

### मैं Aspose.Slides for Java दस्तावेज़ और डाउनलोड कहां से प्राप्त कर सकता हूं?

 आप दस्तावेज़ यहां पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/) और लाइब्रेरी को यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
