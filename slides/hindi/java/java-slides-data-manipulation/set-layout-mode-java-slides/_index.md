---
title: जावा स्लाइड्स में लेआउट मोड सेट करें
linktitle: जावा स्लाइड्स में लेआउट मोड सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java स्लाइड के लिए लेआउट मोड सेट करना सीखें। स्रोत कोड के साथ इस चरण-दर-चरण मार्गदर्शिका में चार्ट की स्थिति और आकार को अनुकूलित करें।
weight: 23
url: /hi/java/data-manipulation/set-layout-mode-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में लेआउट मोड सेट करें


## जावा स्लाइड्स में लेआउट मोड सेट करने का परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके Java स्लाइड में चार्ट के लिए लेआउट मोड कैसे सेट करें। लेआउट मोड स्लाइड के भीतर चार्ट की स्थिति और आकार निर्धारित करता है।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java प्रोजेक्ट में सेट अप है। आप लाइब्रेरी को यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: एक प्रस्तुति बनाएं

सबसे पहले, हमें एक नई प्रस्तुति बनानी होगी।

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## चरण 2: स्लाइड और चार्ट जोड़ें

इसके बाद, हम इसमें एक स्लाइड और एक चार्ट जोड़ेंगे। इस उदाहरण में, हम एक क्लस्टर्ड कॉलम चार्ट बनाएंगे।

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## चरण 3: चार्ट लेआउट सेट करें

 अब, चार्ट के लिए लेआउट सेट करते हैं। हम स्लाइड के भीतर चार्ट की स्थिति और आकार को समायोजित करेंगे।`setX`, `setY`, `setWidth`, `setHeight` इसके अतिरिक्त, हम विधियाँ निर्धारित करेंगे।`LayoutTargetType` लेआउट मोड निर्धारित करने के लिए.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

इस उदाहरण में, हमने चार्ट का लेआउट लक्ष्य प्रकार "आंतरिक" निर्धारित किया है, जिसका अर्थ है कि इसे स्लाइड के आंतरिक क्षेत्र के सापेक्ष स्थित और आकारित किया जाएगा।

## चरण 4: प्रस्तुति सहेजें

अंत में, आइए चार्ट लेआउट सेटिंग्स के साथ प्रेजेंटेशन को सेव करें।

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में लेआउट मोड सेट करने के लिए पूरा स्रोत कोड

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

 इस ट्यूटोरियल में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके Java स्लाइड में चार्ट के लिए लेआउट मोड कैसे सेट करें। आप चार्ट की स्थिति और आकार को अपनी विशिष्ट आवश्यकताओं के अनुसार मानों को समायोजित करके अनुकूलित कर सकते हैं।`setX`, `setY`, `setWidth`, `setHeight` , और`setLayoutTargetType`यह आपको अपनी स्लाइडों में चार्ट की स्थिति पर नियंत्रण देता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Aspose.Slides for Java में चार्ट के लिए लेआउट मोड कैसे बदलूं?

 Aspose.Slides for Java में चार्ट के लेआउट मोड को बदलने के लिए, आप इसका उपयोग कर सकते हैं`setLayoutTargetType` चार्ट के प्लॉट क्षेत्र पर विधि। आप इसे या तो सेट कर सकते हैं`LayoutTargetType.Inner` या`LayoutTargetType.Outer` आपके इच्छित लेआउट पर निर्भर करता है।

### क्या मैं स्लाइड के भीतर चार्ट की स्थिति और आकार को अनुकूलित कर सकता हूँ?

 हां, आप स्लाइड के भीतर चार्ट की स्थिति और आकार को अनुकूलित कर सकते हैं`setX`, `setY`, `setWidth` , और`setHeight` चार्ट के प्लॉट क्षेत्र पर विधियाँ। अपनी आवश्यकताओं के अनुसार चार्ट की स्थिति और आकार को समायोजित करने के लिए इन मानों को समायोजित करें।

### मैं Aspose.Slides for Java के बारे में अधिक जानकारी कहां पा सकता हूं?

 आप Aspose.Slides for Java के बारे में अधिक जानकारी यहाँ पा सकते हैं[प्रलेखन](https://reference.aspose.com/slides/java/)इसमें जावा में स्लाइड और चार्ट के साथ प्रभावी ढंग से काम करने में आपकी मदद करने के लिए विस्तृत API संदर्भ और उदाहरण शामिल हैं।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
