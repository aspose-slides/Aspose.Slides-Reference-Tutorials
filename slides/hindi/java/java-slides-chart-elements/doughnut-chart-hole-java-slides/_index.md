---
"description": "Aspose.Slides for Java का उपयोग करके Java स्लाइड्स में कस्टम होल साइज़ के साथ डोनट चार्ट बनाएँ। चार्ट कस्टमाइज़ेशन के लिए सोर्स कोड के साथ चरण-दर-चरण मार्गदर्शिका।"
"linktitle": "जावा स्लाइड्स में डोनट चार्ट होल"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में डोनट चार्ट होल"
"url": "/hi/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में डोनट चार्ट होल


## जावा स्लाइड्स में छेद वाले डोनट चार्ट का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके छेद वाला डोनट चार्ट बनाने में मार्गदर्शन करेंगे। यह चरण-दर-चरण मार्गदर्शिका आपको स्रोत कोड उदाहरणों के साथ प्रक्रिया के माध्यम से ले जाएगी।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java प्रोजेक्ट में सेट अप है। आप इसे यहाँ से डाउनलोड कर सकते हैं [Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/).

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## चरण 2: प्रस्तुति आरंभ करें

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
```

## चरण 3: डोनट चार्ट बनाएं

```java
try {
    // पहली स्लाइड पर डोनट चार्ट बनाएं
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // डोनट चार्ट में छेद का आकार निर्धारित करें (प्रतिशत में)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // प्रस्तुति को डिस्क पर सहेजें
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // प्रस्तुति ऑब्जेक्ट का निपटान करें
    if (presentation != null) presentation.dispose();
}
```

## चरण 4: कोड चलाएँ

निर्दिष्ट छेद आकार के साथ डोनट चार्ट बनाने के लिए अपने IDE या टेक्स्ट एडिटर में जावा कोड चलाएँ। `"Your Document Directory"` उस वास्तविक पथ के साथ जहां आप प्रस्तुति को सहेजना चाहते हैं.

## जावा स्लाइड्स में डोनट चार्ट होल के लिए पूरा स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// प्रस्तुति को डिस्क पर लिखें
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि Aspose.Slides for Java का उपयोग करके छेद वाला डोनट चार्ट कैसे बनाया जाता है। आप छेद के आकार को समायोजित करके अनुकूलित कर सकते हैं `setDoughnutHoleSize` विधि पैरामीटर.

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट खंडों का रंग कैसे बदल सकता हूँ?

चार्ट खंडों का रंग बदलने के लिए, आप इसका उपयोग कर सकते हैं `setDataPointsInLegend` विधि पर `IChart` ऑब्जेक्ट और प्रत्येक डेटा बिंदु के लिए वांछित रंग सेट करें।

### क्या मैं डोनट चार्ट खंडों में लेबल जोड़ सकता हूँ?

हां, आप डोनट चार्ट सेगमेंट में लेबल जोड़ सकते हैं `setDataPointsLabelValue` विधि पर `IChart` वस्तु।

### क्या चार्ट में शीर्षक जोड़ना संभव है?

ज़रूर! आप चार्ट में शीर्षक जोड़ सकते हैं `setTitle` विधि पर `IChart` ऑब्जेक्ट और वांछित शीर्षक पाठ प्रदान करना।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}