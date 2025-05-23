---
"date": "2025-04-22"
"description": "जानें कि पायथन के साथ Aspose.Slides का उपयोग करके PowerPoint में TextBox टेक्स्ट, बटन कैप्शन और छवियों को कैसे संशोधित किया जाए। इंटरैक्टिव तत्वों के साथ अपनी प्रस्तुतियों को बेहतर बनाएँ।"
"title": "मास्टर Aspose.Slides for Python&#58; PowerPoint ActiveX नियंत्रणों को आसानी से संशोधित करें"
"url": "/hi/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# पायथन के लिए Aspose.Slides में महारत हासिल करना: PowerPoint ActiveX नियंत्रणों को संशोधित करना

आज के गतिशील डिजिटल परिदृश्य में, आकर्षक सामग्री बनाने के लिए Microsoft PowerPoint प्रस्तुतियों को अनुकूलित करना आवश्यक है। चाहे आप इंटरैक्टिव प्रशिक्षण मॉड्यूल विकसित कर रहे हों या उपयोगकर्ता इनपुट क्षमताओं के साथ व्यावसायिक प्रस्तुतियों को बढ़ा रहे हों, PowerPoint ActiveX नियंत्रणों को संशोधित करने से आपकी प्रस्तुति की कार्यक्षमता में उल्लेखनीय वृद्धि हो सकती है। यह ट्यूटोरियल टेक्स्टबॉक्स टेक्स्ट और बटन कैप्शन बदलने, छवियों को प्रतिस्थापित करने, स्लाइड से ActiveX नियंत्रणों को हटाने या हटाने के लिए पायथन के लिए Aspose.Slides का उपयोग करने का पता लगाता है।

## आप क्या सीखेंगे
- पावरपॉइंट प्रस्तुतियों में टेक्स्टबॉक्स टेक्स्ट और बटन कैप्शन को कैसे संशोधित करें।
- ActiveX नियंत्रणों के भीतर छवियों को प्रतिस्थापित करने की तकनीकें।
- ActiveX नियंत्रणों को प्रभावी ढंग से पुनः स्थापित करने या हटाने के तरीके।
- वास्तविक दुनिया के परिदृश्यों में इन विशेषताओं के व्यावहारिक अनुप्रयोग।

Aspose.Slides for Python में गोता लगाने से पहले, आइए पूर्वापेक्षाओं की समीक्षा करें।

## आवश्यक शर्तें
इस ट्यूटोरियल का अनुसरण करने के लिए, सुनिश्चित करें कि आपके पास ये हैं:
- **पायथन**: आपके सिस्टम पर संस्करण 3.6 या उच्चतर स्थापित है।
- **.NET के माध्यम से पायथन के लिए Aspose.Slides**: इसे पाइप का उपयोग करके स्थापित किया जा सकता है।
- पायथन प्रोग्रामिंग की बुनियादी समझ और पावरपॉइंट की संरचना से परिचित होना।

### पर्यावरण सेटअप आवश्यकताएँ
1. **Aspose.Slides स्थापित करें**:
   .NET के माध्यम से Python के लिए Aspose.Slides स्थापित करने के लिए निम्नलिखित कमांड का उपयोग करें:

   ```bash
   pip install aspose.slides
   ```

