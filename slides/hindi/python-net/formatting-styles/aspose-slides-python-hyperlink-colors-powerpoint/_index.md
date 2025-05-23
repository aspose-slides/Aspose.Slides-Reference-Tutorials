---
"date": "2025-04-23"
"description": "Aspose.Slides for Python का उपयोग करके PowerPoint प्रस्तुतियों में हाइपरलिंक रंगों को अनुकूलित करना सीखें। वैयक्तिकृत लिंक शैलियों के साथ अपनी स्लाइड्स को कुशलतापूर्वक बेहतर बनाएँ।"
"title": "पायथन के लिए Aspose.Slides का उपयोग करके PowerPoint में हाइपरलिंक रंग कैसे सेट करें"
"url": "/hi/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# पायथन के लिए Aspose.Slides का उपयोग करके PowerPoint में हाइपरलिंक रंग कैसे सेट करें

## परिचय

Aspose.Slides for Python के साथ हाइपरलिंक रंगों को अनुकूलित करके अपने PowerPoint प्रस्तुतियों की दृश्य अपील को बढ़ाना बहुत आसान है। यह मार्गदर्शिका आपको Python का उपयोग करके अपनी स्लाइड में विशिष्ट रंगों के साथ हाइपरलिंक सेट करने के बारे में बताएगी।

**आप क्या सीखेंगे:**
- पावरपॉइंट में टेक्स्ट आकृतियों के भीतर हाइपरलिंक रंग कैसे सेट करें।
- एक आकर्षक प्रस्तुति बनाने में शामिल चरण।
- पायथन के लिए Aspose.Slides की प्रमुख विशेषताएं जो इस अनुकूलन को सुविधाजनक बनाती हैं।

आइये शुरू करने से पहले आवश्यक पूर्वापेक्षाओं पर नजर डालें।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपका वातावरण निम्नलिखित के साथ तैयार है:
- **पुस्तकालय और संस्करण:** स्थापित करना `aspose.slides` सुनिश्चित करें कि आपके मशीन पर पायथन स्थापित है।
- **पर्यावरण सेटअप आवश्यकताएँ:** यह ट्यूटोरियल विंडोज़, मैक या लिनक्स पर पायथन के बुनियादी सेटअप को मानता है।
- **ज्ञान पूर्वापेक्षाएँ:** पायथन प्रोग्रामिंग से परिचित होना लाभदायक होगा।

## पायथन के लिए Aspose.Slides सेट अप करना

पायथन के लिए Aspose.Slides का उपयोग शुरू करने के लिए, pip के माध्यम से पैकेज स्थापित करें:

```bash
pip install aspose.slides
```

**लाइसेंस प्राप्ति चरण:**
- **मुफ्त परीक्षण:** यहां से परीक्षण संस्करण डाउनलोड करें [एस्पोज का रिलीज़ पेज](https://releases.aspose.com/slides/python-net/).
- **अस्थायी लाइसेंस:** अस्थायी लाइसेंस का अनुरोध करें [खरीद पृष्ठ](https://purchase.aspose.com/temporary-license/) विस्तारित पहुंच के लिए.
- **खरीदना:** बिना किसी सीमा के सुविधाओं को पूरी तरह से अनलॉक करने के लिए, लाइसेंस खरीदने पर विचार करें [Aspose का खरीद पृष्ठ](https://purchase.aspose.com/buy).

**बुनियादी आरंभीकरण:**
एक बार इंस्टॉल और लाइसेंस प्राप्त होने के बाद, अपनी स्क्रिप्ट में Aspose.Slides आयात करें:

```python
import aspose.slides as slides
```

## कार्यान्वयन मार्गदर्शिका

यह अनुभाग आपको पावरपॉइंट प्रस्तुति में हाइपरलिंक रंग सेट करने के बारे में मार्गदर्शन करता है।

### हाइपरलिंक रंग सुविधा सेट करें

#### अवलोकन

पायथन के लिए Aspose.Slides का उपयोग करके टेक्स्ट आकृतियों में एम्बेड किए गए हाइपरलिंक्स के रंग को कस्टमाइज़ करें। यह पठनीयता और दृश्य अपील को बढ़ाता है।

##### चरण 1: एक नई प्रस्तुति बनाएँ

किसी प्रस्तुति का उदाहरण बनाएँ:

```python
with slides.Presentation() as presentation:
    # आपका कोड यहाँ
```

##### चरण 2: टेक्स्ट के साथ आकृति जोड़ें

पहली स्लाइड में एक आयताकार आकृति जोड़ें और हाइपरलिंक सहित पाठ सम्मिलित करें।

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### चरण 3: हाइपरलिंक गुण सेट करें

हाइपरलिंक निर्दिष्ट करें और उसका रंग सेट करें. `hyperlink_click` प्रॉपर्टी निर्दिष्ट करती है कि क्लिक करने पर लिंक को कहां नेविगेट करना चाहिए।

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# हाइपरलिंक के लिए रंग स्रोत को भाग प्रारूप पर सेट करें तथा भरण प्रकार और रंग निर्धारित करें।
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### चरण 4: प्रस्तुति सहेजें

अपनी प्रस्तुति को निर्दिष्ट निर्देशिका में सहेजें:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}