---
title: जावा पावरपॉइंट में टेक्स्ट फ़्रेम के लिए कस्टम रोटेशन कोण
linktitle: जावा पावरपॉइंट में टेक्स्ट फ़्रेम के लिए कस्टम रोटेशन कोण
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides का उपयोग करके Java PowerPoint में टेक्स्ट फ़्रेम के लिए रोटेशन कोण को कस्टमाइज़ करना सीखें। अपनी प्रस्तुतियों को गतिशील रूप से बेहतर बनाएँ।
weight: 14
url: /hi/java/java-powerpoint-text-box-manipulation/custom-rotation-angle-text-frame-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा पावरपॉइंट में टेक्स्ट फ़्रेम के लिए कस्टम रोटेशन कोण

## परिचय
इस ट्यूटोरियल में, हम Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में टेक्स्ट फ़्रेम रोटेशन कोणों में हेरफेर करने का तरीका जानेंगे। स्लाइड के भीतर टेक्स्ट की दृश्य अपील और स्पष्टता को बढ़ाने के लिए रोटेशन कोणों को अनुकूलित करना महत्वपूर्ण है। चाहे आप गतिशील चार्ट बना रहे हों या कस्टम शीर्षक जोड़ रहे हों, सटीक टेक्स्ट फ़्रेम रोटेशन प्रस्तुति सौंदर्यशास्त्र में काफी सुधार कर सकता है।
## आवश्यक शर्तें
इस ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान.
- आपकी मशीन पर JDK (जावा डेवलपमेंट किट) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
- IDE (एकीकृत विकास वातावरण) जैसे कि IntelliJ IDEA या Eclipse की स्थापना।
## पैकेज आयात करें
जावा में पावरपॉइंट प्रस्तुतियों के साथ काम करने के लिए आवश्यक Aspose.Slides क्लासेस को आयात करना सुनिश्चित करें:
```java
import com.aspose.slides.*;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
सबसे पहले, अपने IDE में एक नया Java प्रोजेक्ट बनाएं और अपने प्रोजेक्ट के बिल्ड पथ में Aspose.Slides for Java लाइब्रेरी जोड़ें।
## चरण 2: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
नए PowerPoint प्रस्तुति के साथ कार्य करने के लिए प्रस्तुति ऑब्जेक्ट को आरंभ करें:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## चरण 3: स्लाइड में चार्ट जोड़ें
पहली स्लाइड में एक क्लस्टर कॉलम चार्ट जोड़ें:
```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 300);
```
## चरण 4: चार्ट डेटा लेबल अनुकूलित करें
चार्ट श्रृंखला में डेटा लेबल के रोटेशन कोण को अनुकूलित करें:
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getTextBlockFormat().setRotationAngle(65);
```
## चरण 5: शीर्षक रोटेशन कोण सेट करें
चार्ट में कस्टम शीर्षक जोड़ें और उसका रोटेशन कोण समायोजित करें:
```java
chart.getChartTitle().addTextFrameForOverriding("Custom title").getTextFrameFormat().setRotationAngle(-30);
```
## चरण 6: प्रेजेंटेशन सहेजें
संशोधित प्रस्तुति को निर्दिष्ट निर्देशिका में सहेजें:
```java
presentation.save(dataDir + "textframe-rotation_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
Aspose.Slides का उपयोग करके Java PowerPoint प्रस्तुतियों में टेक्स्ट फ़्रेम के लिए रोटेशन कोण को अनुकूलित करने से डेवलपर्स को आसानी से आकर्षक और पेशेवर दिखने वाली स्लाइड बनाने में मदद मिलती है। इन चरणों का पालन करके, आप अपनी प्रस्तुतियों की पठनीयता और डिज़ाइन को गतिशील रूप से बढ़ा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### Java के लिए Aspose.Slides क्या है?
Aspose.Slides for Java एक मजबूत लाइब्रेरी है जो जावा डेवलपर्स को प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और परिवर्तित करने में सक्षम बनाती है।
### मैं Java के लिए Aspose.Slides का निःशुल्क परीक्षण संस्करण कैसे डाउनलोड कर सकता हूँ?
 आप Java के लिए Aspose.Slides का निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### मैं Aspose.Slides for Java के लिए दस्तावेज़ कहां पा सकता हूं?
 Aspose.Slides for Java के लिए विस्तृत दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/slides/java/).
### क्या Aspose.Slides एंटरप्राइज़ अनुप्रयोगों के लिए उपयुक्त है?
हां, Aspose.Slides को पावरपॉइंट प्रस्तुतियों को बनाने और प्रबंधित करने के लिए एंटरप्राइज़-स्तरीय आवश्यकताओं को संभालने के लिए डिज़ाइन किया गया है।
### मैं Java के लिए Aspose.Slides का समर्थन कैसे प्राप्त करूं?
 तकनीकी सहायता और सामुदायिक संपर्क के लिए, यहां जाएं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
