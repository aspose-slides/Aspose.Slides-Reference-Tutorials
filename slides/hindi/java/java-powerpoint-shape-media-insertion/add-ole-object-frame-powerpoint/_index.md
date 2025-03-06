---
title: PowerPoint में OLE ऑब्जेक्ट फ़्रेम जोड़ें
linktitle: PowerPoint में OLE ऑब्जेक्ट फ़्रेम जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Aspose.Slides for Java का उपयोग करके OLE ऑब्जेक्ट फ़्रेम को PowerPoint प्रस्तुतियों में सहजता से कैसे एकीकृत किया जाए।
weight: 13
url: /hi/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## परिचय
PowerPoint प्रस्तुतियों में OLE (ऑब्जेक्ट लिंकिंग और एम्बेडिंग) ऑब्जेक्ट फ़्रेम जोड़ने से आपकी स्लाइड्स की दृश्य अपील और कार्यक्षमता में उल्लेखनीय वृद्धि हो सकती है। Aspose.Slides for Java के साथ, यह प्रक्रिया सुव्यवस्थित और कुशल हो जाती है। इस ट्यूटोरियल में, हम आपको अपने PowerPoint प्रस्तुतियों में OLE ऑब्जेक्ट फ़्रेम को सहजता से एकीकृत करने के लिए आवश्यक चरणों के माध्यम से मार्गदर्शन करेंगे।
### आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. जावा डेवलपमेंट एनवायरनमेंट: सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2.  Aspose.Slides for Java: वेबसाइट से Aspose.Slides for Java डाउनलोड करें और इंस्टॉल करें[यहाँ](https://releases.aspose.com/slides/java/).
3. जावा प्रोग्रामिंग की बुनियादी समझ: जावा प्रोग्रामिंग अवधारणाओं और वाक्यविन्यास से स्वयं को परिचित कराएं।
## पैकेज आयात करें
सबसे पहले, आपको Aspose.Slides for Java की कार्यक्षमताओं का लाभ उठाने के लिए आवश्यक पैकेज आयात करने की आवश्यकता है। यहाँ बताया गया है कि आप यह कैसे कर सकते हैं:
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## चरण 1: अपना वातावरण सेट करें
सुनिश्चित करें कि आपका प्रोजेक्ट ठीक से कॉन्फ़िगर किया गया है और Aspose.Slides लाइब्रेरी आपके क्लासपाथ में शामिल है।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
जिस PowerPoint फ़ाइल पर आप काम कर रहे हैं, उसका प्रतिनिधित्व करने के लिए एक प्रेजेंटेशन ऑब्जेक्ट बनाएँ:
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// PPTX का प्रतिनिधित्व करने वाले प्रेजेंटेशन क्लास को इंस्टेंटिएट करें
Presentation pres = new Presentation();
```
## चरण 3: स्लाइड तक पहुंचें और ऑब्जेक्ट लोड करें
उस स्लाइड तक पहुंचें जहां आप OLE ऑब्जेक्ट फ़्रेम जोड़ना चाहते हैं और ऑब्जेक्ट फ़ाइल लोड करें:
```java
ISlide sld = pres.getSlides().get_Item(0);
// स्ट्रीम करने के लिए फ़ाइल लोड करें
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## चरण 4: एम्बेडेड डेटा ऑब्जेक्ट बनाएँ
फ़ाइल एम्बेड करने के लिए डेटा ऑब्जेक्ट बनाएँ:
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## चरण 5: OLE ऑब्जेक्ट फ़्रेम जोड़ें
स्लाइड में OLE ऑब्जेक्ट फ़्रेम आकार जोड़ें:
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## चरण 6: प्रस्तुति सहेजें
संशोधित प्रस्तुति को डिस्क पर सहेजें:
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में OLE ऑब्जेक्ट फ़्रेम जोड़ना सफलतापूर्वक सीख लिया है। यह शक्तिशाली सुविधा आपको विभिन्न प्रकार की ऑब्जेक्ट एम्बेड करने की अनुमति देती है, जिससे आपकी स्लाइड्स की अन्तरक्रियाशीलता और दृश्य अपील बढ़ जाती है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Java के लिए Aspose.Slides का उपयोग करके Excel फ़ाइलों के अलावा अन्य ऑब्जेक्ट्स एम्बेड कर सकता हूँ?
हां, आप वर्ड दस्तावेज़, पीडीएफ फाइलें आदि सहित विभिन्न प्रकार की वस्तुओं को एम्बेड कर सकते हैं।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
Aspose.Slides PowerPoint संस्करणों की एक विस्तृत श्रृंखला के साथ संगतता प्रदान करता है, जिससे निर्बाध एकीकरण सुनिश्चित होता है।
### क्या मैं OLE ऑब्जेक्ट फ़्रेम के स्वरूप को अनुकूलित कर सकता हूँ?
बिल्कुल! Aspose.Slides OLE ऑब्जेक्ट फ़्रेम की उपस्थिति और व्यवहार को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए समर्थन कहां पा सकता हूं?
 आप Aspose.Slides फोरम से समर्थन और सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
