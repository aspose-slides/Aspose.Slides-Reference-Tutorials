---
"date": "2025-04-22"
"description": "تعلّم كيفية إنشاء مخططات بيانية باستخدام Aspose.Slides لبايثون. حسّن عرض البيانات في عروضك التقديمية."
"title": "إنشاء مخططات الصندوق والشارب في بايثون باستخدام Aspose.Slides"
"url": "/ar/python-net/charts-graphs/create-box-whisker-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات الصندوق والشارب في بايثون باستخدام Aspose.Slides

## كيفية إنشاء مخطط الصندوق والشارب باستخدام Aspose.Slides لـ Python

حسّن مهاراتك في تصور البيانات بتعلم كيفية إنشاء مخططات بيانية باستخدام مكتبة Aspose.Slides القوية. هذه المخططات ممتازة لعرض التوزيعات الإحصائية، مما يُسهّل تفسير البيانات المعقدة بنظرة واحدة.

**ما سوف تتعلمه:**
- إعداد بيئتك باستخدام Aspose.Slides لـ Python
- إنشاء وتخصيص مخططات الصناديق والشوارب
- التطبيقات العملية وفرص التكامل
- نصائح التحسين للحصول على أداء أفضل

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:
- **Aspose.Slides لـ Python:** مكتبة ضرورية لإنشاء عروض PowerPoint والتلاعب بها.
- **بيئة بايثون:** سوف تحتاج إلى تثبيت Python قيد التشغيل (يفضل Python 3.x).
- **المعرفة الأساسية بلغة بايثون:** ستساعدك المعرفة ببرمجة Python على المتابعة بسهولة أكبر.

## إعداد Aspose.Slides لـ Python

### معلومات التثبيت

للبدء، قم بتثبيت مكتبة Aspose.Slides باستخدام pip:

```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص

توفر Aspose خيارات ترخيص مختلفة:
- **نسخة تجريبية مجانية:** قم بتنزيل ترخيص مؤقت لاستكشاف الميزات الكاملة دون قيود التقييم.
- **رخصة مؤقتة:** مثالي للمشاريع قصيرة المدى أو لأغراض الاختبار.
- **شراء:** احصل على ترخيص دائم إذا كنت بحاجة إلى الوصول المستمر.

يمكنك الحصول على هذه التراخيص عبر [صفحة الشراء](https://purchase.aspose.com/buy) أو اطلب نسخة تجريبية مجانية على [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

### التهيئة والإعداد الأساسي

بعد التثبيت، شغّل Aspose.Slides لبايثون لبدء العمل مع العروض التقديمية. إليك كيفية إعداد بيئتك:

```python
import aspose.slides as slides

# تهيئة مثيل العرض التقديمي
def setup_presentation():
    with slides.Presentation() as pres:
        # قم بإجراء عمليات مثل إضافة الرسوم البيانية هنا
        pass
```

## دليل التنفيذ

في هذا القسم، سنرشدك خلال إنشاء مخطط الصندوق والشارب.

### إضافة مخطط الصندوق والشارب إلى العرض التقديمي الخاص بك

#### ملخص

لعرض البيانات بفعالية في عرضك التقديمي، أنشئ مخططًا بيانيًا مربعًا باستخدام Aspose.Slides لبايثون. هذا النوع من المخططات ممتاز لعرض التوزيعات وتحديد القيم المتطرفة.

#### التنفيذ خطوة بخطوة

1. **إنشاء عرض تقديمي جديد:**
   
   ابدأ بتهيئة مثيل عرض تقديمي جديد:
   
   ```python
   import aspose.slides as slides
   
   def create_box_and_whisker_chart():
       # إنشاء مثيل عرض تقديمي جديد
       with slides.Presentation() as pres:
           # أضف الرسم البياني في الخطوات اللاحقة
           pass
   ```

2. **أضف الرسم البياني إلى الشريحة الخاصة بك:**
   
   أدخل مخطط الصندوق والشارب في الموضع المطلوب:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           # أضف مخطط الصندوق والشارب على الشريحة الأولى في الموضع (50، 50) بالحجم (500، 400)
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
   ```

3. **مسح البيانات الموجودة:**
   
   تأكد من أن الرسم البياني فارغ قبل إضافة بيانات جديدة:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           
           # مسح أي فئات وبيانات السلسلة الموجودة
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)  # مسح المصنف لإدخال بيانات جديدة
   ```

4. **إضافة الفئات إلى الرسم البياني الخاص بك:**
   
   املأ الرسم البياني الخاص بك بالفئات:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           # تحديد فئات لبيانات الرسم البياني
           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))
   ```

5. **تكوين السلسلة:**
   
   قم بإعداد السلسلة الخاصة بك بالخصائص المطلوبة:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           # إضافة سلسلة جديدة وتكوين خصائصها
           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           # تحديد نقاط البيانات للسلسلة
           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))
   ```

6. **حفظ العرض التقديمي:**
   
   احفظ عملك باستخدام الرسم البياني المضاف حديثًا:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))

           # حفظ العرض التقديمي
           pres.save("YOUR_OUTPUT_DIRECTORY/charts_box_chart_out.pptx", slides.export.SaveFormat.PPTX)

   create_box_and_whisker_chart()
   ```

### نصائح استكشاف الأخطاء وإصلاحها

- **التحقق من تثبيت المكتبة:** يضمن `aspose.slides` تم تثبيته بشكل صحيح.
- **التحقق من إعداد الترخيص:** إذا واجهت أي قيود، فتأكد من إعداد ملف الترخيص الخاص بك بشكل صحيح.
- **أخطاء نحوية:** تأكد مرة أخرى من عدم وجود أخطاء مطبعية أو أخطاء في بناء الجملة البرمجية.

## التطبيقات العملية وفرص التكامل

تُستخدم مخططات الصندوق والشارب على نطاق واسع في تحليلات الأعمال لعرض البيانات الإحصائية بإيجاز. فهي تساعد على تحديد الاتجاهات والقيم الشاذة والتباينات داخل مجموعات البيانات، مما يجعلها مثالية للعروض التقديمية والتقارير ولوحات المعلومات.

يتيح دمج Aspose.Slides مع Python إنشاء عروض تقديمية تفاعلية غنية على PowerPoint بشكل سلس برمجيًا، مما يعزز الطريقة التي تتواصل بها مع الأفكار القائمة على البيانات.

## نصائح التحسين لتحقيق أداء أفضل

- **تبسيط إدخال البيانات:** تأكد من أن مجموعات البيانات الخاصة بك نظيفة ومنظمة بشكل جيد قبل إنشاء المخططات البيانية لتجنب الأخطاء أثناء التصور.
- **تحسين تخصيص الرسم البياني:** استخدم خيارات التخصيص في Aspose.Slides بحكمة لتحسين قابلية قراءة المخطط دون زيادة تحميل العرض التقديمي بعناصر مفرطة.
- **أتمتة المهام المتكررة:** استخدم نصوص Python لأتمتة المهام المتكررة مثل تنسيق البيانات وإنشاء المخططات، مما يوفر الوقت ويقلل الأخطاء.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}