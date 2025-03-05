---
title: जावा स्लाइड्स में प्रगति अद्यतन के साथ पीडीएफ में कनवर्ट करें
linktitle: जावा स्लाइड्स में प्रगति अद्यतन के साथ पीडीएफ में कनवर्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके जावा में प्रगति अपडेट के साथ PowerPoint को PDF में बदलें। निर्बाध रूपांतरण के लिए स्रोत कोड और प्रगति ट्रैकिंग के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 36
url: /hi/java/presentation-conversion/convert-pdf-progress-update-java-slides/
---

## जावा के लिए Aspose.Slides का उपयोग करके जावा में प्रगति अपडेट के साथ PowerPoint को PDF में परिवर्तित करने का परिचय

इस चरण-दर-चरण मार्गदर्शिका में, हम प्रदर्शित करेंगे कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति (PPTX) को Java में PDF फ़ाइल में कैसे परिवर्तित किया जाए। इसके अतिरिक्त, हम रूपांतरण प्रक्रिया के दौरान प्रगति अपडेट शामिल करेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- जावा विकास वातावरण की स्थापना.
-  Aspose.Slides for Java लाइब्रेरी आपके प्रोजेक्ट में जोड़ दी गई है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://downloads.aspose.com/slides/java).

## चरण 1: Aspose.Slides for Java लाइब्रेरी आयात करें

आरंभ करने के लिए, आपको अपने जावा प्रोजेक्ट में Aspose.Slides लाइब्रेरी को आयात करना होगा। सुनिश्चित करें कि आपने अपने क्लासपाथ में Aspose.Slides JAR फ़ाइलें जोड़ी हैं।

```java
import com.aspose.slides.*;
```

## चरण 2: एक जावा क्लास बनाएं

 एक जावा क्लास बनाएं जहां आप पावरपॉइंट को पीडीएफ में बदलेंगे। चलिए इसका नाम रखते हैं`PowerPointToPdfConverter`.

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

## चरण 4: 'आपकी दस्तावेज़ निर्देशिका' को बदलें

 प्रतिस्थापित करें`"Your Document Directory"` में`PowerPointToPdfConverter` क्लास में अपनी पावरपॉइंट फ़ाइल का वास्तविक पथ और वांछित आउटपुट निर्देशिका डालें।

## चरण 5: संकलित करें और चलाएँ

अपने जावा क्लास को संकलित करें और चलाएँ`PowerPointToPdfConverter` क्लास। यह कंसोल में प्रगति अपडेट प्रदान करते हुए पावरपॉइंट प्रेजेंटेशन को पीडीएफ फाइल में परिवर्तित करेगा।

## जावा स्लाइड्स में प्रगति अद्यतन के साथ पीडीएफ में कनवर्ट करने के लिए पूर्ण स्रोत कोड

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

इस चरण-दर-चरण मार्गदर्शिका में, हमने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुति (PPTX) को Java में PDF फ़ाइल में बदलने का तरीका खोजा। इसके अतिरिक्त, हमने ऑपरेशन की स्थिति पर नज़र रखने के लिए रूपांतरण प्रक्रिया के दौरान प्रगति अपडेट लागू किए।

## अक्सर पूछे जाने वाले प्रश्न

### मैं Java के लिए Aspose.Slides कैसे डाउनलोड करूं?

 आप Aspose.Slides for Java को Aspose वेबसाइट से डाउनलोड कर सकते हैं[यहाँ](https://downloads.aspose.com/slides/java).

###  इसका उद्देश्य क्या है?`IProgressCallback`?

`IProgressCallback` निर्यात संचालन के दौरान प्रगति रिपोर्टिंग को लागू करने के लिए Aspose.Slides द्वारा Java के लिए प्रदान किया गया एक इंटरफ़ेस है। यह आपको प्रस्तुतियों को PDF में परिवर्तित करने जैसे कार्यों की प्रगति को ट्रैक करने की अनुमति देता है।

### क्या मैं अन्य PowerPoint कार्यों के लिए Aspose.Slides for Java का उपयोग कर सकता हूँ?

हां, Aspose.Slides for Java पावरपॉइंट प्रस्तुतियों के साथ काम करने के लिए व्यापक कार्यक्षमता प्रदान करता है, जिसमें उन्हें बनाना, संशोधित करना और विभिन्न प्रारूपों में परिवर्तित करना शामिल है।

### मैं पीडीएफ रूपांतरण विकल्पों को कैसे अनुकूलित कर सकता हूं?

 आप पीडीएफ रूपांतरण विकल्पों को संशोधित करके अनुकूलित कर सकते हैं`PdfOptions` कॉल करने से पहले ऑब्जेक्ट`presentation.save` विधि। इसमें पृष्ठ का आकार, गुणवत्ता और अन्य जैसे गुण सेट करना शामिल है।
