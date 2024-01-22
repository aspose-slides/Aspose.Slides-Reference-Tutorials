---
title: जावा स्लाइड्स में त्रुटि पट्टियाँ जोड़ें
linktitle: जावा स्लाइड्स में त्रुटि पट्टियाँ जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके जावा में PowerPoint चार्ट में त्रुटि बार जोड़ने का तरीका जानें। त्रुटि पट्टियों को अनुकूलित करने के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 13
url: /hi/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Aspose.Slides का उपयोग करके जावा स्लाइड्स में त्रुटि बार जोड़ने का परिचय

इस ट्यूटोरियल में, हम दिखाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड में चार्ट में त्रुटि बार कैसे जोड़ें। त्रुटि पट्टियाँ चार्ट में डेटा बिंदुओं की परिवर्तनशीलता या अनिश्चितता के बारे में बहुमूल्य जानकारी प्रदान करती हैं। हम एक बबल चार्ट बनाएंगे और उसमें त्रुटि पट्टियाँ जोड़ेंगे। आएँ शुरू करें!

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित और सेटअप है। आप लाइब्रेरी को यहां से डाउनलोड कर सकते हैं[Aspose वेबसाइट](https://downloads.aspose.com/slides/java).

## चरण 1: एक खाली प्रस्तुतिकरण बनाएं

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// ख़ाली प्रस्तुतिकरण बनाना
Presentation presentation = new Presentation();
```

इस चरण में, हम एक खाली प्रेजेंटेशन बनाते हैं जहां हम त्रुटि पट्टियों के साथ अपना चार्ट जोड़ेंगे।

## चरण 2: एक बबल चार्ट बनाएं

```java
// बबल चार्ट बनाना
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

यहां, हम एक बबल चार्ट बनाते हैं और स्लाइड पर उसकी स्थिति और आयाम निर्दिष्ट करते हैं।

## चरण 3: त्रुटि पट्टियाँ जोड़ना और प्रारूप सेट करना

```java
// त्रुटि पट्टियाँ जोड़ना और उसका प्रारूप निर्धारित करना
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

इस चरण में, हम चार्ट में त्रुटि पट्टियाँ जोड़ते हैं और उनका प्रारूप निर्धारित करते हैं। आप मान, प्रकार और अन्य गुणों को बदलकर त्रुटि पट्टियों को अनुकूलित कर सकते हैं।

- `errBarX` एक्स-अक्ष के साथ त्रुटि पट्टियों का प्रतिनिधित्व करता है।
- `errBarY` Y-अक्ष के साथ त्रुटि पट्टियों का प्रतिनिधित्व करता है।
- हम X और Y दोनों त्रुटि पट्टियों को दृश्यमान बनाते हैं।
- `setValueType` त्रुटि पट्टियों के लिए मान प्रकार निर्दिष्ट करता है (जैसे, निश्चित या प्रतिशत)।
- `setValue` त्रुटि पट्टियों के लिए मान निर्धारित करता है।
- `setType` त्रुटि पट्टियों के प्रकार को परिभाषित करता है (उदाहरण के लिए, प्लस या माइनस)।
-  हम त्रुटि बार लाइनों की चौड़ाई का उपयोग करके निर्धारित करते हैं`getFormat().getLine().setWidth(2)`.
- `setEndCap`निर्दिष्ट करता है कि त्रुटि पट्टियों पर अंतिम कैप शामिल करना है या नहीं।

## चरण 4: प्रस्तुति सहेजें

```java
// प्रस्तुतिकरण सहेजा जा रहा है
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

अंत में, हम प्रेजेंटेशन को अतिरिक्त त्रुटि पट्टियों के साथ एक निर्दिष्ट स्थान पर सहेजते हैं।

इतना ही! आपने Java के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड में एक चार्ट में त्रुटि पट्टियाँ सफलतापूर्वक जोड़ दी हैं।

## जावा स्लाइड्स में त्रुटि बार जोड़ने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// ख़ाली प्रस्तुतिकरण बनाना
Presentation presentation = new Presentation();
try
{
	// बबल चार्ट बनाना
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// त्रुटि पट्टियाँ जोड़ना और उसका प्रारूप निर्धारित करना
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
	// प्रस्तुतिकरण सहेजा जा रहा है
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने पता लगाया है कि जावा के लिए Aspose.Slides का उपयोग करके चार्ट में त्रुटि बार जोड़कर अपनी PowerPoint प्रस्तुतियों को कैसे बढ़ाया जाए। त्रुटि पट्टियाँ डेटा परिवर्तनशीलता और अनिश्चितताओं में मूल्यवान अंतर्दृष्टि प्रदान करती हैं, जिससे आपकी प्रस्तुतियाँ अधिक जानकारीपूर्ण और देखने में आकर्षक बनती हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं त्रुटि पट्टियों के स्वरूप को और अधिक कैसे अनुकूलित कर सकता हूँ?

जैसा कि चरण 3 में दिखाया गया है, आप त्रुटि पट्टियों को उनके गुणों, जैसे लाइन शैली, रंग और चौड़ाई को संशोधित करके अनुकूलित कर सकते हैं।

### क्या मैं विभिन्न चार्ट प्रकारों में त्रुटि पट्टियाँ जोड़ सकता हूँ?

हाँ, आप Java के लिए Aspose.Slides द्वारा समर्थित विभिन्न चार्ट प्रकारों में त्रुटि पट्टियाँ जोड़ सकते हैं। बस वांछित चार्ट प्रकार बनाएं और समान त्रुटि बार अनुकूलन चरणों का पालन करें।

### मैं स्लाइड पर चार्ट की स्थिति और आकार को कैसे समायोजित कर सकता हूँ?

 आप पैरामीटर्स को समायोजित करके चार्ट की स्थिति और आयामों को नियंत्रित कर सकते हैं`addChart` विधि, जैसा कि चरण 2 में दिखाया गया है।

### मुझे जावा के लिए Aspose.Slides के बारे में अधिक जानकारी कहां मिल सकती है?

 आप इसका उल्लेख कर सकते हैं[जावा दस्तावेज़ीकरण के लिए Aspose.Slides](https://reference.aspose.com/slides/java/) पुस्तकालय के उपयोग के बारे में विस्तृत जानकारी के लिए।