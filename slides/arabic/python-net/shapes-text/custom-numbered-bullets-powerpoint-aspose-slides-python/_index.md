---
"date": "2025-04-24"
"description": "تعرّف على كيفية إنشاء قوائم نقطية مرقمة مخصصة في PowerPoint باستخدام Aspose.Slides لـ Python. حسّن عروضك التقديمية بتنسيق فريد."
"title": "قوائم نقطية مرقمة مخصصة في PowerPoint باستخدام Aspose.Slides لـ Python"
"url": "/ar/python-net/shapes-text/custom-numbered-bullets-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# قوائم نقطية مرقمة مخصصة في PowerPoint باستخدام Aspose.Slides لـ Python

## مقدمة
هل ترغب في الارتقاء بجاذبية عروض PowerPoint التقديمية إلى مستوى أعلى من مجرد النقاط الأساسية؟ سواءً كان ذلك لتقارير الشركات أو المحاضرات الأكاديمية أو اجتماعات العمل، فإن تخصيص القوائم الأساسية يجذب انتباه جمهورك ويحافظ عليه بفعالية أكبر. **Aspose.Slides لـ Python**، لديك المرونة اللازمة لتخصيص النقاط المرقمة وفقًا لاحتياجات التنسيق الفريدة لديك.

في هذا الدليل الشامل، سنوضح كيفية إعداد نقاط مرقمة مخصصة باستخدام Aspose.Slides في PowerPoint باستخدام Python. بدمج هذه الميزة في عروضك التقديمية، يمكنك الحصول على مظهر احترافي وأنيق.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides لـ Python
- إنشاء قوائم نقطية مرقمة مخصصة
- تكوين إعدادات الرصاصة برمجيًا
- تحسين الأداء واستكشاف المشكلات الشائعة وإصلاحها

لنبدأ! تأكد من تجهيز كل شيء للمتابعة.

## المتطلبات الأساسية
قبل تنفيذ النقاط المرقمة المخصصة باستخدام Aspose.Slides لـ Python، تأكد من أن لديك:

### المكتبات المطلوبة:
- **Aspose.Slides لـ Python**:مكتبة قوية لإنشاء عروض PowerPoint والتلاعب بها.

### إعداد البيئة:
- تم تثبيت Python 3.x على نظامك.
- إن الفهم الأساسي لمفاهيم برمجة Python مفيد ولكنه ليس إلزاميًا.

## إعداد Aspose.Slides لـ Python
للبدء، قم بتثبيت `aspose.slides` المكتبة باستخدام pip:

```bash
pip install aspose.slides
```

### الحصول على الترخيص:
Aspose.Slides منتج تجاري يُقدّم نسخة تجريبية مجانية لاختبار إمكانياته. يمكنك الحصول على ترخيص مؤقت أو شراء ترخيص للاستخدام المستمر.

- **نسخة تجريبية مجانية**:الوصول إلى الوظائف الأساسية دون قيود.
- **رخصة مؤقتة**:طلب على موقع Aspose للحصول على حق الوصول الكامل مؤقتًا.
- **شراء**:فكر في شراء ترخيص للمشاريع طويلة الأمد.

### التهيئة الأساسية:
بمجرد التثبيت، قم بتشغيل العرض التقديمي الخاص بك على النحو التالي:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # الكود الخاص بك هنا...
```

يقوم هذا الإعداد بإعداد البيئة لإضافة نقاط مرقمة مخصصة إلى شرائح PowerPoint الخاصة بك.

## دليل التنفيذ
لنبدأ بإنشاء قوائم نقطية مرقمة مخصصة. كل خطوة مُقسّمة لتسهيل التنفيذ ووضوحه.

### إضافة شكل مستطيل باستخدام إطارات النص
#### ملخص:
أولاً، أضف شكلاً يحتوي على إطارات نصية للنقاط النقطية.

```python
# أضف شكل مستطيل إلى الشريحة الأولى
shape = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 200, 200, 400, 200)
```
- **شرح المعلمات**: ال `add_auto_shape` تأخذ الطريقة معلمات لنوع الشكل (المستطيل)، والموضع (إحداثيات x و y)، والأبعاد (العرض والارتفاع).

### تكوين إطارات النص
#### ملخص:
قم بالوصول إلى إطار النص الخاص بالمستطيل لإضافة نقاط نقطية.

```python
# الوصول إلى إطار النص الخاص بالشكل التلقائي الذي تم إنشاؤه
text_frame = shape.text_frame

# قم بإزالة أي فقرة افتراضية موجودة إذا كانت موجودة
text_frame.paragraphs.clear()
```
- **غاية**:يضمن وجود سجل نظيف قبل إضافة نقاط مخصصة.

### إضافة نقاط مرقمة مخصصة
#### ملخص:
أضف فقرات بإعدادات نقطية محددة:

```python
# إضافة فقرات بنقاط مرقمة مخصصة
for start_number, bullet_text in [(2, "bullet 2"), (3, "bullet 3"), (7, "bullet 7")]:
    paragraph = slides.Paragraph()
    paragraph.text = bullet_text
    paragraph.paragraph_format.depth = 4
    paragraph.paragraph_format.bullet.numbered_bullet_start_with = start_number
    paragraph.paragraph_format.bullet.type = slides.BulletType.NUMBERED
    text_frame.paragraphs.add(paragraph)
```
- **إعدادات**:تبدأ كل فقرة برقم محدد، مما يوفر المرونة والتحكم في تنسيق العرض.

### حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الذي قمت بتكوينه:

```python
# احفظ العرض التقديمي\presentation.save("YOUR_OUTPUT_DIRECTORY/text_set_custom_bullets_number_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}