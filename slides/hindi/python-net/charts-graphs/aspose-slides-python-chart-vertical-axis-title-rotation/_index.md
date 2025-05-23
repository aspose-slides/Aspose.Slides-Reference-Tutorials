---
"date": "2025-04-23"
"description": "पायथन के लिए Aspose.Slides का उपयोग करके प्रस्तुतियों में चार्ट शीर्षकों के रोटेशन कोण को समायोजित करना सीखें, जिससे पठनीयता और सौंदर्यबोध में वृद्धि हो।"
"title": "पायथन के लिए Aspose.Slides में चार्ट के वर्टिकल एक्सिस शीर्षक रोटेशन को कैसे सेट करें"
"url": "/hi/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# पायथन के लिए Aspose.Slides में चार्ट के वर्टिकल एक्सिस शीर्षक रोटेशन को कैसे सेट करें

## परिचय

डेटा प्रस्तुतियों में, चार्ट पठनीयता में सुधार करना महत्वपूर्ण है। Aspose.Slides for Python का उपयोग करके अपने चार्ट के ऊर्ध्वाधर अक्ष शीर्षक के रोटेशन कोण को समायोजित करने से शीर्षक आपकी स्लाइड में अच्छी तरह से फिट हो सकते हैं या अलग दिख सकते हैं। यह ट्यूटोरियल आपको कार्यक्षमता और दृश्य अपील दोनों को बढ़ाने के लिए इस रोटेशन कोण को सेट करने के माध्यम से मार्गदर्शन करता है।

**आप क्या सीखेंगे:**
- पायथन के लिए Aspose.Slides को कैसे स्थापित और कॉन्फ़िगर करें।
- अपनी स्लाइडों में चार्ट जोड़ने और अनुकूलित करने के चरण.
- चार्ट शीर्षकों का घूर्णन कोण निर्धारित करने की तकनीकें।
- डेटा विज़ुअलाइज़ेशन में इन सुविधाओं के लिए वास्तविक दुनिया अनुप्रयोग।

आइए कार्यान्वयन में उतरने से पहले आवश्यक शर्तों पर चर्चा कर लें।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास:
- **पायथन पर्यावरण**: पायथन 3.x को यहां से स्थापित करें [python.org](https://www.python.org/).
- **Aspose.Slides लाइब्रेरी**: प्रस्तुतियों को प्रभावी ढंग से संचालित करने के लिए पाइप के माध्यम से इंस्टॉल करें।
- **पायथन प्रोग्रामिंग का बुनियादी ज्ञान**पायथन सिंटैक्स और फ़ाइल ऑपरेशन से परिचित होने से आपको आगे बढ़ने में मदद मिलेगी।

## पायथन के लिए Aspose.Slides सेट अप करना

Aspose.Slides का उपयोग करने के लिए, इसे pip का उपयोग करके इंस्टॉल करें। अपना टर्मिनल या कमांड प्रॉम्प्ट खोलें और चलाएँ:

```bash
pip install aspose.slides
```

### लाइसेंस प्राप्ति चरण

Aspose विभिन्न लाइसेंस विकल्प प्रदान करता है:
- **मुफ्त परीक्षण**: यहां से परीक्षण संस्करण डाउनलोड करें [एस्पोज का रिलीज़ पेज](https://releases.aspose.com/slides/python-net/).
- **अस्थायी लाइसेंस**: के माध्यम से विस्तारित सुविधाओं के लिए एक अस्थायी लाइसेंस प्राप्त करें [खरीद पोर्टल](https://purchase.aspose.com/temporary-license/).
- **खरीदना**यदि आपको यह उपकरण अपरिहार्य लगता है तो इसे खरीदने पर विचार करें, यह उपलब्ध है [Aspose खरीद पृष्ठ](https://purchase.aspose.com/buy).

#### बुनियादी आरंभीकरण और सेटअप

अपनी पायथन स्क्रिप्ट में Aspose.Slides को आरंभ करने का तरीका यहां दिया गया है:

```python
import aspose.slides as slides

# एक प्रस्तुति ऑब्जेक्ट बनाएँ
def main():
    with slides.Presentation() as pres:
        # आपका कोड यहां जाएगा
        pass

if __name__ == "__main__":
    main()
```

## कार्यान्वयन मार्गदर्शिका

### चार्ट जोड़ना और अनुकूलित करना

#### अवलोकन

इस अनुभाग में, हम आपकी स्लाइड में एक क्लस्टर कॉलम चार्ट जोड़ेंगे और इसके ऊर्ध्वाधर अक्ष शीर्षक के रोटेशन कोण को सेट करके इसे अनुकूलित करेंगे।

#### चरण:

##### चरण 1: क्लस्टर्ड कॉलम चार्ट जोड़ें

परिभाषित आयामों के साथ विशिष्ट निर्देशांक पर एक चार्ट जोड़कर आरंभ करें:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # स्लाइड 1 में क्लस्टर्ड कॉलम चार्ट जोड़ें
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### चरण 2: वर्टिकल अक्ष शीर्षक कॉन्फ़िगर करें

ऊर्ध्वाधर अक्ष शीर्षक के लिए घूर्णन कोण सक्षम और सेट करें:

```python
def configure_chart(chart):
    # ऊर्ध्वाधर अक्ष शीर्षक सक्षम करें
    chart.axes.vertical_axis.has_title = True
    
    # घूर्णन कोण को 90 डिग्री पर सेट करें
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### चरण 3: अपनी प्रस्तुति सहेजें

अंत में, अपने प्रस्तुतीकरण को परिवर्तनों के साथ सहेजें:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # प्रस्तुति सहेजें
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}