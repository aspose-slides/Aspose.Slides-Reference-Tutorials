---
"date": "2025-04-22"
"description": "تعرّف على كيفية إنشاء مخططات دائرية باستخدام بايثون وAspose.Slides. يغطي هذا الدليل خطوة بخطوة الإعداد والتخصيص وأفضل الممارسات لتحسين عروضك التقديمية."
"title": "كيفية إنشاء مخططات دائرية في بايثون باستخدام Aspose.Slides - دليل خطوة بخطوة"
"url": "/ar/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخططات دائرية في بايثون باستخدام Aspose.Slides: دليل خطوة بخطوة

في مجال تصور البيانات، يُؤثر عرض المعلومات بفعالية بشكل كبير على الفهم واتخاذ القرارات. سواءً كنت تُعدّ عرضًا تقديميًا للأعمال أو تُحلل مجموعات بيانات مُعقدة، تُعدّ المخططات البيانية أدوات أساسية. من بين أنواع المخططات البيانية المُختلفة، تُوفر المخططات الدائرية طريقةً جذابةً لتمثيل البيانات المتناسبة بفتحة مركزية بديهية. سيُرشدك هذا الدليل المُفصّل خطوةً بخطوة إلى كيفية إنشاء مخطط دائري في بايثون باستخدام Aspose.Slides، وهي مكتبة فعّالة لإدارة العروض التقديمية.

## ما سوف تتعلمه
- كيفية إعداد Aspose.Slides واستخدامه لـ Python
- عملية إضافة مخطط دائري إلى شرائح العرض التقديمي الخاصة بك
- تخصيص السلسلة والفئات داخل الرسم البياني
- ضبط العناصر المرئية مثل العلامات والألوان وتأثيرات الانفجار
- أفضل الممارسات لتحسين الأداء باستخدام Aspose.Slides

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك:
- **بيئة بايثون**:تم تثبيت Python 3.x على جهازك.
- **Aspose.Slides لـ Python**:قم بتثبيت هذه المكتبة باستخدام pip.
- **فهم أساسيات برمجة بايثون**:ستكون المعرفة بالحلقات والبرمجة الموجهة للكائنات مفيدة.

## إعداد Aspose.Slides لـ Python
للبدء، قم بتثبيت مكتبة Aspose.Slides عبر pip:

```bash
pip install aspose.slides
```

### الحصول على الترخيص
يقدم Aspose نسخة تجريبية مجانية لاختبار الميزات دون قيود لفترة محدودة. للحصول عليها:
1. قم بزيارة [نسخة تجريبية مجانية](https://releases.aspose.com/slides/python-net/) صفحة.
2. اتبع التعليمات لتنزيل ترخيصك المؤقت وتطبيقه.

للاستمرار في الاستخدام، فكر في شراء اشتراك من [صفحة الشراء](https://purchase.aspose.com/buy).

### التهيئة الأساسية
بعد إعداد Aspose.Slides، قم بتهيئته على النحو التالي:

```python
import aspose.slides as slides

# إنشاء مثيل لفئة العرض التقديمي.
with slides.Presentation() as pres:
    # يذهب الكود الخاص بك لمعالجة العروض التقديمية هنا.

# احفظ العرض التقديمي بعد إجراء التغييرات.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## دليل التنفيذ
بعد إعداد Aspose.Slides، اتبع الخطوات التالية لإضافة مخطط دائري إلى شريحة العرض التقديمي الخاصة بك شريحة تلو الأخرى.

### إنشاء عرض تقديمي جديد وإضافة شريحة
ابدأ بإنشاء مثيل لـ `Presentation` فصل:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # الوصول إلى الشرائح أو إنشائها ضمن هذا السياق.
```

### إضافة مخطط دائري إلى الشريحة الأولى
قم بالوصول إلى الشريحة الأولى واستخدم `add_chart` الطريقة. حدد نوع الرسم البياني كـ `DOUGHNUT`، مع الموضع والحجم:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### تكوين بيانات الرسم البياني
مسح البيانات الموجودة وتكوين الإعدادات مثل إخفاء الأسطورة:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### إضافة السلاسل والفئات
أضف سلاسل وفئات متعددة لمخطط دائري. إليك كيفية إنشاء 15 سلسلة بخصائص محددة:

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

أضف الفئات بشكل مشابه:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # أضف نقاط البيانات لكل سلسلة.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # تخصيص مظهر كل نقطة بيانات.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # تكوين إعدادات التسمية للسلسلة الأخيرة.
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

### حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الخاص بك في الدليل المحدد:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## التطبيقات العملية
تعتبر مخططات الكعكة متعددة الاستخدامات ويمكن استخدامها في سيناريوهات مختلفة مثل:
1. **تخصيص الميزانية**:يوضح كيفية استخدام الأقسام المختلفة للأموال المخصصة لها.
2. **تحليل حصة السوق**:مقارنة حصة السوق للمنتجات أو الشركات المنافسة.
3. **نتائج الاستطلاع**:تصور الاستجابات لأسئلة الاستطلاع حول التفضيلات أو مستويات الرضا.

## اعتبارات الأداء
لضمان الأداء الأمثل عند استخدام Aspose.Slides:
- قم بتقليل استخدام الذاكرة عن طريق التخلص من الكائنات بشكل صحيح بعد الاستخدام.
- قم بتحميل العروض التقديمية إلى الذاكرة فقط عند الضرورة، وأغلقها في أقرب وقت ممكن.
- خذ في الاعتبار معالجة الشرائح بشكل دفعي إذا كنت تعمل مع عدد كبير من المخططات البيانية.

## خاتمة
باتباع هذا الدليل، ستتعلم كيفية إنشاء مخططات دائرية ديناميكية باستخدام Aspose.Slides لبايثون. تُحسّن هذه التصورات عروضك التقديمية بجعل البيانات أكثر سهولة في الفهم وتفاعلية. واصل استكشاف ميزات المكتبة لمزيد من تخصيص مخططاتك وتحسينها.

## قسم الأسئلة الشائعة
1. **هل يمكنني استخدام Aspose.Slides دون شراء ترخيص؟**
   - نعم، يمكنك البدء باستخدام ترخيص تجريبي مجاني لأغراض التقييم.
2. **كيف يمكنني تغيير ألوان الرسم البياني في Aspose.Slides؟**
   - استخدم `fill_format` الخاصية لتعيين اللون المطلوب لعناصر الرسم البياني الخاص بك.
3. **هل من الممكن تصدير المخططات كصور؟**
   - نعم، يمكنك تقديم الشرائح التي تحتوي على مخططات بيانية بتنسيقات الصور باستخدام إمكانيات التقديم التي توفرها المكتبة.
4. **ما هي بعض المشكلات الشائعة عند إضافة المخططات البيانية؟**
   - تأكد من إضافة جميع نقاط البيانات والفئات بشكل صحيح قبل محاولة حفظ الرسم البياني أو عرضه.
5. **هل يمكنني دمج Aspose.Slides مع مكتبات Python الأخرى؟**
   - بالتأكيد! يمكنك استخدامه مع مكتبات مثل Pandas لتحسين إمكانيات معالجة البيانات.

## موارد
- [توثيق Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [تنزيل Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [شراء ترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية وترخيص مؤقت](https://releases.aspose.com/slides/python-net/)
- [منتدى مجتمع Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}