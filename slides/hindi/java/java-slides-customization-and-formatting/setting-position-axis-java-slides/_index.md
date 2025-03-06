---
title: जावा स्लाइड्स में स्थिति अक्ष सेट करना
linktitle: जावा स्लाइड्स में स्थिति अक्ष सेट करना
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Java के लिए Aspose.Slides के साथ अपने चार्ट को बेहतर बनाएँ। Java स्लाइड में स्थिति अक्ष सेट करना, शानदार प्रस्तुतियाँ बनाना और चार्ट लेआउट को आसानी से कस्टमाइज़ करना सीखें।
weight: 16
url: /hi/java/customization-and-formatting/setting-position-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में स्थिति अक्ष सेट करना


## Aspose.Slides for Java में स्थिति अक्ष सेट करने का परिचय

इस ट्यूटोरियल में, हम सीखेंगे कि Aspose.Slides for Java का उपयोग करके चार्ट में स्थिति अक्ष कैसे सेट करें। जब आप अपने चार्ट की उपस्थिति और लेआउट को कस्टमाइज़ करना चाहते हैं तो अक्ष की स्थिति निर्धारित करना उपयोगी हो सकता है। हम एक क्लस्टर कॉलम चार्ट बनाएंगे और श्रेणियों के बीच क्षैतिज अक्ष की स्थिति को समायोजित करेंगे।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java प्रोजेक्ट में सेट अप है। आप लाइब्रेरी को यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: प्रेजेंटेशन बनाना

सबसे पहले, आइए काम करने के लिए एक नई प्रस्तुति बनाएं:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 प्रतिस्थापित करना सुनिश्चित करें`"Your Document Directory"` आपके दस्तावेज़ निर्देशिका के वास्तविक पथ के साथ.

## चरण 2: चार्ट जोड़ना

इसके बाद, हम स्लाइड में एक क्लस्टर्ड कॉलम चार्ट जोड़ेंगे। हम चार्ट का प्रकार, स्थिति (x, y निर्देशांक) और चार्ट का आयाम (चौड़ाई और ऊंचाई) निर्दिष्ट करते हैं:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

यहाँ, हमने स्थिति (50, 50) पर 450 की चौड़ाई और 300 की ऊँचाई के साथ एक क्लस्टर कॉलम चार्ट जोड़ा है। आप इन मानों को आवश्यकतानुसार समायोजित कर सकते हैं।

## चरण 3: स्थिति अक्ष सेट करना

श्रेणियों के बीच स्थिति अक्ष सेट करने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

यह कोड श्रेणियों के बीच प्रदर्शित करने के लिए क्षैतिज अक्ष निर्धारित करता है, जो कुछ चार्ट लेआउट के लिए उपयोगी हो सकता है।

## चरण 4: प्रस्तुति को सहेजना

अंत में, आइए चार्ट के साथ प्रस्तुति को सेव करें:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 प्रतिस्थापित करें`"AsposeClusteredColumnChart.pptx"` अपने इच्छित फ़ाइल नाम के साथ.

बस! आपने Aspose.Slides for Java का उपयोग करके सफलतापूर्वक एक क्लस्टर्ड कॉलम चार्ट बना लिया है और श्रेणियों के बीच स्थिति अक्ष सेट कर लिया है।

## संपूर्ण स्रोत कोड
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Slides for Java का उपयोग करके चार्ट में स्थिति अक्ष सेट करने का तरीका खोजा है। इस गाइड में बताए गए चरणों का पालन करके, आपने सीखा है कि क्लस्टर किए गए कॉलम चार्ट को कैसे बनाया जाए और श्रेणियों के बीच क्षैतिज अक्ष की स्थिति निर्धारित करके इसके स्वरूप को कैसे अनुकूलित किया जाए। Aspose.Slides for Java चार्ट और प्रस्तुतियों के साथ काम करने के लिए शक्तिशाली सुविधाएँ प्रदान करता है, जो इसे Java डेवलपर्स के लिए एक मूल्यवान उपकरण बनाता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट को और अधिक अनुकूलित कैसे करूँ?

आप चार्ट के विभिन्न पहलुओं को अनुकूलित कर सकते हैं, जिसमें डेटा श्रृंखला, चार्ट शीर्षक, लेजेंड और बहुत कुछ शामिल है।[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/) विस्तृत निर्देशों और उदाहरणों के लिए.

### क्या मैं चार्ट का प्रकार बदल सकता हूँ?

 हां, आप चार्ट प्रकार को संशोधित करके बदल सकते हैं`ChartType` चार्ट जोड़ते समय पैरामीटर। Aspose.Slides for Java विभिन्न चार्ट प्रकारों जैसे बार चार्ट, लाइन चार्ट और बहुत कुछ का समर्थन करता है।

### मैं और अधिक उदाहरण और दस्तावेज कहां पा सकता हूं?

 आप यहां पर विस्तृत दस्तावेज और अधिक उदाहरण पा सकते हैं[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/) पृष्ठ।

सिस्टम संसाधनों को रिलीज़ करने के लिए जब आप प्रस्तुतिकरण ऑब्जेक्ट का उपयोग कर लें तो उसे हटाना न भूलें:

```java
if (pres != null) pres.dispose();
```

इस ट्यूटोरियल के लिए बस इतना ही। आपने सीखा कि Aspose.Slides for Java का उपयोग करके चार्ट में स्थिति अक्ष कैसे सेट करें।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
