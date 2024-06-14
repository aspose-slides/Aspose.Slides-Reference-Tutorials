---
title: जावा स्लाइड्स में सूत्रों की गणना करें
linktitle: जावा स्लाइड्स में सूत्रों की गणना करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java Slides में फ़ार्मुलों की गणना करना सीखें। गतिशील PowerPoint प्रस्तुतियों के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 10
url: /hi/java/data-manipulation/calculate-formulas-java-slides/
---

## Aspose.Slides का उपयोग करके जावा स्लाइड्स में सूत्रों की गणना करने का परिचय

इस गाइड में, हम Aspose.Slides for Java API का उपयोग करके Java स्लाइड्स में फ़ॉर्मूला की गणना करने का तरीका प्रदर्शित करेंगे। Aspose.Slides PowerPoint प्रस्तुतियों के साथ काम करने के लिए एक शक्तिशाली लाइब्रेरी है, और यह स्लाइड्स के भीतर चार्ट में हेरफेर करने और फ़ॉर्मूला गणना करने की सुविधाएँ प्रदान करती है।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा विकास पर्यावरण
-  Aspose.Slides for Java लाइब्रेरी (आप इसे यहां से डाउनलोड कर सकते हैं)[यहाँ](https://releases.aspose.com/slides/java/)
- जावा प्रोग्रामिंग का बुनियादी ज्ञान

## चरण 1: एक नई प्रस्तुति बनाएँ

सबसे पहले, आइए एक नया पावरपॉइंट प्रेजेंटेशन बनाएं और उसमें एक स्लाइड जोड़ें। इस उदाहरण में हम एक ही स्लाइड के साथ काम करेंगे।

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## चरण 2: स्लाइड में चार्ट जोड़ें

अब, स्लाइड में एक क्लस्टर्ड कॉलम चार्ट जोड़ें। हम इस चार्ट का उपयोग फ़ॉर्मूला गणनाओं को प्रदर्शित करने के लिए करेंगे।

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## चरण 3: सूत्र और मान सेट करें

इसके बाद, हम Aspose.Slides API का उपयोग करके चार्ट डेटा सेल के लिए सूत्र और मान सेट करेंगे। हम इन सेल के लिए सूत्रों की गणना करेंगे।

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

// सेल A1 के लिए सूत्र पुनः सेट करें
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## चरण 4: प्रस्तुति सहेजें

अंत में, आइए संशोधित प्रस्तुति को गणना किए गए सूत्रों के साथ सहेजें।

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## जावा स्लाइड्स में सूत्रों की गणना के लिए पूर्ण स्रोत कोड

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
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

इस गाइड में, हमने सीखा है कि Aspose.Slides for Java का उपयोग करके Java स्लाइड में फ़ार्मुलों की गणना कैसे करें। हमने एक नई प्रस्तुति बनाई, उसमें एक चार्ट जोड़ा, चार्ट डेटा सेल के लिए फ़ार्मुलों और मानों को सेट किया, और गणना किए गए फ़ार्मुलों के साथ प्रस्तुति को सहेजा।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट डेटा कक्षों के लिए सूत्र कैसे सेट करूँ?

 आप चार्ट डेटा कक्षों के लिए सूत्र सेट कर सकते हैं`setFormula` उसकि विधि`IChartDataCell` Aspose.Slides में.

### मैं चार्ट डेटा कक्षों के लिए मान कैसे सेट करूँ?

 आप चार्ट डेटा कक्षों के लिए मान सेट कर सकते हैं`setValue` उसकि विधि`IChartDataCell` Aspose.Slides में.

### मैं कार्यपुस्तिका में सूत्रों की गणना कैसे करूँ?

 आप किसी कार्यपुस्तिका में सूत्रों की गणना कर सकते हैं`calculateFormulas` उसकि विधि`IChartDataWorkbook` Aspose.Slides में.
