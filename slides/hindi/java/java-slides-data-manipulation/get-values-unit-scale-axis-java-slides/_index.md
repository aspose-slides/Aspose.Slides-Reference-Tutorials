---
title: जावा स्लाइड्स में अक्ष से मान और इकाई स्केल प्राप्त करें
linktitle: जावा स्लाइड्स में अक्ष से मान और इकाई स्केल प्राप्त करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java Slides में अक्षों से मान और इकाई स्केल प्राप्त करना सीखें। अपनी डेटा विश्लेषण क्षमताओं को बढ़ाएँ।
weight: 20
url: /hi/java/data-manipulation/get-values-unit-scale-axis-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में अक्ष से मान और इकाई स्केल प्राप्त करने का परिचय

इस ट्यूटोरियल में, हम जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में अक्ष से मान और इकाई स्केल प्राप्त करने का तरीका जानेंगे। चाहे आप डेटा विज़ुअलाइज़ेशन प्रोजेक्ट पर काम कर रहे हों या अपने जावा अनुप्रयोगों में चार्ट डेटा का विश्लेषण करने की आवश्यकता हो, अक्ष मानों तक पहुँचने का तरीका समझना आवश्यक है। हम आपको प्रक्रिया के बारे में चरण दर चरण बताएँगे, साथ ही कोड उदाहरण भी देंगे।

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

1. जावा विकास वातावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है और आप जावा प्रोग्रामिंग अवधारणाओं से परिचित हैं।

2.  Aspose.Slides for Java: Aspose.Slides for Java लाइब्रेरी को डाउनलोड करें और इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.aspose.com/slides/java/).

## चरण 1: प्रेजेंटेशन बनाना

आरंभ करने के लिए, आइए Aspose.Slides for Java का उपयोग करके एक नई प्रस्तुति बनाएं:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 प्रतिस्थापित करें`"Your Document Directory"` उस निर्देशिका का पथ जहाँ आप प्रस्तुति को सहेजना चाहते हैं.

## चरण 2: चार्ट जोड़ना

इसके बाद, हम प्रस्तुति में एक चार्ट जोड़ेंगे। इस उदाहरण में, हम एक क्षेत्र चार्ट बनाएंगे:

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
chart.validateChartLayout();
```

हमने प्रस्तुति की पहली स्लाइड में एक क्षेत्र चार्ट जोड़ा है। आप आवश्यकतानुसार चार्ट प्रकार और स्थिति को अनुकूलित कर सकते हैं।

## चरण 3: ऊर्ध्वाधर अक्ष मान प्राप्त करना

अब, आइए चार्ट के ऊर्ध्वाधर अक्ष से मान प्राप्त करें:

```java
double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
```

यहाँ, हम ऊर्ध्वाधर अक्ष के अधिकतम और न्यूनतम मान प्राप्त कर रहे हैं। ये मान विभिन्न डेटा विश्लेषण कार्यों के लिए उपयोगी हो सकते हैं।

## चरण 4: क्षैतिज अक्ष मान प्राप्त करना

इसी प्रकार, हम क्षैतिज अक्ष से मान प्राप्त कर सकते हैं:

```java
double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
```

`majorUnit` और`minorUnit` मान क्रमशः क्षैतिज अक्ष पर प्रमुख और लघु इकाइयों का प्रतिनिधित्व करते हैं।

## चरण 5: प्रस्तुति को सहेजना

एक बार जब हम अक्ष मान प्राप्त कर लेते हैं, तो हम प्रस्तुति को सहेज सकते हैं:

```java
pres.save(dataDir + "ChartValues.pptx", SaveFormat.Pptx);
```

यह कोड प्राप्त अक्ष मानों के साथ प्रस्तुति को PowerPoint फ़ाइल में सहेजता है।

## जावा स्लाइड्स में अक्ष से मान और इकाई स्केल प्राप्त करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
	chart.validateChartLayout();
	double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
	double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
	double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
	double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
	// प्रस्तुति सहेजना
	pres.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में अक्षों से मान और इकाई स्केल प्राप्त करने का तरीका खोजा है। चार्ट के साथ काम करते समय और अपने जावा अनुप्रयोगों के भीतर डेटा का विश्लेषण करते समय यह अविश्वसनीय रूप से मूल्यवान हो सकता है। जावा के लिए Aspose.Slides आपको प्रस्तुतियों के साथ प्रोग्रामेटिक रूप से काम करने के लिए आवश्यक उपकरण प्रदान करता है, जिससे आपको चार्ट डेटा और बहुत कुछ पर नियंत्रण मिलता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Aspose.Slides for Java में चार्ट प्रकार को कैसे अनुकूलित कर सकता हूँ?

 चार्ट प्रकार को अनुकूलित करने के लिए, बस प्रतिस्थापित करें`ChartType.Area` अपनी प्रस्तुति में चार्ट जोड़ते समय इच्छित चार्ट प्रकार का चयन करें।

### क्या मैं चार्ट अक्ष लेबल का स्वरूप बदल सकता हूँ?

हां, आप Aspose.Slides for Java का उपयोग करके चार्ट अक्ष लेबल की उपस्थिति को अनुकूलित कर सकते हैं। विस्तृत मार्गदर्शन के लिए दस्तावेज़ देखें।

### क्या Aspose.Slides for Java नवीनतम Java संस्करणों के साथ संगत है?

Aspose.Slides for Java को नवीनतम Java संस्करणों का समर्थन करने के लिए नियमित रूप से अद्यतन किया जाता है, जिससे नवीनतम Java विकासों के साथ संगतता सुनिश्चित होती है।

### क्या मैं व्यावसायिक परियोजनाओं में Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?

हां, आप व्यावसायिक परियोजनाओं में जावा के लिए Aspose.Slides का उपयोग कर सकते हैं। यह विभिन्न परियोजना आवश्यकताओं के अनुरूप लाइसेंसिंग विकल्प प्रदान करता है।

### मैं Aspose.Slides for Java के लिए और अधिक संसाधन और दस्तावेज़ कहां पा सकता हूं?

 आप यहां पर व्यापक दस्तावेज और अतिरिक्त संसाधन पा सकते हैं[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/) वेबसाइट।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
