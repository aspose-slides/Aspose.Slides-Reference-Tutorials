---
"description": "Aspose.Slides for Java का उपयोग करके PowerPoint में अंतर्निहित प्रॉपर्टी तक पहुँचने का तरीका जानें। यह ट्यूटोरियल आपको लेखक, निर्माण तिथि और बहुत कुछ प्राप्त करने में मार्गदर्शन करता है।"
"linktitle": "PowerPoint में अंतर्निहित गुणों तक पहुँचें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "PowerPoint में अंतर्निहित गुणों तक पहुँचें"
"url": "/hi/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint में अंतर्निहित गुणों तक पहुँचें

## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में अंतर्निहित गुणों तक पहुँचने का तरीका जानेंगे। Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो जावा डेवलपर्स को प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों के साथ काम करने की अनुमति देती है, जिससे गुणों को पढ़ने और संशोधित करने जैसे कार्य सहजता से संभव हो जाते हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. जावा डेवलपमेंट किट (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK इंस्टॉल है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java: Aspose.Slides for Java को यहां से डाउनलोड और इंस्टॉल करें [इस लिंक](https://releases.aspose.com/slides/java/).

## पैकेज आयात करें
सबसे पहले, आपको अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करने होंगे। अपनी जावा फ़ाइल की शुरुआत में निम्न आयात कथन जोड़ें:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## चरण 1: प्रेजेंटेशन ऑब्जेक्ट सेट करें
आप जिस PowerPoint प्रेजेंटेशन के साथ काम करना चाहते हैं, उसे दर्शाने के लिए प्रेजेंटेशन ऑब्जेक्ट को सेट अप करके शुरू करें। आप इसे इस तरह से कर सकते हैं:
```java
// प्रस्तुति फ़ाइल वाली निर्देशिका का पथ
String dataDir = "path_to_your_presentation_directory/";
// प्रेजेंटेशन क्लास को इंस्टैंसिएट करें
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## चरण 2: दस्तावेज़ गुण तक पहुँचें
प्रेजेंटेशन ऑब्जेक्ट सेट अप करने के बाद, आप IDocumentProperties इंटरफ़ेस का उपयोग करके प्रेजेंटेशन के बिल्ट-इन प्रॉपर्टीज़ तक पहुँच सकते हैं। यहाँ बताया गया है कि आप विभिन्न प्रॉपर्टीज़ को कैसे प्राप्त कर सकते हैं:
### वर्ग
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### वर्तमान स्थिति
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### निर्माण तिथि
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### लेखक
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### विवरण
```java
System.out.println("Description : " + documentProperties.getComments());
```
### कीवर्ड
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### अंतिम बार संशोधित
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### पर्यवेक्षक
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### संशोधित तिथि
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### प्रस्तुति प्रारूप
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### अंतिम प्रिंट तिथि
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### उत्पादकों के बीच साझा किया गया
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### विषय
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### शीर्षक
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में अंतर्निहित गुणों तक कैसे पहुँचा जाए। ऊपर बताए गए चरणों का पालन करके, आप आसानी से प्रोग्रामेटिक रूप से लेखक, निर्माण तिथि और शीर्षक जैसे विभिन्न गुणों को पुनः प्राप्त कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Java के लिए Aspose.Slides का उपयोग करके इन अंतर्निहित गुणों को संशोधित कर सकता हूं?
हां, आप Aspose.Slides का उपयोग करके इन गुणों को संशोधित कर सकते हैं। बस IDocumentProperties इंटरफ़ेस द्वारा प्रदान की गई उपयुक्त सेटर विधियों का उपयोग करें।
### क्या Aspose.Slides PowerPoint के विभिन्न संस्करणों के साथ संगत है?
Aspose.Slides PowerPoint संस्करणों की एक विस्तृत श्रृंखला का समर्थन करता है, जो विभिन्न प्लेटफार्मों पर संगतता सुनिश्चित करता है।
### क्या मैं कस्टम गुण भी प्राप्त कर सकता हूँ?
हां, अंतर्निहित गुणों के अलावा, आप Java के लिए Aspose.Slides का उपयोग करके कस्टम गुणों को पुनः प्राप्त और संशोधित भी कर सकते हैं।
### क्या Aspose.Slides दस्तावेज़ीकरण और समर्थन प्रदान करता है?
हां, आप यहां पर व्यापक दस्तावेज पा सकते हैं और सहायता मंचों तक पहुंच सकते हैं। [Aspose वेबसाइट](https://reference.aspose.com/slides/java/).
### क्या Java के लिए Aspose.Slides का कोई परीक्षण संस्करण उपलब्ध है?
हां, आप यहां से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं [यहाँ](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}