---
"date": "2025-04-22"
"description": "जानें कि पायथन और Aspose.Slides के साथ डोनट चार्ट कैसे बनाएं। यह चरण-दर-चरण मार्गदर्शिका आपके प्रस्तुतीकरण को बेहतर बनाने के लिए सेटअप, अनुकूलन और सर्वोत्तम अभ्यासों को कवर करती है।"
"title": "Aspose.Slides का उपयोग करके पायथन में डोनट चार्ट कैसे बनाएं - एक चरण-दर-चरण मार्गदर्शिका"
"url": "/hi/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides का उपयोग करके पायथन में डोनट चार्ट कैसे बनाएं: एक चरण-दर-चरण मार्गदर्शिका

डेटा विज़ुअलाइज़ेशन के क्षेत्र में, जानकारी को प्रभावी ढंग से प्रस्तुत करना समझ और निर्णय लेने को महत्वपूर्ण रूप से प्रभावित कर सकता है। चाहे आप कोई व्यावसायिक प्रस्तुति तैयार कर रहे हों या जटिल डेटासेट का विश्लेषण कर रहे हों, चार्ट आवश्यक उपकरण हैं। विभिन्न चार्ट प्रकारों में, डोनट चार्ट एक सहज केंद्र छेद के साथ आनुपातिक डेटा को दर्शाने का एक आकर्षक तरीका प्रदान करते हैं। यह चरण-दर-चरण मार्गदर्शिका आपको Aspose.Slides का उपयोग करके पायथन में डोनट चार्ट बनाने के बारे में बताएगी - प्रस्तुतियों में हेरफेर करने के लिए एक शक्तिशाली लाइब्रेरी।

## आप क्या सीखेंगे
- पायथन के लिए Aspose.Slides को कैसे सेट अप और उपयोग करें
- अपनी प्रस्तुति स्लाइड में डोनट चार्ट जोड़ने की प्रक्रिया
- चार्ट के भीतर श्रृंखला और श्रेणियों को अनुकूलित करना
- लेबल, रंग और विस्फोट प्रभाव जैसे दृश्य तत्वों को समायोजित करना
- Aspose.Slides के साथ प्रदर्शन को अनुकूलित करने के लिए सर्वोत्तम अभ्यास

## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास:
- **पायथन पर्यावरण**: आपकी मशीन पर पायथन 3.x स्थापित है।
- **पायथन के लिए Aspose.Slides**: इस लाइब्रेरी को pip का उपयोग करके स्थापित करें.
- **पायथन प्रोग्रामिंग की बुनियादी समझ**लूप्स और ऑब्जेक्ट-ओरिएंटेड प्रोग्रामिंग से परिचित होना उपयोगी होगा।

## पायथन के लिए Aspose.Slides सेट अप करना
आरंभ करने के लिए, पाइप के माध्यम से Aspose.Slides लाइब्रेरी स्थापित करें:

```bash
pip install aspose.slides
```

