---
"date": "2025-04-22"
"description": "تعلّم كيفية عرض تسميات النسب المئوية بسهولة على الرسوم البيانية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Python. مثالي لتحسين تصور البيانات."
"title": "كيفية عرض تسميات النسب المئوية على الرسوم البيانية باستخدام Aspose.Slides لـ Python - دليل شامل"
"url": "/ar/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية عرض تسميات النسبة المئوية على الرسوم البيانية باستخدام Aspose.Slides لـ Python

## مقدمة

يُعدّ تصوّر البيانات بفعالية أمرًا بالغ الأهمية في العروض التقديمية والتقارير، خاصةً عند إبراز النسب أو التوزيعات بوضوح. ولكن ماذا لو كنتَ بحاجة إلى عرض هذه النسب المئوية مباشرةً على مخططاتك البيانية؟ سيرشدك هذا الدليل الشامل إلى كيفية استخدام **Aspose.Slides لـ Python** لعرض قيم النسب المئوية كعلامات على الرسم البياني بسهولة.

### ما سوف تتعلمه:
- كيفية إنشاء المخططات البيانية ودمجها في عروض PowerPoint باستخدام Aspose.Slides لـ Python.
- عرض نقاط البيانات كنسب مئوية على المخططات البيانية الخاصة بك.
- حفظ وإدارة عروض PowerPoint بكفاءة.

هل أنت مستعد لإضافة عناصر مرئية ثاقبة إلى بياناتك؟ لنلقِ نظرة أولًا على ما تحتاجه قبل البدء في البرمجة!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:
- **Aspose.Slides لـ Python**:تعتبر هذه المكتبة ضرورية لإنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا.
- **بيئة بايثون**:فهم أساسي لبرمجة بايثون وإعداد البيئة.
- **مدير حزمة PIP**:تستخدم لتثبيت Aspose.Slides.

## إعداد Aspose.Slides لـ Python

لبدء استخدام Aspose.Slides، ستحتاج أولاً إلى تثبيته:

```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص:
يمكنك البدء بفترة تجريبية مجانية أو الحصول على ترخيص مؤقت لاستكشاف كامل إمكانيات Aspose.Slides. للاستخدام الممتد، يمكنك شراء اشتراك.

#### التهيئة والإعداد الأساسي

بمجرد التثبيت، ستقوم بتهيئة بيئة العرض التقديمي الخاصة بك على النحو التالي:

```python
import aspose.slides as slides

# تهيئة كائن العرض التقديمي
def create_presentation():
    with slides.Presentation() as presentation:
        # الكود الخاص بك هنا
```

## دليل التنفيذ

الآن بعد أن قمنا بالإعداد، دعنا ننتقل إلى عرض النسب المئوية على الرسوم البيانية.

### إنشاء الرسم البياني وإضافة البيانات

#### ملخص
سنقوم بإنشاء مخطط عمودي مكدس مع تسميات النسبة المئوية لكل نقطة بيانات، مما يسمح للمشاهدين برؤية النسب الدقيقة في لمحة.

##### الخطوة 1: إضافة مخطط إلى الشريحة الخاصة بك

```python
# الوصول إلى الشريحة الأولى في العرض التقديمي الخاص بك
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # إضافة مخطط عمودي مكدس
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

يضيف مقتطف الكود هذا مخططًا أساسيًا إلى الشريحة الأولى. `add_chart` تحدد الطريقة نوع الرسم البياني وموضعه وحجمه.

##### الخطوة 2: حساب القيم الإجمالية للفئات

```python
def calculate_totals(chart):
    total_for_category = []
    # جمع القيم عبر جميع السلاسل لكل فئة
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

تحسب هذه الحلقة إجمالي جميع نقاط البيانات عبر السلسلة، وهو أمر بالغ الأهمية لحسابات النسبة المئوية.

#### تعيين تسميات النسبة المئوية

##### الخطوة 3: تكوين نقاط بيانات السلسلة

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # تعيين خيارات العلامة الافتراضية لإخفاء المعلومات غير الضرورية
        series.labels.default_data_label_format.show_legend_key = False
        
        # حساب وتعيين تسميات النسبة المئوية
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # إنشاء جزء نص بقيمة النسبة المئوية
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # مسح العلامات الموجودة وإضافة علامة النسبة المئوية الجديدة
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # إخفاء عناصر تسمية البيانات الأخرى
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

تقوم هذه القطعة بمعالجة كل نقطة بيانات لحساب نسبتها من الإجمالي وتعيينها كعلامة.

### حفظ العرض التقديمي الخاص بك

```python
def save_presentation(presentation, output_directory):
    # احفظ عرضك التقديمي مع التعديلات
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}