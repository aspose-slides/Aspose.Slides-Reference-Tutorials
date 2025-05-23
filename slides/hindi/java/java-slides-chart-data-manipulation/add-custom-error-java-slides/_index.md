---
"description": "Aspose.Slides का उपयोग करके Java स्लाइड्स में PowerPoint चार्ट में कस्टम त्रुटि बार जोड़ने का तरीका जानें। सटीक डेटा विज़ुअलाइज़ेशन के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।"
"linktitle": "जावा स्लाइड्स में कस्टम त्रुटि जोड़ें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में कस्टम त्रुटि जोड़ें"
"url": "/hi/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में कस्टम त्रुटि जोड़ें


## Aspose.Slides का उपयोग करके जावा स्लाइड्स में कस्टम त्रुटि बार जोड़ने का परिचय

इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में चार्ट में कस्टम त्रुटि बार कैसे जोड़ें। त्रुटि बार चार्ट पर डेटा बिंदुओं में परिवर्तनशीलता या अनिश्चितता प्रदर्शित करने के लिए उपयोगी होते हैं।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित और कॉन्फ़िगर की गई है।
- एक जावा विकास वातावरण स्थापित किया गया।

## चरण 1: एक खाली प्रस्तुति बनाएं

सबसे पहले, एक खाली पावरपॉइंट प्रेजेंटेशन बनाएं।

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// खाली प्रस्तुति बनाना
Presentation presentation = new Presentation();
```

## चरण 2: बबल चार्ट जोड़ें

इसके बाद, हम प्रस्तुति में एक बबल चार्ट जोड़ेंगे।

```java
// बबल चार्ट बनाना
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## चरण 3: कस्टम त्रुटि बार जोड़ें

अब, चार्ट श्रृंखला में कस्टम त्रुटि बार जोड़ें।

```java
// कस्टम त्रुटि बार जोड़ना और उनका प्रारूप निर्धारित करना
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## चरण 4: त्रुटि बार डेटा सेट करें

इस चरण में, हम चार्ट श्रृंखला डेटा बिंदुओं तक पहुंचेंगे और प्रत्येक बिंदु के लिए कस्टम त्रुटि बार मान सेट करेंगे।

```java
// चार्ट श्रृंखला डेटा बिंदुओं तक पहुंचना और व्यक्तिगत बिंदुओं के लिए त्रुटि बार मान सेट करना
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// चार्ट श्रृंखला बिंदुओं के लिए त्रुटि बार सेट करना
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## चरण 5: प्रस्तुति सहेजें

अंत में, प्रस्तुति को कस्टम त्रुटि बार के साथ सहेजें।

```java
// प्रस्तुति सहेजना
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

बस! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में चार्ट में कस्टम त्रुटि बार सफलतापूर्वक जोड़ दिए हैं।

## जावा स्लाइड्स में कस्टम त्रुटि जोड़ने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// खाली प्रस्तुति बनाना
Presentation presentation = new Presentation();
try
{
	// बबल चार्ट बनाना
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// कस्टम त्रुटि बार जोड़ना और उसका प्रारूप निर्धारित करना
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// चार्ट श्रृंखला डेटा बिंदु तक पहुंचना और व्यक्तिगत बिंदु के लिए त्रुटि बार मान सेट करना
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// चार्ट श्रृंखला बिंदुओं के लिए त्रुटि बार सेट करना
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// प्रस्तुति सहेजना
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस व्यापक ट्यूटोरियल में, आपने सीखा है कि Aspose.Slides for Java का उपयोग करके चार्ट में कस्टम त्रुटि बार जोड़कर अपने PowerPoint प्रेजेंटेशन को कैसे बेहतर बनाया जाए। त्रुटि बार डेटा परिवर्तनशीलता और अनिश्चितता के बारे में मूल्यवान जानकारी प्रदान करते हैं, जिससे आपके चार्ट अधिक जानकारीपूर्ण और आकर्षक बनते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं त्रुटि बार के स्वरूप को कैसे अनुकूलित करूँ?

आप त्रुटि बार के गुणों को संशोधित करके उसके स्वरूप को अनुकूलित कर सकते हैं `IErrorBarsFormat` ऑब्जेक्ट, जैसे लाइन शैली, लाइन रंग, और त्रुटि बार चौड़ाई।

### क्या मैं अन्य चार्ट प्रकारों में त्रुटि बार जोड़ सकता हूँ?

हां, आप Java के लिए Aspose.Slides द्वारा समर्थित विभिन्न चार्ट प्रकारों में त्रुटि बार जोड़ सकते हैं, जिसमें बार चार्ट, लाइन चार्ट और स्कैटर चार्ट शामिल हैं।

### मैं प्रत्येक डेटा बिंदु के लिए अलग-अलग त्रुटि बार मान कैसे सेट करूं?

आप डेटा बिंदुओं के माध्यम से लूप कर सकते हैं और प्रत्येक बिंदु के लिए कस्टम त्रुटि बार मान सेट कर सकते हैं, जैसा कि ऊपर दिए गए कोड में दिखाया गया है।

### क्या विशिष्ट डेटा बिंदुओं के लिए त्रुटि बार को छिपाना संभव है?

हां, आप अलग-अलग डेटा बिंदुओं के लिए त्रुटि बार की दृश्यता को नियंत्रित कर सकते हैं `setVisible` की संपत्ति `IErrorBarsFormat` वस्तु।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}