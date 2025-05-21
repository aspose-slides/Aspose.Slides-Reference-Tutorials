---
"date": "2025-04-22"
"description": "تعلّم كيفية إنشاء وتخصيص المخططات الدائرية في PowerPoint باستخدام Aspose.Slides لـ Python. حسّن عروضك التقديمية برؤى مبنية على البيانات."
"title": "أنشئ مخططات دائرية جذابة على PowerPoint باستخدام Aspose.Slides لـ Python | دروس في المخططات والرسوم البيانية"
"url": "/ar/python-net/charts-graphs/aspose-slides-python-powerpoint-pie-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات دائرية في PowerPoint باستخدام Aspose.Slides لـ Python

**فئة:** المخططات والرسوم البيانية

يُعدّ إنشاء عروض تقديمية جذابة وغنية بالمعلومات أمرًا أساسيًا لتوصيل الأفكار المستندة إلى البيانات بفعالية. إذا كنت ترغب في تحسين شرائح PowerPoint الخاصة بك من خلال تضمين مخططات دائرية جذابة بصريًا، **Aspose.Slides لـ Python** المكتبة أداة ممتازة تُبسّط هذه العملية. في هذا البرنامج التعليمي، سنشرح لك كيفية إنشاء مخطط دائري في PowerPoint باستخدام Aspose.Slides لـ Python.

## ما سوف تتعلمه:
- تثبيت وإعداد Aspose.Slides لـ Python
- إنشاء مخطط دائري أساسي في شرائح PowerPoint
- قم بتخصيص مخططك الدائري باستخدام نقاط البيانات والألوان والحدود والعلامات وخطوط القيادة والتدوير
- تحسين الأداء عند العمل مع المخططات البيانية

دعونا نتعمق في الخطوات اللازمة للبدء.

## المتطلبات الأساسية

قبل تنفيذ الكود، تأكد من أن لديك ما يلي:
- تم تثبيت Python على نظامك (يوصى بالإصدار 3.6 أو أحدث)
- `pip` مدير الحزم لتثبيت المكتبات
- فهم أساسي لبرمجة بايثون وعروض PowerPoint

## إعداد Aspose.Slides لـ Python

للبدء في العمل مع Aspose.Slides لـ Python، تحتاج إلى تثبيت المكتبة باستخدام pip:

```bash
pip install aspose.slides
```

