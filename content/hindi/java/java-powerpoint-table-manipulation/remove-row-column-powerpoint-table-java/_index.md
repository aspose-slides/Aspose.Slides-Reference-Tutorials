---
title: जावा का उपयोग करके पावरपॉइंट टेबल में पंक्ति या कॉलम हटाएं
linktitle: जावा का उपयोग करके पावरपॉइंट टेबल में पंक्ति या कॉलम हटाएं
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java के साथ Java का उपयोग करके PowerPoint टेबल से पंक्तियों या स्तंभों को हटाने का तरीका जानें। डेवलपर्स के लिए आसान चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 18
url: /hi/java/java-powerpoint-table-manipulation/remove-row-column-powerpoint-table-java/
---
## परिचय
इस ट्यूटोरियल में, हम जावा का उपयोग करके Aspose.Slides की सहायता से PowerPoint टेबल से पंक्ति या कॉलम को हटाने का तरीका जानेंगे। जावा के लिए Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों को बनाने, हेरफेर करने और परिवर्तित करने की अनुमति देती है। यह ट्यूटोरियल विशेष रूप से PowerPoint स्लाइड्स के भीतर तालिकाओं को संशोधित करने की प्रक्रिया पर ध्यान केंद्रित करता है, जो चरण-दर-चरण प्रदर्शित करता है कि किसी तालिका से विशिष्ट पंक्तियों या स्तंभों को कैसे हटाया जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ निर्धारित हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है
- एकीकृत विकास वातावरण (IDE) जैसे कि IntelliJ IDEA या Eclipse
-  Aspose.Slides for Java लाइब्रेरी। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/)
- जावा प्रोग्रामिंग भाषा और ऑब्जेक्ट-ओरिएंटेड अवधारणाओं की बुनियादी समझ

## पैकेज आयात करें
आरंभ करने के लिए, सुनिश्चित करें कि आपने अपनी जावा फ़ाइल की शुरुआत में Aspose.Slides से आवश्यक पैकेज आयात किए हैं:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ITable;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```
## चरण 1: प्रेजेंटेशन ऑब्जेक्ट को आरंभ करें
सबसे पहले, Aspose.Slides का उपयोग करके एक नया PowerPoint प्रेजेंटेशन ऑब्जेक्ट बनाएं:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
 प्रतिस्थापित करें`"Your Document Directory"` उस पथ के साथ जहाँ आप अपनी पावरपॉइंट फ़ाइल को सहेजना चाहते हैं।
## चरण 2: स्लाइड तक पहुंचें और तालिका जोड़ें
इसके बाद, उस स्लाइड पर पहुँचें जहाँ आप तालिका जोड़ना चाहते हैं और निर्दिष्ट स्तंभ चौड़ाई और पंक्ति ऊँचाई के साथ एक तालिका बनाएँ:
```java
ISlide slide = pres.getSlides().get_Item(0);
double[] colWidth = new double[]{100, 50, 30};
double[] rowHeight = new double[]{30, 50, 30};
ITable table = slide.getShapes().addTable(100, 100, colWidth, rowHeight);
```
पैरामीटर समायोजित करें (`100, 100` (इस मामले में) स्लाइड पर आवश्यकतानुसार तालिका को स्थान देने के लिए।
## चरण 3: तालिका से एक पंक्ति हटाएँ
 तालिका से किसी विशिष्ट पंक्ति को हटाने के लिए, का उपयोग करें`removeAt` विधि पर`Rows` तालिका का संग्रह:
```java
table.getRows().removeAt(1, false);
```
 प्रतिस्थापित करें`1` उस पंक्ति के इंडेक्स के साथ जिसे आप हटाना चाहते हैं। दूसरा पैरामीटर (`false`) निर्दिष्ट करता है कि स्लाइड पर संबंधित सामग्री को हटाया जाए या नहीं।
## चरण 4: तालिका से एक कॉलम हटाएँ
 इसी तरह, तालिका से किसी विशिष्ट कॉलम को हटाने के लिए, का उपयोग करें`removeAt` विधि पर`Columns` तालिका का संग्रह:
```java
table.getColumns().removeAt(1, false);
```
 प्रतिस्थापित करें`1` उस कॉलम की अनुक्रमणिका के साथ जिसे आप हटाना चाहते हैं.
## चरण 5: प्रस्तुति सहेजें
अंत में, संशोधित प्रस्तुति को अपनी डिस्क पर निर्दिष्ट स्थान पर सहेजें:
```java
pres.save(dataDir + "ModifiedTablePresentation.pptx", SaveFormat.Pptx);
```
 प्रतिस्थापित करना सुनिश्चित करें`"ModifiedTablePresentation.pptx"` इच्छित फ़ाइल नाम के साथ.

## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा और Aspose.Slides का उपयोग करके पंक्तियों और स्तंभों को हटाकर PowerPoint तालिकाओं में हेरफेर करने का तरीका खोजा है। इन चरणों का पालन करके, आप अपनी आवश्यकताओं के अनुरूप अपनी प्रस्तुतियों में तालिकाओं को प्रोग्रामेटिक रूप से अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Java के लिए Aspose.Slides का उपयोग करके किसी तालिका में पंक्तियाँ या कॉलम जोड़ सकता हूँ?
हां, आप Aspose.Slides API द्वारा प्रदान की गई विधियों का उपयोग करके पंक्तियों और स्तंभों को गतिशील रूप से जोड़ सकते हैं।
### क्या Aspose.Slides अन्य PowerPoint हेरफेर कार्यों का समर्थन करता है?
Aspose.Slides पावरपॉइंट प्रस्तुतियों को बनाने, संशोधित करने और परिवर्तित करने के लिए व्यापक समर्थन प्रदान करता है, जिसमें स्लाइड निर्माण, पाठ स्वरूपण और बहुत कुछ शामिल है।
### मैं Aspose.Slides के लिए और अधिक उदाहरण और दस्तावेज़ कहां पा सकता हूं?
 विस्तृत दस्तावेज और उदाहरण यहां देखे जा सकते हैं[Aspose.Slides for Java दस्तावेज़](https://reference.aspose.com/slides/java/) पृष्ठ।
### क्या Aspose.Slides एंटरप्राइज़-स्तरीय पावरपॉइंट स्वचालन के लिए उपयुक्त है?
हां, Aspose.Slides को इसकी मजबूत सुविधाओं और प्रदर्शन के कारण PowerPoint कार्यों को स्वचालित करने के लिए एंटरप्राइज़ वातावरण में व्यापक रूप से उपयोग किया जाता है।
### क्या मैं खरीदने से पहले Aspose.Slides आज़मा सकता हूँ?
 हां, आप Aspose.Slides का निःशुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).