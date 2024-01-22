---
title: जावा स्लाइड्स में कस्टम त्रुटि जोड़ें
linktitle: जावा स्लाइड्स में कस्टम त्रुटि जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके जावा स्लाइड्स में PowerPoint चार्ट में कस्टम त्रुटि बार जोड़ने का तरीका जानें। सटीक डेटा विज़ुअलाइज़ेशन के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 11
url: /hi/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Aspose.Slides का उपयोग करके जावा स्लाइड्स में कस्टम त्रुटि बार जोड़ने का परिचय

इस ट्यूटोरियल में, आप सीखेंगे कि जावा के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में चार्ट में कस्टम त्रुटि बार कैसे जोड़ें। किसी चार्ट पर डेटा बिंदुओं में परिवर्तनशीलता या अनिश्चितता प्रदर्शित करने के लिए त्रुटि पट्टियाँ उपयोगी होती हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा लाइब्रेरी के लिए Aspose.Slides आपके प्रोजेक्ट में स्थापित और कॉन्फ़िगर किया गया है।
- एक जावा विकास वातावरण स्थापित किया गया।

## चरण 1: एक खाली प्रस्तुतिकरण बनाएं

सबसे पहले, एक खाली पावरपॉइंट प्रेजेंटेशन बनाएं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// ख़ाली प्रस्तुतिकरण बनाना
Presentation presentation = new Presentation();
```

## चरण 2: एक बबल चार्ट जोड़ें

इसके बाद, हम प्रेजेंटेशन में एक बबल चार्ट जोड़ेंगे।

```java
// बबल चार्ट बनाना
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## चरण 3: कस्टम त्रुटि पट्टियाँ जोड़ें

अब, चार्ट श्रृंखला में कस्टम त्रुटि पट्टियाँ जोड़ें।

```java
// कस्टम त्रुटि पट्टियाँ जोड़ना और उनका प्रारूप सेट करना
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## चरण 4: त्रुटि पट्टियाँ डेटा सेट करें

इस चरण में, हम चार्ट श्रृंखला डेटा बिंदुओं तक पहुंचेंगे और प्रत्येक बिंदु के लिए कस्टम त्रुटि बार मान सेट करेंगे।

```java
// चार्ट श्रृंखला डेटा बिंदुओं तक पहुंच और व्यक्तिगत बिंदुओं के लिए त्रुटि बार मान सेट करना
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// चार्ट श्रृंखला बिंदुओं के लिए त्रुटि पट्टियाँ सेट करना
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## चरण 5: प्रस्तुति सहेजें

अंत में, प्रेजेंटेशन को कस्टम एरर बार के साथ सेव करें।

```java
// प्रस्तुतिकरण सहेजा जा रहा है
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

इतना ही! आपने Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुति में एक चार्ट में कस्टम त्रुटि पट्टियाँ सफलतापूर्वक जोड़ दी हैं।

## जावा स्लाइड्स में कस्टम त्रुटि जोड़ने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// ख़ाली प्रस्तुतिकरण बनाना
Presentation presentation = new Presentation();
try
{
	// बबल चार्ट बनाना
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// कस्टम त्रुटि पट्टियाँ जोड़ना और उसका प्रारूप सेट करना
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// चार्ट श्रृंखला डेटा बिंदु तक पहुंच और व्यक्तिगत बिंदु के लिए त्रुटि बार मान सेट करना
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// चार्ट श्रृंखला बिंदुओं के लिए त्रुटि पट्टियाँ सेट करना
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// प्रस्तुतिकरण सहेजा जा रहा है
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस व्यापक ट्यूटोरियल में, आपने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके चार्ट में कस्टम त्रुटि बार जोड़कर अपनी PowerPoint प्रस्तुतियों को कैसे बढ़ाया जाए। त्रुटि पट्टियाँ डेटा परिवर्तनशीलता और अनिश्चितता में मूल्यवान अंतर्दृष्टि प्रदान करती हैं, जिससे आपके चार्ट अधिक जानकारीपूर्ण और देखने में आकर्षक बनते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं त्रुटि पट्टियों के स्वरूप को कैसे अनुकूलित करूँ?

 आप के गुणों को संशोधित करके त्रुटि पट्टियों की उपस्थिति को अनुकूलित कर सकते हैं`IErrorBarsFormat` ऑब्जेक्ट, जैसे लाइन शैली, लाइन रंग और त्रुटि बार चौड़ाई।

### क्या मैं अन्य चार्ट प्रकारों में त्रुटि पट्टियाँ जोड़ सकता हूँ?

हां, आप जावा के लिए Aspose.Slides द्वारा समर्थित विभिन्न चार्ट प्रकारों में त्रुटि बार जोड़ सकते हैं, जिसमें बार चार्ट, लाइन चार्ट और स्कैटर चार्ट शामिल हैं।

### मैं प्रत्येक डेटा बिंदु के लिए अलग-अलग त्रुटि बार मान कैसे सेट करूं?

आप डेटा बिंदुओं के माध्यम से लूप कर सकते हैं और प्रत्येक बिंदु के लिए कस्टम त्रुटि बार मान सेट कर सकते हैं, जैसा कि ऊपर दिए गए कोड में दिखाया गया है।

### क्या विशिष्ट डेटा बिंदुओं के लिए त्रुटि पट्टियों को छिपाना संभव है?

 हां, आप इसे सेट करके अलग-अलग डेटा बिंदुओं के लिए त्रुटि पट्टियों की दृश्यता को नियंत्रित कर सकते हैं`setVisible` की संपत्ति`IErrorBarsFormat` वस्तु।