---
title: जावा पावरपॉइंट में कस्टम प्रॉम्प्ट टेक्स्ट जोड़ें
linktitle: जावा पावरपॉइंट में कस्टम प्रॉम्प्ट टेक्स्ट जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java PowerPoint में कस्टम प्रॉम्प्ट टेक्स्ट जोड़ना सीखें। इस ट्यूटोरियल के साथ आसानी से उपयोगकर्ता इंटरैक्शन को बढ़ाएँ।
type: docs
weight: 12
url: /hi/java/java-powerpoint-text-box-manipulation/add-custom-prompt-text-java-powerpoint/
---
## परिचय
आज के डिजिटल युग में, प्रभावी संचार के लिए गतिशील और आकर्षक प्रस्तुतियाँ बनाना महत्वपूर्ण है। Aspose.Slides for Java डेवलपर्स को PowerPoint प्रस्तुतियों को प्रोग्रामेटिक रूप से हेरफेर करने की शक्ति देता है, स्लाइड, आकार, टेक्स्ट और बहुत कुछ को अनुकूलित करने के लिए व्यापक सुविधाएँ प्रदान करता है। यह ट्यूटोरियल आपको Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में प्लेसहोल्डर्स में कस्टम प्रॉम्प्ट टेक्स्ट जोड़ने की प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
इस ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपके सिस्टम पर JDK (जावा डेवलपमेंट किट) स्थापित है।
-  Aspose.Slides for Java इंस्टॉल किया गया है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- इंटेलीज आईडिया या एक्लिप्स जैसा एक एकीकृत विकास वातावरण (आईडीई) स्थापित करना।

## पैकेज आयात करें
आरंभ करने के लिए, अपनी जावा फ़ाइल में आवश्यक Aspose.Slides क्लासेस आयात करें:
```java
import com.aspose.slides.*;
```

## चरण 1: प्रस्तुति लोड करें
सबसे पहले, उस पावरपॉइंट प्रेजेंटेशन को लोड करें जहां आप प्लेसहोल्डर्स में कस्टम प्रॉम्प्ट टेक्स्ट जोड़ना चाहते हैं।
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Presentation2.pptx");
```
## चरण 2: स्लाइड आकृतियों के माध्यम से पुनरावृति करें
स्लाइड तक पहुंचें और प्लेसहोल्डर्स को खोजने के लिए इसके आकृतियों के माध्यम से पुनरावृत्ति करें।
```java
try {
    ISlide slide = pres.getSlides().get_Item(0);
    for (IShape shape : slide.getShapes()) {
        if (shape.getPlaceholder() != null && shape instanceof AutoShape) {
            // केवल ऑटोशेप प्लेसहोल्डर्स को संसाधित करें
            String text = "";
            if (shape.getPlaceholder().getType() == PlaceholderType.CenteredTitle) {
                text = "Click to add custom title";
            } else if (shape.getPlaceholder().getType() == PlaceholderType.Subtitle) {
                text = "Click to add custom subtitle";
            }
            
            // कस्टम प्रॉम्प्ट टेक्स्ट सेट करें
            ((IAutoShape) shape).getTextFrame().setText(text);
            
            // सत्यापन के लिए प्लेसहोल्डर टेक्स्ट प्रिंट करें
            System.out.println(String.format("Placeholder with text: %s", text));
        }
    }
    
    //संशोधित प्रस्तुति सहेजें
    pres.save(dataDir + "Placeholders_PromptText.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## निष्कर्ष
निष्कर्ष में, Aspose.Slides for Java प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को अनुकूलित करने के कार्य को सरल बनाता है। इस ट्यूटोरियल का अनुसरण करके, आप प्लेसहोल्डर्स में आसानी से सार्थक प्रॉम्प्ट टेक्स्ट जोड़कर उपयोगकर्ता इंटरैक्शन को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड में किसी भी प्लेसहोल्डर में प्रॉम्प्ट टेक्स्ट जोड़ सकता हूँ?
हां, आप प्रोग्रामेटिक रूप से विभिन्न प्रकार के प्लेसहोल्डर्स के लिए कस्टम प्रॉम्प्ट टेक्स्ट सेट कर सकते हैं।
### क्या Aspose.Slides for Java PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides PowerPoint संस्करणों की एक विस्तृत श्रृंखला का समर्थन करता है, जो संगतता और विश्वसनीयता सुनिश्चित करता है।
### मैं Aspose.Slides for Java के लिए और अधिक उदाहरण और दस्तावेज़ कहां पा सकता हूं?
 दौरा करना[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/) विस्तृत मार्गदर्शिका और उदाहरण के लिए.
### मैं Aspose.Slides for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आप प्राप्त कर सकते हैं[अस्थायी लाइसेंस](https://purchase.aspose.com/temporary-license/) Aspose.Slides की सम्पूर्ण विशेषताओं का मूल्यांकन करने के लिए.
### क्या Aspose.Slides for Java स्लाइडों में कस्टम एनिमेशन जोड़ने का समर्थन करता है?
हां, Aspose.Slides स्लाइड एनिमेशन को प्रोग्रामेटिक रूप से प्रबंधित करने के लिए API प्रदान करता है।