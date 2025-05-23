---
"date": "2025-04-18"
"description": "Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में तालिका पहलू अनुपात को लॉक या अनलॉक करना सीखें। यह मार्गदर्शिका सेटअप, कोड कार्यान्वयन और व्यावहारिक अनुप्रयोगों को कवर करती है।"
"title": "जावा के लिए Aspose.Slides का उपयोग करके PowerPoint में टेबल आस्पेक्ट रेशियो को लॉक और अनलॉक कैसे करें"
"url": "/hi/java/tables/lock-unlock-table-aspect-ratio-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# जावा के लिए Aspose.Slides का उपयोग करके PowerPoint में टेबल आस्पेक्ट रेशियो को लॉक और अनलॉक कैसे करें

## परिचय

क्या आप अपने PowerPoint प्रस्तुतियों में सुसंगत तालिका लेआउट बनाए रखने में संघर्ष कर रहे हैं? पहलू अनुपातों को लॉक या अनलॉक करने की क्षमता के साथ, संपादन के दौरान तालिकाओं का आकार बदलने का प्रबंधन करना आसान हो जाता है। यह ट्यूटोरियल आपको टेबल आयामों को कुशलतापूर्वक नियंत्रित करने के लिए "Aspose.Slides for Java" का उपयोग करने के बारे में मार्गदर्शन करता है। आप न केवल पहलू अनुपातों में हेरफेर करना सीखेंगे बल्कि इस सुविधा को व्यापक प्रस्तुति वर्कफ़्लो में एकीकृत करना भी सीखेंगे।

**आप क्या सीखेंगे:**
- पावरपॉइंट प्रस्तुतियों में तालिकाओं के पहलू अनुपात को कैसे लॉक और अनलॉक करें।
- Maven, Gradle या प्रत्यक्ष डाउनलोड का उपयोग करके Java के लिए Aspose.Slides की सेटअप प्रक्रिया।
- स्पष्ट स्पष्टीकरण के साथ चरण-दर-चरण कोड कार्यान्वयन।
- बड़े स्लाइडशो के साथ काम करते समय व्यावहारिक अनुप्रयोग और प्रदर्शन संबंधी विचार।

आइये शुरू करने से पहले आवश्यक शर्तों पर गौर करें।

## आवश्यक शर्तें

इस ट्यूटोरियल का अनुसरण करने के लिए, सुनिश्चित करें कि आपके पास ये हैं:
- **जावा डेवलपमेंट किट (JDK):** आपकी मशीन पर संस्करण 16 या बाद का संस्करण स्थापित है।
- **आईडीई:** कोई भी जावा आईडीई जैसे इंटेलीज आईडिया या एक्लिप्स।
- **मावेन/ग्रैडल:** यदि आप निर्भरताओं के लिए पैकेज प्रबंधकों का उपयोग करना चुनते हैं।
- जावा प्रोग्रामिंग की बुनियादी समझ और पावरपॉइंट की तालिका कार्यक्षमताओं से परिचित होना।

## Java के लिए Aspose.Slides सेट अप करना

### मावेन सेटअप
Maven का उपयोग करके अपने प्रोजेक्ट में Aspose.Slides को शामिल करने के लिए, निम्नलिखित निर्भरता जोड़ें:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### ग्रेडेल सेटअप
Gradle का उपयोग करने वाले लोग इसे अपने में शामिल करें `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### प्रत्यक्षत: डाउनलोड
वैकल्पिक रूप से, नवीनतम संस्करण यहाँ से डाउनलोड करें [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).

#### लाइसेंस प्राप्ति चरण
- **मुफ्त परीक्षण:** बुनियादी कार्यक्षमताओं का पता लगाने के लिए निःशुल्क परीक्षण से शुरुआत करें।
- **अस्थायी लाइसेंस:** मूल्यांकन के दौरान पूर्ण सुविधा तक पहुंच के लिए अस्थायी लाइसेंस प्राप्त करें।
- **क्रय लाइसेंस:** दीर्घकालिक, निर्बाध उपयोग के लिए लाइसेंस खरीदने पर विचार करें।

अपना परिवेश सेट अप करने और आवश्यक लाइसेंस प्राप्त करने के बाद, अपने जावा अनुप्रयोग में Aspose.Slides को निम्न प्रकार से आरंभ करें:

```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        // आपका कोड यहाँ...
    }
}
```

## कार्यान्वयन मार्गदर्शिका

### लॉक/अनलॉक तालिका पहलू अनुपात

यह सुविधा आपको अपनी प्रस्तुतियों में तालिकाओं के पहलू अनुपात को बनाए रखने या समायोजित करने की अनुमति देती है, जिससे सुसंगत डिज़ाइन और पठनीयता सुनिश्चित होती है।

#### तालिका तक पहुँचना
अपनी प्रस्तुति लोड करके और इच्छित तालिका तक पहुँचकर आरंभ करें:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ITable;

// प्रस्तुति फ़ाइल लोड करें.
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/pres.pptx");
ITable table = (ITable) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

#### पहलू अनुपात की जाँच और संशोधन

जांचें कि क्या पहलू अनुपात लॉक है, फिर इसकी स्थिति टॉगल करें:

```java
// वर्तमान पहलू अनुपात लॉक स्थिति की जाँच करें.
boolean isLocked = table.getGraphicalObjectLock().getAspectRatioLocked();

// पहलू अनुपात लॉक स्थिति को उलटें.
table.getGraphicalObjectLock().setAspectRatioLocked(!isLocked);
```

यह टॉगलिंग सुविधा आपकी डिज़ाइन प्रक्रिया के दौरान लचीले समायोजन की अनुमति देती है।

#### परिवर्तन सहेजना
परिवर्तन करने के बाद, अद्यतन प्रस्तुति को सहेजें:

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/pres-out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}