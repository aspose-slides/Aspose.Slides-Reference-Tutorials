---
"description": "हमारे विस्तृत चरण-दर-चरण ट्यूटोरियल के साथ Java के लिए Aspose.Slides का उपयोग करके PowerPoint में डायनामिक टेबल बनाना सीखें।"
"linktitle": "जावा के साथ PowerPoint में स्क्रैच से टेबल बनाएं"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा के साथ PowerPoint में स्क्रैच से टेबल बनाएं"
"url": "/hi/java/java-powerpoint-table-manipulation/create-table-from-scratch-powerpoint-java/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा के साथ PowerPoint में स्क्रैच से टेबल बनाएं

## परिचय
क्या आपको कभी जावा का उपयोग करके पावरपॉइंट प्रेजेंटेशन में डायनेमिक टेबल बनाने की ज़रूरत पड़ी है? खैर, आप सही जगह पर हैं! इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके स्क्रैच से टेबल बनाने की प्रक्रिया से अवगत कराएँगे। चाहे आप एक अनुभवी जावा डेवलपर हों या अभी शुरुआत कर रहे हों, आपको यह गाइड अनुसरण करने में आसान और अविश्वसनीय रूप से उपयोगी लगेगी। आइए इसमें गोता लगाएँ और अपनी पावरपॉइंट स्लाइड्स को कुछ असाधारण में बदलें!
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपकी मशीन पर JDK स्थापित है।
2. Aspose.Slides for Java: से नवीनतम संस्करण डाउनलोड करें [साइट](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): IntelliJ IDEA, Eclipse, या NetBeans जैसे IDE का उपयोग करें।
4. प्रस्तुति टेम्पलेट: कार्य करने के लिए एक पावरपॉइंट फ़ाइल, या आप एक नई फ़ाइल बना सकते हैं।
## पैकेज आयात करें
सबसे पहले, आइए आवश्यक पैकेज आयात करें। ये आयात हमें अपने प्रोजेक्ट में Aspose.Slides कार्यक्षमताओं का उपयोग करने की अनुमति देंगे।
```java
import com.aspose.slides.*;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
### प्रोजेक्ट निर्देशिका बनाना
अपनी प्रोजेक्ट डायरेक्टरी सेट अप करके शुरू करें। एक फ़ोल्डर बनाएँ जहाँ आपका जावा प्रोजेक्ट रहेगा। इस फ़ोल्डर के अंदर, स्रोत फ़ाइलों और संसाधनों के लिए उपनिर्देशिकाएँ बनाएँ।
### Aspose.Slides लाइब्रेरी जोड़ना
Aspose.Slides for Java लाइब्रेरी को यहाँ से डाउनलोड करें [डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/)डाउनलोड हो जाने के बाद, लाइब्रेरी को अपने प्रोजेक्ट के बिल्ड पथ में जोड़ें।
## चरण 2: प्रस्तुति आरंभ करें
आइए पहले एक मौजूदा पावरपॉइंट प्रेजेंटेशन लोड करके शुरू करें। अगर आपके पास कोई नहीं है, तो एक नई पावरपॉइंट फ़ाइल बनाएँ।
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "UpdateExistingTable.pptx");
```
## चरण 3: स्लाइड और आकृतियों तक पहुँचें
### पहली स्लाइड तक पहुंचें
हमें उस स्लाइड तक पहुंचने की आवश्यकता है जहां तालिका बनाई जाएगी। इस उदाहरण में, हम पहली स्लाइड का उपयोग करेंगे।
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
### आकृतियों के माध्यम से पुनरावृति करें
इसके बाद, हम स्लाइड पर आकृतियों के माध्यम से किसी भी मौजूदा तालिका को खोजने के लिए पुनरावृति करते हैं। यदि कोई तालिका है, तो हम उसे संशोधित करेंगे; अन्यथा, हम एक नई तालिका बनाएंगे।
```java
ITable table = null;
for (IShape shape : slide.getShapes()) {
    if (shape instanceof ITable) {
        table = (ITable) shape;
    }
}
```
## चरण 4: एक नई तालिका बनाएँ
यदि कोई तालिका मौजूद नहीं है, तो हम एक नई तालिका बनाएंगे। तालिका के लिए आयाम और स्थिति निर्धारित करें।
```java
double[] columns = { 50, 100, 100, 100 };
double[] rows = { 50, 50, 50, 50 };
table = slide.getShapes().addTable(100, 50, columns, rows);
```
## चरण 5: तालिका भरें
अब, आइए टेबल में कुछ डेटा भरें। हम टेबल के सेल में टेक्स्ट जोड़ेंगे।
```java
table.getRows().get_Item(0).get_Item(0).getTextFrame().setText("Column 1");
table.getRows().get_Item(0).get_Item(1).getTextFrame().setText("Column 2");
table.getRows().get_Item(1).get_Item(0).getTextFrame().setText("Row 1");
table.getRows().get_Item(1).get_Item(1).getTextFrame().setText("Data");
```
## चरण 6: प्रस्तुति सहेजें
अंत में, प्रस्तुति को निर्दिष्ट निर्देशिका में सहेजें।
```java
presentation.save(dataDir + "UpdateTable_out.pptx", SaveFormat.Pptx);
```
## चरण 7: सफ़ाई करें
संसाधनों को मुक्त करने के लिए प्रस्तुति ऑब्जेक्ट को हटाना सुनिश्चित करें।
```java
if (presentation != null) presentation.dispose();
```

## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में स्क्रैच से टेबल बनाना सरल और कुशल है। इन चरणों का पालन करके, आप अपनी प्रेजेंटेशन में टेबल को गतिशील रूप से जेनरेट और मैनिपुलेट कर सकते हैं, जिससे आपकी स्लाइड्स अधिक इंटरैक्टिव और डेटा-समृद्ध बन सकती हैं। हैप्पी कोडिंग!
### अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java, Java अनुप्रयोगों में PowerPoint फ़ाइलों के साथ काम करने के लिए एक शक्तिशाली लाइब्रेरी है। यह आपको प्रोग्रामेटिक रूप से प्रस्तुतियाँ बनाने, संशोधित करने और प्रबंधित करने की अनुमति देता है।
### क्या मैं Aspose.Slides का निःशुल्क उपयोग कर सकता हूँ?
Aspose एक प्रदान करता है [मुफ्त परीक्षण](https://releases.aspose.com/) जिसका उपयोग आप लाइसेंस खरीदने से पहले लाइब्रेरी की क्षमताओं का परीक्षण करने के लिए कर सकते हैं।
### मैं Aspose.Slides के लिए अस्थायी लाइसेंस कैसे प्राप्त करूं?
आप अस्थायी लाइसेंस का अनुरोध कर सकते हैं [साइट](https://purchase.aspose.com/temporary-license/).
### क्या Aspose.Slides सभी जावा संस्करणों के साथ संगत है?
Aspose.Slides Java SE 6 और इसके बाद के संस्करण के साथ संगत है।
### मैं Aspose.Slides दस्तावेज़ कहां पा सकता हूं?
दस्तावेज़ उपलब्ध है [यहाँ](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}