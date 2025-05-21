---
"date": "2025-04-22"
"description": "تعلّم كيفية إنشاء مخططات بيانية ديناميكية وإجراء حسابات صيغية في PowerPoint باستخدام Aspose.Slides لـ Python. حسّن عروضك التقديمية بسهولة."
"title": "إنشاء مخطط رئيسي وحساب الصيغة في PowerPoint باستخدام Aspose.Slides لـ Python"
"url": "/ar/python-net/charts-graphs/create-charts-calculate-formulas-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان إنشاء المخططات وحساب الصيغ في PowerPoint باستخدام Aspose.Slides لـ Python

إن إنشاء مخططات ديناميكية وإجراء حسابات صيغية ضمن عرض تقديمي على PowerPoint يُحسّن بشكل كبير من المظهر المرئي والرؤى المستندة إلى البيانات لشرائحك. **Aspose.Slides لـ Python**يمكنك أتمتة هذه المهام بكفاءة، مما يجعلها أداة قيّمة للمطورين الذين يتطلعون إلى إنشاء عروض تقديمية احترافية برمجيًا. سيرشدك هذا البرنامج التعليمي خلال إنشاء مخططات أعمدة مجمعة وحساب الصيغ في مصنفات بيانات المخططات باستخدام Aspose.Slides لـ Python.

## ما سوف تتعلمه

- كيفية إنشاء مخطط عمودي مجمع في PowerPoint
- إعداد الصيغ وحسابها داخل خلايا مصنف الرسم البياني
- تحسين الأداء عند العمل مع Aspose.Slides
- التطبيقات العملية لهذه الميزات في سيناريوهات العالم الحقيقي

دعونا نلقي نظرة على المتطلبات الأساسية قبل أن نبدأ.

### المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك:

1. **Aspose.Slides لـ Python** تم تثبيته. يمكنك تثبيته عبر pip:
   ```bash
   pip install aspose.slides
   ```
