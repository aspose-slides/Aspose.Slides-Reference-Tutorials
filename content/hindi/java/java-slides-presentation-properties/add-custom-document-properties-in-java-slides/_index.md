---
title: जावा स्लाइड्स में कस्टम दस्तावेज़ गुण जोड़ें
linktitle: जावा स्लाइड्स में कस्टम दस्तावेज़ गुण जोड़ें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: जानें कि जावा स्लाइड्स में कस्टम दस्तावेज़ गुणों के साथ पावरपॉइंट प्रस्तुतियों को कैसे बढ़ाया जाए। जावा के लिए Aspose.Slides का उपयोग करके कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 13
url: /hi/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

## जावा स्लाइड्स में कस्टम दस्तावेज़ गुण जोड़ने का परिचय

इस ट्यूटोरियल में, हम आपको Java के लिए Aspose.Slides का उपयोग करके PowerPoint प्रेजेंटेशन में कस्टम दस्तावेज़ गुण जोड़ने की प्रक्रिया के बारे में बताएंगे। कस्टम दस्तावेज़ गुण आपको संदर्भ या वर्गीकरण के लिए प्रस्तुति के बारे में अतिरिक्त जानकारी संग्रहीत करने की अनुमति देते हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके जावा प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी स्थापित और सेटअप है।

## चरण 1: आवश्यक पैकेज आयात करें

```java
import com.aspose.slides.*;
```

## चरण 2: एक नई प्रस्तुति बनाएं

सबसे पहले, आपको एक नया प्रेजेंटेशन ऑब्जेक्ट बनाना होगा। आप इसे इस प्रकार कर सकते हैं:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";

// प्रेजेंटेशन क्लास को इंस्टेंट करें
Presentation presentation = new Presentation();
```

## चरण 3: दस्तावेज़ गुण प्राप्त करना

इसके बाद, आप प्रस्तुतिकरण के दस्तावेज़ गुणों को पुनः प्राप्त करेंगे। इन गुणों में शीर्षक, लेखक और कस्टम गुण जैसे अंतर्निहित गुण शामिल हैं जिन्हें आप जोड़ सकते हैं।

```java
// दस्तावेज़ गुण प्राप्त करना
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## चरण 4: कस्टम गुण जोड़ना

अब, प्रेजेंटेशन में कस्टम गुण जोड़ें। कस्टम गुणों में एक नाम और एक मान शामिल होता है। आप अपनी इच्छानुसार कोई भी जानकारी संग्रहीत करने के लिए उनका उपयोग कर सकते हैं।

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## चरण 5: किसी विशेष सूचकांक पर संपत्ति का नाम प्राप्त करना

आप किसी विशिष्ट इंडेक्स पर कस्टम प्रॉपर्टी का नाम भी पुनः प्राप्त कर सकते हैं। यदि आपको विशिष्ट गुणों के साथ काम करने की आवश्यकता हो तो यह उपयोगी हो सकता है।

```java
// किसी विशेष सूचकांक पर संपत्ति का नाम प्राप्त करना
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## चरण 6: चयनित संपत्ति को हटाना

यदि आप किसी कस्टम प्रॉपर्टी को हटाना चाहते हैं, तो आप उसका नाम निर्दिष्ट करके ऐसा कर सकते हैं। यहां, हम चरण 5 में प्राप्त संपत्ति को हटा रहे हैं।

```java
// चयनित संपत्ति को हटाया जा रहा है
documentProperties.removeCustomProperty(getPropertyName);
```

## चरण 7: प्रस्तुति को सहेजना

अंत में, प्रेजेंटेशन को किसी फ़ाइल में जोड़े और हटाए गए कस्टम गुणों के साथ सहेजें।

```java
// प्रस्तुतिकरण सहेजा जा रहा है
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## जावा स्लाइड्स में कस्टम दस्तावेज़ गुण जोड़ने के लिए संपूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
// प्रेजेंटेशन क्लास को इंस्टेंट करें
Presentation presentation = new Presentation();
// दस्तावेज़ गुण प्राप्त करना
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// कस्टम गुण जोड़ना
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// विशेष सूचकांक पर संपत्ति का नाम प्राप्त करना
String getPropertyName = documentProperties.getCustomPropertyName(2);
// चयनित संपत्ति को हटाया जा रहा है
documentProperties.removeCustomProperty(getPropertyName);
// प्रस्तुतिकरण सहेजा जा रहा है
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## निष्कर्ष

आपने सीखा है कि Aspose.Slides का उपयोग करके जावा में PowerPoint प्रस्तुति में कस्टम दस्तावेज़ गुण कैसे जोड़ें। कस्टम गुण आपकी प्रस्तुतियों से संबंधित अतिरिक्त जानकारी संग्रहीत करने के लिए मूल्यवान हो सकते हैं। आप अपने विशिष्ट उपयोग के मामले के लिए आवश्यकतानुसार अधिक कस्टम गुणों को शामिल करने के लिए इस ज्ञान का विस्तार कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं कस्टम संपत्ति का मूल्य कैसे प्राप्त करूं?

 किसी कस्टम प्रॉपर्टी का मूल्य पुनर्प्राप्त करने के लिए, आप इसका उपयोग कर सकते हैं`get_Item` पर विधि`documentProperties` वस्तु। उदाहरण के लिए:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### क्या मैं विभिन्न डेटा प्रकारों के कस्टम गुण जोड़ सकता हूँ?

हां, आप विभिन्न डेटा प्रकारों के कस्टम गुण जोड़ सकते हैं, जिनमें संख्याएं, स्ट्रिंग्स, दिनांक और बहुत कुछ शामिल हैं, जैसा कि उदाहरण में दिखाया गया है। जावा के लिए Aspose.Slides विभिन्न डेटा प्रकारों को सहजता से संभालता है।

### क्या मेरे द्वारा जोड़ी जा सकने वाली कस्टम संपत्तियों की संख्या की कोई सीमा है?

आपके द्वारा जोड़ी जा सकने वाली कस्टम संपत्तियों की संख्या की कोई सख्त सीमा नहीं है। हालाँकि, ध्यान रखें कि अत्यधिक संख्या में गुण जोड़ने से आपकी प्रस्तुति फ़ाइल का प्रदर्शन और आकार प्रभावित हो सकता है।

### मैं प्रेजेंटेशन में सभी कस्टम संपत्तियों को कैसे सूचीबद्ध कर सकता हूं?

आप सभी कस्टम गुणों को सूचीबद्ध करने के लिए उनके माध्यम से लूप कर सकते हैं। यह कैसे करें इसका एक उदाहरण यहां दिया गया है:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

यह कोड प्रेजेंटेशन में सभी कस्टम प्रॉपर्टी के नाम और मान प्रदर्शित करेगा।