### लाइसेंस अधिग्रहण
Aspose सीमित समय के लिए बिना किसी सीमा के सुविधाओं का परीक्षण करने के लिए निःशुल्क परीक्षण प्रदान करता है। इसे प्राप्त करने के लिए:
1. दौरा करना [मुफ्त परीक्षण](https://releases.aspose.com/slides/python-net/) पृष्ठ.
2. अपना अस्थायी लाइसेंस डाउनलोड करने और लागू करने के लिए निर्देशों का पालन करें।

निरंतर उपयोग के लिए, से सदस्यता खरीदने पर विचार करें [खरीद पृष्ठ](https://purchase.aspose.com/buy).

### मूल आरंभीकरण
Aspose.Slides को सेट अप करने के बाद, इसे निम्न प्रकार से आरंभ करें:

```python
import aspose.slides as slides

# प्रेजेंटेशन क्लास का एक उदाहरण बनाएं.
with slides.Presentation() as pres:
    # प्रस्तुतियों में हेरफेर करने के लिए आपका कोड यहां है।

# परिवर्तन करने के बाद प्रस्तुति को सुरक्षित करें.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## कार्यान्वयन मार्गदर्शिका
Aspose.Slides सेटअप के साथ, अपनी प्रस्तुति में स्लाइड-दर-स्लाइड डोनट चार्ट जोड़ने के लिए इन चरणों का पालन करें।

### नया प्रेजेंटेशन बनाना और स्लाइड जोड़ना
इसका एक उदाहरण बनाकर शुरू करें `Presentation` कक्षा:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # इस संदर्भ में स्लाइडों तक पहुंचें या उन्हें बनाएं.
```

### पहली स्लाइड में डोनट चार्ट जोड़ना
पहली स्लाइड पर पहुँचें और इसका उपयोग करें `add_chart` विधि. चार्ट प्रकार को इस प्रकार निर्दिष्ट करें `DOUGHNUT`, स्थिति और आकार के साथ:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### चार्ट डेटा कॉन्फ़िगर करना
मौजूदा डेटा साफ़ करें और लेजेंड छिपाने जैसी सेटिंग्स कॉन्फ़िगर करें:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### श्रृंखला और श्रेणियाँ जोड़ना
डोनट चार्ट के लिए कई श्रृंखलाएँ और श्रेणियाँ जोड़ें। यहाँ विशिष्ट गुणों वाली 15 श्रृंखलाएँ बनाने का तरीका बताया गया है:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

इसी प्रकार श्रेणियाँ जोड़ें:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # प्रत्येक श्रृंखला के लिए डेटा बिंदु जोड़ें.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # प्रत्येक डेटा बिंदु का स्वरूप अनुकूलित करें.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # अंतिम श्रृंखला के लिए लेबल सेटिंग कॉन्फ़िगर करें.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### प्रस्तुति को सहेजना
अंत में, अपनी प्रस्तुति को निर्दिष्ट निर्देशिका में सहेजें:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## व्यावहारिक अनुप्रयोगों
डोनट चार्ट बहुमुखी हैं और इन्हें विभिन्न परिदृश्यों में उपयोग किया जा सकता है जैसे:
1. **बजट आवंटन**: यह प्रदर्शित करना कि विभिन्न विभाग अपने आवंटित धन का उपयोग किस प्रकार करते हैं।
2. **बाजार हिस्सेदारी विश्लेषण**प्रतिस्पर्धी उत्पादों या कंपनियों की बाजार हिस्सेदारी की तुलना करना।
3. **सर्वेक्षण परिणाम**: वरीयताओं या संतुष्टि के स्तर के बारे में सर्वेक्षण प्रश्नों के उत्तरों को दृश्यमान बनाना।

## प्रदर्शन संबंधी विचार
Aspose.Slides का उपयोग करते समय इष्टतम प्रदर्शन सुनिश्चित करने के लिए:
- उपयोग के बाद वस्तुओं का उचित तरीके से निपटान करके मेमोरी उपयोग को न्यूनतम करें।
- केवल आवश्यक होने पर ही प्रस्तुतियों को मेमोरी में लोड करें, और उन्हें यथाशीघ्र बंद कर दें।
- यदि आप बड़ी संख्या में चार्ट के साथ काम कर रहे हैं तो बैच प्रोसेसिंग स्लाइड पर विचार करें।

## निष्कर्ष
इस गाइड का पालन करके, आपने सीखा है कि पायथन के लिए Aspose.Slides का उपयोग करके गतिशील डोनट चार्ट कैसे बनाएं। ये विज़ुअलाइज़ेशन डेटा को अधिक सुपाच्य और आकर्षक बनाकर आपकी प्रस्तुतियों को बेहतर बना सकते हैं। अपने चार्ट को और अधिक अनुकूलित और अनुकूलित करने के लिए लाइब्रेरी की सुविधाओं का पता लगाना जारी रखें।

## अक्सर पूछे जाने वाले प्रश्न अनुभाग
1. **क्या मैं लाइसेंस खरीदे बिना Aspose.Slides का उपयोग कर सकता हूँ?**
   - हां, आप मूल्यांकन प्रयोजनों के लिए निःशुल्क परीक्षण लाइसेंस के साथ शुरुआत कर सकते हैं।
2. **मैं Aspose.Slides में चार्ट का रंग कैसे बदल सकता हूँ?**
   - उपयोग `fill_format` अपने चार्ट तत्वों के लिए वांछित रंग सेट करने के लिए प्रॉपर्टी का उपयोग करें।
3. **क्या चार्ट को छवियों के रूप में निर्यात करना संभव है?**
   - हां, आप लाइब्रेरी की रेंडरिंग क्षमताओं का उपयोग करके चार्ट युक्त स्लाइडों को छवि प्रारूपों में रेंडर कर सकते हैं।
4. **चार्ट जोड़ते समय कुछ सामान्य समस्याएं क्या हैं?**
   - अपने चार्ट को सहेजने या प्रदर्शित करने का प्रयास करने से पहले सुनिश्चित करें कि सभी डेटा बिंदु और श्रेणियां ठीक से जोड़ी गई हैं।
5. **क्या मैं Aspose.Slides को अन्य पायथन लाइब्रेरीज़ के साथ एकीकृत कर सकता हूँ?**
   - बिल्कुल! आप डेटा हेरफेर क्षमताओं को बढ़ाने के लिए पांडा जैसी लाइब्रेरी के साथ इसका उपयोग कर सकते हैं।

## संसाधन
- [Aspose.Slides दस्तावेज़ीकरण](https://reference.aspose.com/slides/python-net/)
- [Aspose.Slides डाउनलोड करें](https://releases.aspose.com/slides/python-net/)
- [लाइसेंस खरीदें](https://purchase.aspose.com/buy)
- [निःशुल्क परीक्षण और अस्थायी लाइसेंस](https://releases.aspose.com/slides/python-net/)
- [Aspose सामुदायिक मंच](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}