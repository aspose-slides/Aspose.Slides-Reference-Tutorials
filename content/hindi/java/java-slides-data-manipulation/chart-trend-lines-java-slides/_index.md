---
title: जावा स्लाइड्स में चार्ट ट्रेंड लाइन्स
linktitle: जावा स्लाइड्स में चार्ट ट्रेंड लाइन्स
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में विभिन्न ट्रेंड लाइनें जोड़ने का तरीका जानें। प्रभावी डेटा विज़ुअलाइज़ेशन के लिए कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 15
url: /hi/java/data-manipulation/chart-trend-lines-java-slides/
---

## जावा स्लाइड्स में चार्ट ट्रेंड लाइन्स का परिचय: एक चरण-दर-चरण मार्गदर्शिका

इस व्यापक गाइड में, हम यह पता लगाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में चार्ट ट्रेंड लाइन कैसे बनाई जाए। चार्ट ट्रेंड लाइनें आपकी प्रस्तुतियों के लिए एक मूल्यवान अतिरिक्त हो सकती हैं, जो डेटा रुझानों को प्रभावी ढंग से देखने और विश्लेषण करने में मदद करती हैं। हम आपको स्पष्ट स्पष्टीकरण और कोड उदाहरणों के साथ प्रक्रिया के बारे में बताएंगे।

## आवश्यक शर्तें

इससे पहले कि हम चार्ट ट्रेंड लाइनें बनाने में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

- जावा विकास पर्यावरण
- जावा लाइब्रेरी के लिए Aspose.Slides
- आपकी पसंद का एक कोड संपादक

## चरण 1: आरंभ करना

आइए आवश्यक वातावरण स्थापित करके और एक नई प्रस्तुति बनाकर शुरुआत करें:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि यह पहले से मौजूद नहीं है तो निर्देशिका बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// ख़ाली प्रस्तुतिकरण बनाना
Presentation pres = new Presentation();
```

हमने अपनी प्रस्तुति शुरू कर दी है, और अब हम एक क्लस्टर्ड कॉलम चार्ट जोड़ने के लिए तैयार हैं:

```java
// क्लस्टर्ड कॉलम चार्ट बनाना
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## चरण 2: घातीय रुझान रेखा जोड़ना

आइए हमारी चार्ट श्रृंखला में एक घातीय प्रवृत्ति रेखा जोड़कर शुरुआत करें:

```java
// चार्ट श्रृंखला 1 के लिए घातीय प्रवृत्ति रेखा जोड़ना
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## चरण 3: रैखिक रुझान रेखा जोड़ना

इसके बाद, हम अपनी चार्ट श्रृंखला में एक रेखीय प्रवृत्ति रेखा जोड़ेंगे:

```java
// चार्ट श्रृंखला 1 के लिए रैखिक प्रवृत्ति रेखा जोड़ना
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## चरण 4: लॉगरिदमिक ट्रेंड लाइन जोड़ना

अब, आइए एक अलग चार्ट श्रृंखला में एक लघुगणकीय प्रवृत्ति रेखा जोड़ें:

```java
// चार्ट श्रृंखला 2 के लिए लघुगणकीय प्रवृत्ति रेखा जोड़ना
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## चरण 5: मूविंग एवरेज ट्रेंड लाइन जोड़ना

हम एक चलती औसत प्रवृत्ति रेखा भी जोड़ सकते हैं:

```java
// चार्ट श्रृंखला 2 के लिए चलती औसत प्रवृत्ति रेखा जोड़ना
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## चरण 6: बहुपद प्रवृत्ति रेखा जोड़ना

एक बहुपद प्रवृत्ति रेखा जोड़ना:

```java
// चार्ट शृंखला 3 के लिए बहुपद प्रवृत्ति रेखा जोड़ना
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## चरण 7: पावर ट्रेंड लाइन जोड़ना

अंत में, आइए एक पावर ट्रेंड लाइन जोड़ें:

```java
// चार्ट श्रृंखला 3 के लिए पावर ट्रेंड लाइन जोड़ना
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## चरण 8: प्रस्तुति को सहेजना

