---
title: Java के लिए Aspose.Slides का उपयोग करके टेक्स्ट फ़्रेम में कॉलम जोड़ें
linktitle: Java के लिए Aspose.Slides का उपयोग करके टेक्स्ट फ़्रेम में कॉलम जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: अपने पावरपॉइंट प्रेजेंटेशन को बेहतर बनाने के लिए Aspose.Slides for Java का उपयोग करके टेक्स्ट फ़्रेम में कॉलम जोड़ना सीखें। हमारी चरण-दर-चरण मार्गदर्शिका प्रक्रिया को सरल बनाती है।
weight: 11
url: /hi/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके कॉलम जोड़ने के लिए टेक्स्ट फ़्रेम में हेरफेर करने का तरीका जानेंगे। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो जावा डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने में सक्षम बनाती है। टेक्स्ट फ़्रेम में कॉलम जोड़ने से स्लाइड के भीतर टेक्स्ट की दृश्य अपील और संगठन में वृद्धि होती है, जिससे प्रस्तुतियाँ अधिक आकर्षक और पढ़ने में आसान हो जाती हैं।
## आवश्यक शर्तें
इस ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- आपकी मशीन पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- जावा प्रोग्रामिंग की बुनियादी समझ.
- एकीकृत विकास वातावरण (आईडीई) जैसे कि एक्लिप्स या इंटेलीज आईडिया।
- मावेन या ग्रेडल जैसे उपकरणों का उपयोग करके परियोजना निर्भरताओं को प्रबंधित करने की जानकारी।

## पैकेज आयात करें
सबसे पहले, प्रस्तुतियों और पाठ फ़्रेमों के साथ काम करने के लिए Aspose.Slides से आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;
```
## चरण 1: प्रस्तुति आरंभ करें
एक नया पावरपॉइंट प्रेजेंटेशन ऑब्जेक्ट बनाकर शुरू करें:
```java
String dataDir = "Your Document Directory";
String outPptxFileName = dataDir + "ColumnsTest.pptx";
// एक नया प्रस्तुतिकरण ऑब्जेक्ट बनाएँ
Presentation pres = new Presentation();
```
## चरण 2: टेक्स्ट फ़्रेम के साथ ऑटोशेप जोड़ें
पहली स्लाइड में एक ऑटोशेप (जैसे, आयत) जोड़ें और उसके टेक्स्ट फ़्रेम तक पहुँचें:
```java
// पहली स्लाइड में ऑटोशेप जोड़ें
IAutoShape shape1 = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
// ऑटोशेप के टेक्स्ट फ़्रेम तक पहुँचें
TextFrameFormat format = (TextFrameFormat) shape1.getTextFrame().getTextFrameFormat();
```
## चरण 3: कॉलम संख्या और टेक्स्ट सेट करें
पाठ फ़्रेम के भीतर स्तंभों की संख्या और पाठ सामग्री सेट करें:
```java
// स्तंभों की संख्या निर्धारित करें
format.setColumnCount(2);
// पाठ सामग्री सेट करें
shape1.getTextFrame().setText("All these columns are limited to be within a single text container -- " +
    "you can add or delete text and the new or remaining text automatically adjusts " +
    "itself to flow within the container. You cannot have text flow from one container " +
    "to other though -- we told you PowerPoint's column options for text are limited!");
```
## चरण 4: प्रस्तुति सहेजें
परिवर्तन करने के बाद प्रस्तुति सहेजें:
```java
// प्रस्तुति सहेजें
pres.save(outPptxFileName, SaveFormat.Pptx);
```
## चरण 5: कॉलम स्पेसिंग समायोजित करें (वैकल्पिक)
यदि आवश्यक हो, तो स्तंभों के बीच रिक्ति समायोजित करें:
```java
// स्तंभ रिक्ति सेट करें
format.setColumnSpacing(20);
// अद्यतन कॉलम स्पेसिंग के साथ प्रस्तुति को सहेजें
pres.save(outPptxFileName, SaveFormat.Pptx);
// यदि आवश्यक हो तो आप कॉलम की संख्या और रिक्ति को पुनः बदल सकते हैं
format.setColumnCount(3);
format.setColumnSpacing(15);
pres.save(outPptxFileName, SaveFormat.Pptx);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने दिखाया है कि PowerPoint प्रस्तुतियों में टेक्स्ट फ़्रेम के भीतर कॉलम जोड़ने के लिए Aspose.Slides for Java का उपयोग कैसे करें। यह क्षमता टेक्स्ट सामग्री की दृश्य प्रस्तुति को बढ़ाती है, स्लाइड में पठनीयता और संरचना में सुधार करती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं किसी टेक्स्ट फ़्रेम में तीन से अधिक कॉलम जोड़ सकता हूँ?
 हां, आप इसे समायोजित कर सकते हैं`setColumnCount` आवश्यकतानुसार अधिक कॉलम जोड़ने की विधि।
### क्या Aspose.Slides व्यक्तिगत रूप से कॉलम की चौड़ाई समायोजित करने का समर्थन करता है?
नहीं, Aspose.Slides स्वचालित रूप से टेक्स्ट फ्रेम के भीतर कॉलम के लिए समान चौड़ाई निर्धारित करता है।
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप एक निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के बारे में अधिक दस्तावेज़ कहां पा सकता हूं?
 विस्तृत दस्तावेज उपलब्ध है[यहाँ](https://reference.aspose.com/slides/java/).
### मैं Aspose.Slides for Java के लिए तकनीकी सहायता कैसे प्राप्त कर सकता हूं?
 आप समुदाय से सहायता ले सकते हैं[यहाँ](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
