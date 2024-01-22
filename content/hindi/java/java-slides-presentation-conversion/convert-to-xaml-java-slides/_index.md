---
title: जावा स्लाइड्स में XAML में कनवर्ट करें
linktitle: जावा स्लाइड्स में XAML में कनवर्ट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides के साथ जावा में PowerPoint प्रस्तुतियों को XAML में परिवर्तित करना सीखें। निर्बाध एकीकरण के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 28
url: /hi/java/presentation-conversion/convert-to-xaml-java-slides/
---

## परिचय जावा स्लाइड में XAML में कनवर्ट करें

इस व्यापक गाइड में, हम यह पता लगाएंगे कि जावा एपीआई के लिए Aspose.Slides का उपयोग करके प्रस्तुतियों को XAML प्रारूप में कैसे परिवर्तित किया जाए। XAML (एक्स्टेंसिबल एप्लिकेशन मार्कअप लैंग्वेज) यूजर इंटरफेस बनाने के लिए व्यापक रूप से उपयोग की जाने वाली मार्कअप लैंग्वेज है। प्रस्तुतियों को XAML में परिवर्तित करना आपके PowerPoint सामग्री को विभिन्न अनुप्रयोगों में एकीकृत करने में एक महत्वपूर्ण कदम हो सकता है, विशेष रूप से WPF (विंडोज प्रेजेंटेशन फाउंडेशन) जैसी प्रौद्योगिकियों के साथ निर्मित अनुप्रयोगों में।

## आवश्यक शर्तें

इससे पहले कि हम रूपांतरण प्रक्रिया में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

-  जावा एपीआई के लिए Aspose.Slides: आपके पास अपने विकास परिवेश में Java के लिए Aspose.Slides इंस्टॉल और सेटअप होना चाहिए। यदि नहीं, तो आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

## चरण 1: प्रस्तुति लोड हो रही है

आरंभ करने के लिए, हमें स्रोत पावरपॉइंट प्रेजेंटेशन को लोड करना होगा जिसे हम XAML में कनवर्ट करना चाहते हैं। आप अपनी प्रस्तुति फ़ाइल को पथ प्रदान करके ऐसा कर सकते हैं। आरंभ करने के लिए यहां एक कोड स्निपेट दिया गया है:

```java
// स्रोत प्रस्तुति का पथ
String presentationFileName = "XamlEtalon.pptx";
Presentation pres = new Presentation(presentationFileName);
```

## चरण 2: रूपांतरण विकल्पों को कॉन्फ़िगर करना

प्रेजेंटेशन को परिवर्तित करने से पहले, आप आउटपुट को अपनी आवश्यकताओं के अनुरूप बनाने के लिए विभिन्न रूपांतरण विकल्पों को कॉन्फ़िगर कर सकते हैं। हमारे मामले में, हम XAML रूपांतरण विकल्प बनाएंगे और उन्हें निम्नानुसार सेट करेंगे:

```java
// रूपांतरण विकल्प बनाएँ
XamlOptions xamlOptions = new XamlOptions();
xamlOptions.setExportHiddenSlides(true);
```

ये विकल्प हमें छिपी हुई स्लाइडों को निर्यात करने और रूपांतरण प्रक्रिया को अनुकूलित करने की अनुमति देते हैं।

## चरण 3: आउटपुट सेवर को लागू करना

परिवर्तित XAML सामग्री को सहेजने के लिए, हमें एक आउटपुट सेवर को परिभाषित करने की आवश्यकता है। यहां XAML के लिए आउटपुट सेवर का एक कस्टम कार्यान्वयन है:

```java
class NewXamlSaver implements IXamlOutputSaver
{
    private Map<String, String> m_result = new HashMap<String, String>();

    public Map<String, String> getResults()
    {
        return m_result;
    }

    public void save(String path, byte[] data)
    {
        String name = new File(path).getName();
        m_result.put(name, new String(data, StandardCharsets.UTF_8));
    }
}
```

यह कस्टम आउटपुट सेवर परिवर्तित XAML डेटा को एक मानचित्र में संग्रहीत करता है।

## चरण 4: स्लाइड्स को परिवर्तित करना और सहेजना

प्रेजेंटेशन लोड होने और रूपांतरण विकल्प सेट होने के साथ, अब हम स्लाइड्स को परिवर्तित करने और उन्हें XAML फ़ाइलों के रूप में सहेजने के लिए आगे बढ़ सकते हैं। यहां बताया गया है कि आप यह कैसे कर सकते हैं:

