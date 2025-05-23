---
"date": "2025-04-23"
"description": "जानें कि Python और Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों को उच्च-गुणवत्ता वाली TIFF छवियों में कैसे परिवर्तित करें। आयाम अनुकूलित करें, गुणवत्ता अनुकूलित करें और टिप्पणियाँ प्रबंधित करें।"
"title": "Aspose.Slides का उपयोग करके Python में कस्टम आयामों के साथ PowerPoint को TIFF में बदलें"
"url": "/hi/python-net/presentation-management/convert-powerpoint-to-tiff-custom-size-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# पायथन के लिए Aspose.Slides का उपयोग करके कस्टम आयामों के साथ पावरपॉइंट प्रस्तुतियों को TIFF में परिवर्तित करें

PowerPoint प्रस्तुतियों को उच्च-रिज़ॉल्यूशन TIFF छवियों में परिवर्तित करना साझा करने, संग्रहीत करने और मुद्रण उद्देश्यों के लिए आवश्यक है। यह ट्यूटोरियल आपको कस्टम आयामों के साथ अपनी प्रस्तुतियों को TIFF प्रारूप में बदलने के लिए Aspose.Slides for Python का उपयोग करने के बारे में मार्गदर्शन करता है। आप सीखेंगे कि छवि गुणवत्ता को कैसे प्रबंधित करें, लेआउट नोट्स और टिप्पणियाँ शामिल करें, और रूपांतरण प्रदर्शन को अनुकूलित करें।

## आप क्या सीखेंगे:
- पायथन के लिए Aspose.Slides को स्थापित और सेट करना
- पावरपॉइंट स्लाइड्स को अनुकूलित आयामों के साथ TIFF छवियों में परिवर्तित करना
- नोट्स और टिप्पणियाँ शामिल करने के लिए विकल्प कॉन्फ़िगर करना
- अपनी रूपांतरण प्रक्रिया को अनुकूलित करने के लिए सर्वोत्तम अभ्यास लागू करना

आइये, पूर्वापेक्षाओं की समीक्षा से शुरुआत करें!

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### आवश्यक लाइब्रेरी और निर्भरताएँ:
- **पायथन के लिए Aspose.Slides**: यह लाइब्रेरी पावरपॉइंट फ़ाइलों को संभालने के लिए आवश्यक है।
- **पायथन पर्यावरण**: पायथन 3.6 या बाद के संस्करण के साथ संगतता सुनिश्चित करें।
- **पीआईपी पैकेज मैनेजर**: Aspose.Slides को स्थापित करने के लिए उपयोग किया जाता है।

### स्थापना आवश्यकताएं:
- पायथन प्रोग्रामिंग और फ़ाइल हैंडलिंग से बुनियादी परिचितता।
- पायथन स्क्रिप्ट, जैसे VSCode या PyCharm, को चलाने के लिए स्थापित एक विकास वातावरण।

## पायथन के लिए Aspose.Slides सेट अप करना

पावरपॉइंट प्रस्तुतियों को TIFF प्रारूप में परिवर्तित करने के लिए, पहले Aspose.Slides लाइब्रेरी स्थापित करें:

### पाइप स्थापना:
```bash
pip install aspose.slides
```

#### लाइसेंस प्राप्ति:
- **मुफ्त परीक्षण**: यहां से निःशुल्क परीक्षण डाउनलोड करके प्रारंभ करें [एस्पोज का रिलीज़ पेज](https://releases.aspose.com/slides/python-net/).
- **अस्थायी लाइसेंस**: अधिक सुविधाएँ अनलॉक करने के लिए विस्तारित लाइसेंस के लिए आवेदन करें [यहाँ](https://purchase.aspose.com/temporary-license/).
- **खरीदना**: पूर्ण क्षमताओं को अनलॉक करने के लिए, सदस्यता खरीदने पर विचार करें [Aspose की खरीद साइट](https://purchase.aspose.com/buy).

#### बुनियादी आरंभीकरण:
एक बार इंस्टॉल हो जाने पर, आप निम्नलिखित सेटअप के साथ Aspose.Slides को प्रारंभ कर सकते हैं:
```python
import aspose.slides as slides

# प्रस्तुति फ़ाइल के आरंभीकरण और लोडिंग का उदाहरण\स्लाइड्स के साथ.Presentation("path/to/presentation.pptx") वर्तमान के रूप में:
    print("Presentation loaded successfully!")
```

## कार्यान्वयन मार्गदर्शिका

अब, आइए पावरपॉइंट प्रस्तुतियों को कस्टम आयामों के साथ TIFF छवियों में परिवर्तित करने का तरीका जानें।

### कस्टम आयामों के साथ पावरपॉइंट प्रेजेंटेशन को TIFF में बदलें

यह अनुभाग आयाम और संपीड़न प्रकार निर्दिष्ट करते हुए एक प्रस्तुति को TIFF छवि में परिवर्तित करने के कार्यान्वयन को कवर करता है।

#### अपना प्रेजेंटेशन लोड करें
Aspose.Slides का उपयोग करके अपनी PowerPoint फ़ाइल लोड करके प्रारंभ करें:
```python
import aspose.slides as slides

def convert_to_tiff_custom_size():
    # अपना दस्तावेज़ निर्देशिका पथ निर्दिष्ट करें
    with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/welcome-to-powerpoint.pptx") as pres:
        # रूपांतरण सेटिंग के लिए TiffOptions आरंभ करें
```

#### TIFF विकल्प कॉन्फ़िगर करें
संपीड़न प्रकार, लेआउट विकल्प, DPI और कस्टम छवि आकार सेट करें:
```python
tiff_options = slides.export.TiffOptions()
        
        # डिफ़ॉल्ट LZW संपीड़न प्रकार सेट करें
        tiff_options.compression_type = slides.export.TiffCompressionTypes.DEFAULT
        
        # नोट्स और टिप्पणियों का लेआउट कॉन्फ़िगर करें
        slides_layout_options = slides.export.NotesCommentsLayoutingOptions()
        slides_layout_options.notes_position = slides.export.NotesPositions.BOTTOM_FULL
        tiff_options.slides_layout_options = slides_layout_options
        
        # छवि गुणवत्ता के लिए कस्टम DPI परिभाषित करें
        tiff_options.dpi_x = 200
        tiff_options.dpi_y = 100
        
        # TIFF छवियों के लिए वांछित आउटपुट आकार सेट करें
        tiff_options.image_size = drawing.Size(1728, 1078)
```

#### परिवर्तित TIFF फ़ाइल को सहेजें
अंत में, अपनी प्रस्तुति को TIFF फ़ाइल के रूप में सहेजें:
```python
        # आउटपुट निर्देशिका और फ़ाइल नाम निर्दिष्ट करें
        pres.save("YOUR_OUTPUT_DIRECTORY/convert_to_tiff_custom_size_out.tiff\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}