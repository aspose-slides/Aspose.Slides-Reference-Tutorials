---
"description": "Aspose.Slides का उपयोग करके बाहरी संसाधनों से वेक्टर आधारित SVG छवियों को Java स्लाइड में जोड़ना सीखें। उच्च-गुणवत्ता वाले दृश्यों के साथ शानदार प्रस्तुतियाँ बनाएँ।"
"linktitle": "जावा स्लाइड्स में बाहरी संसाधन से SVG ऑब्जेक्ट से छवि जोड़ें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में बाहरी संसाधन से SVG ऑब्जेक्ट से छवि जोड़ें"
"url": "/hi/java/image-handling/add-image-from-svg-object-from-external-resource-in-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में बाहरी संसाधन से SVG ऑब्जेक्ट से छवि जोड़ें


## जावा स्लाइड्स में बाहरी संसाधन से SVG ऑब्जेक्ट से छवि जोड़ने का परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि Aspose.Slides का उपयोग करके किसी बाहरी संसाधन से SVG (स्केलेबल वेक्टर ग्राफ़िक्स) ऑब्जेक्ट से अपनी जावा स्लाइड में छवि कैसे जोड़ें। यह एक मूल्यवान सुविधा हो सकती है जब आप अपनी प्रस्तुतियों में वेक्टर-आधारित छवियों को शामिल करना चाहते हैं, जिससे उच्च-गुणवत्ता वाले दृश्य सुनिश्चित होते हैं। आइए चरण-दर-चरण मार्गदर्शिका में गोता लगाएँ।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- जावा विकास पर्यावरण
- Aspose.Slides for Java लाइब्रेरी
- एक SVG छवि फ़ाइल (उदाहरणार्थ, "image1.svg")

## परियोजना की स्थापना

सुनिश्चित करें कि आपका जावा डेवलपमेंट एनवायरनमेंट इस प्रोजेक्ट के लिए तैयार है। आप जावा के लिए अपने पसंदीदा इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (IDE) का उपयोग कर सकते हैं।

## चरण 1: अपने प्रोजेक्ट में Aspose.Slides जोड़ना

अपने प्रोजेक्ट में Aspose.Slides जोड़ने के लिए, आप Maven का उपयोग कर सकते हैं या मैन्युअल रूप से लाइब्रेरी डाउनलोड कर सकते हैं। दस्तावेज़ देखें [Aspose.Slides for Java API संदर्भ](https://reference.aspose.com/slides/java/) इसे अपने प्रोजेक्ट में शामिल करने के बारे में विस्तृत निर्देशों के लिए यहां क्लिक करें।

## चरण 2: एक प्रस्तुति बनाएं

आइए Aspose.Slides का उपयोग करके एक प्रस्तुति बनाना शुरू करें:

```java
String dataDir = "Your Document Directory";
String outPptxPath = dataDir + "presentation_external.pptx";
Presentation p = new Presentation();
```

सुनिश्चित करें कि आप प्रतिस्थापित करें `"Your Document Directory"` आपके प्रोजेक्ट निर्देशिका के वास्तविक पथ के साथ.

## चरण 3: SVG छवि लोड करना

हमें बाहरी संसाधन से SVG छवि लोड करने की आवश्यकता है। आप इसे इस प्रकार कर सकते हैं:

```java
String svgContent = new String(Files.readAllBytes(Paths.get(dataDir + "image1.svg")));
ISvgImage svgImage = new SvgImage(svgContent, new ExternalResourceResolver(), dataDir);
```

इस कोड में, हम "image1.svg" फ़ाइल से SVG सामग्री पढ़ते हैं और एक बनाते हैं `ISvgImage` वस्तु।

## चरण 4: स्लाइड में SVG छवि जोड़ना

अब, आइए SVG छवि को स्लाइड में जोड़ें:

```java
IPPImage ppImage = p.getImages().addImage(svgImage);
p.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, ppImage.getWidth(), ppImage.getHeight(), ppImage);
```

हम प्रस्तुति में पहली स्लाइड में SVG छवि को चित्र फ़्रेम के रूप में जोड़ते हैं।

## चरण 5: प्रस्तुति को सहेजना

अंत में, प्रस्तुति को सहेजें:

```java
p.save(outPptxPath, SaveFormat.Pptx);
```

यह कोड निर्दिष्ट निर्देशिका में प्रस्तुति को "presentation_external.pptx" के रूप में सहेजता है।

## जावा स्लाइड्स में बाहरी संसाधन से SVG ऑब्जेक्ट से छवि जोड़ने के लिए पूर्ण स्रोत कोड

```java
        // दस्तावेज़ निर्देशिका का पथ.
        String dataDir = "Your Document Directory";
        String outPptxPath = dataDir + "presentation_external.pptx";
        Presentation p = new Presentation();
        try
        {
            String svgContent = new String(Files.readAllBytes(Paths.get(dataDir + "image1.svg")));
            ISvgImage svgImage = new SvgImage(svgContent, new ExternalResourceResolver(), dataDir);
            IPPImage ppImage = p.getImages().addImage(svgImage);
            p.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, ppImage.getWidth(), ppImage.getHeight(), ppImage);
            p.save(outPptxPath, SaveFormat.Pptx);
        }
        finally
        {
            if (p != null) p.dispose();
        }
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि Aspose.Slides का उपयोग करके बाहरी संसाधन से SVG ऑब्जेक्ट से जावा स्लाइड में छवि कैसे जोड़ें। यह सुविधा आपको अपनी प्रस्तुतियों में उच्च-गुणवत्ता वाली वेक्टर-आधारित छवियों को शामिल करने की अनुमति देती है, जिससे उनकी दृश्य अपील बढ़ जाती है।

## अक्सर पूछे जाने वाले प्रश्न

### मैं स्लाइड पर जोड़ी गई SVG छवि की स्थिति को कैसे अनुकूलित कर सकता हूं?

आप निर्देशांक को संशोधित करके SVG छवि की स्थिति को समायोजित कर सकते हैं `addPictureFrame` विधि. पैरामीटर `(0, 0)` छवि फ़्रेम के ऊपरी-बाएँ कोने के X और Y निर्देशांक को दर्शाते हैं।

### क्या मैं एक ही स्लाइड में एकाधिक SVG छवियाँ जोड़ने के लिए इस दृष्टिकोण का उपयोग कर सकता हूँ?

हां, आप प्रत्येक छवि के लिए प्रक्रिया को दोहराकर और तदनुसार उनकी स्थिति को समायोजित करके एक ही स्लाइड में एकाधिक SVG छवियां जोड़ सकते हैं।

### बाह्य SVG संसाधनों के लिए कौन से प्रारूप समर्थित हैं?

Aspose.Slides for Java विभिन्न SVG प्रारूपों का समर्थन करता है, लेकिन सर्वोत्तम परिणाम प्राप्त करने के लिए यह सुनिश्चित करना अनुशंसित है कि आपकी SVG फ़ाइलें लाइब्रेरी के साथ संगत हों।

### क्या Aspose.Slides for Java नवीनतम Java संस्करणों के साथ संगत है?

हां, Aspose.Slides for Java नवीनतम Java संस्करणों के साथ संगत है। अपने Java परिवेश के लिए लाइब्रेरी के संगत संस्करण का उपयोग करना सुनिश्चित करें।

### क्या मैं स्लाइडों में जोड़े गए SVG चित्रों पर एनिमेशन लागू कर सकता हूँ?

हां, आप गतिशील प्रस्तुतियाँ बनाने के लिए Aspose.Slides का उपयोग करके अपनी स्लाइडों में SVG छवियों पर एनिमेशन लागू कर सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}