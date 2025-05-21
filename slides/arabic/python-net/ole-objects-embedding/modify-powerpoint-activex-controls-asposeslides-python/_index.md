---
"date": "2025-04-22"
"description": "تعلّم كيفية تعديل نص مربع النص، وتعليقات الأزرار، والصور في PowerPoint باستخدام Aspose.Slides مع Python. حسّن عروضك التقديمية بعناصر تفاعلية."
"title": "إتقان Aspose.Slides لـ Python - تعديل عناصر تحكم ActiveX في PowerPoint بسهولة"
"url": "/ar/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان Aspose.Slides للغة Python: تعديل عناصر تحكم ActiveX في PowerPoint

في ظلّ المشهد الرقمي المتغيّر اليوم، يُعدّ تخصيص عروض مايكروسوفت باوربوينت التقديمية أمرًا أساسيًا لإنشاء محتوى جذاب. سواء كنت تُطوّر وحدات تدريبية تفاعلية أو تُحسّن عروضك التقديمية التجارية بإمكانيات إدخال المستخدم، فإن تعديل عناصر تحكم ActiveX في PowerPoint يُحسّن أداء عرضك التقديمي بشكل ملحوظ. يستكشف هذا البرنامج التعليمي استخدام Aspose.Slides في بايثون لتغيير نص مربع النص وتسميات الأزرار، واستبدال الصور، وإعادة وضع عناصر تحكم ActiveX، أو إزالتها من الشرائح.

## ما سوف تتعلمه
- كيفية تعديل نص مربع النص وأسماء الأزرار في العروض التقديمية في PowerPoint.
- تقنيات استبدال الصور داخل عناصر التحكم ActiveX.
- طرق لإعادة وضع عناصر التحكم ActiveX أو إزالتها بشكل فعال.
- التطبيقات العملية لهذه الميزات في سيناريوهات العالم الحقيقي.

قبل الغوص في Aspose.Slides لـ Python، دعنا نراجع المتطلبات الأساسية.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك:
- **بايثون**:الإصدار 3.6 أو أعلى مثبتًا على نظامك.
- **Aspose.Slides لـ Python عبر .NET**:يمكن تثبيته باستخدام pip.
- فهم أساسي لبرمجة بايثون والتعرف على بنية PowerPoint.

### متطلبات إعداد البيئة
1. **تثبيت Aspose.Slides**:
   استخدم الأمر التالي لتثبيت Aspose.Slides لـ Python عبر .NET:

   ```bash
   pip install aspose.slides
   ```

2. **الحصول على الترخيص**: 
   ابدأ بالحصول على [رخصة تجريبية مجانية](https://releases.aspose.com/slides/python-net/) أو قم بالتقدم بطلب للحصول على ترخيص مؤقت لاستكشاف الإمكانيات الكاملة دون قيود.

3. **التهيئة الأساسية**:
   قم باستيراد الوحدات النمطية اللازمة وتحميل مستند PowerPoint الخاص بك كما هو موضح أدناه:

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # سيتم وضع الكود الخاص بك هنا.
   ```

## دليل التنفيذ
### الميزة: تغيير نص مربع النص واستبدال الصورة
#### ملخص
تتيح لك هذه الميزة تحديث النص داخل عنصر التحكم ActiveX الخاص بـ TextBox واستبدال الصورة المرتبطة به، وهو أمر مفيد لتخصيص العروض التقديمية أو تحديث المحتوى بشكل ديناميكي.

##### دليل خطوة بخطوة
1. **تحميل العرض التقديمي**:
   ابدأ بتحميل عرض PowerPoint الذي يحتوي على عناصر التحكم ActiveX.

   ```python
def change_textbox_and_image():
    مع slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") كعرض تقديمي:
        الشريحة = العرض التقديمي.الشرائح[0]
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
3. **إنشاء صورة بديلة**:
   إنشاء صورة لاستبدال المحتوى الأصلي أثناء تنشيط ActiveX.

   ```python
            import aspose.pydrawing as drawing

            # إنشاء صورة بأبعاد محددة
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # أضف خطوط حدودية للحصول على مظهر أنيق
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
### الميزة: تغيير تسمية الزر واستبدال الصورة
#### ملخص
قم بتحديث تسميات الأزرار ضمن عناصر التحكم ActiveX في العرض التقديمي الخاص بك، مما يوفر إمكانيات تفاعل ديناميكية للمستخدم.

##### دليل خطوة بخطوة
1. **تحميل العرض التقديمي**:
   كما في السابق، ابدأ بتحميل ملف PowerPoint.

   ```python
def change_button_caption_and_image():
    مع slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") كعرض تقديمي:
        الشريحة = العرض التقديمي.الشرائح[0]
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
3. **إنشاء صورة بديلة**:
   إنشاء صورة للاستبدال البصري.

   ```python
            # إنشاء خريطة نقطية لأبعاد الزر
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # أضف خطوط حدودية لتحسين المظهر الجمالي
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
### الميزة: نقل عناصر التحكم ActiveX لأسفل وحفظ العرض التقديمي
#### ملخص
تعرف على كيفية إعادة وضع عناصر التحكم ActiveX داخل الشريحة، مما يعزز مرونة التخطيط.

##### دليل خطوة بخطوة
1. **تحميل العرض التقديمي**:
   افتح مستند PowerPoint الخاص بك للتحرير.

   ```python
def move_active_x_controls_and_save():
    مع slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") كعرض تقديمي:
        الشريحة = العرض التقديمي.الشرائح[0]
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
**خاتمة:**
باتباع هذا الدليل، يمكنك تعديل عناصر تحكم ActiveX في PowerPoint بفعالية باستخدام Aspose.Slides للغة بايثون. هذا يُحسّن تفاعلية عروضك التقديمية وتخصيصها، مما يجعلها أكثر جاذبية لجمهورك.

## توصيات الكلمات الرئيسية
- "تعديل عناصر تحكم ActiveX في PowerPoint"
- "Aspose.Slides لـ Python"
- "تغيير نص مربع النص في PowerPoint"
- "استبدال الصور في عناصر تحكم ActiveX"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}