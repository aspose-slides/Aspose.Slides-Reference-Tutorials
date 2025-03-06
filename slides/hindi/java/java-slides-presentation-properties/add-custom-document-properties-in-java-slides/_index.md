---
title: जावा स्लाइड्स में कस्टम दस्तावेज़ गुण जोड़ें
linktitle: जावा स्लाइड्स में कस्टम दस्तावेज़ गुण जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि Java Slides में कस्टम डॉक्यूमेंट प्रॉपर्टीज़ के साथ PowerPoint प्रेजेंटेशन को कैसे बेहतर बनाया जाए। Java के लिए Aspose.Slides का उपयोग करके कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 13
url: /hi/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में कस्टम दस्तावेज़ गुण जोड़ने का परिचय

इस ट्यूटोरियल में, हम आपको Aspose.Slides for Java का उपयोग करके PowerPoint प्रेजेंटेशन में कस्टम दस्तावेज़ गुण जोड़ने की प्रक्रिया से परिचित कराएँगे। कस्टम दस्तावेज़ गुण आपको संदर्भ या वर्गीकरण के लिए प्रेजेंटेशन के बारे में अतिरिक्त जानकारी संग्रहीत करने की अनुमति देते हैं।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास Aspose.Slides for Java लाइब्रेरी स्थापित है और आपके Java प्रोजेक्ट में सेट अप है।

## चरण 1: आवश्यक पैकेज आयात करें

```java
import com.aspose.slides.*;
```

## चरण 2: एक नई प्रस्तुति बनाएँ

सबसे पहले, आपको एक नया प्रेजेंटेशन ऑब्जेक्ट बनाना होगा। आप इसे इस प्रकार कर सकते हैं:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// प्रेजेंटेशन क्लास को इंस्टैंसिएट करें
Presentation presentation = new Presentation();
```

## चरण 3: दस्तावेज़ गुण प्राप्त करना

इसके बाद, आप प्रस्तुति के दस्तावेज़ गुण प्राप्त करेंगे। इन गुणों में शीर्षक, लेखक और कस्टम गुण जैसे अंतर्निहित गुण शामिल हैं जिन्हें आप जोड़ सकते हैं।

```java
// दस्तावेज़ गुण प्राप्त करना
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## चरण 4: कस्टम गुण जोड़ना

अब, प्रेजेंटेशन में कस्टम प्रॉपर्टीज जोड़ते हैं। कस्टम प्रॉपर्टीज में एक नाम और एक मान होता है। आप इनका इस्तेमाल अपनी मनचाही जानकारी स्टोर करने के लिए कर सकते हैं।

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## चरण 5: किसी विशेष इंडेक्स पर प्रॉपर्टी का नाम प्राप्त करना

आप किसी खास इंडेक्स पर कस्टम प्रॉपर्टी का नाम भी प्राप्त कर सकते हैं। यदि आपको विशिष्ट प्रॉपर्टी के साथ काम करने की आवश्यकता है तो यह उपयोगी हो सकता है।

```java
// किसी विशेष इंडेक्स पर संपत्ति का नाम प्राप्त करना
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## चरण 6: चयनित प्रॉपर्टी हटाना

यदि आप कोई कस्टम प्रॉपर्टी हटाना चाहते हैं, तो आप उसका नाम निर्दिष्ट करके ऐसा कर सकते हैं। यहाँ, हम चरण 5 में प्राप्त की गई प्रॉपर्टी को हटा रहे हैं।

```java
// चयनित संपत्ति हटाना
documentProperties.removeCustomProperty(getPropertyName);
```

## चरण 7: प्रस्तुति को सहेजना

अंत में, जोड़े गए और हटाए गए कस्टम गुणों के साथ प्रस्तुति को एक फ़ाइल में सहेजें।

```java
// प्रस्तुति सहेजना
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में कस्टम दस्तावेज़ गुण जोड़ने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास को इंस्टैंसिएट करें
Presentation presentation = new Presentation();
// दस्तावेज़ गुण प्राप्त करना
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// कस्टम गुण जोड़ना
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// विशेष इंडेक्स पर संपत्ति का नाम प्राप्त करना
String getPropertyName = documentProperties.getCustomPropertyName(2);
// चयनित संपत्ति हटाना
documentProperties.removeCustomProperty(getPropertyName);
// प्रस्तुति सहेजना
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

आपने सीखा है कि Aspose.Slides का उपयोग करके Java में PowerPoint प्रेजेंटेशन में कस्टम दस्तावेज़ गुण कैसे जोड़ें। कस्टम गुण आपके प्रेजेंटेशन से संबंधित अतिरिक्त जानकारी संग्रहीत करने के लिए मूल्यवान हो सकते हैं। आप अपने विशिष्ट उपयोग मामले के लिए आवश्यकतानुसार अधिक कस्टम गुण शामिल करने के लिए इस ज्ञान का विस्तार कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं कस्टम प्रॉपर्टी का मान कैसे प्राप्त करूं?

 किसी कस्टम प्रॉपर्टी का मान प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`get_Item` विधि पर`documentProperties` वस्तु. उदाहरण के लिए:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### क्या मैं विभिन्न डेटा प्रकारों के कस्टम गुण जोड़ सकता हूँ?

हां, आप विभिन्न डेटा प्रकारों के कस्टम गुण जोड़ सकते हैं, जिसमें संख्याएं, स्ट्रिंग्स, दिनांक और बहुत कुछ शामिल हैं, जैसा कि उदाहरण में दिखाया गया है। Aspose.Slides for Java विभिन्न डेटा प्रकारों को सहजता से संभालता है।

### क्या मेरे द्वारा जोड़ी जा सकने वाली कस्टम प्रॉपर्टीज़ की संख्या की कोई सीमा है?

आप जो कस्टम प्रॉपर्टी जोड़ सकते हैं, उनकी संख्या पर कोई सख्त सीमा नहीं है। हालाँकि, ध्यान रखें कि बहुत ज़्यादा संख्या में प्रॉपर्टी जोड़ने से आपकी प्रेजेंटेशन फ़ाइल का प्रदर्शन और आकार प्रभावित हो सकता है।

### मैं किसी प्रस्तुति में सभी कस्टम गुण कैसे सूचीबद्ध कर सकता हूँ?

आप सभी कस्टम प्रॉपर्टी को सूचीबद्ध करने के लिए लूप कर सकते हैं। ऐसा करने का एक उदाहरण यहां दिया गया है:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

यह कोड प्रस्तुति में सभी कस्टम गुणों के नाम और मान प्रदर्शित करेगा।
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