```java
try {
    // अपनी स्वयं की आउटपुट-सेविंग सेवा को परिभाषित करें
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.setOutputSaver(newXamlSaver);
    
    // स्लाइड परिवर्तित करें
    pres.save(xamlOptions);
    
    // XAML फ़ाइलों को आउटपुट निर्देशिका में सहेजें
    for (Map.Entry<String, String> pair : newXamlSaver.getResults().entrySet()) {
        FileWriter writer = new FileWriter(pair.getKey(), true);
        writer.append(pair.getValue());
        writer.close();
    }
} catch(IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```

इस चरण में, हम कस्टम आउटपुट सेवर सेट करते हैं, रूपांतरण करते हैं, और परिणामी XAML फ़ाइलों को सहेजते हैं।

## जावा स्लाइड्स में XAML में कनवर्ट करने के लिए संपूर्ण स्रोत कोड

```java
	// स्रोत प्रस्तुति का पथ
	String presentationFileName = RunExamples.getDataDir_Conversion() + "XamlEtalon.pptx";
	Presentation pres = new Presentation(presentationFileName);
	try {
		// रूपांतरण विकल्प बनाएँ
		XamlOptions xamlOptions = new XamlOptions();
		xamlOptions.setExportHiddenSlides(true);
		// अपनी स्वयं की आउटपुट-सेविंग सेवा को परिभाषित करें
		NewXamlSaver newXamlSaver = new NewXamlSaver();
		xamlOptions.setOutputSaver(newXamlSaver);
		// स्लाइड परिवर्तित करें
		pres.save(xamlOptions);
		// XAML फ़ाइलों को आउटपुट निर्देशिका में सहेजें
		for (Map.Entry<String, String> pair : newXamlSaver.getResults().entrySet()) {
			FileWriter writer = new FileWriter(RunExamples.getOutPath() + pair.getKey(), true);
			writer.append(pair.getValue());
			writer.close();
		}
	} catch(IOException e) {
		e.printStackTrace();
	} finally {
		if (pres != null) pres.dispose();
	}
}
/
 * Represents an output saver implementation for transfer data to the external storage.
 */
static class NewXamlSaver implements IXamlOutputSaver
{
	private Map<String, String> m_result =  new HashMap<String, String>();
	public Map<String, String> getResults()
	{
		return m_result;
	}
	public void save(String path, byte[] data)
	{
		String name = new File(path).getName();
		m_result.put(name, new String(data, StandardCharsets.UTF_8));
	}
```

## निष्कर्ष

जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा में XAML में प्रस्तुतियों को परिवर्तित करना आपके PowerPoint सामग्री को उन अनुप्रयोगों में एकीकृत करने का एक शक्तिशाली तरीका है जो XAML-आधारित उपयोगकर्ता इंटरफ़ेस पर निर्भर हैं। इस गाइड में बताए गए चरणों का पालन करके, आप इस कार्य को आसानी से पूरा कर सकते हैं और अपने एप्लिकेशन की उपयोगिता बढ़ा सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं जावा के लिए Aspose.Slides कैसे स्थापित करूं?

 आप जावा के लिए Aspose.Slides को वेबसाइट से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

### क्या मैं XAML आउटपुट को और अधिक अनुकूलित कर सकता हूँ?

हां, आप जावा एपीआई के लिए Aspose.Slides द्वारा प्रदान किए गए रूपांतरण विकल्पों को समायोजित करके XAML आउटपुट को अनुकूलित कर सकते हैं। यह आपको अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए आउटपुट को तैयार करने की अनुमति देता है।

### XAML का उपयोग किस लिए किया जाता है?

XAML (एक्स्टेंसिबल एप्लिकेशन मार्कअप लैंग्वेज) एक मार्कअप लैंग्वेज है जिसका उपयोग एप्लिकेशन में यूजर इंटरफेस बनाने के लिए किया जाता है, विशेष रूप से WPF (विंडोज प्रेजेंटेशन फाउंडेशन) और UWP (यूनिवर्सल विंडोज प्लेटफॉर्म) जैसी प्रौद्योगिकियों के साथ निर्मित अनुप्रयोगों में।

### मैं रूपांतरण के दौरान छिपी हुई स्लाइडों को कैसे संभाल सकता हूँ?

रूपांतरण के दौरान छिपी हुई स्लाइडों को निर्यात करने के लिए, सेट करें`setExportHiddenSlides` का विकल्प`true` आपके XAML रूपांतरण विकल्पों में, जैसा कि इस गाइड में दिखाया गया है।

### क्या Aspose.Slides द्वारा समर्थित कोई अन्य आउटपुट स्वरूप हैं?

हां, Aspose.Slides पीडीएफ, HTML, छवियों और अन्य सहित आउटपुट स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है। आप एपीआई दस्तावेज़ में इन विकल्पों का पता लगा सकते हैं।