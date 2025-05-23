---
"date": "2025-04-24"
"description": "जानें कि Aspose.Slides for Python के साथ PowerPoint में कस्टम क्रमांकित बुलेट सूचियाँ कैसे बनाएँ। अद्वितीय फ़ॉर्मेटिंग के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।"
"title": "पायथन के लिए Aspose.Slides का उपयोग करके PowerPoint में कस्टम क्रमांकित बुलेट सूचियाँ"
"url": "/hi/python-net/shapes-text/custom-numbered-bullets-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# पायथन के लिए Aspose.Slides का उपयोग करके PowerPoint में कस्टम क्रमांकित बुलेट सूचियाँ

## परिचय
क्या आप अपने पावरपॉइंट प्रेजेंटेशन की विज़ुअल अपील को डिफ़ॉल्ट बुलेट पॉइंट से आगे बढ़ाना चाहते हैं? चाहे वह कॉर्पोरेट रिपोर्ट, अकादमिक व्याख्यान या व्यावसायिक मीटिंग के लिए हो, बुलेट लिस्ट को कस्टमाइज़ करने से आपके दर्शकों का ध्यान अधिक प्रभावी ढंग से आकर्षित और बनाए रखा जा सकता है। **पायथन के लिए Aspose.Slides**, आपके पास अपनी विशिष्ट स्वरूपण आवश्यकताओं के अनुसार क्रमांकित बुलेट्स को तैयार करने की सुविधा है।

इस विस्तृत गाइड में, हम दिखाएंगे कि पायथन के साथ पावरपॉइंट में Aspose.Slides का उपयोग करके कस्टम क्रमांकित बुलेट कैसे सेट करें। अपनी प्रस्तुतियों में इस सुविधा को एकीकृत करके, आप एक पेशेवर और पॉलिश लुक प्राप्त कर सकते हैं।

**आप क्या सीखेंगे:**
- पायथन के लिए Aspose.Slides सेट अप करना
- कस्टम क्रमांकित बुलेट सूचियाँ बनाना
- बुलेट सेटिंग को प्रोग्रामेटिक रूप से कॉन्फ़िगर करना
- प्रदर्शन को अनुकूलित करना और सामान्य समस्याओं का निवारण करना

चलिए शुरू करते हैं! सुनिश्चित करें कि आपके पास आगे बढ़ने के लिए सब कुछ तैयार है।

## आवश्यक शर्तें
पायथन के लिए Aspose.Slides के साथ कस्टम क्रमांकित बुलेट्स को लागू करने से पहले, सुनिश्चित करें कि आपके पास ये हैं:

### आवश्यक पुस्तकालय:
- **पायथन के लिए Aspose.Slides**: पावरपॉइंट प्रस्तुतियों को बनाने और उनमें हेरफेर करने के लिए एक मजबूत लाइब्रेरी।

### पर्यावरण सेटअप:
- आपके सिस्टम पर पायथन 3.x स्थापित है।
- पायथन प्रोग्रामिंग अवधारणाओं की बुनियादी समझ उपयोगी है लेकिन अनिवार्य नहीं है।

## पायथन के लिए Aspose.Slides सेट अप करना
आरंभ करने के लिए, स्थापित करें `aspose.slides` पाइप का उपयोग कर लाइब्रेरी:

```bash
pip install aspose.slides
```

### लाइसेंस प्राप्ति:
Aspose.Slides एक व्यावसायिक उत्पाद है जो अपनी क्षमताओं के परीक्षण के लिए निःशुल्क परीक्षण प्रदान करता है। आप एक अस्थायी लाइसेंस प्राप्त कर सकते हैं या निरंतर उपयोग के लिए एक खरीद सकते हैं।

- **मुफ्त परीक्षण**: बिना किसी सीमा के बुनियादी कार्यक्षमता तक पहुंच।
- **अस्थायी लाइसेंस**: अस्थायी रूप से पूर्ण पहुँच प्राप्त करने के लिए Aspose वेबसाइट पर अनुरोध करें।
- **खरीदना**दीर्घकालिक परियोजनाओं के लिए लाइसेंस खरीदने पर विचार करें।

### बुनियादी आरंभीकरण:
एक बार इंस्टॉल हो जाने पर, अपनी प्रस्तुति को निम्न प्रकार आरंभ करें:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # आपका कोड यहाँ...
```

यह सेटअप आपके पावरपॉइंट स्लाइडों में कस्टम क्रमांकित बुलेट्स जोड़ने के लिए वातावरण तैयार करता है।

## कार्यान्वयन मार्गदर्शिका
आइए कस्टम क्रमांकित बुलेट सूचियाँ बनाने की प्रक्रिया शुरू करें। स्पष्टता और कार्यान्वयन में आसानी के लिए प्रत्येक चरण को विभाजित किया गया है।

### टेक्स्ट फ़्रेम के साथ आयताकार आकार जोड़ना
#### अवलोकन:
सबसे पहले, एक आकृति जोड़ें जिसमें बुलेट बिंदुओं के लिए टेक्स्ट फ़्रेम होंगे।

```python
# पहली स्लाइड में एक आयताकार आकार जोड़ें
shape = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 200, 200, 400, 200)
```
- **पैरामीटर्स की व्याख्या**: द `add_auto_shape` विधि आकार प्रकार (आयत), स्थिति (x और y निर्देशांक), और आयाम (चौड़ाई और ऊंचाई) के लिए पैरामीटर लेती है।

### टेक्स्ट फ़्रेम कॉन्फ़िगर करना
#### अवलोकन:
बुलेट पॉइंट जोड़ने के लिए आयत के टेक्स्ट फ़्रेम तक पहुँचें.

```python
# निर्मित ऑटोशेप के टेक्स्ट फ़्रेम तक पहुँचें
text_frame = shape.text_frame

# यदि कोई डिफ़ॉल्ट मौजूदा पैराग्राफ़ मौजूद हो तो उसे हटा दें
text_frame.paragraphs.clear()
```
- **उद्देश्य**: कस्टम बुलेट पॉइंट जोड़ने से पहले एक साफ़ स्लेट सुनिश्चित करता है।

### कस्टम क्रमांकित बुलेट जोड़ना
#### अवलोकन:
विशिष्ट बुलेट सेटिंग के साथ पैराग्राफ़ जोड़ें:

```python
# कस्टम क्रमांकित बुलेट के साथ पैराग्राफ़ जोड़ें
for start_number, bullet_text in [(2, "bullet 2"), (3, "bullet 3"), (7, "bullet 7")]:
    paragraph = slides.Paragraph()
    paragraph.text = bullet_text
    paragraph.paragraph_format.depth = 4
    paragraph.paragraph_format.bullet.numbered_bullet_start_with = start_number
    paragraph.paragraph_format.bullet.type = slides.BulletType.NUMBERED
    text_frame.paragraphs.add(paragraph)
```
- **विन्यास**प्रत्येक पैराग्राफ एक विशिष्ट संख्या से शुरू होता है, जिससे प्रस्तुति स्वरूपण पर लचीलापन और नियंत्रण मिलता है।

### प्रस्तुति को सहेजना
अंत में, अपनी कॉन्फ़िगर की गई प्रस्तुति को सहेजें:

```python
# प्रस्तुति सहेजें\presentation.save("YOUR_OUTPUT_DIRECTORY/text_set_custom_bullets_number_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}