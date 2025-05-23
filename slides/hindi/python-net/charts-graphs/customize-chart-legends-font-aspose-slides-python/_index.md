---
"date": "2025-04-22"
"description": "पायथन के लिए Aspose.Slides का उपयोग करके चार्ट लेजेंड फ़ॉन्ट गुणों को अनुकूलित करना सीखें। अलग-अलग लेजेंड प्रविष्टियों के लिए बोल्ड, इटैलिक और रंगीन फ़ॉन्ट के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।"
"title": "पायथन के लिए Aspose.Slides का उपयोग करके चार्ट लीजेंड फ़ॉन्ट को अनुकूलित करें एक व्यापक गाइड"
"url": "/hi/python-net/charts-graphs/customize-chart-legends-font-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# पायथन के लिए Aspose.Slides का उपयोग करके प्रस्तुतियों में चार्ट लीजेंड फ़ॉन्ट को अनुकूलित करना

## परिचय
दृश्य रूप से आकर्षक प्रस्तुतियाँ बनाना आवश्यक है, खासकर जब चार्ट के माध्यम से डेटा प्रदर्शित किया जाता है। एक आम चुनौती चार्ट लेजेंड को अपनी प्रस्तुति शैली या ब्रांडिंग आवश्यकताओं के साथ संरेखित करने के लिए अनुकूलित करना है। यह मार्गदर्शिका दर्शाती है कि पायथन के लिए Aspose.Slides का उपयोग करके चार्ट में अलग-अलग लेजेंड प्रविष्टियों के लिए बोल्डनेस, इटैलिक्स, आकार और रंग जैसे फ़ॉन्ट गुणों को कैसे अनुकूलित किया जाए।

**आप क्या सीखेंगे:**
- पायथन के लिए Aspose.Slides को सेट अप करना और उसका उपयोग करना
- चार्ट लेजेंड के फ़ॉन्ट गुणों को अनुकूलित करना
- बोल्ड, इटैलिक जैसी विशिष्ट फ़ॉन्ट शैलियाँ लागू करना और रंग बदलना
- कस्टम फ़ॉन्ट के साथ चार्ट को बेहतर बनाने के व्यावहारिक उदाहरण

आइए देखें कि आप यह अनुकूलन कैसे प्राप्त कर सकते हैं।

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- **पुस्तकालय**: पायथन के लिए Aspose.Slides. इसे pip का उपयोग करके स्थापित करें।
- **पर्यावरण**: आपके मशीन पर स्थापित एक पायथन वातावरण (अधिमानतः पायथन 3.x)।
- **ज्ञान**पायथन प्रोग्रामिंग की बुनियादी समझ और प्रस्तुतियों को प्रोग्रामेटिक रूप से संभालने की जानकारी।

## पायथन के लिए Aspose.Slides सेट अप करना
### इंस्टालेशन
आरंभ करने के लिए, अपने टर्मिनल में निम्नलिखित कमांड चलाकर Aspose.Slides लाइब्रेरी स्थापित करें:

```bash
pip install aspose.slides
```

### लाइसेंस अधिग्रहण
Aspose.Slides एक वाणिज्यिक उत्पाद है जिसमें विभिन्न लाइसेंसिंग विकल्प हैं:
- **मुफ्त परीक्षण**: पूर्ण कार्यक्षमता के लिए अस्थायी लाइसेंस प्राप्त करें।
- **अस्थायी लाइसेंस**: बिना किसी सीमा के सभी सुविधाओं का परीक्षण करने के लिए अस्थायी लाइसेंस के लिए आवेदन करें।
- **खरीदना**अपनी आवश्यकताओं के आधार पर सदस्यता या स्थायी लाइसेंस खरीदें।

### मूल आरंभीकरण
यहां बताया गया है कि आप अपनी पायथन स्क्रिप्ट में Aspose.Slides को कैसे आरंभ और सेट अप कर सकते हैं:

```python
import aspose.slides as slides

# एक प्रस्तुति उदाहरण आरंभ करें\स्लाइड्स.प्रेजेंटेशन() के साथ इस प्रकार:
    # आपका कोड यहाँ
```

## कार्यान्वयन मार्गदर्शिका
इस अनुभाग में, हम व्यक्तिगत लेजेंड प्रविष्टियों के फ़ॉन्ट गुणों को अनुकूलित करने के बारे में जानेंगे।

### चार्ट जोड़ना और उस तक पहुँचना
सबसे पहले, आइए अपनी स्लाइड में एक क्लस्टर कॉलम चार्ट जोड़ें:

```python
# स्थिति (50, 50) पर 600 चौड़ाई और 400 ऊँचाई वाला एक क्लस्टर कॉलम चार्ट जोड़ें
class ShapeCollection:
    def __init__(self):
        self.chart = None

    def add_chart(self, chart_type, x, y, width, height):
        # यह वास्तविक Aspose.Slides विधि के लिए एक प्लेसहोल्डर मात्र है।
        return "ChartObject"

class SlideCollection:
    def __init__(self):
        self.shapes = ShapeCollection()

# pres.slides[0].shapes का अनुकरण
slide_shapes = SlideCollection()
chart = slide_shapes.shapes.add_chart(slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 600, 400)
```

### लेजेंड फ़ॉन्ट गुण अनुकूलित करना
#### लीजेंड प्रविष्टि के पाठ प्रारूप तक पहुँचना
किसी विशिष्ट लेजेंड प्रविष्टि के फ़ॉन्ट गुण संशोधित करने के लिए:

```python
class Chart:
    def __init__(self):
        self.legend = "LegendObject"

# चार्ट.लेजेंड.प्रविष्टियाँ[1].text_format का अनुकरण
chart_object = Chart()
tf = "SimulatedTextFormatObject"
```

#### फ़ॉन्ट गुण सेट करना
यहां, हम बोल्डनेस, आकार, इटैलिक्स और रंग जैसे पहलुओं को अनुकूलित करते हैं:

```python
class TextFormat:
    def __init__(self):
        self.portion_format = PortionFormat()

class PortionFormat:
    def __init__(self):
        self.font_bold = False
        self.font_height = 0
        self.font_italic = False
        self.fill_format = FillFormat()

class FillFormat:
    def __init__(self):
        self.fill_type = "None"
        self.solid_fill_color = SolidFillColor()

class SolidFillColor:
    def __init__(self):
        self.color = None

class Color:
    blue = 'blue'

tf.portion_format.font_bold = True
# फ़ॉन्ट आकार 20 पॉइंट पर सेट करें
tf.portion_format.font_height = 20  
tf.portion_format.font_italic = True

# ठोस भरण प्रकार का उपयोग करके फ़ॉन्ट का रंग नीला सेट करें
tf.portion_format.fill_format.fill_type = "SOLID"
tf.portion_format.fill_format.solid_fill_color.color = Color.blue
```

### प्रस्तुति को सहेजना
अंत में, अपनी प्रस्तुति को इन अनुकूलनों के साथ सहेजें:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_individual_legend_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}