2. فهم أساسي لبرمجة بايثون والعمل مع المكتبات.
3. إعداد بيئة تدعم Python (يوصى باستخدام Python 3.x).
4. المعرفة بعروض PowerPoint، وخاصة فيما يتعلق بالشرائح والمخططات البيانية.
5. اختياريًا، يمكنك الحصول على ترخيص لـ Aspose.Slides إذا كنت بحاجة إلى ميزات متقدمة تتجاوز النسخة التجريبية المجانية. يمكنك الحصول على ترخيص مؤقت من [موقع Aspose](https://purchase.aspose.com/temporary-license/).

### إعداد Aspose.Slides لـ Python

1. **تثبيت**:قم بتثبيت Aspose.Slides باستخدام pip:
   ```bash
   pip install aspose.slides
   ```
2. **الحصول على الترخيص**:لاستخدام Aspose.Slides دون قيود التقييم، يمكنك التقدم بطلب للحصول على ترخيص مؤقت أو شراء ترخيص من [موقع Aspose](https://purchase.aspose.com/buy). اتبع الإرشادات المقدمة على موقعهم لتنزيل ترخيصك وتنشيطه.
3. **التهيئة الأساسية**:
   ```python
   import aspose.slides as slides

   # قم بتحميل الترخيص إذا كان متاحًا
   license = slides.License()
   try:
       license.set_license("path_to_your_license_file")
   except Exception as e:
       print(f"License setup failed: {e}")
   ```

بعد أن أصبحت بيئتك جاهزة، دعنا ننتقل إلى تنفيذ ميزات إنشاء المخطط وحساب الصيغة.

### دليل التنفيذ

#### الميزة 1: إنشاء مخطط في PowerPoint

**ملخص**:تتيح لك هذه الميزة إنشاء مخطط عمودي مجمع داخل الشريحة الأولى من عرض تقديمي جديد في PowerPoint باستخدام Aspose.Slides لـ Python.

**خطوات التنفيذ**:

##### الخطوة 1: إنشاء عرض تقديمي جديد
ابدأ بإنشاء كائن عرض تقديمي جديد. ستكون هذه مساحة العمل لإضافة الشرائح والمخططات.
```python
def create_chart():
    """Create a clustered column chart on the first slide."""
    with slides.Presentation() as presentation:
        # سوف نضيف المزيد من الخطوات هنا قريبا!
```

##### الخطوة 2: إضافة مخطط عمودي مجمع
ضع الرسم البياني عند الإحداثيات (10، 10) بأبعاد 600 × 300 بكسل.
```python
        s_chart = presentation.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 10, 10, 600, 300
        )
```

##### الخطوة 3: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الجديد في الدليل المحدد.
```python
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_create_out.pptx", slides.export.SaveFormat.PPTX)
```
**وظيفة كاملة**:وهكذا تبدو الوظيفة الكاملة:
```python
def create_chart():
    """Create a clustered column chart on the first slide."""
    with slides.Presentation() as presentation:
        s_chart = presentation.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 10, 10, 600, 300
        )
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_create_out.pptx", slides.export.SaveFormat.PPTX)
```

#### الميزة 2: حساب الصيغة في خلايا المصنف

**ملخص**:توضح هذه الميزة كيفية تعيين الصيغ وحسابها داخل مصنف بيانات الرسم البياني باستخدام Aspose.Slides.

**خطوات التنفيذ**:

##### الخطوة 1: تهيئة العرض التقديمي باستخدام الرسم البياني
قم بإنشاء عرض تقديمي جديد وأضف مخططًا عموديًا مجمعًا كما في السابق.
```python
def calculate_formulas():
    """Calculate explicit formulas within the chart's workbook."""
    with slides.Presentation() as presentation:
        s_chart = presentation.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 10, 10, 600, 300
        )
```

##### الخطوة 2: الوصول إلى المصنف وتعيين الصيغ
قم بالوصول إلى مصنف بيانات الرسم البياني لتعيين الصيغ في خلايا محددة.
```python
        workbook = s_chart.chart_data.chart_data_workbook

        # تعيين صيغة للخلية A1
        cell_a1 = workbook.get_cell(0, "A1")
        cell_a1.formula = "ABS(A2) + MAX(B2:C2)"
```

##### الخطوة 3: حساب الصيغ وتعيين القيم
احسب الصيغ المحددة مبدئيًا في خلايا المصنف.
```python
        workbook.calculate_formulas()

        # تعيين القيم لـ B2 وC2، ثم إعادة الحساب
        workbook.get_cell(0, "A2").value = -1  # تعيين القيمة لـ A2
        cell_b2 = workbook.get_cell(0, "B2")
        cell_b2.formula = "2"
        workbook.calculate_formulas()

        cell_c2 = workbook.get_cell(0, "C2")
        cell_c2.formula = "A2 + 4"
        workbook.calculate_formulas()
```

##### الخطوة 4: تحديث الصيغ وإعادة حسابها
قم بتعديل الصيغة في A1 لإظهار الحسابات القائمة على النطاق.
```python
        # تحديث الصيغة في A1 لاستخدام نطاق، ثم إعادة الحساب
        cell_a1.formula = "MAX(2:2)"
        workbook.calculate_formulas()
```

##### الخطوة 5: حفظ العرض التقديمي باستخدام الصيغ المحسوبة
احفظ ملف العرض التقديمي بعد حساب كافة الصيغ.
```python
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_calculate_formulas_out.pptx", slides.export.SaveFormat.PPTX)
```
**وظيفة كاملة**:وهكذا تبدو الوظيفة الكاملة:
```python
def calculate_formulas():
    """Calculate explicit formulas within the chart's workbook."""
    with slides.Presentation() as presentation:
        s_chart = presentation.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 10, 10, 600, 300
        )
        workbook = s_chart.chart_data.chart_data_workbook

        cell_a1 = workbook.get_cell(0, "A1")
        cell_a1.formula = "ABS(A2) + MAX(B2:C2)"
        workbook.calculate_formulas()

        workbook.get_cell(0, "A2").value = -1  # تعيين القيمة لـ A2
        cell_b2 = workbook.get_cell(0, "B2")
        cell_b2.formula = "2"
        workbook.calculate_formulas()

        cell_c2 = workbook.get_cell(0, "C2")
        cell_c2.formula = "A2 + 4"
        workbook.calculate_formulas()

        # تحديث الصيغة في A1 لاستخدام النطاق وإعادة الحساب
        cell_a1.formula = "MAX(2:2)"
        workbook.calculate_formulas()

        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_calculate_formulas_out.pptx", slides.export.SaveFormat.PPTX)
```

### التطبيقات العملية

- **تصور البيانات**:استخدم Aspose.Slides لإنشاء مخططات ثاقبة تعرض اتجاهات البيانات المعقدة ضمن شريحة واحدة، مما يعزز العروض التقديمية للأعمال.
  
- **التقارير الآلية**:إنشاء التقارير تلقائيًا من مجموعات البيانات عن طريق إنشاء المخططات البيانية وملئها بالبيانات في الوقت الفعلي.

- **المواد التعليمية**:يمكن للمدرسين إنشاء مواد تعليمية ديناميكية مع تحليل قائم على صيغة لمواضيع مثل التمويل أو الإحصاء.

### اعتبارات الأداء

- **تحسين التعامل مع البيانات**عند التعامل مع مجموعات بيانات كبيرة، فكر في تحميل البيانات الضرورية فقط إلى المصنف لتحسين الأداء.
  
- **تقليل الحسابات المكررة**:أعد حساب الصيغ فقط عندما يكون ذلك ضروريًا لتقليل وقت المعالجة.
  
- **إدارة الموارد الفعالة**:تأكد من إغلاق العروض التقديمية والموارد بشكل صحيح بعد الحفظ لمنع تسرب الذاكرة.

### خاتمة

باتباع هذا الدليل، يمكنك استخدام Aspose.Slides for Python بفعالية لإنشاء مخططات PowerPoint ديناميكية وإجراء حسابات صيغ معقدة. تُعد هذه الإمكانيات أساسية لإنشاء عروض تقديمية قائمة على البيانات، غنية بالمعلومات وجذابة بصريًا. جرّب أنواعًا مختلفة من المخططات والصيغ للاستفادة الكاملة من قوة Aspose.Slides في مشاريعك.

### توصيات الكلمات الرئيسية
- **الكلمة الأساسية**: Aspose.Slides لـ Python
- **الكلمة الرئيسية الثانوية 1**:إنشاء مخطط PowerPoint
- **الكلمة الرئيسية الثانوية 2**:حسابات الصيغة في PowerPoint

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}