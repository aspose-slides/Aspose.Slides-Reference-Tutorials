---
"date": "2025-04-24"
"description": "تعرف على كيفية تحريك النص في PowerPoint باستخدام Aspose.Slides for Python، مما يعزز عروضك التقديمية باستخدام التأثيرات الديناميكية."
"title": "تحريك النصوص في PowerPoint باستخدام Aspose.Slides لـ Python - دليل خطوة بخطوة"
"url": "/ar/python-net/animations-transitions/animate-text-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تحريك النص في PowerPoint باستخدام Aspose.Slides لـ Python: دليل خطوة بخطوة

## مقدمة

هل ترغب في جعل عروض PowerPoint التقديمية أكثر جاذبية؟ يُمكن للنص المتحرك أن يُحوّل شرائحك إلى عروض ديناميكية تجذب جمهورك. يُقدم هذا البرنامج التعليمي دليلاً مُفصّلاً حول استخدام **Aspose.Slides لـ Python** لتحريك النص حرفًا بحرف مع تأخيرات قابلة للتخصيص.

### ما سوف تتعلمه:
- إعداد Aspose.Slides لـ Python
- تعليمات خطوة بخطوة لتحريك النص بالأحرف
- تكوين معلمات الرسوم المتحركة مثل التأخيرات
- حفظ العرض التقديمي الخاص بك مع الرسوم المتحركة

بنهاية هذا البرنامج التعليمي، ستكون جاهزًا لتحسين عروضك التقديمية بسهولة. لنبدأ بالتأكد من توفر جميع المتطلبات الأساسية.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

### المكتبات والتبعيات المطلوبة:
- **Aspose.Slides لـ Python**:المكتبة الأساسية لإنشاء عروض PowerPoint والتلاعب بها.
- **بايثون 3.x**:تأكد من أن بيئتك تقوم بتشغيل إصدار متوافق من Python. 

### متطلبات إعداد البيئة:
- قم بتثبيت pip (مثبت حزمة Python) إذا لم يكن متاحًا بالفعل.

### المتطلبات المعرفية:
- فهم أساسي لبرمجة بايثون
- المعرفة بكيفية التعامل مع النصوص والأشكال في PowerPoint

بعد تغطية هذه المتطلبات الأساسية، ستكون جاهزًا لإعداد Aspose.Slides لـ Python.

## إعداد Aspose.Slides لـ Python

لبدء تحريك النص باستخدام Aspose.Slides، اتبع الخطوات التالية:

### تثبيت:
استخدم pip لتثبيت المكتبة باستخدام هذا الأمر في محطتك الطرفية أو موجه الأوامر:

```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص:
- **نسخة تجريبية مجانية**:ابدأ باستكشاف الميزات دون تكاليف أولية.
- **رخصة مؤقتة**:احصل على ترخيص مؤقت للوصول الموسع بعد فترة التجربة، وهو مثالي لبيئات التطوير.
- **شراء**:فكر في شراء ترخيص كامل للاستخدام والدعم على المدى الطويل.

### التهيئة الأساسية:
فيما يلي كيفية تهيئة Aspose.Slides في البرنامج النصي Python الخاص بك:

```python
import aspose.slides as slides

# إنشاء مثيل عرض تقديمي جديد
presentation = slides.Presentation()
```

يؤدي هذا إلى إرساء الأساس لإضافة الرسوم المتحركة إلى شرائح PowerPoint الخاصة بك.

## دليل التنفيذ

الآن، دعونا نقوم بتقسيم عملية تحريك النص إلى خطوات قابلة للإدارة.

### إضافة شكل بيضاوي ونص إلى الشريحة الخاصة بك

#### ملخص:
لتحريك النص، سنقوم أولاً بإضافة شكل (قطع ناقص) لعرض النص عليه.

#### خطوات:
1. **إنشاء عرض تقديمي**  
   تهيئة كائن عرض تقديمي جديد.
2. **إضافة شكل بيضاوي**  
   قم بإدراج شكل بيضاوي على الشريحة الأولى وحدد موضعه وحجمه.
3. **تعيين النص للشكل**  
   أضف النص المطلوب إلى هذا الشكل.

إليك كيفية تنفيذ هذه الخطوات:

```python
# الخطوة 1: إنشاء عرض تقديمي جديد مع slides.Presentation() كعرض تقديمي:
    # الخطوة 2: إضافة شكل بيضاوي
    oval = presentation.slides[0].shapes.add_auto_shape(
        slides.ShapeType.ELLIPSE, 100, 100, 300, 150)
    
    # الخطوة 3: تعيين النص للشكل
    oval.text_frame.text = "The new animated text"
```

### تحريك النص بالأحرف

#### ملخص:
بعد ذلك، سنطبق تأثير الرسوم المتحركة لجعل كل حرف يظهر بشكل منفصل عند النقر فوقه.

#### خطوات:
1. **الوصول إلى الجدول الزمني للشريحة**  
   استرداد الجدول الزمني الذي يتم تخزين الرسوم المتحركة فيه.
2. **إضافة تأثير الرسوم المتحركة**  
   إنشاء تأثير مظهر يحرك النص عن طريق الحروف عند النقر عليها.
3. **تعيين التأخير بين الحروف**  
   قم بإعداد فترة زمنية بين كل جزء متحرك من النص.

دعونا ننفذ هذه الميزات:

```python
    # الوصول إلى الجدول الزمني الرئيسي للرسوم المتحركة للشريحة الأولى
timeline = presentation.slides[0].timeline

# أضف تأثير المظهر لتحريك النص حسب الحرف عند النقر عليه
effect = timeline.main_sequence.add_effect(
    oval, slides.animation.EffectType.APPEAR,
    slides.animation.EffectSubtype.NONE,
    slides.animation.EffectTriggerType.ON_CLICK)

# ضبط نوع الرسوم المتحركة والتأخير بين الحروف
effect.animate_text_type = slides.animation.AnimateTextType.BY_LETTER
effect.delay_between_text_parts = -1.5  # التأخير بالثواني (سلبي للحظة)
```

### حفظ العرض التقديمي الخاص بك

وأخيرًا، احفظ عرضك التقديمي في الدليل المخصص:

```python
    # حفظ العرض التقديمي مع الرسوم المتحركة
presentation.save("YOUR_OUTPUT_DIRECTORY/AnimateTextEffect_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}