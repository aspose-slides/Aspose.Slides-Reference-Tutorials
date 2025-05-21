---
"date": "2025-04-22"
"description": "تعرّف على كيفية إضافة وتخصيص المخططات الدائرية في عروض PowerPoint التقديمية باستخدام Aspose.Slides للغة Python. وفّر الوقت وتأكد من اتساق العمل مع هذا الدليل المفصل."
"title": "كيفية إضافة وتخصيص المخططات الدائرية في PowerPoint باستخدام Aspose.Slides لـ Python"
"url": "/ar/python-net/charts-graphs/add-customize-pie-charts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة وتخصيص المخططات الدائرية في PowerPoint باستخدام Aspose.Slides لـ Python

## مقدمة
يُعدّ إنشاء عروض تقديمية جذابة بصريًا أمرًا بالغ الأهمية، خاصةً عند الحاجة إلى عرض بيانات معقدة بإيجاز. سواءً تعلق الأمر بتقارير مالية أو مقاييس أداء، تُعدّ المخططات الدائرية أداة فعّالة لتوضيح النسب في لمحة سريعة. مع ذلك، قد تستغرق إضافة هذه المخططات يدويًا إلى شرائحك وقتًا طويلاً وقد تكون عرضةً للتناقضات.

مع مكتبة Aspose.Slides لبايثون، تُصبح أتمتة هذه العملية سلسة. سيرشدك هذا البرنامج التعليمي إلى كيفية استخدام Aspose.Slides لبايثون لإضافة وتخصيص المخططات الدائرية بسهولة في عروض PowerPoint التقديمية. باتباعك لهذا الدليل، لن توفر الوقت فحسب، بل ستضمن أيضًا تناسقًا في شرائحك.

**ما سوف تتعلمه:**
- كيفية إضافة مخطط دائري إلى شريحة
- تعيين العنوان وتمركز النص على مخطط دائري
- تكوين سلسلة البيانات والفئات للحصول على رؤى تفصيلية
- تمكين الاختلافات التلقائية في الألوان للشرائح المميزة

لنتعمق في كيفية تطبيق هذه الميزات بفعالية. قبل البدء، تأكد من إعداد بيئتك بشكل صحيح.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، ستحتاج إلى:
- تم تثبيت Python على جهازك (يوصى باستخدام الإصدار 3.x)
- مكتبة Aspose.Slides للغة بايثون
- فهم أساسي لبرمجة بايثون وعروض PowerPoint

