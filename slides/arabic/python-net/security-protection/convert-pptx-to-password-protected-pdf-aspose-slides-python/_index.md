---
"date": "2025-04-23"
"description": "تعرف على كيفية تحويل عروض PowerPoint بشكل آمن إلى ملفات PDF محمية بكلمة مرور باستخدام Aspose.Slides for Python."
"title": "تحويل PPTX إلى PDF محمي بكلمة مرور باستخدام Aspose.Slides في Python"
"url": "/ar/python-net/security-protection/convert-pptx-to-password-protected-pdf-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تحويل عرض تقديمي من PowerPoint إلى ملف PDF محمي بكلمة مرور باستخدام Aspose.Slides لـ Python

في عصرنا الرقمي، تُعدّ مشاركة العروض التقديمية بأمان أمرًا بالغ الأهمية. تخيّل أنك تحتاج إلى توزيع مقترح عملك أو موادك التعليمية مع ضمان وصول الأشخاص المصرح لهم فقط إليها. هنا يأتي دور تحويل عرض PowerPoint التقديمي إلى ملف PDF محمي بكلمة مرور. سيرشدك هذا البرنامج التعليمي إلى كيفية استخدام Aspose.Slides للغة Python لتحقيق هذه الوظيفة بسلاسة.

**ما سوف تتعلمه:**
- كيفية تثبيت وإعداد Aspose.Slides لـ Python
- تحويل ملفات PPTX إلى ملفات PDF آمنة ومحمية بكلمة مرور
- تخصيص خيارات تصدير PDF لتحسين الأمان

دعونا نتعمق في المتطلبات الأساسية قبل أن نبدأ!

## المتطلبات الأساسية

قبل المتابعة بهذا البرنامج التعليمي، تأكد من أن لديك ما يلي:

1. **تم تثبيت بايثون**:تأكد من تشغيل إصدار متوافق من Python (يوصى باستخدام 3.x).
2. **مكتبة Aspose.Slides**:سوف تحتاج إلى تثبيت Aspose.Slides لـ Python باستخدام pip.
3. **المعرفة الأساسية بلغة بايثون**:ستكون المعرفة بمفاهيم البرمجة الأساسية في Python مفيدة.

## إعداد Aspose.Slides لـ Python

للبدء، ستحتاج إلى تثبيت مكتبة Aspose.Slides. يُمكنك القيام بذلك بسهولة عبر pip:

```bash
pip install aspose.slides
```

### خطوات الحصول على الترخيص

يتطلب Aspose.Slides ترخيصًا للاستفادة من كافة الوظائف، ولكن يمكنك البدء بإصدار تجريبي مجاني أو الحصول على ترخيص مؤقت لاستكشاف ميزاته.

- **نسخة تجريبية مجانية**:الوصول إلى ميزات محدودة دون تكلفة.
- **رخصة مؤقتة**:اطلب ترخيصًا مؤقتًا إذا كنت ترغب في تجربة المجموعة الكاملة من الميزات.
- **شراء**:للاستخدام طويل الأمد، فكر في شراء ترخيص. 

### التهيئة الأساسية

بمجرد التثبيت، قم بتهيئة بيئتك وإعداد مسارات الدليل لملفات الإدخال والإخراج:

```python
import aspose.slides as slides

document_dir = "YOUR_DOCUMENT_DIRECTORY/"
output_dir = "YOUR_OUTPUT_DIRECTORY/"
```

## دليل التنفيذ: تحويل PPTX إلى ملف PDF محمي بكلمة مرور

الآن بعد أن قمت بإعداد Aspose.Slides، دعنا ننتقل إلى عملية تحويل العرض التقديمي إلى ملف PDF آمن.

### الخطوة 1: تحميل العرض التقديمي الخاص بك

أولاً، قم بتحميل ملف PowerPoint الخاص بك باستخدام `Presentation` تتضمن هذه الخطوة تحديد المسار الذي يوجد به ملف PPTX الخاص بك:

```python
with slides.Presentation(document_dir + "welcome-to-powerpoint.pptx") as presentation:
```

### الخطوة 2: تكوين خيارات تصدير PDF

بعد ذلك، قم بإنشاء مثيل لـ `PdfOptions`يسمح لك هذا الكائن بتعيين خيارات مختلفة لعملية التصدير، بما في ذلك حماية كلمة المرور:

```python
class PdfOptions:
    def __init__(self):
        self.password = None  # التهيئة بدون كلمة مرور افتراضيًا

pdf_options = slides.export.PdfOptions()
pdf_options.password = "your_password"
```

في مقتطف التعليمات البرمجية هذا، استبدل `"your_password"` مع إعدادات أمان PDF المطلوبة.

### الخطوة 3: حفظ العرض التقديمي كملف PDF محمي بكلمة مرور

أخيرًا، احفظ العرض التقديمي الخاص بك في دليل الإخراج المطلوب بصيغة ملف PDF محمي بكلمة مرور:

```python
class SaveFormat:
    PDF = 'PDF'

def save(presentation, path, format, options):
    # محاكاة وظيفة الحفظ
    pass

# استخدام أساليب وهمية لمحاكاة وظائف Aspose.Slides الفعلية لأغراض التوضيح.
save(presentation, output_dir + "secure_pptx.pdf\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}