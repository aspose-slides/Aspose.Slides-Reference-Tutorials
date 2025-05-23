---
"date": "2025-04-23"
"description": "Aspose.Slides for Python के साथ PowerPoint में आयताकार आकृतियों को स्वचालित रूप से बनाना और फ़ॉर्मेट करना सीखें। अपने प्रेजेंटेशन कौशल को सहजता से बढ़ाएँ।"
"title": "पायथन के लिए Aspose.Slides का उपयोग करके PowerPoint में आयत आकृतियों को स्वचालित करें"
"url": "/hi/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# पायथन के लिए Aspose.Slides का उपयोग करके PowerPoint में एक आयत आकार कैसे बनाएं और प्रारूपित करें
## परिचय
क्या आपने कभी अपने PowerPoint प्रेजेंटेशन में कस्टम शेप को जल्दी से जोड़ने की ज़रूरत महसूस की है, लेकिन ऑटोमेशन की कमी से जूझ रहे हैं? अगर आप स्लाइड दर स्लाइड आयतों को मैन्युअल रूप से फ़ॉर्मेट करने से थक गए हैं, तो यह ट्यूटोरियल आपकी मदद करेगा। "Aspose.Slides for Python" का लाभ उठाते हुए, हम कोड की कुछ ही पंक्तियों में आयताकार आकार को जोड़ने और स्टाइल करने को स्वचालित कर देंगे। इस गाइड के अंत तक, आप निम्न में महारत हासिल कर लेंगे:
- प्रोग्रामेटिक रूप से आयताकार आकार बनाना
- रंग और रेखा शैली जैसे स्वरूपण विकल्प लागू करना
- अपनी प्रस्तुति को आसानी से सहेजना
आइये जानें कि आप अपनी स्लाइड निर्माण प्रक्रिया को कैसे बदल सकते हैं!
### आवश्यक शर्तें
कोडिंग शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित चीजें तैयार हैं:
- **पायथन** आपकी मशीन पर स्थापित (संस्करण 3.6 या उच्चतर अनुशंसित है)
- **पायथन के लिए Aspose.Slides** लाइब्रेरी, जो हमें पावरपॉइंट प्रस्तुतियों में हेरफेर करने की अनुमति देती है
- पायथन प्रोग्रामिंग अवधारणाओं की बुनियादी समझ और पाइप का उपयोग करके पैकेज स्थापित करने से परिचित होना
## पायथन के लिए Aspose.Slides सेट अप करना
### इंस्टालेशन
Aspose.Slides पैकेज स्थापित करने के लिए, अपना टर्मिनल या कमांड प्रॉम्प्ट खोलें और चलाएँ:
```bash
pip install aspose.slides
```
यह कमांड PyPI से Python के लिए Aspose.Slides का नवीनतम संस्करण लाता है और स्थापित करता है।
### लाइसेंस अधिग्रहण
Aspose.Slides एक व्यावसायिक उत्पाद है, लेकिन आप इसे निःशुल्क परीक्षण लाइसेंस का उपयोग करके शुरू कर सकते हैं। इसे प्राप्त करने का तरीका यहां बताया गया है:
1. **मुफ्त परीक्षण:** मिलने जाना [Aspose निःशुल्क परीक्षण](https://releases.aspose.com/slides/python-net/) और मूल्यांकन के लिए साइन अप करें।
2. **अस्थायी लाइसेंस:** बिना किसी सीमा के अधिक व्यापक परीक्षण के लिए, अस्थायी लाइसेंस का अनुरोध करें [अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/).
3. **खरीदना:** जब आप लाइव होने के लिए तैयार हों, तो के माध्यम से लाइसेंस खरीदें [Aspose खरीद पृष्ठ](https://purchase.aspose.com/buy).
एक बार लाइसेंस प्राप्त हो जाने पर, अपने प्रोजेक्ट में लाइसेंस लागू करने के लिए दस्तावेज़ों का पालन करें।
### मूल आरंभीकरण
यहां बताया गया है कि आप पायथन के लिए Aspose.Slides को कैसे आरंभ कर सकते हैं:
```python
import aspose.slides as slides
\# प्रस्तुतिकरण वर्ग आरंभ करें
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
यह स्निपेट एक नई प्रस्तुति तैयार करता है और पुष्टि करता है कि यह संशोधित करने के लिए तैयार है।
## कार्यान्वयन मार्गदर्शिका
### आयताकार आकार बनाना
#### अवलोकन
इस अनुभाग में, हम Python के लिए Aspose.Slides का उपयोग करके PowerPoint स्लाइड में एक आयताकार आकार जोड़ने पर ध्यान केंद्रित करेंगे।
#### आकृति बनाने के चरण
1. **प्रस्तुति खोलें या बनाएँ:**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # हम यहाँ अपना आयत जोड़ेंगे
   ```
2. **स्लाइड तक पहुंचें:**
   वह पहली स्लाइड पुनः प्राप्त करें जहां हम आकृति जोड़ना चाहते हैं।
   ```python
   slide = pres.slides[0]
   ```
3. **आयताकार आकार जोड़ें:**
   उपयोग `add_auto_shape` स्लाइड पर एक आयत बनाने की विधि.
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - पैरामीटर: `ShapeType.RECTANGLE`, x-स्थिति (50), y-स्थिति (150), चौड़ाई (150), ऊंचाई (50)।
### आयत को प्रारूपित करना
#### अवलोकन
इसके बाद, हम अपने आयत आकार पर भरण रंग और रेखा शैली सहित स्वरूपण लागू करेंगे।
#### फ़ॉर्मेटिंग के लिए चरण
1. **रंग भरना:**
   आयत की पृष्ठभूमि के लिए एक विशिष्ट रंग के साथ एक ठोस भरण सेट करें।
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **रेखा शैली:**
   आयत की रेखा को उसके रंग और चौड़ाई सहित अनुकूलित करें।
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **प्रस्तुति सहेजें:**
   अंत में, प्रस्तुति को फ़ाइल में सहेजें.
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}