**الحصول على الترخيص:**
يمكنك البدء بتنزيل ترخيص تجريبي مجاني من [صفحة تنزيل Aspose](https://releases.aspose.com/slides/python-net/)للاستخدام الأكثر شمولاً، فكر في شراء ترخيص كامل أو الحصول على ترخيص مؤقت لأغراض التقييم.

### التهيئة والإعداد الأساسي

بمجرد تثبيت Aspose.Slides، قم باستيراد الوحدات النمطية الضرورية في البرنامج النصي Python الخاص بك:

```python
import aspose.slides as slides
import aspose.pydrawing as drawing
```

## دليل التنفيذ

في هذا القسم، سنقوم بتقسيم عملية إنشاء مخطط دائري إلى خطوات مفصلة.

### إنشاء مخطط دائري وتخصيصه

#### ملخص
يتضمن إنشاء مخطط دائري تهيئة كائن عرض تقديمي، وإضافة شريحة، ثم إدراج مخطط يحتوي على نقاط بيانات مخصصة وعناصر مرئية.

#### خطوات إنشاء مخطط دائري

1. **إنشاء فئة عرض تقديمي**
   ابدأ بإنشاء نموذج عرض تقديمي. سيكون هذا النموذج بمثابة حاوية لشرائحك ومخططاتك.

   ```python
   with slides.Presentation() as presentation:
       # الوصول إلى الشريحة الأولى
       slide = presentation.slides[0]
   ```

2. **إضافة مخطط دائري إلى الشريحة**
   استخدم `add_chart` طريقة لإدراج مخطط دائري عند إحداثيات محددة على الشريحة.

   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

3. **تعيين عنوان الرسم البياني**
   قم بتخصيص الرسم البياني الخاص بك باستخدام عنوان مناسب وتنسيقه لتمركز النص.

   ```python
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

4. **مصنف بيانات مخطط الوصول**
   استخدم `chart_data_workbook` لإدارة وتخصيص فئات البيانات والسلاسل الخاصة بك.

   ```python
   fact = chart.chart_data.chart_data_workbook
   default_worksheet_index = 0

   # مسح أي سلسلة أو فئات موجودة
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()

   # إضافة فئات جديدة (أرباع)
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   # إضافة سلسلة جديدة
   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   ```

5. **ملء السلسلة بنقاط البيانات**
   قم بإدراج نقاط البيانات في سلسلتك لتمثيل أجزاء مختلفة من الفطيرة.

   ```python
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 3, 1, 30))
   ```

6. **تطبيق ألوان متنوعة على الرسم البياني**
   قم بتخصيص كل شريحة فطيرة بألوان مختلفة.

   ```python
   chart.chart_data.series_groups[0].is_color_varied = True

   # تحديد وظيفة لتخصيص مظهر النقطة
   def customize_point(point, fill_color, line_color):
       point.format.fill.fill_type = slides.FillType.SOLID
       point.format.fill.solid_fill_color.color = drawing.Color(fill_color)
       
       point.format.line.fill_format.fill_type = slides.FillType.SOLID
       point.format.line.fill_format.solid_fill_color.color = drawing.Color(line_color)
       point.format.line.width = 3.0
       point.format.line.style = slides.LineStyle.THIN_THICK
       point.format.line.dash_style = slides.LineDashStyle.DASH_DOT
   
   # تخصيص مظهر نقطة البيانات الأولى
   customize_point(series.data_points[0], "Cyan", "Gray")
   ```

7. **تخصيص العلامات لنقاط البيانات**
   قم بضبط إعدادات التسمية لعرض القيم أو النسب المئوية أو أسماء السلسلة.

   ```python
   def customize_label(point, show_value=True, show_legend_key=False,
                       show_percentage=False, show_series_name=False):
       lbl = point.label
       lbl.data_label_format.show_value = show_value
       lbl.data_label_format.show_legend_key = show_legend_key
       lbl.data_label_format.show_percentage = show_percentage
       lbl.data_label_format.show_series_name = show_series_name
   
   # تعيين خصائص التسمية لنقطة البيانات الأولى
   customize_label(series.data_points[0], True)
   ```

8. **تمكين خطوط القائد وتدوير شرائح الفطيرة**
   لتحسين إمكانية القراءة، قم بتمكين خطوط القيادة وتدوير الشرائح حسب الحاجة.

   ```python
   series.labels.default_data_label_format.show_leader_lines = True

   # قم بتدوير شريحة الفطيرة الأولى إلى 180 درجة
   chart.chart_data.series_groups[0].first_slice_angle = 180
   ```

9. **حفظ العرض التقديمي**
   وأخيرًا، احفظ العرض التقديمي الخاص بك مع جميع التخصيصات المطبقة.

   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من تثبيت Aspose.Slides واستيراده بشكل صحيح.
- تحقق من وجود أي أخطاء مطبعية في أسماء الطرق أو المعلمات، حيث يمكن أن تؤدي إلى حدوث أخطاء.
- تأكد من وجود مسار الدليل الذي تحفظ فيه ملف الإخراج.

## التطبيقات العملية

المخططات الدائرية متعددة الاستخدامات ومفيدة في مختلف المجالات:
1. **تحليلات الأعمال**:تصور توزيع الإيرادات بين المنتجات أو الخدمات المختلفة.
2. **تقارير التسويق**:إظهار حصة السوق للمنافسين في صناعة معينة.
3. **العروض التعليمية**:إظهار البيانات الإحصائية المتعلقة بأداء الطلاب أو البيانات الديموغرافية.

## اعتبارات الأداء
- قم بتقليل استخدام الموارد عن طريق تحسين عناصر الرسم البياني وتقليل التعقيد غير الضروري.
- استخدم هياكل بيانات فعالة عند التعامل مع مجموعات البيانات الكبيرة للرسوم البيانية.
- قم بإدارة الذاكرة بشكل فعال عن طريق تحرير الموارد فورًا بعد الاستخدام.

## خاتمة

باتباع هذا الدليل، ستتعلم كيفية إنشاء مخطط دائري في PowerPoint باستخدام Aspose.Slides للغة بايثون. يمكنك الآن تطبيق هذه التقنيات على عروضك التقديمية واستكشاف خيارات تخصيص إضافية. فكّر في دمج أنواع أخرى من المخططات أو الاستفادة من ميزات Aspose.Slides الإضافية لتحسين مهاراتك في تصور البيانات.

### الخطوات التالية
- تجربة تخصيصات مختلفة للمخططات
- استكشاف تكامل الرسوم البيانية في التقارير الديناميكية
- تعمق أكثر في وثائق Aspose.Slides للحصول على ميزات أكثر تقدمًا

## قسم الأسئلة الشائعة

1. **ما هو Aspose.Slides؟**
   - مكتبة قوية تسمح بإنشاء عروض PowerPoint والتلاعب بها برمجيًا.
2. **هل يمكنني استخدام Aspose.Slides مجانًا؟**
   - نعم، يمكنك البدء بنسخة تجريبية أو تقييم إمكانياتها قبل الشراء.
3. **ما هي بعض أنواع المخططات الأخرى التي يمكنني إنشاؤها؟**
   - بالإضافة إلى المخططات الدائرية، يمكنك إنشاء مخططات شريطية ومخططات خطية ومخططات تشتت والمزيد باستخدام Aspose.Slides.

## توصيات الكلمات الرئيسية
- "Aspose.Slides لـ Python"
- "مخطط دائري في باوربوينت"
- "مخططات PowerPoint بلغة بايثون"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}