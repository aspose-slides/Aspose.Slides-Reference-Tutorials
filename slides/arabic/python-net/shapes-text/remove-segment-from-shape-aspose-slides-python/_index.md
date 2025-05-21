---
"date": "2025-04-23"
"description": "تعرف على كيفية إزالة الأجزاء من الأشكال الهندسية باستخدام Aspose.Slides لـ Python، مما يعزز تصميمات العرض التقديمي لديك باستخدام صور مرئية مخصصة."
"title": "كيفية إزالة جزء من الأشكال باستخدام Aspose.Slides في Python"
"url": "/ar/python-net/shapes-text/remove-segment-from-shape-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إزالة جزء من الأشكال باستخدام Aspose.Slides في Python

## مقدمة

غالبًا ما يتطلب إنشاء عروض تقديمية جذابة تخصيص الأشكال بما يتجاوز تصميماتها الافتراضية. إزالة أجزاء محددة من أشكال، مثل القلوب، يُحسّن بشكل كبير من السرد البصري ويجعل الشرائح أكثر تميزًا. سيرشدك هذا البرنامج التعليمي إلى كيفية إزالة الأجزاء من الأشكال الهندسية باستخدام Aspose.Slides لـ Python.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides لـ Python
- خطوات إزالة جزء من شكل موجود في عرض تقديمي
- التطبيقات العملية واعتبارات الأداء

دعونا نجهز بيئتك لبدء تعديل تلك الأشكال!

## المتطلبات الأساسية

قبل البدء، تأكد من أن لديك:
- **بايثون 3.6 أو أحدث**:مطلوب للتوافق.
- **Aspose.Slides لـ Python**:مكتبة ضرورية للتلاعب بالعروض التقديمية في بايثون.

### متطلبات إعداد البيئة
1. تثبيت Aspose.Slides باستخدام pip:
   ```bash
   pip install aspose.slides
   ```
2. تأكد من أن لديك دليل صالح لحفظ ملفات الإخراج.

### متطلبات المعرفة
- فهم أساسي لبرمجة بايثون.
- إن المعرفة بتنسيقات العرض التقديمي مثل PPTX مفيدة.

## إعداد Aspose.Slides لـ Python

للبدء، قم بتثبيت مكتبة Aspose.Slides القوية باستخدام pip:
```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية**:اختبار الميزات باستخدام ترخيص مؤقت.
- **رخصة مؤقتة**:احصل عليه من [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/).
- **شراء**:فكر في الشراء للحصول على إمكانية الوصول إلى الميزات الكاملة.

### التهيئة والإعداد الأساسي
فيما يلي كيفية تهيئة Aspose.Slides في مشروعك:
```python
import aspose.slides as slides

def setup_presentation():
    # تهيئة كائن العرض التقديمي باستخدام إدارة الموارد التلقائية
    with slides.Presentation() as pres:
        print("Presentation initialized successfully!")
```

## دليل التنفيذ: إزالة القطعة من الشكل

الآن، لنركز على إزالة جزء من شكل. هذه الميزة مفيدة بشكل خاص لتخصيص الأشكال المعقدة مثل القلوب.

### نظرة عامة على الميزة
يرشدك هذا الدليل خلال كيفية إزالة جزء محدد (على سبيل المثال، الجزء الثالث) من مسار على شكل قلب في العرض التقديمي الخاص بك.

#### الخطوة 1: تهيئة العرض التقديمي
```python
# إنشاء عرض تقديمي موجود أو تحميله
with slides.Presentation() as pres:
    # أضف شكلًا تلقائيًا من نوع HEART إلى الشريحة الأولى
    shape = pres.slides[0].shapes.add_auto_shape(slides.ShapeType.HEART, 100, 100, 300, 300)
```

#### الخطوة 2: الوصول إلى مسارات الهندسة وتعديلها
```python
# الوصول إلى مسارات الهندسة من شكل القلب
path = shape.get_geometry_paths()[0]

# إزالة جزء محدد (الفهرس 2) من المسار
del path.s_segments[2]

# تحديث الشكل بالمسار المعدل
shape.set_geometry_path(path)
```

#### الخطوة 3: احفظ العرض التقديمي الخاص بك
```python
# حفظ العرض التقديمي المحدث في دليل الإخراج
pres.save("YOUR_OUTPUT_DIRECTORY/shapes_geometry_path_remove_at_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}