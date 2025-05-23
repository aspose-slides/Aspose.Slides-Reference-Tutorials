---
"description": "Aspose.Slides for Java का उपयोग करके PowerPoint प्रस्तुतियों में पैराग्राफ निर्देशांक प्राप्त करना सीखें। सटीक स्थिति के लिए स्रोत कोड के साथ हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"linktitle": "जावा स्लाइड्स में पैराग्राफ के आयताकार निर्देशांक प्राप्त करें"
"second_title": "Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई"
"title": "जावा स्लाइड्स में पैराग्राफ के आयताकार निर्देशांक प्राप्त करें"
"url": "/hi/java/additional-utilities/get-rectangular-coordinates-of-paragraph-in-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# जावा स्लाइड्स में पैराग्राफ के आयताकार निर्देशांक प्राप्त करें


## Aspose.Slides for Java में पैराग्राफ के आयताकार निर्देशांक प्राप्त करने का परिचय

इस ट्यूटोरियल में, हम Aspose.Slides for Java API का उपयोग करके PowerPoint प्रेजेंटेशन में पैराग्राफ़ के आयताकार निर्देशांक प्राप्त करने का तरीका प्रदर्शित करेंगे। नीचे दिए गए चरणों का पालन करके, आप प्रोग्रामेटिक रूप से स्लाइड के भीतर पैराग्राफ़ की स्थिति और आयाम प्राप्त कर सकते हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java डेवलपमेंट वातावरण में सेट अप है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://downloads.aspose.com/slides/java).

## चरण 1: आवश्यक लाइब्रेरीज़ आयात करें

आरंभ करने के लिए, अपने जावा प्रोजेक्ट में Aspose.Slides के साथ काम करने के लिए आवश्यक लाइब्रेरीज़ आयात करें:

```java
import com.aspose.slides.*;
import java.awt.geom.Rectangle2D;
```

## चरण 2: प्रस्तुति लोड करें

इस चरण में, हम उस पावरपॉइंट प्रेजेंटेशन को लोड करेंगे जिसमें वह पैराग्राफ होगा जिसके निर्देशांक हम प्राप्त करना चाहते हैं।

```java
// पावरपॉइंट प्रस्तुति फ़ाइल का पथ
String presentationPath = "YourPresentation.pptx";

// प्रस्तुति लोड करें
Presentation presentation = new Presentation(presentationPath);
```

प्रतिस्थापित करना सुनिश्चित करें `"YourPresentation.pptx"` अपनी PowerPoint फ़ाइल के वास्तविक पथ के साथ.

## चरण 3: पैराग्राफ निर्देशांक प्राप्त करें

अब, हम स्लाइड के भीतर एक विशिष्ट पैराग्राफ तक पहुंचेंगे, इसके आयताकार निर्देशांक निकालेंगे, और परिणाम प्रिंट करेंगे।