अब जब हमने अपने चार्ट में विभिन्न ट्रेंड लाइनें जोड़ ली हैं, तो आइए प्रेजेंटेशन को सेव करें:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

बधाई हो! आपने जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में विभिन्न प्रकार की ट्रेंड लाइनों के साथ सफलतापूर्वक एक प्रेजेंटेशन बनाया है।

## जावा स्लाइड्स में चार्ट ट्रेंड लाइन्स के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि यह पहले से मौजूद नहीं है तो निर्देशिका बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// ख़ाली प्रस्तुतिकरण बनाना
Presentation pres = new Presentation();
// क्लस्टर्ड कॉलम चार्ट बनाना
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// चार्ट श्रृंखला 1 के लिए संभावित प्रवृत्ति रेखा जोड़ना
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// चार्ट श्रृंखला 1 के लिए रैखिक प्रवृत्ति रेखा जोड़ना
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// चार्ट श्रृंखला 2 के लिए लॉगरिदमिक ट्रेंड लाइन जोड़ना
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// चार्ट श्रृंखला 2 के लिए मूविंगएवरेज ट्रेंड लाइन जोड़ना
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// चार्ट शृंखला 3 के लिए बहुपद प्रवृत्ति रेखा जोड़ना
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// चार्ट श्रृंखला 3 के लिए पावर ट्रेंड लाइन जोड़ना
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// प्रस्तुतिकरण सहेजा जा रहा है
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि जावा लाइब्रेरी के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में चार्ट में विभिन्न प्रकार की ट्रेंड लाइनें कैसे जोड़ें। चाहे आप डेटा विश्लेषण पर काम कर रहे हों या जानकारीपूर्ण प्रस्तुतियाँ बना रहे हों, रुझानों की कल्पना करने की क्षमता एक शक्तिशाली उपकरण हो सकती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides में ट्रेंड लाइन का रंग कैसे बदलूं?

ट्रेंड लाइन का रंग बदलने के लिए, आप इसका उपयोग कर सकते हैं`getSolidFillColor().setColor(Color)` विधि, जैसा कि एक रेखीय प्रवृत्ति रेखा जोड़ने के उदाहरण में दिखाया गया है।

### क्या मैं एक ही चार्ट श्रृंखला में एकाधिक ट्रेंड लाइनें जोड़ सकता हूँ?

 हां, आप एक ही चार्ट श्रृंखला में कई ट्रेंड लाइनें जोड़ सकते हैं। बस कॉल करें`getTrendLines().add()` प्रत्येक ट्रेंड लाइन के लिए विधि जिसे आप जोड़ना चाहते हैं।

### मैं जावा के लिए Aspose.Slides में एक चार्ट से एक ट्रेंड लाइन कैसे हटाऊं?

 किसी चार्ट से ट्रेंड लाइन हटाने के लिए, आप इसका उपयोग कर सकते हैं`removeAt(int index)` विधि, उस प्रवृत्ति रेखा के सूचकांक को निर्दिष्ट करना जिसे आप हटाना चाहते हैं।

### क्या ट्रेंड लाइन समीकरण डिस्प्ले को अनुकूलित करना संभव है?

 हां, आप इसका उपयोग करके ट्रेंड लाइन समीकरण डिस्प्ले को कस्टमाइज़ कर सकते हैं`setDisplayEquation(boolean)` विधि, जैसा कि उदाहरण में दिखाया गया है।

### मैं जावा के लिए Aspose.Slides के लिए अधिक संसाधनों और उदाहरणों तक कैसे पहुंच सकता हूं?

 आप जावा के लिए Aspose.Slides के लिए अतिरिक्त संसाधनों, दस्तावेज़ीकरण और उदाहरणों तक पहुंच सकते हैं[Aspose वेबसाइट](https://reference.aspose.com/slides/java/).