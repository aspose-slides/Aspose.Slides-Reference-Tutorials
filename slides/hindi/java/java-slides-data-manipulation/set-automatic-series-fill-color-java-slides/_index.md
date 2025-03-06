---
title: जावा स्लाइड्स में स्वचालित श्रृंखला भरण रंग सेट करें
linktitle: जावा स्लाइड्स में स्वचालित श्रृंखला भरण रंग सेट करें
second_title: Aspose.Slides जावा पावरपॉइंट प्रोसेसिंग एपीआई
description: Aspose.Slides for Java का उपयोग करके Java स्लाइड्स में स्वचालित श्रृंखला भरण रंग सेट करना सीखें। गतिशील प्रस्तुतियों के लिए कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका।
weight: 14
url: /hi/java/data-manipulation/set-automatic-series-fill-color-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## जावा स्लाइड्स में स्वचालित श्रृंखला भरण रंग सेट करने का परिचय

इस ट्यूटोरियल में, हम जावा एपीआई के लिए Aspose.Slides का उपयोग करके जावा स्लाइड में स्वचालित श्रृंखला भरण रंग सेट करने का तरीका जानेंगे। जावा के लिए Aspose.Slides एक शक्तिशाली लाइब्रेरी है जो आपको प्रोग्रामेटिक रूप से पावरपॉइंट प्रेजेंटेशन बनाने, हेरफेर करने और प्रबंधित करने की अनुमति देती है। इस गाइड के अंत तक, आप चार्ट बनाने और स्वचालित श्रृंखला भरण रंग आसानी से सेट करने में सक्षम होंगे।

## आवश्यक शर्तें

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (JDK) स्थापित है।
-  Aspose.Slides for Java लाइब्रेरी आपके प्रोजेक्ट में जोड़ दी गई है। आप इसे यहाँ से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/slides/java/).

अब जबकि हमारी रूपरेखा तैयार हो गई है, तो आइए चरण-दर-चरण मार्गदर्शिका से शुरुआत करें।

## चरण 1: Java के लिए Aspose.Slides का परिचय

Aspose.Slides for Java एक Java API है जो डेवलपर्स को PowerPoint प्रस्तुतियों के साथ काम करने की अनुमति देता है। यह स्लाइड, चार्ट, आकृतियाँ और बहुत कुछ बनाने, संपादित करने और हेरफेर करने सहित कई प्रकार की सुविधाएँ प्रदान करता है।

## चरण 2: अपना जावा प्रोजेक्ट सेट अप करना

कोडिंग शुरू करने से पहले, सुनिश्चित करें कि आपने अपने पसंदीदा एकीकृत विकास वातावरण (IDE) में एक जावा प्रोजेक्ट सेट अप किया है। अपने प्रोजेक्ट में Aspose.Slides for Java लाइब्रेरी जोड़ना सुनिश्चित करें।

## चरण 3: पावरपॉइंट प्रेजेंटेशन बनाना

आरंभ करने के लिए, निम्नलिखित कोड स्निपेट का उपयोग करके एक नया पावरपॉइंट प्रेजेंटेशन बनाएं:

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

 प्रतिस्थापित करें`"Your Document Directory"` उस पथ के साथ जहाँ आप प्रस्तुति को सहेजना चाहते हैं.

## चरण 4: प्रस्तुति में चार्ट जोड़ना

इसके बाद, आइए प्रस्तुति में एक क्लस्टर्ड कॉलम चार्ट जोड़ें। इसे पूरा करने के लिए हम निम्नलिखित कोड का उपयोग करेंगे:

```java
// क्लस्टर कॉलम चार्ट बनाना
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

यह कोड प्रस्तुति की पहली स्लाइड पर एक क्लस्टर कॉलम चार्ट बनाता है।

## चरण 5: स्वचालित श्रृंखला भरण रंग सेट करना

अब मुख्य भाग आता है—स्वचालित श्रृंखला भरण रंग सेट करना। हम चार्ट की श्रृंखला के माध्यम से पुनरावृति करेंगे और उनके भरण प्रारूप को स्वचालित पर सेट करेंगे:

```java
// श्रृंखला भरण प्रारूप को स्वचालित पर सेट करना
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

यह कोड सुनिश्चित करता है कि श्रृंखला भरण रंग स्वचालित पर सेट है।

## चरण 6: प्रस्तुति को सहेजना

प्रस्तुति को सहेजने के लिए निम्नलिखित कोड का उपयोग करें:

```java
// प्रस्तुति फ़ाइल को डिस्क पर लिखें
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

 प्रतिस्थापित करें`"AutoFillSeries_out.pptx"` इच्छित फ़ाइल नाम के साथ.

## जावा स्लाइड्स में स्वचालित श्रृंखला भरण रंग सेट करने के लिए पूर्ण स्रोत कोड

```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// क्लस्टर कॉलम चार्ट बनाना
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// श्रृंखला भरण प्रारूप को स्वचालित पर सेट करना
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// प्रस्तुति फ़ाइल को डिस्क पर लिखें
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## निष्कर्ष

बधाई हो! आपने Aspose.Slides for Java का उपयोग करके Java स्लाइड में स्वचालित श्रृंखला भरण रंग सफलतापूर्वक सेट कर लिया है। अब आप इस ज्ञान का उपयोग अपने Java अनुप्रयोगों में गतिशील और आकर्षक PowerPoint प्रस्तुतियाँ बनाने के लिए कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### मैं चार्ट प्रकार को भिन्न शैली में कैसे बदल सकता हूँ?

 आप चार्ट प्रकार को बदलकर बदल सकते हैं`ChartType.ClusteredColumn` वांछित चार्ट प्रकार के साथ, जैसे`ChartType.Line` या`ChartType.Pie`.

### क्या मैं चार्ट के स्वरूप को और अधिक अनुकूलित कर सकता हूँ?

हां, आप चार्ट के विभिन्न गुणों, जैसे रंग, फ़ॉन्ट और लेबल को संशोधित करके चार्ट के स्वरूप को अनुकूलित कर सकते हैं।

### क्या Aspose.Slides for Java व्यावसायिक उपयोग के लिए उपयुक्त है?

हां, Aspose.Slides for Java का इस्तेमाल व्यक्तिगत और व्यावसायिक दोनों तरह की परियोजनाओं के लिए किया जा सकता है। अधिक जानकारी के लिए आप उनकी लाइसेंसिंग शर्तों को देख सकते हैं।

### क्या Aspose.Slides द्वारा Java के लिए कोई अन्य सुविधाएं प्रदान की गई हैं?

हां, Aspose.Slides for Java कई प्रकार की सुविधाएं प्रदान करता है, जिसमें स्लाइड मैनीपुलेशन, टेक्स्ट फॉर्मेटिंग और एनीमेशन समर्थन शामिल है।

### मैं अधिक संसाधन और दस्तावेज कहां पा सकता हूं?

 आप Aspose.Slides for Java के लिए विस्तृत दस्तावेज़ यहां से प्राप्त कर सकते हैं[यहाँ](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
