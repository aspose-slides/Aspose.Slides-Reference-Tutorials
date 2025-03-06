---
title: पावरपॉइंट में शेप बेवल प्रभावी डेटा प्राप्त करें
linktitle: पावरपॉइंट में शेप बेवल प्रभावी डेटा प्राप्त करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके PowerPoint में शेप बेवल प्रभावी डेटा प्राप्त करना सीखें। शानदार विज़ुअल इफ़ेक्ट के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।
weight: 26
url: /hi/java/java-powerpoint-shape-formatting-geometry/get-shape-bevel-effective-data-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
आधुनिक व्यावसायिक प्रस्तुतियों में, दृश्य अपील जानकारी को प्रभावी ढंग से व्यक्त करने में महत्वपूर्ण भूमिका निभाती है। PowerPoint प्रस्तुतियों में आकृतियों के दृश्य प्रभाव को बढ़ाने वाले तत्वों में से एक बेवल प्रभाव है। Aspose.Slides for Java आकृतियों के विभिन्न गुणों तक पहुँचने और उनमें हेरफेर करने के लिए शक्तिशाली उपकरण प्रदान करता है, जिसमें उनके बेवल प्रभाव भी शामिल हैं। इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके आकृति बेवल प्रभावी डेटा प्राप्त करने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. जावा प्रोग्रामिंग भाषा की बुनियादी समझ।
2. आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
3.  Aspose.Slides for Java डाउनलोड और इंस्टॉल किया गया। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके प्रारंभ करें:
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;

```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
अपनी दस्तावेज़ निर्देशिका का पथ निर्धारित करें जहाँ PowerPoint प्रस्तुति स्थित है:
```java
String dataDir = "Your Document Directory";
```
## चरण 2: प्रस्तुति लोड करें
Aspose.Slides लाइब्रेरी का उपयोग करके PowerPoint प्रस्तुति लोड करें:
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## चरण 3: बेवल प्रभावी डेटा पुनर्प्राप्त करें
आकृति के प्रभावी बेवल डेटा तक पहुँचें:
```java
IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
```
## चरण 4: बेवल गुण प्रिंट करें
प्रभावी आकार के शीर्ष चेहरे राहत गुणों को प्रिंट करें:
```java
System.out.println("= Effective shape's top face relief properties =");
System.out.println("Type: " + threeDEffectiveData.getBevelTop().getBevelType());
System.out.println("Width: " + threeDEffectiveData.getBevelTop().getWidth());
System.out.println("Height: " + threeDEffectiveData.getBevelTop().getHeight());
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने प्रदर्शित किया है कि Aspose.Slides for Java का उपयोग करके PowerPoint में शेप बेवल प्रभावी डेटा कैसे प्राप्त करें। इन चरणों का पालन करके, आप अपनी प्रस्तुतियों की दृश्य अपील को बढ़ाने के लिए आकृतियों के विभिन्न गुणों तक आसानी से पहुँच सकते हैं और उनमें हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं एक साथ कई आकृतियों पर बेवल प्रभाव लागू कर सकता हूँ?
हां, आप स्लाइड में आकृतियों के माध्यम से पुनरावृत्ति कर सकते हैं और आवश्यकतानुसार बेवल प्रभाव लागू कर सकते हैं।
### क्या Aspose.Slides बेवेल के अलावा अन्य 3D प्रभावों का समर्थन करता है?
हां, Aspose.Slides 3D प्रभावों की एक विस्तृत श्रृंखला प्रदान करता है जिसे आप PowerPoint प्रस्तुतियों में आकृतियों पर लागू कर सकते हैं।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगतता सुनिश्चित करता है, जिससे आप विभिन्न वातावरणों में सहजता से काम कर सकते हैं।
### क्या मैं बेवल प्रभाव गुणों को और अधिक अनुकूलित कर सकता हूँ?
बिल्कुल, आपके पास बेवल प्रभाव गुणों पर पूर्ण नियंत्रण है और आप उन्हें अपनी आवश्यकताओं के अनुसार अनुकूलित कर सकते हैं।
### मैं Aspose.Slides के लिए अधिक संसाधन और समर्थन कहां पा सकता हूं?
 आप यहां जा सकते हैं[Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides/11) किसी भी प्रश्न, सहायता या अतिरिक्त संसाधनों के लिए.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
