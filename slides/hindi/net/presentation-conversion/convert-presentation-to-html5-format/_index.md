---
title: प्रस्तुति को HTML5 प्रारूप में बदलें
linktitle: प्रस्तुति को HTML5 प्रारूप में बदलें
second_title: Aspose.Slides .NET पावरपॉइंट प्रोसेसिंग API
description: जानें कि .NET के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों को HTML5 प्रारूप में कैसे परिवर्तित किया जाए। वेब साझाकरण के लिए आसान और कुशल रूपांतरण।
weight: 22
url: /hi/net/presentation-conversion/convert-presentation-to-html5-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## .NET के लिए Aspose.Slides का उपयोग करके प्रस्तुति को HTML5 प्रारूप में बदलें

इस गाइड में, हम आपको Aspose.Slides for .NET लाइब्रेरी का उपयोग करके PowerPoint प्रेजेंटेशन (PPT/PPTX) को HTML5 फ़ॉर्मेट में बदलने की प्रक्रिया से अवगत कराएँगे। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो आपको विभिन्न फ़ॉर्मेट में PowerPoint प्रेजेंटेशन को बदलने और बदलने की अनुमति देती है।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. विज़ुअल स्टूडियो: आपके सिस्टम पर विज़ुअल स्टूडियो स्थापित होना आवश्यक है।
2.  Aspose.Slides for .NET: Aspose.Slides for .NET लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://downloads.aspose.com/slides/net).

## रूपांतरण चरण

किसी प्रस्तुति को HTML5 प्रारूप में परिवर्तित करने के लिए इन चरणों का पालन करें:

### एक नया प्रोजेक्ट बनाएं

विज़ुअल स्टूडियो खोलें और एक नया प्रोजेक्ट बनाएं।

### Aspose.Slides में संदर्भ जोड़ें

अपने प्रोजेक्ट में, सॉल्यूशन एक्सप्लोरर में "संदर्भ" पर राइट-क्लिक करें और "संदर्भ जोड़ें" चुनें। आपके द्वारा डाउनलोड किए गए Aspose.Slides DLL को ब्राउज़ करें और जोड़ें।

### रूपांतरण कोड लिखें

कोड संपादक में, प्रस्तुति को HTML5 प्रारूप में परिवर्तित करने के लिए निम्नलिखित कोड लिखें:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

namespace PresentationToHTML5Converter
{
    class Program
    {
        static void Main(string[] args)
        {
            // प्रस्तुति लोड करें
            using (Presentation presentation = new Presentation("input.pptx"))
            {
                // HTML5 विकल्प परिभाषित करें
                Html5Options options = new Html5Options();

                // प्रस्तुति को HTML5 के रूप में सहेजें
                presentation.Save("output.html", SaveFormat.Html, options);
            }
        }
    }
}
```

 प्रतिस्थापित करें`"input.pptx"` आपके इनपुट प्रस्तुति के पथ के साथ और`"output.html"` वांछित आउटपुट HTML फ़ाइल पथ के साथ.

## एप्लिकेशन चलाएँ

अपना एप्लिकेशन बनाएं और चलाएं। यह प्रेजेंटेशन को HTML5 फॉर्मेट में बदल देगा और इसे HTML फ़ाइल के रूप में सेव कर देगा।

## निष्कर्ष

इन चरणों का पालन करके, आप आसानी से Aspose.Slides for .NET लाइब्रेरी का उपयोग करके PowerPoint प्रस्तुतियों को HTML5 प्रारूप में परिवर्तित कर सकते हैं। यह आपको PowerPoint सॉफ़्टवेयर की आवश्यकता के बिना वेब पर अपनी प्रस्तुतियों को साझा करने में सक्षम बनाता है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं HTML5 आउटपुट के स्वरूप को कैसे अनुकूलित कर सकता हूँ?

 आप HTML5 आउटपुट के स्वरूप को विभिन्न विकल्पों को सेट करके अनुकूलित कर सकते हैं`Html5Options`वर्ग देखें।[प्रलेखन](https://reference.aspose.com/slides/net/aspose.slides.export/html5options) उपलब्ध अनुकूलन विकल्पों के लिए.

### क्या मैं एनिमेशन और ट्रांजिशन के साथ प्रस्तुतियों को परिवर्तित कर सकता हूँ?

हां, Aspose.Slides for .NET एनिमेशन और ट्रांजिशन के साथ प्रस्तुतियों को HTML5 प्रारूप में परिवर्तित करने का समर्थन करता है।

### क्या Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?

 हां, आप .NET के लिए Aspose.Slides का निःशुल्क परीक्षण संस्करण प्राप्त कर सकते हैं[डाउनलोड पृष्ठ](https://releases.aspose.com/slides/net).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
