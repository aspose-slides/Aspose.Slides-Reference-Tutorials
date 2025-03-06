---
title: जावा स्लाइड्स में चार्ट प्लॉट क्षेत्र से चौड़ाई और ऊंचाई प्राप्त करें
linktitle: जावा स्लाइड्स में चार्ट प्लॉट क्षेत्र से चौड़ाई और ऊंचाई प्राप्त करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java Slides में चार्ट प्लॉट क्षेत्र आयाम प्राप्त करना सीखें। अपने PowerPoint स्वचालन कौशल को बढ़ाएँ।
weight: 21
url: /hi/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## परिचय

चार्ट PowerPoint प्रस्तुतियों में डेटा को विज़ुअलाइज़ करने का एक शक्तिशाली तरीका है। कभी-कभी, आपको विभिन्न कारणों से चार्ट के प्लॉट क्षेत्र के आयामों को जानने की आवश्यकता हो सकती है, जैसे कि चार्ट के भीतर तत्वों का आकार बदलना या उनका स्थान बदलना। यह मार्गदर्शिका प्रदर्शित करेगी कि Java और Aspose.Slides for Java का उपयोग करके प्लॉट क्षेत्र की चौड़ाई और ऊँचाई कैसे प्राप्त करें।

## आवश्यक शर्तें

 इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java प्रोजेक्ट में सेट अप है। आप Aspose वेबसाइट से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: वातावरण की स्थापना

सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी जोड़ी गई है। आप अपने प्रोजेक्ट की निर्भरता में लाइब्रेरी को शामिल करके या मैन्युअल रूप से JAR फ़ाइल जोड़कर ऐसा कर सकते हैं।

## चरण 2: पावरपॉइंट प्रेजेंटेशन बनाना

आइए एक पावरपॉइंट प्रेजेंटेशन बनाकर और उसमें एक स्लाइड जोड़कर शुरुआत करें। यह हमारे चार्ट के लिए कंटेनर का काम करेगा।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 प्रतिस्थापित करें`"Your Document Directory"` अपने दस्तावेज़ निर्देशिका के पथ के साथ.

## चरण 3: चार्ट जोड़ना

अब, स्लाइड में एक क्लस्टर्ड कॉलम चार्ट जोड़ें। हम चार्ट लेआउट को भी मान्य करेंगे।

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

यह कोड (500, 350) आयाम के साथ स्थिति (100, 100) पर एक क्लस्टर कॉलम चार्ट बनाता है।

## चरण 4: प्लॉट क्षेत्र का आयाम प्राप्त करना

चार्ट के प्लॉट क्षेत्र की चौड़ाई और ऊंचाई प्राप्त करने के लिए, हम निम्नलिखित कोड का उपयोग कर सकते हैं:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 अब, चर`x`, `y`, `w` , और`h` प्लॉट क्षेत्र के X-निर्देशांक, Y-निर्देशांक, चौड़ाई और ऊंचाई के संबंधित मान शामिल करें।

## चरण 5: प्रस्तुति को सहेजना

अंत में, चार्ट के साथ प्रस्तुति को सेव करें।

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 प्रतिस्थापित करना सुनिश्चित करें`"Chart_out.pptx"` अपने इच्छित आउटपुट फ़ाइल नाम के साथ.

## जावा स्लाइड्स में चार्ट प्लॉट क्षेत्र से चौड़ाई और ऊंचाई प्राप्त करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// चार्ट के साथ प्रस्तुति सहेजें
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## निष्कर्ष

इस लेख में, हमने बताया है कि Aspose.Slides for Java API का उपयोग करके Java Slides में चार्ट के प्लॉट क्षेत्र की चौड़ाई और ऊँचाई कैसे प्राप्त करें। यह जानकारी तब उपयोगी हो सकती है जब आपको PowerPoint प्रस्तुतियों में अपने चार्ट के लेआउट को गतिशील रूप से समायोजित करने की आवश्यकता हो।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट प्रकार को क्लस्टर्ड कॉलम के अलावा किसी अन्य प्रकार में कैसे बदल सकता हूँ?

 आप चार्ट प्रकार को बदलकर बदल सकते हैं`ChartType.ClusteredColumn` वांछित चार्ट प्रकार गणना के साथ, जैसे`ChartType.Line` या`ChartType.Pie`.

### क्या मैं चार्ट के अन्य गुणों को संशोधित कर सकता हूँ?

हां, आप Aspose.Slides for Java API का उपयोग करके चार्ट के विभिन्न गुणों, जैसे डेटा, लेबल और फ़ॉर्मेटिंग को संशोधित कर सकते हैं। अधिक जानकारी के लिए दस्तावेज़ देखें।

### क्या Aspose.Slides for Java व्यावसायिक पावरपॉइंट स्वचालन के लिए उपयुक्त है?

हां, Aspose.Slides for Java जावा अनुप्रयोगों में PowerPoint कार्यों को स्वचालित करने के लिए एक शक्तिशाली लाइब्रेरी है। यह प्रस्तुतियों, स्लाइडों, आकृतियों, चार्टों और बहुत कुछ के साथ काम करने के लिए व्यापक सुविधाएँ प्रदान करता है।

### मैं Aspose.Slides for Java के बारे में अधिक कैसे जान सकता हूँ?

 आप Aspose.Slides for Java प्रलेखन पृष्ठ पर विस्तृत प्रलेखन और उदाहरण पा सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
