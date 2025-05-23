---
"date": "2025-04-17"
"description": "Aspose.Slides का उपयोग करके जावा में मार्कर के साथ लाइन चार्ट बनाना सीखें। यह ट्यूटोरियल चार्ट निर्माण, श्रृंखला जोड़ना और प्रस्तुतियों को प्रभावी ढंग से सहेजना सिखाता है।"
"title": "जावा के लिए Aspose.Slides का उपयोग करके डिफ़ॉल्ट मार्कर के साथ लाइन चार्ट बनाएं"
"url": "/hi/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# जावा के लिए Aspose.Slides का उपयोग करके डिफ़ॉल्ट मार्कर के साथ लाइन चार्ट बनाएं
## परिचय
प्रस्तुतियों, रिपोर्ट और डैशबोर्ड के लिए आकर्षक और जानकारीपूर्ण चार्ट बनाना आवश्यक है। सॉफ़्टवेयर विकास में इस प्रक्रिया को स्वचालित करने से समय की बचत होती है और दस्तावेज़ों में एकरूपता सुनिश्चित होती है। यह ट्यूटोरियल प्रदर्शित करता है कि Aspose.Slides for Java का उपयोग करके मार्करों के साथ लाइन चार्ट कैसे बनाएं।
**जावा के लिए Aspose.Slides** यह एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft Office इंस्टॉल किए बिना प्रोग्रामेटिक रूप से PowerPoint प्रस्तुतियों में हेरफेर करने में सक्षम बनाती है। यह स्लाइड बनाने, संपादित करने और निर्यात करने जैसे कार्यों को सरल बनाता है, जिससे यह स्वचालित दस्तावेज़ निर्माण के लिए एक आवश्यक उपकरण बन जाता है।
**आप क्या सीखेंगे:**
- Java के लिए Aspose.Slides को कैसे आरंभ करें
- मार्करों के साथ लाइन चार्ट बनाने के चरण
- चार्ट में श्रृंखला और श्रेणियां जोड़ना
- चार्ट लेजेंड कॉन्फ़िगर करना
- प्रस्तुति को सहेजना
क्या आप इसमें शामिल होने के लिए तैयार हैं? आइए पहले सुनिश्चित करें कि आपने सब कुछ सेट कर लिया है!
## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपका विकास परिवेश तैयार है:
1. **लाइब्रेरी और निर्भरताएँ:**
   - Aspose.Slides for Java लाइब्रेरी (संस्करण 25.4 अनुशंसित)
   - जावा डेवलपमेंट किट (JDK) संस्करण 16 या उच्चतर
2. **पर्यावरण सेटअप:**
   - आपके IDE को Maven या Gradle बिल्ड टूल्स का समर्थन करना चाहिए।
   - यदि आवश्यक हो तो सुनिश्चित करें कि आपके पास वैध लाइसेंस फ़ाइल है।
3. **ज्ञान पूर्वापेक्षाएँ:**
   - जावा प्रोग्रामिंग की बुनियादी समझ
   - मावेन या ग्रेडल का उपयोग करके प्रोजेक्ट बनाने की जानकारी
