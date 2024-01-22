---
title: जावा स्लाइड्स में प्रगति अद्यतन के साथ पीडीएफ में कनवर्ट करें
linktitle: जावा स्लाइड्स में प्रगति अद्यतन के साथ पीडीएफ में कनवर्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Slides का उपयोग करके जावा में प्रगति अपडेट के साथ पावरपॉइंट को पीडीएफ में बदलें। निर्बाध रूपांतरण के लिए स्रोत कोड और प्रगति ट्रैकिंग के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 36
url: /hi/java/presentation-conversion/convert-pdf-progress-update-java-slides/
---

## जावा के लिए Aspose.Slides का उपयोग करके जावा में प्रगति अपडेट के साथ पावरपॉइंट को पीडीएफ में कनवर्ट करने का परिचय

इस चरण-दर-चरण मार्गदर्शिका में, हम दिखाएंगे कि जावा के लिए Aspose.Slides का उपयोग करके जावा में एक PowerPoint प्रेजेंटेशन (PPTX) को एक पीडीएफ फ़ाइल में कैसे परिवर्तित किया जाए। इसके अतिरिक्त, हम रूपांतरण प्रक्रिया के दौरान प्रगति अद्यतन शामिल करेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:

- जावा विकास पर्यावरण की स्थापना।
-  जावा लाइब्रेरी के लिए Aspose.Slides आपके प्रोजेक्ट में जोड़ा गया। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://downloads.aspose.com/slides/java).

## चरण 1: जावा लाइब्रेरी के लिए Aspose.Slides आयात करें

आरंभ करने के लिए, आपको Aspose.Slides लाइब्रेरी को अपने जावा प्रोजेक्ट में आयात करना होगा। सुनिश्चित करें कि आपने Aspose.Slides JAR फ़ाइलें अपने क्लासपाथ में जोड़ ली हैं।

```java
import com.aspose.slides.*;
```

## चरण 2: एक जावा क्लास बनाएं

एक जावा क्लास बनाएं जहां आप पावरपॉइंट से पीडीएफ रूपांतरण करेंगे। आइए इसे नाम दें`PowerPointToPdfConverter`.

```java
public class PowerPointToPdfConverter {
    public static void main(String[] args) {
        // दस्तावेज़ निर्देशिका का पथ.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "ConvertToPDF.pptx");
        try {
            ISaveOptions saveOptions = new PdfOptions();
            saveOptions.setProgressCallback(new ExportProgressHandler());
            presentation.save(dataDir + "ConvertToPDF.pdf", SaveFormat.Pdf, saveOptions);
        } finally {
            if (presentation != null) presentation.dispose();
        }
    }
}
```

## चरण 3: प्रगति कॉलबैक लागू करें

 हम रूपांतरण प्रक्रिया के दौरान अपडेट प्राप्त करने के लिए एक प्रगति कॉलबैक हैंडलर लागू करेंगे। आइए नाम से एक क्लास बनाएं`ExportProgressHandler` इस उद्देश्य से।

```java
class ExportProgressHandler implements IProgressCallback {
    public void reporting(double progressValue) {
        // यहां प्रगति प्रतिशत मान का उपयोग करें
        long progress = Math.round(progressValue);
        System.out.println(progress + "% file converted");
    }
}
```

## चरण 4: 'अपनी दस्तावेज़ निर्देशिका' बदलें

 प्रतिस्थापित करें`"Your Document Directory"` में`PowerPointToPdfConverter` आपकी PowerPoint फ़ाइल के वास्तविक पथ और वांछित आउटपुट निर्देशिका के साथ क्लास।

## चरण 5: संकलित करें और चलाएँ

 अपनी जावा क्लास संकलित करें और चलाएँ`PowerPointToPdfConverter` कक्षा। यह कंसोल में प्रगति अपडेट प्रदान करते हुए पावरपॉइंट प्रेजेंटेशन को पीडीएफ फाइल में बदल देगा।

## जावा स्लाइड में प्रगति अद्यतन के साथ पीडीएफ में कनवर्ट करने के लिए संपूर्ण स्रोत कोड

```java
        // दस्तावेज़ निर्देशिका का पथ.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "ConvertToPDF.pptx");
        try
        {
            ISaveOptions saveOptions = new PdfOptions();
            saveOptions.setProgressCallback(new ExportProgressHandler());
            presentation.save(dataDir + "ConvertToPDF.pdf", SaveFormat.Pdf, saveOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
    }
}
class ExportProgressHandler implements IProgressCallback
{
    public void reporting(double progressValue)
    {
        // यहां प्रगति प्रतिशत मान का उपयोग करें
        long progress = Math.round(progressValue);
        System.out.println(progress + "% file converted");
```

## निष्कर्ष

इस चरण-दर-चरण मार्गदर्शिका में, हमने पता लगाया कि जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रेजेंटेशन (PPTX) को जावा में एक पीडीएफ फ़ाइल में कैसे परिवर्तित किया जाए। इसके अतिरिक्त, हमने ऑपरेशन की स्थिति पर नज़र रखने के लिए रूपांतरण प्रक्रिया के दौरान प्रगति अपडेट लागू किए।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे डाउनलोड करूं?

 आप जावा के लिए Aspose.Slides को Aspose वेबसाइट से डाउनलोड कर सकते हैं[यहाँ](https://downloads.aspose.com/slides/java).

###  का उद्देश्य क्या है`IProgressCallback`?

`IProgressCallback` निर्यात संचालन के दौरान प्रगति रिपोर्टिंग को लागू करने के लिए जावा के लिए Aspose.Slides द्वारा प्रदान किया गया एक इंटरफ़ेस है। यह आपको प्रस्तुतियों को पीडीएफ में परिवर्तित करने जैसे कार्यों की प्रगति को ट्रैक करने की अनुमति देता है।

### क्या मैं अन्य PowerPoint संचालन के लिए Java के लिए Aspose.Slides का उपयोग कर सकता हूँ?

हां, जावा के लिए Aspose.Slides PowerPoint प्रस्तुतियों के साथ काम करने के लिए व्यापक कार्यक्षमता प्रदान करता है, जिसमें उन्हें बनाना, संशोधित करना और उन्हें विभिन्न प्रारूपों में परिवर्तित करना शामिल है।

### मैं पीडीएफ रूपांतरण विकल्पों को कैसे अनुकूलित कर सकता हूं?

 आप पीडीएफ रूपांतरण विकल्पों को संशोधित करके अनुकूलित कर सकते हैं`PdfOptions` कॉल करने से पहले ऑब्जेक्ट करें`presentation.save`तरीका। इसमें पृष्ठ आकार, गुणवत्ता और बहुत कुछ जैसी सेटिंग गुण शामिल हैं।
