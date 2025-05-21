---
"date": "2025-04-23"
"description": "تعرّف على كيفية أتمتة عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Python. يغطي هذا الدليل الإعداد، وإنشاء الشرائح، وإضافة الأشكال، وحفظ عرضك التقديمي بسهولة."
"title": "إنشاء عروض تقديمية على PowerPoint باستخدام Aspose.Slides لـ Python - دليل كامل"
"url": "/ar/python-net/getting-started/create-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء وحفظ عرض تقديمي في PowerPoint باستخدام Aspose.Slides لـ Python

## مقدمة

هل ترغب في أتمتة إنشاء عروض PowerPoint التقديمية باستخدام بايثون؟ سواءً كنت تُنشئ تقارير أو عروض شرائح أو أي مواد عرض تقديمي برمجيًا، فإن إتقان هذه المهمة سيوفر عليك الكثير من الوقت. سيرشدك هذا البرنامج التعليمي خلال إنشاء عرض تقديمي جديد على PowerPoint باستخدام Aspose.Slides لبايثون، وإضافة شكل تلقائي (مثل خط)، وحفظه بسهولة.

**ما سوف تتعلمه:**
- كيفية إعداد البيئة الخاصة بك لاستخدام Aspose.Slides.
- عملية إنشاء عرض تقديمي PowerPoint في Python.
- إضافة الأشكال إلى الشرائح برمجيًا.
- حفظ العروض التقديمية بسهولة.

دعنا نتعمق في المتطلبات الأساسية أولاً حتى تكون مستعدًا لبدء الترميز!

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. **المكتبات المطلوبة**:سوف تحتاج إلى `aspose.slides` المكتبة لهذا البرنامج التعليمي.
2. **نسخة بايثون**:يوصى باستخدام Python 3.x (تأكد من التوافق مع Aspose.Slides).
3. **إعداد البيئة**:
   - قم بتثبيت Python وإعداد بيئة افتراضية إذا كنت ترغب في ذلك.

4. **متطلبات المعرفة**:
   - فهم أساسي لبرمجة بايثون.
   - المعرفة بكيفية التعامل مع الملفات في بايثون.

بعد إعدادك، دعنا ننتقل إلى تثبيت Aspose.Slides لـ Python.

## إعداد Aspose.Slides لـ Python

### تثبيت

يمكنك بسهولة تثبيت Aspose.Slides عبر pip:

```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص

يوفر Aspose.Slides نسخة تجريبية مجانية، وتراخيص مؤقتة، وخيارات شراء:
- **نسخة تجريبية مجانية**:لاختبار قدرات المكتبة دون قيود.
- **رخصة مؤقتة**:احصل على هذا لأغراض التقييم على جهازك المحلي.
- **شراء**:للإستخدام التجاري طويل الأمد.

يزور [شراء Aspose](https://purchase.aspose.com/buy) لاستكشاف هذه الخيارات. بعد الحصول على الترخيص، يمكنك إعداده في الكود الخاص بك:

```python
import aspose.slides as slides

# تطبيق الترخيص (على افتراض أن لديك ملف .lic)
license = slides.License()
license.set_license("path_to_your_licence_file.lic")
```

## دليل التنفيذ

الآن، دعنا نتعرف على كيفية إنشاء عرض تقديمي وحفظه.

### إنشاء عرض تقديمي جديد

الهدف الأساسي من هذا البرنامج التعليمي هو توضيح كيفية إنشاء عرض تقديمي لبرنامج PowerPoint من الصفر باستخدام Python.

#### ملخص

سنبدأ بتهيئة `Presentation` الكائن الذي يمثل ملف العرض التقديمي الخاص بنا.

```python
import aspose.slides as slides

# إنشاء كائن عرض تقديمي يمثل ملف عرض تقديمي مع slides.Presentation() كعرض تقديمي:
    # احصل على الشريحة الأولى (الشريحة الافتراضية التي تمت إضافتها بواسطة Aspose.Slides)
slide = presentation.slides[0]

    # إضافة شكل تلقائي من نوع الخط إلى الشريحة
slide.shapes.add_auto_shape(slides.ShapeType.LINE, 50, 150, 300, 0)

    # حفظ العرض التقديمي بتنسيق PPTX
presentation.save("YOUR_OUTPUT_DIRECTORY/create_new_presentation_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}