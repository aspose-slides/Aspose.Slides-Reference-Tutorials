---
title: जावा स्लाइड्स में लीजेंड कस्टम विकल्प सेट करें
linktitle: जावा स्लाइड्स में लीजेंड कस्टम विकल्प सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में कस्टम लेजेंड विकल्प सेट करना सीखें। अपने पावरपॉइंट चार्ट में लेजेंड स्थिति और आकार को अनुकूलित करें।
type: docs
weight: 14
url: /hi/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

## जावा स्लाइड्स में लीजेंड कस्टम विकल्प सेट करने का परिचय

इस ट्यूटोरियल में, हम दिखाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में चार्ट के लेजेंड गुणों को कैसे अनुकूलित किया जाए। आप अपनी प्रस्तुति आवश्यकताओं के अनुरूप लीजेंड की स्थिति, आकार और अन्य विशेषताओं को संशोधित कर सकते हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा एपीआई के लिए Aspose.Slides स्थापित।
- जावा विकास पर्यावरण की स्थापना।

## चरण 1: आवश्यक कक्षाएं आयात करें:

```java
// जावा कक्षाओं के लिए Aspose.Slides आयात करें
import com.aspose.slides.*;
```

## चरण 2: अपनी दस्तावेज़ निर्देशिका का पथ निर्दिष्ट करें:

```java
String dataDir = "Your Document Directory";
```

##  चरण 3: का एक उदाहरण बनाएं`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## चरण 4: प्रेजेंटेशन में एक स्लाइड जोड़ें:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## चरण 5: स्लाइड में एक क्लस्टर्ड कॉलम चार्ट जोड़ें:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## चरण 6. लीजेंड गुण सेट करें:

- लेजेंड की एक्स-स्थिति सेट करें (चार्ट चौड़ाई के सापेक्ष):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- लेजेंड की Y-स्थिति सेट करें (चार्ट ऊंचाई के सापेक्ष):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- लेजेंड की चौड़ाई निर्धारित करें (चार्ट चौड़ाई के सापेक्ष):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- लेजेंड की ऊंचाई निर्धारित करें (चार्ट ऊंचाई के सापेक्ष):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## चरण 7: प्रस्तुतिकरण को डिस्क पर सहेजें:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

इतना ही! आपने Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुति में चार्ट के लेजेंड गुणों को सफलतापूर्वक अनुकूलित किया है।

## जावा स्लाइड्स में सेट लीजेंड कस्टम विकल्पों के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएं
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
	// डिस्क पर प्रेजेंटेशन लिखें
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रेजेंटेशन में चार्ट के लेजेंड गुणों को कैसे अनुकूलित किया जाए। आप दृश्यात्मक रूप से आकर्षक और जानकारीपूर्ण प्रस्तुतियाँ बनाने के लिए किंवदंती की स्थिति, आकार और अन्य विशेषताओं को संशोधित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

## मैं लेजेंड की स्थिति कैसे बदल सकता हूँ?

 लेजेंड की स्थिति बदलने के लिए, का उपयोग करें`setX` और`setY` लेजेंड ऑब्जेक्ट के तरीके. मान चार्ट की चौड़ाई और ऊंचाई के सापेक्ष निर्दिष्ट किए गए हैं।

## मैं लेजेंड का आकार कैसे समायोजित कर सकता हूं?

 आप इसका उपयोग करके किंवदंती के आकार को समायोजित कर सकते हैं`setWidth` और`setHeight` लेजेंड ऑब्जेक्ट के तरीके. ये मान चार्ट की चौड़ाई और ऊंचाई से भी संबंधित हैं।

## क्या मैं अन्य लेजेंड विशेषताओं को अनुकूलित कर सकता हूँ?

हां, आप लेजेंड की विभिन्न विशेषताओं को अनुकूलित कर सकते हैं, जैसे फ़ॉन्ट शैली, बॉर्डर, पृष्ठभूमि रंग और बहुत कुछ। किंवदंतियों को और अधिक अनुकूलित करने के बारे में विस्तृत जानकारी के लिए Aspose.Slides दस्तावेज़ देखें।