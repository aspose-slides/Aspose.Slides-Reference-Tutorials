---
"date": "2025-04-23"
"description": "تعرّف على كيفية تحسين عروض PowerPoint التقديمية باستخدام مخططات ديناميكية باستخدام Aspose.Slides للغة بايثون. اتبع هذا الدليل خطوة بخطوة لإنشاء مخططات عمودية مجمعة وإدارتها وتنسيقها بفعالية."
"title": "إنشاء وتنسيق المخططات في عروض PowerPoint باستخدام Aspose.Slides لـ Python"
"url": "/ar/python-net/charts-graphs/create-charts-presentation-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء وتنسيق المخططات في عروض PowerPoint باستخدام Aspose.Slides لـ Python

## مقدمة

في عالمنا اليوم الذي يعتمد على البيانات، يُعدّ دمج المخططات البيانية الجذابة بصريًا في العروض التقديمية أمرًا بالغ الأهمية للتواصل الفعال. سواء كنت محلل بيانات أو مدير مشروع أو خبيرًا في مجال الأعمال، فإن المخططات البيانية الديناميكية تُحسّن رسالتك بشكل كبير. سيرشدك هذا البرنامج التعليمي خلال إنشاء وتنسيق مخططات عمودية مجمعة باستخدام Aspose.Slides للغة بايثون، مما يُمكّنك من الارتقاء بعروض PowerPoint الخاصة بك بسهولة.

**ما سوف تتعلمه:**
- كيفية تثبيت وإعداد Aspose.Slides لـ Python
- إنشاء عرض تقديمي جديد وإضافة مخطط عمودي مجمع
- إدارة سلسلة البيانات والفئات داخل الرسم البياني
- ملء وتنسيق بيانات السلسلة لتحسين التصور

هل أنت مستعد لتحسين عروضك التقديمية؟ دعنا نستكشف كيفية الاستفادة من Aspose.Slides لإنشاء مخططات بيانية جذابة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- **تم تثبيت Python:** يوصى باستخدام الإصدار 3.6 أو أعلى.
- **حزمة Aspose.Slides لـ Python:** قم بتثبيت هذه الحزمة باستخدام pip.
- **المعرفة الأساسية لبرمجة بايثون:** ستكون المعرفة بقواعد لغة Python ومعالجة الملفات مفيدة.

## إعداد Aspose.Slides لـ Python

للبدء، ستحتاج إلى تثبيت مكتبة Aspose.Slides. تُبسّط هذه الأداة الفعّالة إنشاء عروض PowerPoint التقديمية ومعالجتها باستخدام بايثون.

### تثبيت

قم بتشغيل الأمر التالي لتثبيت الحزمة:

```bash
pip install aspose.slides
```

### الحصول على الترخيص

يقدم Aspose ترخيصًا تجريبيًا مجانيًا يتيح لك استكشاف كامل إمكانياته دون قيود. اتبع الخطوات التالية للحصول عليه:

