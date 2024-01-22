---
title: जावा स्लाइड्स में सूत्रों की गणना करें
linktitle: जावा स्लाइड्स में सूत्रों की गणना करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में सूत्रों की गणना करना सीखें। गतिशील पावरपॉइंट प्रस्तुतियों के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/java/data-manipulation/calculate-formulas-java-slides/
---

## Aspose.Slides का उपयोग करके जावा स्लाइड्स में सूत्रों की गणना करने का परिचय

इस गाइड में, हम दिखाएंगे कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में सूत्रों की गणना कैसे करें। Aspose.Slides PowerPoint प्रस्तुतियों के साथ काम करने के लिए एक शक्तिशाली लाइब्रेरी है, और यह चार्ट में हेरफेर करने और स्लाइड के भीतर सूत्र गणना करने की सुविधाएँ प्रदान करता है।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा विकास पर्यावरण
-  जावा लाइब्रेरी के लिए Aspose.Slides (आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/)
- जावा प्रोग्रामिंग का बुनियादी ज्ञान

## चरण 1: एक नई प्रस्तुति बनाएं

सबसे पहले, आइए एक नया पावरपॉइंट प्रेजेंटेशन बनाएं और उसमें एक स्लाइड जोड़ें। इस उदाहरण में हम एक स्लाइड के साथ काम करेंगे।

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## चरण 2: स्लाइड में एक चार्ट जोड़ें

अब, स्लाइड में एक क्लस्टर्ड कॉलम चार्ट जोड़ें। हम सूत्र गणना प्रदर्शित करने के लिए इस चार्ट का उपयोग करेंगे।

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## चरण 3: सूत्र और मान निर्धारित करें

इसके बाद, हम Aspose.Slides API का उपयोग करके चार्ट डेटा सेल के लिए सूत्र और मान सेट करेंगे। हम इन कोशिकाओं के लिए सूत्रों की गणना करेंगे।

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// सेल A1 के लिए सूत्र सेट करें
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// सेल A2 के लिए मान सेट करें
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// सेल B2 के लिए सूत्र सेट करें
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// सेल C2 के लिए सूत्र सेट करें
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// सेल A1 के लिए फिर से फॉर्मूला सेट करें
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## चरण 4: प्रस्तुति सहेजें

अंत में, आइए संशोधित प्रस्तुति को परिकलित सूत्रों के साथ सहेजें।

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## जावा स्लाइड्स में सूत्रों की गणना के लिए पूर्ण स्रोत कोड

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस गाइड में, हमने सीखा है कि जावा के लिए Aspose.Slides का उपयोग करके जावा स्लाइड्स में सूत्रों की गणना कैसे करें। हमने एक नई प्रस्तुति बनाई, इसमें एक चार्ट जोड़ा, चार्ट डेटा कोशिकाओं के लिए सूत्र और मान सेट किए, और गणना सूत्रों के साथ प्रस्तुति को सहेजा।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट डेटा सेल के लिए सूत्र कैसे सेट करूं?

 आप इसका उपयोग करके चार्ट डेटा सेल के लिए सूत्र सेट कर सकते हैं`setFormula` उसकि विधि`IChartDataCell` Aspose.Slides में।

### मैं चार्ट डेटा सेल के लिए मान कैसे सेट करूं?

 आप इसका उपयोग करके चार्ट डेटा सेल के लिए मान सेट कर सकते हैं`setValue` उसकि विधि`IChartDataCell` Aspose.Slides में।

### मैं किसी कार्यपुस्तिका में सूत्रों की गणना कैसे करूँ?

 आप इसका उपयोग करके किसी कार्यपुस्तिका में सूत्रों की गणना कर सकते हैं`calculateFormulas` उसकि विधि`IChartDataWorkbook` Aspose.Slides में।