इन सब के साथ, आइए अपने प्रोजेक्ट के लिए Aspose.Slides सेट अप करें!
## Java के लिए Aspose.Slides सेट अप करना
Java के लिए Aspose.Slides का उपयोग करने के लिए, आपको इसे अपने प्रोजेक्ट में निर्भरता के रूप में शामिल करना होगा। इस बात पर निर्भर करते हुए कि आप Maven या Gradle का उपयोग कर रहे हैं, सेटअप थोड़ा अलग होगा।
### मावेन
अपने में निम्नलिखित निर्भरता जोड़ें `pom.xml` फ़ाइल:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### ग्रैडल
इसे अपने में शामिल करें `build.gradle` फ़ाइल:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### प्रत्यक्षत: डाउनलोड
वैकल्पिक रूप से, आप नवीनतम संस्करण यहाँ से डाउनलोड कर सकते हैं [Aspose.Slides for Java रिलीज़](https://releases.aspose.com/slides/java/).
**लाइसेंस प्राप्ति चरण:**
- निःशुल्क परीक्षण के लिए, यहां जाएं [निःशुल्क परीक्षण पृष्ठ](https://releases.aspose.com/slides/java/).
- अस्थायी लाइसेंस प्राप्त करने के लिए, यहां जाएं [अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/).
- उनके माध्यम से पूर्ण लाइसेंस खरीदें [खरीद पोर्टल](https://purchase.aspose.com/buy).
**बुनियादी आरंभीकरण:**
यहां बताया गया है कि आप अपने जावा अनुप्रयोग में Aspose.Slides को कैसे आरंभ कर सकते हैं:
```java
import com.aspose.slides.Presentation;
// एक नया प्रस्तुतिकरण ऑब्जेक्ट आरंभ करें
Presentation pres = new Presentation();
```
अब, चलिए चार्ट बनाना शुरू करते हैं!
## कार्यान्वयन मार्गदर्शिका
### विशेषता 1: डिफ़ॉल्ट मार्कर के साथ चार्ट निर्माण
यह अनुभाग दर्शाता है कि मार्करों से सुसज्जित लाइन चार्ट कैसे बनाया जाता है। डेटा रुझानों को प्रभावी ढंग से देखने के लिए यह सुविधा आवश्यक है।
#### लाइन चार्ट जोड़ना
मार्कर के साथ लाइन चार्ट जोड़ने के लिए:
```java
import com.aspose.slides.*;
// पहली स्लाइड पर पहुँचें
ISlide slide = pres.getSlides().get_Item(0);
// स्लाइड में स्थान (10, 10) पर मार्कर के साथ एक लाइन चार्ट जोड़ें, जिसका आकार (400, 400) हो
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### समाशोधन श्रृंखला और श्रेणियाँ
नये सिरे से शुरुआत करने के लिए:
```java
// एक साफ़ स्लेट सुनिश्चित करने के लिए मौजूदा श्रृंखला और श्रेणियों को साफ़ करें
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// आगे के हेरफेर के लिए चार्ट की डेटा वर्कबुक प्राप्त करें
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### फ़ीचर 2: श्रृंखला और श्रेणियाँ जोड़ना
अपने चार्ट में सार्थक डेटा भरने के लिए श्रृंखला और श्रेणियां जोड़ना महत्वपूर्ण है।
#### एक नई श्रृंखला बनाना
"श्रृंखला 1" नामक नई श्रृंखला जोड़ने के लिए:
```java
// चार्ट में नई श्रृंखला जोड़ें
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// डेटा जनसंख्या के लिए पहली श्रृंखला तक पहुंचें
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### श्रेणियाँ और डेटा बिंदु भरना
श्रेणियाँ और संबंधित डेटा बिंदु जोड़ने के लिए:
```java
// श्रेणी नाम और उनके संबंधित डेटा बिंदु जोड़ें
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// शून्य डेटा बिंदुओं को सुंदर ढंग से संभालना
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### फ़ीचर 3: दूसरी श्रृंखला जोड़ना और डेटा पॉइंट भरना
अतिरिक्त श्रृंखला जोड़ने से आपके चार्ट को अधिक गहराई मिलती है।
#### दूसरी श्रृंखला बनाना और उसमें सामग्री भरना
"श्रृंखला 2" जोड़ने के लिए:
```java
// 'सीरीज 2' नाम से एक और सीरीज जोड़ें
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// डेटा जनसंख्या के लिए दूसरी श्रृंखला तक पहुंचें
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// 'सीरीज 2' के लिए डेटा बिंदु जोड़ें
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### फ़ीचर 4: चार्ट लेजेंड कॉन्फ़िगर करना
लेजेंड को कॉन्फ़िगर करने से चार्ट की पठनीयता बढ़ जाती है.
#### लीजेंड सेटिंग्स समायोजित करना
कॉन्फिगर करना:
```java
// लीजेंड को सक्षम करें और इसे डेटा बिंदुओं पर ओवरले न करने के लिए सेट करें
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### फ़ीचर 5: प्रेजेंटेशन को सहेजना
जब आपका चार्ट तैयार हो जाए, तो प्रस्तुति को फ़ाइल में सेव कर लें।
```java
try {
    // संशोधित प्रस्तुति को निर्दिष्ट निर्देशिका में सहेजें
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## व्यावहारिक अनुप्रयोगों
1. **व्यवसाय रिपोर्टिंग:**
   - समय के साथ रुझान दर्शाने के लिए वित्तीय रिपोर्टों में चार्ट का उपयोग करें।
2. **डेटा विश्लेषण:**
   - विश्लेषण चरणों के दौरान डेटा पैटर्न और सहसंबंधों को दृश्यमान करें।
3. **शिक्षण सामग्री:**
   - शैक्षणिक व्याख्यानों या प्रस्तुतियों के लिए सूचनात्मक स्लाइड बनाएं।
4. **परियोजना प्रबंधन:**
   - दृश्य चार्ट तत्वों के साथ परियोजना समयसीमा को बढ़ाएँ।
5. **विपणन प्रस्तुतियाँ:**
   - चार्ट का उपयोग करके बिक्री के रुझान और अभियान परिणामों को प्रभावी ढंग से प्रदर्शित करें।
## निष्कर्ष
आपने सीखा है कि Aspose.Slides का उपयोग करके जावा में मार्करों के साथ लाइन चार्ट कैसे बनाएं, श्रृंखला और श्रेणियां कैसे जोड़ें, किंवदंतियों को कॉन्फ़िगर करें और प्रस्तुतियाँ कैसे सहेजें। ये कौशल विभिन्न व्यावसायिक अनुप्रयोगों में गतिशील दृश्य सामग्री बनाने के लिए मूल्यवान हैं।
Aspose.Slides सुविधाओं के बारे में अधिक जानने या समुदाय का समर्थन प्राप्त करने के लिए, उनके पर जाएँ [आधिकारिक दस्तावेज](https://docs.aspose.com/slides/java/) या स्टैक ओवरफ्लो जैसे फोरम से जुड़ें।
हैप्पी कोडिंग!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}