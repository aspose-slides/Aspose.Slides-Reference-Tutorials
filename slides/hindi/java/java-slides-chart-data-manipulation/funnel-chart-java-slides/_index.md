---
title: जावा स्लाइड्स में फ़नल चार्ट
linktitle: जावा स्लाइड्स में फ़नल चार्ट
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ PowerPoint प्रस्तुतियों में फ़नल चार्ट बनाना सीखें। प्रभावी डेटा विज़ुअलाइज़ेशन के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 18
url: /hi/java/chart-data-manipulation/funnel-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides for Java में फ़नल चार्ट बनाने का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में फ़नल चार्ट बनाने की प्रक्रिया के बारे में बताएँगे। फ़नल चार्ट डेटा को विज़ुअलाइज़ करने के लिए उपयोगी होते हैं जो अलग-अलग चरणों या श्रेणियों के माध्यम से क्रमिक रूप से कम या "फ़नल" होते हैं। हम आपको इसे प्राप्त करने में मदद करने के लिए स्रोत कोड के साथ चरण-दर-चरण निर्देश प्रदान करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- Aspose.Slides for Java लाइब्रेरी आपके प्रोजेक्ट में स्थापित और सेट अप की गई है।
- एक पावरपॉइंट प्रेजेंटेशन (PPTX) फ़ाइल जहाँ आप फ़नल चार्ट सम्मिलित करना चाहते हैं।

## चरण 1: Java के लिए Aspose.Slides आयात करें

सबसे पहले, आपको अपने जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी को आयात करना होगा। सुनिश्चित करें कि आपने अपने बिल्ड कॉन्फ़िगरेशन में आवश्यक निर्भरताएँ जोड़ दी हैं।

```java
import com.aspose.slides.*;
```

## चरण 2: प्रस्तुति और चार्ट आरंभ करें

इस चरण में, हम एक प्रस्तुति को आरंभ करते हैं और एक स्लाइड में फ़नल चार्ट जोड़ते हैं।

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    //पहली स्लाइड में निर्देशांक (50, 50) पर आयाम (500, 400) के साथ एक फ़नल चार्ट जोड़ें।
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## चरण 3: चार्ट डेटा परिभाषित करें

इसके बाद, हम अपने फ़नल चार्ट के लिए डेटा परिभाषित करते हैं। आप अपनी आवश्यकताओं के अनुसार श्रेणियों और डेटा बिंदुओं को अनुकूलित कर सकते हैं।

```java
// मौजूदा चार्ट डेटा साफ़ करें.
wb.clear(0);

// चार्ट के लिए श्रेणियाँ परिभाषित करें.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// फ़नल चार्ट श्रृंखला के लिए डेटा बिंदु जोड़ें.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## चरण 4: प्रस्तुति सहेजें

अंत में, हम फ़नल चार्ट के साथ प्रस्तुति को एक निर्दिष्ट फ़ाइल में सहेजते हैं।

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

बस! आपने Aspose.Slides for Java का उपयोग करके सफलतापूर्वक एक फ़नल चार्ट बना लिया है और उसे PowerPoint प्रेजेंटेशन में सम्मिलित कर लिया है।

## जावा स्लाइड्स में फ़नल चार्ट के लिए पूर्ण स्रोत कोड

```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
            pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## निष्कर्ष

इस चरण-दर-चरण मार्गदर्शिका में, हमने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति में फ़नल चार्ट बनाने का तरीका दिखाया है। फ़नल चार्ट डेटा को विज़ुअलाइज़ करने के लिए एक मूल्यवान उपकरण है जो प्रगति या संकीर्ण पैटर्न का अनुसरण करता है, जिससे जानकारी को प्रभावी ढंग से व्यक्त करना आसान हो जाता है। 

## अक्सर पूछे जाने वाले प्रश्न

### मैं फ़नल चार्ट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

आप विभिन्न चार्ट गुणों जैसे रंग, लेबल और शैलियों को संशोधित करके फ़नल चार्ट की उपस्थिति को अनुकूलित कर सकते हैं। चार्ट अनुकूलन विकल्पों पर विस्तृत जानकारी के लिए Aspose.Slides दस्तावेज़ देखें।

### क्या मैं फ़नल चार्ट में अधिक डेटा बिंदु या श्रेणियां जोड़ सकता हूं?

हां, आप चरण 3 में दिए गए कोड का विस्तार करके फ़नल चार्ट में अतिरिक्त डेटा बिंदु और श्रेणियां जोड़ सकते हैं। बस आवश्यकतानुसार अधिक श्रेणी लेबल और डेटा बिंदु जोड़ें।

### मैं स्लाइड पर फ़नल चार्ट की स्थिति और आकार कैसे बदल सकता हूँ?

आप चरण 2 में स्लाइड में चार्ट जोड़ते समय दिए गए निर्देशांक और आयामों को संशोधित करके फ़नल चार्ट की स्थिति और आकार को समायोजित कर सकते हैं। तदनुसार मान (50, 50, 500, 400) अपडेट करें।

### क्या मैं चार्ट को विभिन्न प्रारूपों में निर्यात कर सकता हूँ, जैसे कि PDF या छवि?

हां, Aspose.Slides for Java आपको फ़नल चार्ट के साथ प्रेजेंटेशन को PDF, इमेज फॉर्मेट और अन्य सहित विभिन्न फॉर्मेट में एक्सपोर्ट करने की अनुमति देता है। आप इसका उपयोग कर सकते हैं`SaveFormat` प्रस्तुति को सहेजते समय वांछित आउटपुट प्रारूप निर्दिष्ट करने के लिए विकल्प।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
