---
"date": "2025-04-23"
"description": "تعرف على كيفية أتمتة إنشاء رسومات SmartArt في عروض PowerPoint باستخدام Aspose.Slides لـ Python، بما في ذلك استخراج الصور المصغرة وحفظها بكفاءة."
"title": "كيفية إنشاء واسترجاع الصور المصغرة SmartArt باستخدام Aspose.Slides لـ Python"
"url": "/ar/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء واسترجاع الصور المصغرة SmartArt باستخدام Aspose.Slides لـ Python

## مقدمة

إنشاء عروض تقديمية جذابة بصريًا أمرٌ أساسي لجذب انتباه جمهورك. ومن الطرق الفعّالة لتحسين عروض الشرائح دمج رسومات ديناميكية مثل SmartArt في عروض PowerPoint التقديمية. إذا كنت تبحث عن طريقة آلية لإنشاء هذه العناصر المرئية واستخراج الصور المصغرة منها، فسيكون هذا الدليل حول "Aspose.Slides Python" قيّمًا للغاية.

باستخدام Aspose.Slides للغة بايثون، يمكنك بسهولة إنشاء رسومات SmartArt، والوصول إلى عُقد محددة داخلها، واسترجاع صور مصغرة لها، وحفظها لمشاريعك. سيشرح لك هذا البرنامج التعليمي كل خطوة بالتفصيل.

**ما سوف تتعلمه:**
- كيفية تثبيت وإعداد Aspose.Slides لـ Python.
- إنشاء رسم SmartArt في عرض تقديمي في PowerPoint.
- الوصول إلى العقد داخل رسم SmartArt.
- استخراج وحفظ صورة مصغرة من عقدة معينة.

دعونا نتعمق في المتطلبات الأساسية قبل أن نبدأ.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي جاهزًا:

- **المكتبات المطلوبة:** ستحتاج إلى Aspose.Slides لـ Python. تأكد من أن بيئتك تدعم Python 3.x.
- **متطلبات إعداد البيئة:** تثبيت عمل لـ Python وبيئة تطوير متكاملة مناسبة أو محرر نصوص مثل VSCode أو PyCharm.
- **المتطلبات المعرفية:** فهم أساسي لبرمجة بايثون، بما في ذلك تعريفات الوظائف وعمليات الملفات.

## إعداد Aspose.Slides لـ Python

أولاً، عليك تثبيت مكتبة Aspose.Slides. يُمكنك القيام بذلك بسهولة باستخدام pip:

```bash
pip install aspose.slides
```

بعد التثبيت، احصل على ترخيص إذا كنت ترغب في استكشاف جميع الميزات دون قيود. يمكنك البدء بفترة تجريبية مجانية، أو التقدم بطلب للحصول على ترخيص مؤقت، أو شرائه للاستخدام طويل الأمد.

لتهيئة Aspose.Slides في بيئة Python الخاصة بك، قم باستيراد المكتبة في بداية البرنامج النصي الخاص بك:

```python
import aspose.slides as slides
```

## دليل التنفيذ

دعنا نقسم العملية إلى خطوات واضحة لإنشاء صورة مصغرة SmartArt واسترجاعها.

### الخطوة 1: إنشاء مثيل عرض تقديمي جديد

ابدأ بإنشاء نموذج عرض تقديمي. سيكون هذا النموذج هو الحاوية التي ستضيف إليها رسم SmartArt.

```python
with slides.Presentation() as pres:
```

استخدام `with` يضمن إدارة الموارد بشكل صحيح، وحفظ الملف وإغلاقه تلقائيًا عند الخروج.

### الخطوة 2: إضافة SmartArt إلى الشريحة الأولى

بعد ذلك، سنضيف رسم SmartArt إلى الشريحة الأولى. إليك كيفية القيام بذلك:

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

يؤدي هذا إلى إضافة تخطيط دورة أساسي لرسومات SmartArt في الموضع (10، 10) بأبعاد 400 × 300 بكسل.

### الخطوة 3: الوصول إلى العقدة الثانية

الوصول إلى عُقد مُحددة ضمن SmartArt. في هذا المثال، نصل إلى العُقدة الثانية:

```python
node = smart.nodes[1]
```

يتم فهرسة العقد بدءًا من الصفر؛ وبالتالي، `nodes[1]` يشير إلى العقدة الثانية في القائمة.

### الخطوة 4: استرداد الصورة المصغرة

للحصول على صورة مصغرة للشكل داخل العقدة المحددة:

```python
image = node.shapes[0].get_image()
```

يؤدي هذا إلى استرداد صورة الشكل الأول كصورة مصغرة من عقدة SmartArt المحددة.

### الخطوة 5: حفظ الصورة المسترجعة

وأخيرًا، احفظ هذه الصورة المصغرة في الموقع المطلوب بتنسيق JPEG:

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}