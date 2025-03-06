---
title: जावा स्लाइड्स में चार्ट डेटा सेल सूत्र
linktitle: जावा स्लाइड्स में चार्ट डेटा सेल सूत्र
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java PowerPoint प्रस्तुतियों में चार्ट डेटा सेल फ़ॉर्मूले सेट करना सीखें। फ़ॉर्मूले के साथ गतिशील चार्ट बनाएँ।
weight: 11
url: /hi/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides for Java में चार्ट डेटा सेल फ़ार्मुलों का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके चार्ट डेटा सेल फ़ॉर्मूले के साथ काम करने का तरीका जानेंगे। Aspose.Slides के साथ, आप डेटा सेल के लिए फ़ॉर्मूले सेट करने सहित PowerPoint प्रस्तुतियों में चार्ट बना और उनमें हेरफेर कर सकते हैं।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: पावरपॉइंट प्रेजेंटेशन बनाएं

सबसे पहले, आइए एक नया पावरपॉइंट प्रेजेंटेशन बनाएं और उसमें एक चार्ट जोड़ें।

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // पहली स्लाइड में चार्ट जोड़ें
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // चार्ट डेटा के लिए कार्यपुस्तिका प्राप्त करें
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // डेटा सेल संचालन जारी रखें
    // ...
    
    // प्रस्तुति सहेजें
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## चरण 2: डेटा सेल के लिए सूत्र सेट करें

अब, चार्ट में विशिष्ट डेटा सेल के लिए सूत्र सेट करते हैं। इस उदाहरण में, हम दो अलग-अलग सेल के लिए सूत्र सेट करेंगे।

### सेल 1: A1 संकेतन का उपयोग करना

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

ऊपर दिए गए कोड में, हमने A1 संकेतन का उपयोग करके सेल B2 के लिए एक सूत्र निर्धारित किया है। सूत्र F2 से H5 तक के सेल के योग की गणना करता है और परिणाम में 1 जोड़ता है।

### सेल 2: R1C1 संकेतन का उपयोग करना

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

यहाँ, हम R1C1 संकेतन का उपयोग करके सेल C2 के लिए एक सूत्र सेट करते हैं। सूत्र R2C6 से R5C8 की सीमा के भीतर अधिकतम मान की गणना करता है और फिर उसे 3 से विभाजित करता है।

## चरण 3: सूत्रों की गणना करें

सूत्र निर्धारित करने के बाद, निम्नलिखित कोड का उपयोग करके उनकी गणना करना आवश्यक है:

```java
workbook.calculateFormulas();
```

यह चरण यह सुनिश्चित करता है कि चार्ट सूत्रों के आधार पर अद्यतन मानों को प्रतिबिंबित करता है।

## चरण 4: प्रस्तुति सहेजें

अंत में, संशोधित प्रस्तुति को फ़ाइल में सहेजें।

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## जावा स्लाइड्स में चार्ट डेटा सेल फ़ार्मुलों के लिए पूर्ण स्रोत कोड

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने Aspose.Slides for Java में चार्ट डेटा सेल फ़ॉर्मूले के साथ काम करने का तरीका खोजा है। हमने PowerPoint प्रेजेंटेशन बनाना, चार्ट जोड़ना, डेटा सेल के लिए फ़ॉर्मूले सेट करना, फ़ॉर्मूले की गणना करना और प्रेजेंटेशन को सहेजना शामिल किया है। अब आप अपनी प्रेजेंटेशन में गतिशील और डेटा-संचालित चार्ट बनाने के लिए इन क्षमताओं का लाभ उठा सकते हैं।

## पूछे जाने वाले प्रश्न

### मैं किसी विशिष्ट स्लाइड में चार्ट कैसे जोड़ूं?

 किसी विशिष्ट स्लाइड में चार्ट जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`getSlides().get_Item(slideIndex)` वांछित स्लाइड तक पहुंचने के लिए विधि, और फिर का उपयोग करें`addChart` चार्ट जोड़ने की विधि.

### क्या मैं डेटा सेल में विभिन्न प्रकार के सूत्रों का उपयोग कर सकता हूँ?

हां, आप डेटा सेल सूत्रों में गणितीय संक्रियाओं, फ़ंक्शन और अन्य कक्षों के संदर्भों सहित विभिन्न प्रकार के सूत्रों का उपयोग कर सकते हैं।

### मैं चार्ट का प्रकार कैसे बदलूं?

 आप इसका उपयोग करके चार्ट प्रकार बदल सकते हैं`setChartType` विधि पर`IChart` वस्तु और वांछित निर्दिष्ट करना`ChartType`.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
