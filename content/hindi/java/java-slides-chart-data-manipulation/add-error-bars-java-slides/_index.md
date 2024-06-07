---
title: जावा स्लाइड्स में त्रुटि बार जोड़ें
linktitle: जावा स्लाइड्स में त्रुटि बार जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके जावा में PowerPoint चार्ट में त्रुटि बार जोड़ना सीखें। त्रुटि बार को अनुकूलित करने के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 13
url: /hi/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Aspose.Slides का उपयोग करके जावा स्लाइड्स में त्रुटि बार जोड़ने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में चार्ट में त्रुटि बार जोड़ने का तरीका प्रदर्शित करेंगे। त्रुटि बार चार्ट में डेटा बिंदुओं की परिवर्तनशीलता या अनिश्चितता के बारे में मूल्यवान जानकारी प्रदान करते हैं। हम एक बबल चार्ट बनाएंगे और उसमें त्रुटि बार जोड़ेंगे। चलिए शुरू करते हैं!

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java प्रोजेक्ट में सेट अप है। आप लाइब्रेरी को यहाँ से डाउनलोड कर सकते हैं[Aspose वेबसाइट](https://downloads.aspose.com/slides/java).

## चरण 1: एक खाली प्रस्तुति बनाएं

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// खाली प्रस्तुति बनाना
Presentation presentation = new Presentation();
```

इस चरण में, हम एक खाली प्रस्तुति बनाते हैं, जहां हम त्रुटि पट्टियों के साथ अपना चार्ट जोड़ेंगे।

## चरण 2: बबल चार्ट बनाएं

```java
// बबल चार्ट बनाना
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

यहां, हम एक बबल चार्ट बनाते हैं और स्लाइड पर इसकी स्थिति और आयाम निर्दिष्ट करते हैं।

## चरण 3: त्रुटि बार जोड़ना और प्रारूप सेट करना

```java
// त्रुटि बार जोड़ना और उसका प्रारूप निर्धारित करना
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

इस चरण में, हम चार्ट में त्रुटि बार जोड़ते हैं और उनका प्रारूप सेट करते हैं। आप मान, प्रकार और अन्य गुण बदलकर त्रुटि बार को कस्टमाइज़ कर सकते हैं।

- `errBarX` X-अक्ष के साथ त्रुटि बार का प्रतिनिधित्व करता है।
- `errBarY` Y-अक्ष के साथ त्रुटि बार का प्रतिनिधित्व करता है।
- हम X और Y दोनों त्रुटि पट्टियों को दृश्यमान बनाते हैं।
- `setValueType` त्रुटि बार के लिए मान प्रकार निर्दिष्ट करता है (उदाहरण के लिए, निश्चित या प्रतिशत).
- `setValue` त्रुटि बार के लिए मान सेट करता है.
- `setType` त्रुटि बार के प्रकार को परिभाषित करता है (जैसे, प्लस या माइनस).
-  हम त्रुटि बार लाइनों की चौड़ाई निर्धारित करते हैं`getFormat().getLine().setWidth(2)`.
- `setEndCap` निर्दिष्ट करता है कि त्रुटि बार पर अंतिम कैप्स शामिल करना है या नहीं.

## चरण 4: प्रस्तुति सहेजें

```java
// प्रस्तुति सहेजना
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

अंत में, हम जोड़े गए त्रुटि पट्टियों के साथ प्रस्तुति को निर्दिष्ट स्थान पर सहेज लेते हैं।

बस! आपने Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में चार्ट में त्रुटि बार सफलतापूर्वक जोड़ दिया है।

## जावा स्लाइड्स में त्रुटि बार जोड़ने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// खाली प्रस्तुति बनाना
Presentation presentation = new Presentation();
try
{
	// बबल चार्ट बनाना
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// त्रुटि बार जोड़ना और उसका प्रारूप निर्धारित करना
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// प्रस्तुति सहेजना
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Slides for Java का उपयोग करके चार्ट में त्रुटि बार जोड़कर अपने PowerPoint प्रेजेंटेशन को बेहतर बनाने का तरीका खोजा है। त्रुटि बार डेटा परिवर्तनशीलता और अनिश्चितताओं के बारे में मूल्यवान जानकारी प्रदान करते हैं, जिससे आपकी प्रेजेंटेशन अधिक जानकारीपूर्ण और आकर्षक बनती हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं त्रुटि बार के स्वरूप को और अधिक अनुकूलित कैसे कर सकता हूँ?

आप त्रुटि बार के गुणों को संशोधित करके उन्हें अनुकूलित कर सकते हैं, जैसे कि लाइन शैली, रंग और चौड़ाई, जैसा कि चरण 3 में दिखाया गया है।

### क्या मैं विभिन्न चार्ट प्रकारों में त्रुटि बार जोड़ सकता हूँ?

हां, आप Aspose.Slides for Java द्वारा समर्थित विभिन्न चार्ट प्रकारों में त्रुटि बार जोड़ सकते हैं। बस वांछित चार्ट प्रकार बनाएं और उसी त्रुटि बार अनुकूलन चरणों का पालन करें।

### मैं स्लाइड पर चार्ट की स्थिति और आकार को कैसे समायोजित कर सकता हूं?

आप पैरामीटर समायोजित करके चार्ट की स्थिति और आयाम को नियंत्रित कर सकते हैं`addChart` विधि, जैसा कि चरण 2 में दिखाया गया है।

### मैं Aspose.Slides for Java के बारे में अधिक जानकारी कहां पा सकता हूं?

 आप इसका संदर्भ ले सकते हैं[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/) पुस्तकालय के उपयोग के बारे में विस्तृत जानकारी के लिए कृपया देखें.