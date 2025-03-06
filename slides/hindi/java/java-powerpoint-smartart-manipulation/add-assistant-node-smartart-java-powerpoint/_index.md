---
title: जावा पावरपॉइंट में स्मार्टआर्ट में सहायक नोड जोड़ें
linktitle: जावा पावरपॉइंट में स्मार्टआर्ट में सहायक नोड जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में SmartArt में सहायक नोड जोड़ने का तरीका जानें। अपने PowerPoint संपादन कौशल को बढ़ाएँ।
weight: 17
url: /hi/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
इस ट्यूटोरियल में, हम आपको Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में SmartArt में सहायक नोड जोड़ने की प्रक्रिया के बारे में मार्गदर्शन करेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर जावा इंस्टॉल है। आप नवीनतम JDK को यहाँ से डाउनलोड और इंस्टॉल कर सकते हैं।[यहाँ](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java लाइब्रेरी को यहां से डाउनलोड और इंस्टॉल करें[इस लिंक](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा कोड में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
```
## चरण 1: प्रस्तुति सेट करें
अपनी PowerPoint फ़ाइल के पथ का उपयोग करके एक प्रेजेंटेशन इंस्टैंस बनाना शुरू करें:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## चरण 2: आकृतियों के माध्यम से आगे बढ़ें
प्रस्तुति की पहली स्लाइड के अंदर प्रत्येक आकृति को देखें:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## चरण 3: स्मार्टआर्ट आकृतियों की जाँच करें
जाँचें कि क्या आकृति स्मार्टआर्ट प्रकार की है:
```java
if (shape instanceof ISmartArt)
```
## चरण 4: स्मार्टआर्ट नोड्स से गुज़रें
स्मार्टआर्ट आकृति के सभी नोड्स से होकर गुजरें:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## चरण 5: सहायक नोड की जाँच करें
जाँचें कि नोड सहायक नोड है या नहीं:
```java
if (node.isAssistant())
```
## चरण 6: सहायक नोड को सामान्य पर सेट करें
यदि नोड सहायक नोड है, तो उसे सामान्य नोड पर सेट करें:
```java
node.setAssistant(false);
```
## चरण 7: प्रस्तुति सहेजें
संशोधित प्रस्तुति सहेजें:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
बधाई हो! आपने Aspose.Slides का उपयोग करके अपने Java PowerPoint प्रेजेंटेशन में SmartArt में एक सहायक नोड सफलतापूर्वक जोड़ लिया है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं प्रस्तुति में स्मार्टआर्ट में एकाधिक सहायक नोड्स जोड़ सकता हूँ?
हां, आप प्रत्येक नोड के लिए प्रक्रिया को दोहराकर अनेक सहायक नोड जोड़ सकते हैं।
### क्या यह ट्यूटोरियल पावरपॉइंट और पावरपॉइंट टेम्पलेट्स दोनों के लिए काम करता है?
हां, आप इस ट्यूटोरियल को पावरपॉइंट प्रस्तुतियों और टेम्पलेट्स दोनों पर लागू कर सकते हैं।
### क्या Aspose.Slides PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides PowerPoint संस्करण 97-2003 से नवीनतम संस्करण तक का समर्थन करता है।
### क्या मैं सहायक नोड के स्वरूप को अनुकूलित कर सकता हूँ?
हां, आप Aspose.Slides द्वारा प्रदान किए गए विभिन्न गुणों और विधियों का उपयोग करके उपस्थिति को अनुकूलित कर सकते हैं।
### क्या स्मार्टआर्ट में नोड्स की संख्या की कोई सीमा होती है?
पावरपॉइंट में स्मार्टआर्ट बड़ी संख्या में नोड्स का समर्थन करता है, लेकिन बेहतर पठनीयता के लिए इसे उचित रखने की अनुशंसा की जाती है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
