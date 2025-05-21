---
"date": "2025-04-24"
"description": "تعرف على كيفية إنشاء قواعد الرجوع إلى الخطوط وإدارتها باستخدام Aspose.Slides لـ Python لضمان اتساق عروضك التقديمية عبر أنظمة مختلفة."
"title": "إتقان استخدام الخطوط البديلة في Aspose.Slides للغة بايثون - دليل شامل"
"url": "/ar/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان استخدام الخطوط البديلة في Aspose.Slides للغة بايثون: دليل شامل

## مقدمة

قد تكون مشكلات توافق الخطوط صعبة عند إنشاء العروض التقديمية، خاصةً مع أحرف Unicode التي لا تدعمها الخطوط الأساسية. **Aspose.Slides لـ Python** يوفر حلاً قويًا من خلال قواعد الرجوع إلى الخطوط، مما يضمن جاذبية العرض التقديمي ووضوحه عبر أنظمة مختلفة.

في هذا الدليل، سنستكشف كيفية إنشاء وإدارة قواعد الخطوط البديلة باستخدام Aspose.Slides لبايثون. ستتعلم:
- إعداد بيئتك باستخدام Aspose.Slides
- إنشاء مجموعة من قواعد الرجوع إلى الخطوط
- إدارة هذه القواعد عن طريق إضافة أو إزالة الخطوط استنادًا إلى نطاقات Unicode
- تطبيق القواعد على العروض التقديمية وتقديم الشرائح كصور

دعونا نبدأ بإعداد البيئة الخاصة بك.

## المتطلبات الأساسية

تأكد من جاهزية بيئتك لهذه المهمة. إليك ما ستحتاجه:
1. **Aspose.Slides لـ Python**:تدير هذه المكتبة قواعد الرجوع إلى الخطوط.
2. **بيئة بايثون**:تأكد من تثبيت Python (الإصدار 3.6 أو أحدث).
3. **المعرفة الأساسية بلغة بايثون**:ستكون المعرفة بقواعد ومفاهيم Python مفيدة أثناء تعمقنا في مقتطفات التعليمات البرمجية.

## إعداد Aspose.Slides لـ Python

### تثبيت

للبدء، قم بتثبيت مكتبة Aspose.Slides باستخدام pip:

```bash
pip install aspose.slides
```

### الحصول على الترخيص

يقدم Aspose ترخيصًا تجريبيًا مجانيًا لاستكشاف ميزاته دون قيود. إليك كيفية الحصول عليه:
- يزور [صفحة شراء Aspose](https://purchase.aspose.com/buy) لشراء الخيارات أو الوصول إلى ترخيص مؤقت.
- بدلاً من ذلك، قم بتنزيل نسخة تجريبية مجانية من [قسم التنزيلات](https://releases.aspose.com/slides/python-net/).

### التهيئة الأساسية

بمجرد التثبيت، قم بتهيئة Aspose.Slides في البرنامج النصي Python الخاص بك:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## دليل التنفيذ

### إنشاء قواعد الرجوع للخطوط وإدارتها

#### ملخص

تضمن قواعد الرجوع إلى الخطوط أن جميع الأحرف في العرض التقديمي لديك لها خط مناسب، مما يحافظ على قابلية القراءة للغات ذات مجموعات الأحرف الفريدة.

#### خطوات التنفيذ

**1. إنشاء مجموعة قواعد احتياطية للخطوط**

ابدأ بإنشاء مجموعة لتحديد الخطوط البديلة:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. إضافة قاعدة بديلة للخط**

قم بتحديد قاعدة تحدد نطاق Unicode والخط البديل:

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **حدود**: `0x400` هي بداية نطاق Unicode، `0x4FF` هي النهاية، و `"Times New Roman"` هو الخط الاحتياطي.

**3. إدارة القواعد الحالية**

كرر كل قاعدة لتعديلها حسب الحاجة:

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. إزالة القاعدة**

إذا لزم الأمر، قم بإزالة القاعدة الأولى من مجموعتك:

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### تطبيق قواعد الرجوع إلى الخطوط على العرض التقديمي وتقديم صورة

#### ملخص

بمجرد إعداد قواعد الخطوط الاحتياطية، قم بتطبيقها على العروض التقديمية للتأكد من أن النص يستخدم الخطوط الاحتياطية المحددة عند الضرورة.

#### خطوات التنفيذ

**1. تهيئة البيئة الخاصة بك**

إعداد الدلائل للإدخال والإخراج:

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. تطبيق قواعد الرجوع إلى الخلف على العرض التقديمي**

قم بتحميل ملف العرض التقديمي الخاص بك وقم بتطبيق قواعد الخط:

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}