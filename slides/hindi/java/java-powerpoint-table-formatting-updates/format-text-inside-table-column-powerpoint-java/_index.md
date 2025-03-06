---
title: जावा का उपयोग करके पावरपॉइंट में टेबल कॉलम के अंदर टेक्स्ट को फॉर्मेट करें
linktitle: जावा का उपयोग करके पावरपॉइंट में टेबल कॉलम के अंदर टेक्स्ट को फॉर्मेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: इस ट्यूटोरियल के साथ Aspose.Slides for Java का उपयोग करके PowerPoint में टेबल कॉलम के अंदर टेक्स्ट को फ़ॉर्मेट करना सीखें। अपने प्रेजेंटेशन को प्रोग्रामेटिक रूप से बेहतर बनाएँ।
weight: 11
url: /hi/java/java-powerpoint-table-formatting-updates/format-text-inside-table-column-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## परिचय
क्या आप PowerPoint प्रस्तुतियों की दुनिया में उतरने के लिए तैयार हैं, लेकिन एक ट्विस्ट के साथ? अपनी स्लाइड्स को मैन्युअल रूप से फ़ॉर्मेट करने के बजाय, आइए Aspose.Slides for Java का उपयोग करके अधिक कुशल मार्ग अपनाएँ। यह ट्यूटोरियल आपको PowerPoint प्रस्तुतियों में टेबल कॉलम के अंदर टेक्स्ट को प्रोग्रामेटिक रूप से फ़ॉर्मेट करने की प्रक्रिया के बारे में बताएगा। तैयार हो जाइए, क्योंकि यह एक मजेदार सवारी होने वाली है!
## आवश्यक शर्तें
शुरू करने से पहले, आपको कुछ चीजों की आवश्यकता होगी:
1.  जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके मशीन पर JDK इंस्टॉल है। यदि नहीं, तो आप इसे यहाँ से डाउनलोड कर सकते हैं[ओरेकल की वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: से नवीनतम संस्करण डाउनलोड करें[Aspose.Slides डाउनलोड पृष्ठ](https://releases.aspose.com/slides/java/).
3. एकीकृत विकास वातावरण (आईडीई): इंटेलीज आईडिया या एक्लिप्स जैसा आईडीई आपकी कोडिंग यात्रा को आसान बना देगा।
4.  पावरपॉइंट प्रेजेंटेशन: एक पावरपॉइंट फ़ाइल जिसमें एक टेबल हो जिसका इस्तेमाल आप परीक्षण के लिए कर सकते हैं। हम इसे इस तरह से संदर्भित करेंगे`SomePresentationWithTable.pptx`.

## पैकेज आयात करें
सबसे पहले, आइए अपना प्रोजेक्ट सेट करें और आवश्यक पैकेज आयात करें। यह ट्यूटोरियल के लिए हमारा आधार होगा।
```java
import com.aspose.slides.*;
```
## चरण 1: प्रस्तुति लोड करें
हमारी यात्रा का पहला चरण पावरपॉइंट प्रेजेंटेशन को हमारे प्रोग्राम में लोड करना है।
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास का एक उदाहरण बनाएँ
Presentation pres = new Presentation(dataDir + "SomePresentationWithTable.pptx");
```
 कोड की यह पंक्ति एक उदाहरण बनाती है`Presentation` क्लास, जो हमारी पावरपॉइंट फ़ाइल का प्रतिनिधित्व करता है।
## चरण 2: स्लाइड और तालिका तक पहुंचें
इसके बाद, हमें स्लाइड और उस स्लाइड के अंदर मौजूद टेबल तक पहुंचना होगा। सरलता के लिए, मान लें कि टेबल पहली स्लाइड पर पहली आकृति है।
### पहली स्लाइड तक पहुंचें
```java
ISlide slide = pres.getSlides().get_Item(0);
```
यह पंक्ति प्रस्तुति से पहली स्लाइड प्राप्त करती है।
### टेबल तक पहुंचें
```java
ITable someTable = (ITable) slide.getShapes().get_Item(0);
```
यहां, हम पहली स्लाइड पर पहली आकृति तक पहुंच रहे हैं, जिसे हम अपनी तालिका मानते हैं।
## चरण 3: पहले कॉलम के लिए फ़ॉन्ट की ऊंचाई सेट करें
अब, आइए तालिका के पहले कॉलम में पाठ के लिए फ़ॉन्ट की ऊंचाई निर्धारित करें।
```java
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontHeight(25);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
 इन पंक्तियों में, हम परिभाषित करते हैं`PortionFormat` पहले कॉलम के लिए फ़ॉन्ट की ऊंचाई 25 पॉइंट पर सेट करने के लिए ऑब्जेक्ट का उपयोग करें।
## चरण 4: टेक्स्ट को दाईं ओर संरेखित करें
टेक्स्ट संरेखण आपकी स्लाइड की पठनीयता में बड़ा अंतर ला सकता है। आइए पहले कॉलम में टेक्स्ट को दाईं ओर संरेखित करें।

```java
ParagraphFormat paragraphFormat = new ParagraphFormat();
paragraphFormat.setAlignment(TextAlignment.Right);
paragraphFormat.setMarginRight(20);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
 यहाँ, हम एक का उपयोग करते हैं`ParagraphFormat` ऑब्जेक्ट का उपयोग करके टेक्स्ट संरेखण को दाईं ओर सेट करें और दायां मार्जिन 20 जोड़ें।
## चरण 5: टेक्स्ट का वर्टिकल प्रकार सेट करें
पाठ को एक विशिष्ट अभिविन्यास देने के लिए, हम पाठ का ऊर्ध्वाधर प्रकार निर्धारित कर सकते हैं।
```java
TextFrameFormat textFrameFormat = new TextFrameFormat();
textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
यह स्निपेट पहले कॉलम के लिए पाठ अभिविन्यास को लंबवत् सेट करता है।
## चरण 6: प्रेजेंटेशन सहेजें
अंत में, सभी स्वरूपण परिवर्तन करने के बाद, हमें संशोधित प्रस्तुति को सहेजना होगा।
```java
pres.save(dataDir + "result.pptx", SaveFormat.Pptx);
```
 यह कमांड नामक फ़ाइल पर लागू नए प्रारूप के साथ प्रस्तुति को सहेजता है`result.pptx`.

## निष्कर्ष
बस, अब यह हो गया! आपने Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में टेबल कॉलम के अंदर टेक्स्ट को फ़ॉर्मेट कर दिया है। इन कार्यों को स्वचालित करके, आप समय बचा सकते हैं और अपनी प्रेजेंटेशन में एकरूपता सुनिश्चित कर सकते हैं। हैप्पी कोडिंग!
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं एक साथ कई कॉलमों को फ़ॉर्मेट कर सकता हूँ?
हां, आप एक ही स्वरूपण को अनेक स्तंभों पर लागू कर सकते हैं, उनमें पुनरावृत्ति करके तथा वांछित स्वरूपण निर्धारित करके।
### क्या Aspose.Slides PowerPoint के सभी संस्करणों के साथ संगत है?
Aspose.Slides PowerPoint प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है, जो अधिकांश संस्करणों के साथ संगतता सुनिश्चित करता है।
### क्या मैं Aspose.Slides का उपयोग करके अन्य प्रकार के स्वरूपण जोड़ सकता हूँ?
बिल्कुल! Aspose.Slides फ़ॉन्ट शैलियों, रंगों और अधिक सहित व्यापक स्वरूपण विकल्पों की अनुमति देता है।
### मैं Aspose.Slides का निःशुल्क परीक्षण कैसे प्राप्त कर सकता हूँ?
 आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[Aspose निःशुल्क परीक्षण पृष्ठ](https://releases.aspose.com/).
### मैं और अधिक उदाहरण और दस्तावेज कहां पा सकता हूं?
 इसकी जाँच पड़ताल करो[Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) विस्तृत उदाहरण और मार्गदर्शन के लिए.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
