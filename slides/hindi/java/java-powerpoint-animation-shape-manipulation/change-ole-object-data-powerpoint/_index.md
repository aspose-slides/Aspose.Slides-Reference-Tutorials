---
"description": "Aspose.Slides for Java का उपयोग करके PowerPoint में OLE ऑब्जेक्ट डेटा को बदलने का तरीका जानें। कुशल और आसान अपडेट के लिए चरण-दर-चरण मार्गदर्शिका।"
"linktitle": "PowerPoint में OLE ऑब्जेक्ट डेटा बदलें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "PowerPoint में OLE ऑब्जेक्ट डेटा बदलें"
"url": "/hi/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint में OLE ऑब्जेक्ट डेटा बदलें

## परिचय
PowerPoint प्रस्तुतियों में OLE ऑब्जेक्ट डेटा को बदलना एक महत्वपूर्ण कार्य हो सकता है जब आपको प्रत्येक स्लाइड को मैन्युअल रूप से संपादित किए बिना एम्बेडेड सामग्री को अपडेट करने की आवश्यकता होती है। यह व्यापक गाइड आपको Aspose.Slides for Java का उपयोग करके प्रक्रिया के माध्यम से मार्गदर्शन करेगा, जो PowerPoint प्रस्तुतियों को संभालने के लिए डिज़ाइन की गई एक शक्तिशाली लाइब्रेरी है। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, आपको यह ट्यूटोरियल मददगार और अनुसरण करने में आसान लगेगा।
## आवश्यक शर्तें
इससे पहले कि हम कोड में उतरें, आइए सुनिश्चित करें कि आपके पास आरंभ करने के लिए आवश्यक सभी चीजें मौजूद हैं।
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं [ओरेकल की साइट](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java: से नवीनतम संस्करण डाउनलोड करें [Aspose.Slides डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (IDE): आप किसी भी जावा IDE जैसे कि IntelliJ IDEA, Eclipse, या NetBeans का उपयोग कर सकते हैं।
4. Aspose.Cells for Java: OLE ऑब्जेक्ट के भीतर एम्बेडेड डेटा को संशोधित करने के लिए यह आवश्यक है। इसे यहाँ से डाउनलोड करें [Aspose.Cells डाउनलोड पृष्ठ](https://releases.aspose.com/cells/java/).
5. प्रेजेंटेशन फ़ाइल: एम्बेडेड OLE ऑब्जेक्ट के साथ एक PowerPoint फ़ाइल तैयार रखें। इस ट्यूटोरियल के लिए, आइए इसका नाम रखें `ChangeOLEObjectData.pptx`.
## पैकेज आयात करें
सबसे पहले, आइए अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें।
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

अब, आइये इस प्रक्रिया को सरल एवं प्रबंधनीय चरणों में विभाजित करें।
## चरण 1: पावरपॉइंट प्रेजेंटेशन लोड करें
आरंभ करने के लिए, आपको OLE ऑब्जेक्ट युक्त पावरपॉइंट प्रेजेंटेशन लोड करना होगा।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## चरण 2: OLE ऑब्जेक्ट वाली स्लाइड तक पहुँचें
इसके बाद, वह स्लाइड प्राप्त करें जहां OLE ऑब्जेक्ट एम्बेडेड है।
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## चरण 3: स्लाइड में OLE ऑब्जेक्ट ढूंढें
OLE ऑब्जेक्ट का पता लगाने के लिए स्लाइड में आकृतियों के माध्यम से पुनरावृति करें।
```java
OleObjectFrame ole = null;
// ओले फ्रेम के लिए सभी आकृतियों को पार करना
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## चरण 4: OLE ऑब्जेक्ट से एम्बेडेड डेटा निकालें
यदि OLE ऑब्जेक्ट मिल जाए, तो उसका एम्बेडेड डेटा निकालें।
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## चरण 5: Aspose.Cells का उपयोग करके एम्बेडेड डेटा को संशोधित करें
अब, एम्बेडेड डेटा को पढ़ने और संशोधित करने के लिए Aspose.Cells का उपयोग करें, जो इस मामले में संभवतः एक एक्सेल वर्कबुक है।
```java
    Workbook wb = new Workbook(msln);
    // कार्यपुस्तिका डेटा संशोधित करें
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## चरण 6: संशोधित डेटा को OLE ऑब्जेक्ट में वापस सेव करें
आवश्यक परिवर्तन करने के बाद, संशोधित कार्यपुस्तिका को वापस OLE ऑब्जेक्ट में सहेजें।
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## चरण 7: अपडेट की गई प्रस्तुति को सहेजें
अंत में, अपडेट की गई पावरपॉइंट प्रस्तुति को सेव करें।
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## निष्कर्ष
Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में OLE ऑब्जेक्ट डेटा को अपडेट करना एक सीधी प्रक्रिया है, जब आप इसे सरल चरणों में विभाजित करते हैं। यह मार्गदर्शिका आपको प्रस्तुति लोड करने, एम्बेडेड OLE डेटा तक पहुँचने और उसे संशोधित करने, तथा अपडेट की गई प्रस्तुति को सहेजने के बारे में बताती है। इन चरणों के साथ, आप अपने PowerPoint स्लाइड में एम्बेडेड सामग्री को कुशलतापूर्वक प्रबंधित और अपडेट कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### पावरपॉइंट में OLE ऑब्जेक्ट क्या है?
OLE (ऑब्जेक्ट लिंकिंग और एम्बेडिंग) ऑब्जेक्ट अन्य अनुप्रयोगों, जैसे एक्सेल स्प्रेडशीट, से सामग्री को पावरपॉइंट स्लाइडों में एम्बेड करने की अनुमति देता है।
### क्या मैं Aspose.Slides को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?
हां, Aspose.Slides .NET, Python और C++ सहित कई भाषाओं का समर्थन करता है।
### क्या मुझे PowerPoint में OLE ऑब्जेक्ट्स को संशोधित करने के लिए Aspose.Cells की आवश्यकता है?
हां, यदि OLE ऑब्जेक्ट एक एक्सेल स्प्रेडशीट है, तो आपको इसे संशोधित करने के लिए Aspose.Cells की आवश्यकता होगी।
### क्या Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
हाँ, आप प्राप्त कर सकते हैं [मुफ्त परीक्षण](https://releases.aspose.com/) Aspose.Slides की सुविधाओं का परीक्षण करने के लिए.
### मैं Aspose.Slides के लिए दस्तावेज़ कहां पा सकता हूं?
आप विस्तृत दस्तावेज यहाँ पा सकते हैं [Aspose.Slides दस्तावेज़ीकरण पृष्ठ](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}