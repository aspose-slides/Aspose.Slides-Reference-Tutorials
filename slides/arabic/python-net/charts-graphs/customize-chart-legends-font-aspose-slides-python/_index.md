---
"date": "2025-04-22"
"description": "تعرّف على كيفية تخصيص خصائص خطوط أساطير المخططات باستخدام Aspose.Slides لبايثون. حسّن عروضك التقديمية باستخدام خطوط غامقة ومائلة وملونة لكل إدخال من أساطير المخططات."
"title": "تخصيص خطوط أساطير المخططات باستخدام Aspose.Slides لـ Python - دليل شامل"
"url": "/ar/python-net/charts-graphs/customize-chart-legends-font-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تخصيص خطوط أساطير المخططات في العروض التقديمية باستخدام Aspose.Slides لـ Python

## مقدمة
يُعد إنشاء عروض تقديمية جذابة بصريًا أمرًا بالغ الأهمية، خاصةً عند عرض البيانات عبر الرسوم البيانية. ومن التحديات الشائعة تخصيص رموز المخططات لتتماشى مع أسلوب عرضك التقديمي أو احتياجات علامتك التجارية. يوضح هذا الدليل كيفية تخصيص خصائص الخط، مثل الغامق والمائل والحجم واللون، لكل رمز من رموز المخططات باستخدام Aspose.Slides لـ Python.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides واستخدامه لـ Python
- تخصيص خصائص الخط الخاصة بأساطير الرسم البياني
- تطبيق أنماط الخطوط المحددة مثل الغامق والمائل وتغيير الألوان
- أمثلة عملية لتحسين المخططات باستخدام الخطوط المخصصة

دعونا نستكشف كيفية تحقيق هذا التخصيص.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- **المكتبات**Aspose.Slides لبايثون. ثبّته باستخدام pip.
- **بيئة**:بيئة Python (يفضل Python 3.x) تم إعدادها على جهازك.
- **معرفة**:فهم أساسي لبرمجة بايثون والتعرف على كيفية التعامل مع العروض التقديمية برمجيًا.

## إعداد Aspose.Slides لـ Python
### تثبيت
للبدء، قم بتثبيت مكتبة Aspose.Slides عن طريق تشغيل الأمر التالي في محطتك الطرفية:

```bash
pip install aspose.slides
```

### الحصول على الترخيص
Aspose.Slides هو منتج تجاري يحتوي على خيارات ترخيص مختلفة:
- **نسخة تجريبية مجانية**:احصل على ترخيص مؤقت للاستفادة من كافة الوظائف.
- **رخصة مؤقتة**:تقدم بطلب للحصول على ترخيص مؤقت لاختبار كافة الميزات دون قيود.
- **شراء**:قم بشراء اشتراك أو ترخيص دائم بناءً على احتياجاتك.

### التهيئة الأساسية
فيما يلي كيفية تهيئة Aspose.Slides وإعداده في البرنامج النصي Python الخاص بك:

```python
import aspose.slides as slides

# قم بتهيئة مثيل العرض التقديمي باستخدام slides.Presentation() كـ pres:
    # الكود الخاص بك هنا
```

## دليل التنفيذ
في هذا القسم، سنشرح كيفية تخصيص خصائص الخط لإدخالات الأسطورة الفردية.

### إضافة مخطط والوصول إليه
أولاً، دعنا نضيف مخططًا عموديًا مجمعًا إلى الشريحة الخاصة بك:

```python
# أضف مخططًا عموديًا مجمعًا في الموضع (50، 50) بعرض 600 وارتفاع 400
class ShapeCollection:
    def __init__(self):
        self.chart = None

    def add_chart(self, chart_type, x, y, width, height):
        # هذا مجرد عنصر نائب لطريقة Aspose.Slides الفعلية.
        return "ChartObject"

class SlideCollection:
    def __init__(self):
        self.shapes = ShapeCollection()

# محاكاة pres.slides[0].shapes
slide_shapes = SlideCollection()
chart = slide_shapes.shapes.add_chart(slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 600, 400)
```

### تخصيص خصائص خط الأسطورة
#### الوصول إلى تنسيق نص إدخال الأسطورة
لتعديل خصائص الخط لإدخال أسطورة معينة:

```python
class Chart:
    def __init__(self):
        self.legend = "LegendObject"

# محاكاة chart.legend.entries[1].text_format
chart_object = Chart()
tf = "SimulatedTextFormatObject"
```

#### ضبط خصائص الخط
هنا، نقوم بتخصيص جوانب مثل الجرأة والحجم والخط المائل واللون:

```python
class TextFormat:
    def __init__(self):
        self.portion_format = PortionFormat()

class PortionFormat:
    def __init__(self):
        self.font_bold = False
        self.font_height = 0
        self.font_italic = False
        self.fill_format = FillFormat()

class FillFormat:
    def __init__(self):
        self.fill_type = "None"
        self.solid_fill_color = SolidFillColor()

class SolidFillColor:
    def __init__(self):
        self.color = None

class Color:
    blue = 'blue'

tf.portion_format.font_bold = True
# ضبط حجم الخط إلى 20 نقطة
tf.portion_format.font_height = 20  
tf.portion_format.font_italic = True

# اضبط لون الخط إلى اللون الأزرق باستخدام نوع التعبئة الصلبة
tf.portion_format.fill_format.fill_type = "SOLID"
tf.portion_format.fill_format.solid_fill_color.color = Color.blue
```

### حفظ العرض التقديمي
وأخيرًا، احفظ عرضك التقديمي باستخدام هذه التخصيصات:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_individual_legend_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}