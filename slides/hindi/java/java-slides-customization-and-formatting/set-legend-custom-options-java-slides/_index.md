---
title: जावा स्लाइड्स में लेजेंड कस्टम विकल्प सेट करें
linktitle: जावा स्लाइड्स में लेजेंड कस्टम विकल्प सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java स्लाइड में कस्टम लेजेंड विकल्प सेट करना सीखें। अपने PowerPoint चार्ट में लेजेंड की स्थिति और आकार को कस्टमाइज़ करें।
weight: 14
url: /hi/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में लेजेंड कस्टम विकल्प सेट करने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में चार्ट के लेजेंड गुणों को कस्टमाइज़ करने का तरीका दिखाएंगे। आप अपनी प्रेजेंटेशन आवश्यकताओं के अनुरूप लेजेंड की स्थिति, आकार और अन्य विशेषताओं को संशोधित कर सकते हैं।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Aspose.Slides for Java API स्थापित.
- जावा विकास वातावरण की स्थापना.

## चरण 1: आवश्यक कक्षाएं आयात करें:

```java
// Java क्लासों के लिए Aspose.Slides आयात करें
import com.aspose.slides.*;
```

## चरण 2: अपने दस्तावेज़ निर्देशिका का पथ निर्दिष्ट करें:

```java
String dataDir = "Your Document Directory";
```

##  चरण 3: इसका एक उदाहरण बनाएँ`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## चरण 4: प्रस्तुति में स्लाइड जोड़ें:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## चरण 5: स्लाइड में क्लस्टर्ड कॉलम चार्ट जोड़ें:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## चरण 6. लेजेंड गुण सेट करें:

- लेजेंड की X-स्थिति सेट करें (चार्ट की चौड़ाई के सापेक्ष):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- लेजेंड की Y-स्थिति सेट करें (चार्ट ऊंचाई के सापेक्ष):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- लेजेंड की चौड़ाई सेट करें (चार्ट की चौड़ाई के सापेक्ष):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- लेजेंड की ऊंचाई सेट करें (चार्ट ऊंचाई के सापेक्ष):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## चरण 7: प्रस्तुति को डिस्क पर सहेजें:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

बस! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में चार्ट के लेजेंड गुणों को सफलतापूर्वक अनुकूलित कर लिया है।

## जावा स्लाइड्स में सेट लीजेंड कस्टम विकल्प के लिए पूरा स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation presentation = new Presentation();
try
{
	// स्लाइड का संदर्भ प्राप्त करें
	ISlide slide = presentation.getSlides().get_Item(0);
	// स्लाइड पर क्लस्टर्ड कॉलम चार्ट जोड़ें
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// लीजेंड गुण सेट करें
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// प्रस्तुति को डिस्क पर लिखें
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में चार्ट के लेजेंड गुणों को कैसे कस्टमाइज़ किया जाए। आप आकर्षक और जानकारीपूर्ण प्रेजेंटेशन बनाने के लिए लेजेंड की स्थिति, आकार और अन्य विशेषताओं को संशोधित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

## मैं किंवदंती की स्थिति कैसे बदल सकता हूँ?

 किंवदंती की स्थिति बदलने के लिए, का उपयोग करें`setX` और`setY` लीजेंड ऑब्जेक्ट की विधियाँ। मान चार्ट की चौड़ाई और ऊँचाई के सापेक्ष निर्दिष्ट किए जाते हैं।

## मैं किंवदंती का आकार कैसे समायोजित कर सकता हूं?

 आप लेजेंड के आकार को निम्न प्रकार से समायोजित कर सकते हैं:`setWidth` और`setHeight` लीजेंड ऑब्जेक्ट की विधियाँ। ये मान चार्ट की चौड़ाई और ऊँचाई से भी संबंधित हैं।

## क्या मैं अन्य किंवदंती विशेषताओं को अनुकूलित कर सकता हूं?

हां, आप लीजेंड की विभिन्न विशेषताओं को अनुकूलित कर सकते हैं, जैसे कि फ़ॉन्ट शैली, बॉर्डर, पृष्ठभूमि रंग, और बहुत कुछ। लीजेंड को और अधिक अनुकूलित करने के बारे में विस्तृत जानकारी के लिए Aspose.Slides दस्तावेज़ देखें।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
