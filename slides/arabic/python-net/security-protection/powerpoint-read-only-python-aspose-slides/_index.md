---
"date": "2025-04-23"
"description": "تعرّف على كيفية ضبط عروض PowerPoint التقديمية للقراءة فقط وعدّ الشرائح برمجيًا باستخدام Aspose.Slides لـ Python. مثالي لمشاركة المستندات بأمان وإعداد التقارير تلقائيًا."
"title": "تعيين PowerPoint للقراءة فقط وحساب الشرائح باستخدام Python باستخدام Aspose.Slides"
"url": "/ar/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تعيين PowerPoint للقراءة فقط وحساب الشرائح باستخدام Python

## مقدمة
هل واجهتَ يومًا تحدي توزيع عرض تقديمي مع ضمان عدم تغييره؟ أو ربما كنتَ تبحث عن طريقة سهلة للتحقق من عدد الشرائح في عرضك التقديمي دون فتحه؟ مع **Aspose.Slides لـ Python**تصبح هذه المهام سهلة وبسيطة. سيرشدك هذا البرنامج التعليمي إلى كيفية ضبط عروض PowerPoint التقديمية للقراءة فقط وحساب الشرائح باستخدام Aspose.Slides، مما يوفر حلاً فعالاً لإدارة ملفات PowerPoint برمجيًا.

**ما سوف تتعلمه:**
- كيفية إعداد الحماية ضد الكتابة على عرض تقديمي في PowerPoint.
- كيفية حفظ ملف PowerPoint مع قيود القراءة فقط.
- كيفية تحميل العرض التقديمي وحساب عدد الشرائح بكفاءة.

دعونا نتعرف على كيفية تحقيق هذه المهام بسلاسة في Python.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك:
- **بايثون 3.6+** تم تثبيته على نظامك.
- الوصول إلى واجهة سطر الأوامر لتثبيت الحزم.

ستحتاج أيضًا إلى تثبيت Aspose.Slides لـ Python. تتيح لك هذه المكتبة القوية معالجة ملفات PowerPoint بشكل متقدم مباشرةً من بيئة Python. مع أن الإصدار المجاني يتيح وظائف محدودة، إلا أن الحصول على ترخيص (سواءً من خلال نسخة تجريبية مجانية أو شراء) يُوسّع الإمكانيات بشكل كبير.

## إعداد Aspose.Slides لـ Python
لبدء العمل مع Aspose.Slides في بايثون، عليك تثبيته أولًا. إليك الطريقة:

### تثبيت pip
قم بتشغيل الأمر التالي في محطتك الطرفية أو موجه الأوامر:

```bash
pip install aspose.slides
```

سيؤدي هذا إلى تنزيل أحدث إصدار من Aspose.Slides لـ Python وتثبيته.

### خطوات الحصول على الترخيص
1. **نسخة تجريبية مجانية**:ابدأ بإصدار تجريبي مجاني لاستكشاف الوظائف الأساسية.
2. **رخصة مؤقتة**:احصل على ترخيص مؤقت لفتح الميزات الكاملة أثناء فترة التقييم الخاصة بك.
3. **شراء**:فكر في شراء ترخيص لمواصلة الوصول والدعم.

بمجرد حصولك على ملف الترخيص، قم بتحميله في البرنامج النصي الخاص بك على النحو التالي:

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## دليل التنفيذ
في هذا القسم، سنقوم بتقسيم التنفيذ إلى ميزتين رئيسيتين: تعيين العرض التقديمي للقراءة فقط وحساب الشرائح.

### الميزة 1: حفظ العرض التقديمي للقراءة فقط
#### ملخص
تتيح لك هذه الميزة حماية ملف PowerPoint ضد الكتابة، مما يضمن عدم إمكانية تعديله دون إدخال كلمة مرور. يُعد هذا مفيدًا بشكل خاص لتوزيع العروض التقديمية التي يجب أن تبقى دون تغيير من قِبل المستلم.

#### خطوات
##### الخطوة 1: إنشاء كائن عرض تقديمي
ابدأ بإنشاء `Presentation` هذا الكائن يمثل ملف PPT الخاص بك في Python.

```python
import aspose.slides as slides

class ReadWriteProtection:
    def __init__(self, password):
        self.password = password

    def set_write_protection(self, presentation_path, output_directory):
        with slides.Presentation(presentation_path) as presentation:
            presentation.protection_manager.set_write_protection(self.password)
            presentation.save(f"{output_directory}/save_as_read_only_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}