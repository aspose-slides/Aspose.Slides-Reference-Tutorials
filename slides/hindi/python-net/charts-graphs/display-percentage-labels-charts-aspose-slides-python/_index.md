---
"date": "2025-04-22"
"description": "जानें कि पायथन के लिए Aspose.Slides का उपयोग करके PowerPoint प्रस्तुतियों में चार्ट पर प्रतिशत लेबल को आसानी से कैसे प्रदर्शित किया जाए। डेटा विज़ुअलाइज़ेशन को बढ़ाने के लिए बिल्कुल सही।"
"title": "पायथन के लिए Aspose.Slides का उपयोग करके चार्ट पर प्रतिशत लेबल कैसे प्रदर्शित करें - एक व्यापक गाइड"
"url": "/hi/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# पायथन के लिए Aspose.Slides का उपयोग करके चार्ट पर प्रतिशत लेबल कैसे प्रदर्शित करें

## परिचय

प्रस्तुतियों और रिपोर्टों में डेटा को प्रभावी ढंग से विज़ुअलाइज़ करना महत्वपूर्ण है, खासकर जब आप अनुपात या वितरण को स्पष्ट रूप से हाइलाइट करना चाहते हैं। लेकिन क्या होगा अगर आपको उन प्रतिशतों को सीधे अपने चार्ट पर प्रदर्शित करने की आवश्यकता है? यह व्यापक गाइड आपको इसका उपयोग करने में मार्गदर्शन करेगी **पायथन के लिए Aspose.Slides** प्रतिशत मानों को चार्ट पर लेबल के रूप में आसानी से प्रदर्शित करना।

### आप क्या सीखेंगे:
- पायथन के लिए Aspose.Slides का उपयोग करके पावरपॉइंट प्रस्तुतियों में चार्ट कैसे बनाएं और एम्बेड करें।
- आपके चार्ट पर डेटा बिंदुओं को प्रतिशत लेबल के रूप में प्रदर्शित करना।
- पावरपॉइंट प्रस्तुतियों को कुशलतापूर्वक सहेजना और प्रबंधित करना।

क्या आप अपने डेटा में व्यावहारिक दृश्य जोड़ने के लिए तैयार हैं? कोड में जाने से पहले आइए देखें कि आपको क्या चाहिए!

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
- **पायथन के लिए Aspose.Slides**यह लाइब्रेरी प्रोग्रामेटिक रूप से पावरपॉइंट प्रस्तुतियों को बनाने और उनमें बदलाव करने के लिए आवश्यक है।
- **पायथन पर्यावरण**पायथन प्रोग्रामिंग और पर्यावरण सेटअप की बुनियादी समझ।
- **पीआईपी पैकेज मैनेजर**: Aspose.Slides को स्थापित करने के लिए उपयोग किया जाता है।

## पायथन के लिए Aspose.Slides सेट अप करना

Aspose.Slides का उपयोग शुरू करने के लिए, आपको सबसे पहले इसे इंस्टॉल करना होगा:

```bash
pip install aspose.slides
```

### लाइसेंस प्राप्ति चरण:
आप एक निःशुल्क परीक्षण के साथ आरंभ कर सकते हैं या Aspose.Slides की पूर्ण क्षमताओं का पता लगाने के लिए एक अस्थायी लाइसेंस प्राप्त कर सकते हैं। विस्तारित उपयोग के लिए, सदस्यता खरीदने पर विचार करें।

#### बुनियादी आरंभीकरण और सेटअप

एक बार इंस्टॉल हो जाने पर, आप अपने प्रेजेंटेशन वातावरण को इस प्रकार आरंभ करेंगे:

```python
import aspose.slides as slides

# प्रस्तुति ऑब्जेक्ट आरंभ करें
def create_presentation():
    with slides.Presentation() as presentation:
        # आपका कोड यहाँ
```

## कार्यान्वयन मार्गदर्शिका

अब जब हमने तैयारी कर ली है तो चलिए चार्ट पर प्रतिशत प्रदर्शित करना शुरू करते हैं।

### चार्ट बनाना और डेटा जोड़ना

#### अवलोकन
हम प्रत्येक डेटा बिंदु के लिए प्रतिशत लेबल के साथ एक स्टैक्ड कॉलम चार्ट बनाएंगे, जिससे दर्शकों को एक नज़र में सटीक अनुपात देखने में मदद मिलेगी।

##### चरण 1: अपनी स्लाइड में चार्ट जोड़ें

```python
# अपनी प्रस्तुति में पहली स्लाइड तक पहुँचें
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # स्टैक्ड कॉलम चार्ट जोड़ें
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

यह कोड स्निपेट पहली स्लाइड में एक बुनियादी चार्ट जोड़ता है। `add_chart` विधि चार्ट के प्रकार और उसकी स्थिति और आकार को निर्दिष्ट करती है।

##### चरण 2: श्रेणियों के लिए कुल मान की गणना करें

```python
def calculate_totals(chart):
    total_for_category = []
    # प्रत्येक श्रेणी के लिए सभी श्रृंखलाओं में मानों का योग करें
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

यह लूप श्रृंखला में सभी डेटा बिंदुओं का योग गणना करता है, जो प्रतिशत गणना के लिए महत्वपूर्ण है।

#### प्रतिशत लेबल सेट करना

##### चरण 3: श्रृंखला डेटा बिंदु कॉन्फ़िगर करें

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # गैर-ज़रूरी जानकारी छिपाने के लिए डिफ़ॉल्ट लेबल विकल्प सेट करें
        series.labels.default_data_label_format.show_legend_key = False
        
        # प्रतिशत लेबल की गणना करें और सेट करें
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # प्रतिशत मान के साथ एक पाठ भाग बनाएँ
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # मौजूदा लेबल साफ़ करें और नया प्रतिशत लेबल जोड़ें
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # अन्य डेटा लेबल तत्व छिपाएँ
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

यह खंड प्रत्येक डेटा बिंदु को संसाधित करके कुल का प्रतिशत गणना करता है और उसे एक लेबल के रूप में निर्दिष्ट करता है।

### अपनी प्रस्तुति को सहेजना

```python
def save_presentation(presentation, output_directory):
    # संशोधनों के साथ अपनी प्रस्तुति सहेजें
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}