```java
try {
 try
{
	IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
	ITextFrame textFrame = shape.getTextFrame();
	Rectangle2D.Float rect = (textFrame.getParagraphs().get_Item(0)).getRect();
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## जावा स्लाइड्स में पैराग्राफ के आयताकार निर्देशांक प्राप्त करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// एक प्रस्तुति ऑब्जेक्ट को इंस्टैंसिएट करें जो एक प्रस्तुति फ़ाइल का प्रतिनिधित्व करता है
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
try
{
	IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
	ITextFrame textFrame = shape.getTextFrame();
	Rectangle2D.Float rect = (textFrame.getParagraphs().get_Item(0)).getRect();
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

यह कोड स्निपेट पहली स्लाइड के पहले आकार के भीतर पहले पैराग्राफ के आयताकार निर्देशांक (X, Y, चौड़ाई और ऊँचाई) प्राप्त करता है। आप आवश्यकतानुसार विभिन्न आकृतियों या स्लाइडों के भीतर पैराग्राफ तक पहुँचने के लिए सूचकांकों को संशोधित कर सकते हैं।

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा कि PowerPoint प्रेजेंटेशन में पैराग्राफ़ के आयताकार निर्देशांक प्राप्त करने के लिए Aspose.Slides for Java का उपयोग कैसे करें। यह तब उपयोगी हो सकता है जब आपको अपनी स्लाइड्स में टेक्स्ट की स्थिति और आयामों का प्रोग्रामेटिक रूप से विश्लेषण या हेरफेर करने की आवश्यकता हो।

## अक्सर पूछे जाने वाले प्रश्न

### मैं पावरपॉइंट स्लाइड के पैराग्राफ तक कैसे पहुंच सकता हूं?

Aspose.Slides for Java का उपयोग करके PowerPoint स्लाइड के भीतर पैराग्राफ तक पहुंचने के लिए, इन चरणों का पालन करें:
1. पावरपॉइंट प्रस्तुति लोड करें.
2. वांछित स्लाइड प्राप्त करने के लिए निम्न का उपयोग करें: `presentation.getSlides().get_Item(slideIndex)`.
3. पाठ युक्त आकृति तक पहुँचने के लिए निम्न का उपयोग करें `slide.getShapes().get_Item(shapeIndex)`.
4. आकृति का टेक्स्ट फ़्रेम पुनर्प्राप्त करें `shape.getTextFrame()`.
5. टेक्स्ट फ़्रेम के भीतर पैराग्राफ़ तक पहुँचें `textFrame.getParagraphs().get_Item(paragraphIndex)`.

### क्या मैं एकाधिक स्लाइडों में पैराग्राफों के लिए निर्देशांक प्राप्त कर सकता हूँ?

हां, आप आवश्यकतानुसार स्लाइड और आकृतियों के माध्यम से पुनरावृति करके कई स्लाइडों में पैराग्राफ के लिए निर्देशांक प्राप्त कर सकते हैं। बस उनके निर्देशांक प्राप्त करने के लिए प्रत्येक स्लाइड के आकार के भीतर पैराग्राफ तक पहुँचने की प्रक्रिया को दोहराएं।

### मैं पैराग्राफ निर्देशांक को प्रोग्रामेटिक रूप से कैसे परिवर्तित करूँ?

एक बार जब आप पैराग्राफ के निर्देशांक प्राप्त कर लेते हैं, तो आप इस जानकारी का उपयोग पैराग्राफ की स्थिति और आयामों को प्रोग्रामेटिक रूप से बदलने के लिए कर सकते हैं। उदाहरण के लिए, आप पैराग्राफ को फिर से स्थान दे सकते हैं, इसकी चौड़ाई या ऊँचाई को समायोजित कर सकते हैं, या इसके निर्देशांक के आधार पर गणना कर सकते हैं।

### क्या Aspose.Slides PowerPoint फ़ाइलों के बैच प्रोसेसिंग के लिए उपयुक्त है?

हां, Aspose.Slides for Java PowerPoint फ़ाइलों की बैच प्रोसेसिंग के लिए उपयुक्त है। आप डेटा निकालने, सामग्री संशोधित करने या कई PowerPoint प्रस्तुतियों से रिपोर्ट बनाने जैसे कार्यों को कुशलतापूर्वक स्वचालित कर सकते हैं।

### मैं और अधिक उदाहरण और दस्तावेज कहां पा सकता हूं?

आप Aspose.Slides for Java के लिए अधिक कोड उदाहरण और विस्तृत दस्तावेज़ यहाँ पा सकते हैं [Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/java/) वेबसाइट। इसके अतिरिक्त, आप पता लगा सकते हैं [Aspose.Slides फ़ोरम](https://forum.aspose.com/c/slides) सामुदायिक समर्थन और चर्चा के लिए।

### क्या मुझे Java के लिए Aspose.Slides का उपयोग करने के लिए लाइसेंस की आवश्यकता है?

हां, आपको आमतौर पर उत्पादन वातावरण में Aspose.Slides for Java का उपयोग करने के लिए वैध लाइसेंस की आवश्यकता होती है। आप Aspose वेबसाइट से लाइसेंस प्राप्त कर सकते हैं। हालांकि, वे परीक्षण और मूल्यांकन उद्देश्यों के लिए एक परीक्षण संस्करण प्रदान कर सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}