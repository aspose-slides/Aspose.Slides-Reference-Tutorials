---
title: जावा स्लाइड्स में लेआउट मोड सेट करें
linktitle: जावा स्लाइड्स में लेआउट मोड सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके जावा स्लाइड के लिए लेआउट मोड सेट करना सीखें। स्रोत कोड के साथ इस चरण-दर-चरण मार्गदर्शिका में चार्ट स्थिति और आकार को अनुकूलित करें।
type: docs
weight: 23
url: /hi/java/data-manipulation/set-layout-mode-java-slides/
---

## जावा स्लाइड्स में लेआउट मोड सेट करने का परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में चार्ट के लिए लेआउट मोड कैसे सेट करें। लेआउट मोड स्लाइड के भीतर चार्ट की स्थिति और आकार निर्धारित करता है।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित और सेटअप है। आप यहां से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: एक प्रेजेंटेशन बनाएं

सबसे पहले, हमें एक नई प्रस्तुति बनाने की आवश्यकता है।

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## चरण 2: एक स्लाइड और चार्ट जोड़ें

इसके बाद, हम इसमें एक स्लाइड और एक चार्ट जोड़ेंगे। इस उदाहरण में, हम एक क्लस्टर्ड कॉलम चार्ट बनाएंगे।

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## चरण 3: चार्ट लेआउट सेट करें

 अब, चार्ट के लिए लेआउट सेट करते हैं। हम इसका उपयोग करके स्लाइड के भीतर चार्ट की स्थिति और आकार को समायोजित करेंगे`setX`, `setY`, `setWidth`, `setHeight` तरीके. इसके अतिरिक्त, हम सेट करेंगे`LayoutTargetType` लेआउट मोड निर्धारित करने के लिए.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

इस उदाहरण में, हमने चार्ट को उसके लेआउट लक्ष्य प्रकार के लिए "इनर" के रूप में सेट किया है, जिसका अर्थ है कि यह स्लाइड के आंतरिक क्षेत्र के सापेक्ष स्थित और आकार में होगा।

## चरण 4: प्रस्तुति सहेजें

अंत में, आइए प्रस्तुतीकरण को चार्ट लेआउट सेटिंग्स के साथ सहेजें।

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में सेट लेआउट मोड के लिए संपूर्ण स्रोत कोड

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

 इस ट्यूटोरियल में, हमने सीखा है कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में चार्ट के लिए लेआउट मोड कैसे सेट किया जाए। आप इसमें मानों को समायोजित करके अपनी विशिष्ट आवश्यकताओं के अनुसार चार्ट की स्थिति और आकार को अनुकूलित कर सकते हैं`setX`, `setY`, `setWidth`, `setHeight` , और`setLayoutTargetType`तरीके. यह आपको अपनी स्लाइड में चार्ट के स्थान पर नियंत्रण प्रदान करता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides में चार्ट के लिए लेआउट मोड कैसे बदलूं?

 जावा के लिए Aspose.Slides में चार्ट के लेआउट मोड को बदलने के लिए, आप इसका उपयोग कर सकते हैं`setLayoutTargetType` चार्ट के प्लॉट क्षेत्र पर विधि। आप इसे या तो सेट कर सकते हैं`LayoutTargetType.Inner` या`LayoutTargetType.Outer` आपके इच्छित लेआउट के आधार पर.

### क्या मैं स्लाइड के भीतर चार्ट की स्थिति और आकार को अनुकूलित कर सकता हूँ?

 हाँ, आप इसका उपयोग करके स्लाइड के भीतर चार्ट की स्थिति और आकार को अनुकूलित कर सकते हैं`setX`, `setY`, `setWidth` , और`setHeight` चार्ट के प्लॉट क्षेत्र पर विधियाँ। अपनी आवश्यकताओं के अनुसार चार्ट को स्थिति और आकार देने के लिए इन मानों को समायोजित करें।

### मुझे जावा के लिए Aspose.Slides के बारे में अधिक जानकारी कहां मिल सकती है?

 आप जावा के लिए Aspose.Slides के बारे में अधिक जानकारी यहां पा सकते हैं[प्रलेखन](https://reference.aspose.com/slides/java/). इसमें जावा में स्लाइड और चार्ट के साथ प्रभावी ढंग से काम करने में मदद के लिए विस्तृत एपीआई संदर्भ और उदाहरण शामिल हैं।