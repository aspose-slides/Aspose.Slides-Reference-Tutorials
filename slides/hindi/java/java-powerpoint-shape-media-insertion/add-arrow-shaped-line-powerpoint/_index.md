---
title: पावरपॉइंट में तीर के आकार की लाइन जोड़ें
linktitle: पावरपॉइंट में तीर के आकार की लाइन जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में तीर के आकार की रेखाएँ जोड़ना सीखें। दृश्य अपील को सहजता से बढ़ाएँ।
weight: 10
url: /hi/java/java-powerpoint-shape-media-insertion/add-arrow-shaped-line-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# पावरपॉइंट में तीर के आकार की लाइन जोड़ें

## परिचय
पावरपॉइंट प्रेजेंटेशन में तीर के आकार की रेखाएँ जोड़ने से दृश्य अपील बढ़ सकती है और जानकारी को प्रभावी ढंग से संप्रेषित करने में सहायता मिल सकती है। जावा के लिए Aspose.Slides जावा डेवलपर्स के लिए पावरपॉइंट प्रेजेंटेशन को प्रोग्रामेटिक रूप से हेरफेर करने के लिए एक व्यापक समाधान प्रदान करता है। इस ट्यूटोरियल में, हम आपको जावा के लिए Aspose.Slides का उपयोग करके अपने पावरपॉइंट स्लाइड में तीर के आकार की रेखाएँ जोड़ने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
2. Aspose.Slides for Java लाइब्रेरी डाउनलोड की गई और आपके प्रोजेक्ट के क्लासपाथ में जोड़ दी गई।
3. जावा प्रोग्रामिंग का बुनियादी ज्ञान.

## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा क्लास में आवश्यक पैकेज आयात करें:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// यदि निर्देशिका पहले से मौजूद नहीं है तो उसे बनाएं।
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
## चरण 2: प्रस्तुति को तत्कालित करें
```java
// PPTX फ़ाइल का प्रतिनिधित्व करने वाले PresentationEx वर्ग को तत्कालित करें
Presentation pres = new Presentation();
```
## चरण 3: तीर के आकार की रेखा जोड़ें
```java
// पहली स्लाइड प्राप्त करें
ISlide sld = pres.getSlides().get_Item(0);
// प्रकार लाइन का एक ऑटोशेप जोड़ें
IAutoShape shp = sld.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
// लाइन पर कुछ फ़ॉर्मेटिंग लागू करें
shp.getLineFormat().setStyle(LineStyle.ThickBetweenThin);
shp.getLineFormat().setWidth(10);
shp.getLineFormat().setDashStyle(LineDashStyle.DashDot);
shp.getLineFormat().setBeginArrowheadLength(LineArrowheadLength.Short);
shp.getLineFormat().setBeginArrowheadStyle(LineArrowheadStyle.Oval);
shp.getLineFormat().setEndArrowheadLength(LineArrowheadLength.Long);
shp.getLineFormat().setEndArrowheadStyle(LineArrowheadStyle.Triangle);
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Maroon));
```
## चरण 4: प्रस्तुति सहेजें
```java
// PPTX को डिस्क पर लिखें
pres.save(dataDir + "LineShape2_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष
बधाई हो! आपने Aspose.Slides for Java का उपयोग करके अपने PowerPoint प्रेजेंटेशन में सफलतापूर्वक एक तीर के आकार की रेखा जोड़ दी है। अपनी रेखाओं के स्वरूप को अनुकूलित करने और आकर्षक स्लाइड बनाने के लिए विभिन्न फ़ॉर्मेटिंग विकल्पों के साथ प्रयोग करें।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं एक ही स्लाइड में अनेक तीर आकार की रेखाएं जोड़ सकता हूं?
हां, आप प्रत्येक पंक्ति के लिए इस ट्यूटोरियल में बताई गई प्रक्रिया को दोहराकर एक स्लाइड में कई तीर के आकार की लाइनें जोड़ सकते हैं।
### क्या Aspose.Slides for Java PowerPoint के नवीनतम संस्करणों के साथ संगत है?
Aspose.Slides for Java, PowerPoint के विभिन्न संस्करणों के साथ संगतता का समर्थन करता है, जो आपकी प्रस्तुतियों के साथ सहज एकीकरण सुनिश्चित करता है।
### क्या मैं तीर के आकार की रेखा का रंग अनुकूलित कर सकता हूँ?
हां, आप तीर के आकार की रेखा के रंग को समायोजित करके अनुकूलित कर सकते हैं`SolidFillColor` कोड में संपत्ति.
### क्या Aspose.Slides for Java लाइनों के अलावा अन्य आकृतियों का समर्थन करता है?
हां, Java के लिए Aspose.Slides PowerPoint स्लाइडों में आयतों, वृत्तों और बहुभुजों सहित विभिन्न आकृतियों को जोड़ने के लिए व्यापक समर्थन प्रदान करता है।
### मैं Aspose.Slides for Java के लिए और अधिक संसाधन और समर्थन कहां पा सकता हूं?
आप निम्नलिखित लिंक के माध्यम से दस्तावेज़ देख सकते हैं, लाइब्रेरी डाउनलोड कर सकते हैं, और सहायता फ़ोरम तक पहुँच सकते हैं:
 दस्तावेज़ीकरण:[Aspose.Slides for Java दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/)
 डाउनलोड करना:[Aspose.Slides for Java डाउनलोड](https://releases.aspose.com/slides/java/)
 सहायता:[Aspose.Slides for Java समर्थन फ़ोरम](https://forum.aspose.com/c/slides/11)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