2. **लाइसेंस अधिग्रहण**: 
   एक प्राप्त करके शुरू करें [निःशुल्क परीक्षण लाइसेंस](https://releases.aspose.com/slides/python-net/) या बिना किसी सीमा के पूर्ण क्षमताओं का पता लगाने के लिए अस्थायी लाइसेंस के लिए आवेदन करें।

3. **मूल आरंभीकरण**:
   आवश्यक मॉड्यूल आयात करें और अपना पावरपॉइंट दस्तावेज़ नीचे दिखाए अनुसार लोड करें:

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # आपका कोड यहां जाएगा.
   ```

## कार्यान्वयन मार्गदर्शिका
### विशेषता: टेक्स्टबॉक्स टेक्स्ट बदलें और छवि बदलें
#### अवलोकन
यह सुविधा आपको टेक्स्टबॉक्स एक्टिवएक्स नियंत्रण के भीतर पाठ को अद्यतन करने और उससे संबंधित छवि को बदलने की अनुमति देती है, जो प्रस्तुतियों को वैयक्तिकृत करने या सामग्री को गतिशील रूप से अद्यतन करने के लिए उपयोगी है।

##### चरण-दर-चरण मार्गदर्शिका
1. **प्रस्तुति लोड करें**:
   एक्टिवएक्स नियंत्रणों वाले अपने पावरपॉइंट प्रेजेंटेशन को लोड करके आरंभ करें।

   ```python
डेफ़ चेंज_टेक्स्टबॉक्स_और_इमेज():
    प्रस्तुति के रूप में slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") के साथ:
        स्लाइड = प्रस्तुति.स्लाइड्स[0]
```
2. **Access the TextBox Control**:
   Access the specific control you intend to modify.

   ```python
        control = slide.controls[0]
        if control.name == "TextBox1" and control.properties is not None:
            new_text = "Changed text"
            # Remove existing property value for 'Value'
            control.properties.remove("Value")
            # Add the new text as a property
            control.properties.add("Value", new_text)
```
3. **स्थानापन्न छवि बनाएँ**:
   ActiveX सक्रियण के दौरान मूल सामग्री को प्रतिस्थापित करने के लिए एक छवि उत्पन्न करें।

   ```python
            import aspose.pydrawing as drawing

            # निर्दिष्ट आयामों के साथ एक छवि बनाएँ
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # एक चमकदार लुक के लिए बॉर्डर लाइन्स जोड़ें
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_DARK), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Finally, add this image as a substitute for the ActiveX control.

   ```python
                # Add the created image to presentation images
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### विशेषता: बटन कैप्शन और स्थानापन्न छवि बदलें
#### अवलोकन
अपनी प्रस्तुति के ActiveX नियंत्रणों में बटन कैप्शन को अपडेट करें, जिससे गतिशील उपयोगकर्ता सहभागिता की संभावनाएं उपलब्ध हों।

##### चरण-दर-चरण मार्गदर्शिका
1. **प्रस्तुति लोड करें**:
   पहले की तरह, पावरपॉइंट फ़ाइल लोड करके शुरुआत करें।

   ```python
def परिवर्तन_बटन_कैप्शन_और_छवि():
    प्रस्तुति के रूप में slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") के साथ:
        स्लाइड = प्रस्तुति.स्लाइड्स[0]
```
2. **Access the Button Control**:
   Identify and modify the button control's caption.

   ```python
        control = slide.controls[1]
        if control.name == "CommandButton1" and control.properties is not None:
            new_caption = "MessageBox"
            control.properties.remove("Caption")
            control.properties.add("Caption", new_caption)
```
3. **स्थानापन्न छवि बनाएँ**:
   दृश्य प्रतिस्थापन के लिए एक छवि उत्पन्न करें.

   ```python
            # बटन के आयामों के लिए बिटमैप बनाएँ
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # सौंदर्य के लिए सीमा रेखाएं जोड़ें
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_LIGHT_LIGHT), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Save the newly created image in your presentation.

   ```python
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### फ़ीचर: ActiveX नियंत्रणों को नीचे ले जाएं और प्रेजेंटेशन सहेजें
#### अवलोकन
जानें कि स्लाइड के भीतर ActiveX नियंत्रणों को कैसे पुनः स्थापित किया जाए, जिससे लेआउट का लचीलापन बढ़े।

##### चरण-दर-चरण मार्गदर्शिका
1. **प्रस्तुति लोड करें**:
   संपादन के लिए अपना पावरपॉइंट दस्तावेज़ खोलें.

   ```python
def move_active_x_controls_and_save():
    प्रस्तुति के रूप में slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") के साथ:
        स्लाइड = प्रस्तुति.स्लाइड्स[0]
```
2. **Reposition Controls**:
   Iterate through controls to adjust their positions.

   ```python
        for ctl in slide.controls:
            frame = ctl.frame
            # Move each control down by 100 points on the y-axis
            ctl.frame = slides.ShapeFrame(
                frame.x, frame.y + 100, frame.width, frame.height,
                # Rest of your code to move and save controls
```
**निष्कर्ष:**
इस गाइड का पालन करके, आप Python के लिए Aspose.Slides का उपयोग करके PowerPoint ActiveX नियंत्रणों को प्रभावी ढंग से संशोधित कर सकते हैं। यह आपकी प्रस्तुतियों की अन्तरक्रियाशीलता और अनुकूलन को बढ़ाता है, जिससे वे आपके दर्शकों के लिए अधिक आकर्षक बन जाती हैं।

## कीवर्ड अनुशंसाएँ
- "PowerPoint ActiveX नियंत्रण संशोधित करें"
- "पायथन के लिए Aspose.Slides"
- "पावरपॉइंट में टेक्स्टबॉक्स टेक्स्ट बदलें"
- "एक्टिवएक्स नियंत्रणों में छवियों को प्रतिस्थापित करें"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}