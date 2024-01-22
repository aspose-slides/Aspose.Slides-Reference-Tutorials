---
title: जावा स्लाइड्स में चार्ट डेटा सेल फ़ॉर्मूले
linktitle: जावा स्लाइड्स में चार्ट डेटा सेल फ़ॉर्मूले
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा पावरपॉइंट प्रस्तुतियों में चार्ट डेटा सेल फॉर्मूला सेट करना सीखें। सूत्रों के साथ गतिशील चार्ट बनाएं।
type: docs
weight: 11
url: /hi/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

## जावा के लिए Aspose.Slides में चार्ट डेटा सेल फ़ॉर्मूले का परिचय

इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके चार्ट डेटा सेल फ़ार्मुलों के साथ कैसे काम करें, इसका पता लगाएंगे। Aspose.Slides के साथ, आप PowerPoint प्रस्तुतियों में चार्ट बना और हेरफेर कर सकते हैं, जिसमें डेटा सेल के लिए सूत्र सेट करना भी शामिल है।

## आवश्यक शर्तें

 शुरू करने से पहले, सुनिश्चित करें कि आपके पास जावा लाइब्रेरी के लिए Aspose.Slides स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: एक पावरपॉइंट प्रेजेंटेशन बनाएं

सबसे पहले, आइए एक नया पावरपॉइंट प्रेजेंटेशन बनाएं और उसमें एक चार्ट जोड़ें।

```java
String outpptxFile = RunExamples.getOutPath() + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // पहली स्लाइड में एक चार्ट जोड़ें
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

अब, आइए चार्ट में विशिष्ट डेटा सेल के लिए सूत्र सेट करें। इस उदाहरण में, हम दो अलग-अलग कोशिकाओं के लिए सूत्र निर्धारित करेंगे।

### सेल 1: ए1 नोटेशन का उपयोग करना

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

उपरोक्त कोड में, हमने A1 नोटेशन का उपयोग करके सेल B2 के लिए एक सूत्र निर्धारित किया है। सूत्र F2 से H5 तक कोशिकाओं के योग की गणना करता है और परिणाम में 1 जोड़ता है।

### सेल 2: R1C1 नोटेशन का उपयोग करना

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

यहां, हमने R1C1 नोटेशन का उपयोग करके सेल C2 के लिए एक सूत्र निर्धारित किया है। सूत्र R2C6 से R5C8 की सीमा के भीतर अधिकतम मान की गणना करता है और फिर इसे 3 से विभाजित करता है।

## चरण 3: सूत्रों की गणना करें

सूत्र सेट करने के बाद, निम्नलिखित कोड का उपयोग करके उनकी गणना करना आवश्यक है:

```java
workbook.calculateFormulas();
```

यह चरण सुनिश्चित करता है कि चार्ट सूत्रों के आधार पर अद्यतन मूल्यों को दर्शाता है।

## चरण 4: प्रस्तुति सहेजें

अंत में, संशोधित प्रस्तुति को एक फ़ाइल में सहेजें।

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## जावा स्लाइड्स में चार्ट डेटा सेल फ़ॉर्मूले के लिए संपूर्ण स्रोत कोड

```java
String outpptxFile = RunExamples.getOutPath() + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
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

इस ट्यूटोरियल में, हमने पता लगाया है कि जावा के लिए Aspose.Slides में चार्ट डेटा सेल फ़ार्मुलों के साथ कैसे काम किया जाए। हमने पावरपॉइंट प्रेजेंटेशन बनाना, चार्ट जोड़ना, डेटा सेल के लिए सूत्र सेट करना, सूत्रों की गणना करना और प्रेजेंटेशन को सहेजना शामिल किया है। अब आप अपनी प्रस्तुतियों में गतिशील और डेटा-संचालित चार्ट बनाने के लिए इन क्षमताओं का लाभ उठा सकते हैं।

## पूछे जाने वाले प्रश्न

### मैं किसी विशिष्ट स्लाइड में चार्ट कैसे जोड़ूँ?

 किसी विशिष्ट स्लाइड में चार्ट जोड़ने के लिए, आप इसका उपयोग कर सकते हैं`getSlides().get_Item(slideIndex)` वांछित स्लाइड तक पहुँचने की विधि, और फिर इसका उपयोग करें`addChart` चार्ट जोड़ने की विधि.

### क्या मैं डेटा सेल में विभिन्न प्रकार के फ़ार्मुलों का उपयोग कर सकता हूँ?

हाँ, आप डेटा सेल फ़ार्मुलों में गणितीय संचालन, फ़ंक्शंस और अन्य सेल के संदर्भ सहित विभिन्न प्रकार के फ़ार्मुलों का उपयोग कर सकते हैं।

### मैं चार्ट प्रकार कैसे बदलूं?

 आप इसका उपयोग करके चार्ट प्रकार बदल सकते हैं`setChartType` पर विधि`IChart` वस्तु और वांछित निर्दिष्ट करना`ChartType`.