تأكد من توفر الإعدادات اللازمة لتشغيل نصوص بايثون. إذا لم يكن الأمر كذلك، ففكّر في تثبيت بايثون من [python.org](https://www.python.org/downloads/).

## إعداد Aspose.Slides لـ Python
لبدء استخدام Aspose.Slides في مشروعك، قم بتثبيته عبر pip:

```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص
تقدم Aspose نسخة تجريبية مجانية من مكتبتها. يمكنك تنزيل ترخيص مؤقت لاستكشاف الإمكانيات الكاملة دون قيود. للبدء:
- يزور [صفحة شراء Aspose](https://purchase.aspose.com/buy) لخيارات الشراء.
- احصل على ترخيص مؤقت من خلال [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

### التهيئة الأساسية
إليك كيفية تهيئة Aspose.Slides في البرنامج النصي Python الخاص بك:

```python
import aspose.slides as slides

# تهيئة فئة العرض التقديمي لإنشاء ملف عرض تقديمي أو فتحه
with slides.Presentation() as presentation:
    # الكود الخاص بك يذهب هنا
    pass
```

باستخدام هذا الإعداد، ستكون جاهزًا لبدء إضافة المخططات الدائرية إلى عروضك التقديمية.

## دليل التنفيذ

### إضافة مخطط دائري إلى شريحة
#### ملخص
تتضمن إضافة مخطط دائري أساسي إنشاء شكل جديد من النوع `Chart` على شريحتك. سيرشدك هذا القسم خلال خطوات إضافة مخطط دائري افتراضي.

#### خطوات
1. **الوصول إلى الشريحة الأولى**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **إضافة شكل مخطط دائري**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

   - حدود: `ChartType.PIE` يحدد نوع الرسم البياني.
   - تحدد الإحداثيات والأبعاد موضع وحجم الرسم البياني الدائري.

3. **حفظ العرض التقديمي**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_add_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### تعيين عنوان مخطط دائري ونص المركز
#### ملخص
يؤدي تخصيص مخططك الدائري باستخدام عنوان إلى تحسين قابليته للقراءة وتوفير السياق للمشاهدين.

#### خطوات
1. **الوصول إلى الشريحة الأولى**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **إضافة مخطط وتعيين العنوان**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   # عنوان الإعداد
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

3. **حفظ العرض التقديمي**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_pie_chart_title_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### تكوين سلسلة بيانات المخطط الدائري والفئات
#### ملخص
لتجعل مخططك الدائري مفيدًا، تحتاج إلى إدخال بيانات فعلية فيه.

#### خطوات
1. **الوصول إلى الشريحة الأولى**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **تكوين البيانات**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   fact = chart.chart_data.chart_data_workbook
   
   # مسح البيانات الموجودة
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()
   
   # إضافة الفئات والسلاسل مع نقاط البيانات
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   
   # إضافة نقاط البيانات
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 3, 1, 30))
   ```

3. **حفظ العرض التقديمي**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_configure_pie_chart_data_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### تمكين ألوان شرائح المخطط الدائري التلقائية
#### ملخص
إن تعزيز المظهر المرئي من خلال تغيير ألوان الشرائح تلقائيًا قد يجعل الرسم البياني الخاص بك أكثر جاذبية.

#### خطوات
1. **الوصول إلى الشريحة الأولى**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **تمكين تباين الألوان**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   series = chart.chart_data.series[0]
   series.parent_series_group.is_color_varied = True
   ```

3. **حفظ العرض التقديمي**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_enable_automatic_pie_slice_colors_out.pptx", slides.export.SaveFormat.PPTX)
   ```

## التطبيقات العملية
1. **تقارير الأعمال**:استخدم المخططات الدائرية لإظهار توزيع حصة السوق بين المنافسين.
2. **المواد التعليمية**:توضيح النسب المئوية للموضوعات المختلفة التي يغطيها المنهج الدراسي.
3. **التحليل المالي**:عرض فئات النفقات كنسب من الميزانية الإجمالية.
4. **رؤى التسويق**:تصور تقسيم العملاء حسب التركيبة السكانية أو التفضيلات.

يمكن أن يؤدي التكامل مع أدوات تحليل البيانات مثل Pandas إلى أتمتة العملية بشكل أكبر، مما يجعل التحديثات في الوقت الفعلي ممكنة ضمن العروض التقديمية.

## اعتبارات الأداء
عند العمل مع Aspose.Slides وPython:
- قم بتحسين الكود الخاص بك لإدارة الذاكرة بكفاءة، وخاصة عند التعامل مع مجموعات بيانات كبيرة.
- تجنب العمليات المكررة على كائنات العرض.
- يستخدم `with` عبارات لإدارة السياق لضمان تحرير الموارد بشكل مناسب بعد الاستخدام.

## خاتمة
لديك الآن فهم شامل لكيفية إنشاء وتخصيص المخططات الدائرية في PowerPoint باستخدام Aspose.Slides لـ Python. بأتمتة هذه المهام، يمكنك تحسين الإنتاجية بشكل ملحوظ مع ضمان الاتساق في عروضك التقديمية. 

وللمضي قدمًا في هذا الأمر، استكشف دمج مصادر البيانات الديناميكية أو أتمتة إنشاء مجموعات الشرائح بالكامل.

## توصيات الكلمات الرئيسية
- "Aspose.Slides لـ Python"
- "مخطط دائري في باوربوينت"
- "أتمتة مخططات PowerPoint باستخدام Python"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}