1. يزور [نسخة تجريبية مجانية من Aspose](https://releases.aspose.com/slides/python-net/) لتنزيل الحزمة التجريبية.
2. بدلاً من ذلك، يمكنك طلب ترخيص مؤقت من خلال [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

بمجرد حصولك على ملف الترخيص، قم بتهيئته في البرنامج النصي Python الخاص بك:

```python
from aspose.slides import License

# إعداد ترخيص Aspose.Slides
license = License()
license.set_license("path/to/your/license/file.lic")
```

## دليل التنفيذ

سنقوم بتقسيم العملية إلى ثلاث ميزات رئيسية: إنشاء المخططات البيانية، وإدارة سلاسل البيانات والفئات، وتعبئة بيانات السلسلة وتنسيقها.

### الميزة 1: إنشاء مخطط وإضافته إلى العرض التقديمي

#### ملخص

ترتكز هذه الميزة على إضافة مخطط عمودي مجمع إلى العرض التقديمي الخاص بك باستخدام Aspose.Slides لـ Python.

#### التنفيذ خطوة بخطوة

```python
import aspose.slides as slides

def create_and_add_chart():
    with slides.Presentation() as pres:
        # أضف مخططًا عموديًا مجمعًا في الموضع (100، 100) بعرض 400 وارتفاع 300.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        # احفظ العرض التقديمي في ملف في دليل الإخراج الخاص بك.
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_creation_out.pptx", slides.export.SaveFormat.PPTX)

create_and_add_chart()
```

**توضيح:**
- **موضع الرسم البياني وحجمه:** ال `add_chart` يتم استخدام الطريقة مع المعلمات التي تحدد نوع الرسم البياني، والموضع (x،y)، والعرض، والارتفاع.
- **حفظ العرض التقديمي:** يتم حفظ العرض التقديمي في الدليل المحدد.

### الميزة 2: إدارة سلاسل بيانات المخططات والفئات

#### ملخص

يوضح هذا القسم كيفية إدارة سلاسل البيانات والفئات داخل الرسم البياني الخاص بك بشكل فعال.

#### التنفيذ خطوة بخطوة

```python
import aspose.slides as slides

def manage_chart_data_series_and_categories():
    with slides.Presentation() as pres:
        # أضف مخططًا عموديًا مجمعًا في الموضع (100، 100) بعرض 400 وارتفاع 300.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # قم بمسح السلسلة والفئات الموجودة قبل إضافة فئات وسلاسل جديدة.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # إضافة سلسلة جديدة باسم "السلسلة 1" إلى الرسم البياني.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # إضافة ثلاث فئات إلى بيانات الرسم البياني.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # احفظ العرض التقديمي في ملف في دليل الإخراج الخاص بك.
        pres.save("YOUR_OUTPUT_DIRECTORY/chart_series_categories_out.pptx", slides.export.SaveFormat.PPTX)

manage_chart_data_series_and_categories()
```

**توضيح:**
- **مسح البيانات الموجودة:** قبل إضافة سلاسل وفئات جديدة، يتم مسح السلاسل والفئات الموجودة لمنع تكرار البيانات.
- **إضافة السلاسل والفئات:** تمت إضافة سلاسل وفئات جديدة باستخدام `chart_data_workbook` هدف.

### الميزة 3: ملء بيانات السلسلة وتنسيق الرسم البياني

#### ملخص

في هذه الميزة، سنملأ الرسم البياني الخاص بك بنقاط البيانات ونطبق التنسيق لتحسين جاذبيته البصرية.

#### التنفيذ خطوة بخطوة

```python
import aspose.slides as slides
import aspose.pydrawing as drawing

def populate_and_format_series_data():
    with slides.Presentation() as pres:
        # أضف مخططًا عموديًا مجمعًا في الموضع (100، 100) بعرض 400 وارتفاع 300.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # قم بمسح السلسلة والفئات الموجودة قبل إضافة فئات وسلاسل جديدة.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # إضافة سلسلة جديدة باسم "السلسلة 1" إلى الرسم البياني.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # إضافة ثلاث فئات إلى بيانات الرسم البياني.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # خذ سلسلة المخططات الأولى وقم بملئها بنقاط البيانات.
        series = chart.chart_data.series[0]
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 1, 1, -20)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 2, 1, 50)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 3, 1, -30)
        )
        
        # تعيين اللون للقيم السلبية في السلسلة.
        invert_color = drawing.Color.red
        series.invert_if_negative = True
        series.format.fill.fill_type = slides.FillType.SOLID
        series.format.fill.solid_fill_color.color = series.get_automatic_series_color()
        series.inverted_solid_fill_color.color = invert_color
        
        # احفظ العرض التقديمي في ملف في دليل الإخراج الخاص بك.
        pres.save("YOUR_OUTPUT_DIRECTORY/populate_format_series_out.pptx", slides.export.SaveFormat.PPTX)

populate_and_format_series_data()
```

**توضيح:**
- **إضافة نقاط البيانات:** تتم إضافة نقاط البيانات باستخدام `add_data_point_for_bar_series`.
- **تنسيق القيم السلبية:** تعمل خيارات تنسيق الرسم البياني مثل عكس الألوان للقيم السلبية على تحسين قابلية قراءة البيانات.

## التطبيقات العملية

إن استخدام Aspose.Slides لإضافة المخططات وتنسيقها في العروض التقديمية له تطبيقات عديدة:

1. **التقارير التجارية:** قم بتعزيز التقارير الفصلية باستخدام صور ديناميكية تنقل المقاييس الرئيسية بوضوح.
2. **المواد التعليمية:** إنشاء محتوى تعليمي جذاب من خلال تمثيل المعلومات المعقدة بصريًا.
3. **عروض المشاريع:** استخدم المخططات البيانية لتوضيح تقدم المشروع ونتائجه بشكل فعال.

من خلال اتباع هذا الدليل، يمكنك الاستفادة من Aspose.Slides for Python لإنشاء عروض تقديمية مؤثرة وملفتة للنظر.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}