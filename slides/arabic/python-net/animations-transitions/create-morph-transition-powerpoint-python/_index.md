---
"date": "2025-04-23"
"description": "تعلّم كيفية إنشاء انتقالات شكلية ديناميكية في عروض PowerPoint التقديمية باستخدام بايثون باستخدام مكتبة Aspose.Slides الفعّالة. سيساعدك هذا الدليل التفصيلي على تحسين عروضك التقديمية بسهولة."
"title": "إنشاء انتقال مورف في PowerPoint باستخدام Python و Aspose.Slides"
"url": "/ar/python-net/animations-transitions/create-morph-transition-powerpoint-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء انتقال مورف في PowerPoint باستخدام Aspose.Slides لـ Python
## مقدمة
هل ترغب في إضافة انتقالات ديناميكية إلى عروض PowerPoint التقديمية؟ يُتيح انتقال "Morph"، الذي قدمته مايكروسوفت، تحريك التغييرات بين الشرائح بسلاسة، مما يجعله مثاليًا لإنشاء عروض تقديمية جذابة واحترافية. سيرشدك هذا البرنامج التعليمي إلى كيفية تطبيق هذه الميزة باستخدام مكتبة Aspose.Slides القوية مع بايثون.
### ما سوف تتعلمه:
- إعداد البيئة الخاصة بك لـ Aspose.Slides.
- تعليمات خطوة بخطوة لإنشاء وتطبيق انتقال مورف بين الشرائح.
- أمثلة عملية لاستخدام Aspose.Slides في مشاريع Python.
- نصائح لتحسين الأداء واستكشاف المشكلات الشائعة وإصلاحها.
دعونا نلقي نظرة على المتطلبات الأساسية قبل أن نبدأ في تنفيذ هذه الميزة.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- **المكتبات المطلوبة**ثبّت Aspose.Slides. يجب أن يكون بيئتك مُهيأة باستخدام Python 3.x.
- **إعداد البيئة**:الفهم الأساسي لبرمجة Python والمعرفة باستخدام pip لتثبيت الحزم أمر ضروري.
- **متطلبات المعرفة**:ستكون المعرفة بهياكل شرائح PowerPoint مفيدة، على الرغم من أنها ليست ضرورية.
## إعداد Aspose.Slides لـ Python
للبدء في استخدام Aspose.Slides في بيئة Python الخاصة بك، اتبع الخطوات التالية:
### تركيب الأنابيب
أولاً، قم بتثبيت المكتبة باستخدام pip:
```bash
pip install aspose.slides
```
### خطوات الحصول على الترخيص
يمكنك الوصول إلى Aspose.Slides مجانًا لفترة تجريبية. للقيام بذلك، اتبع الخطوات التالية:
- احصل على **رخصة مؤقتة مجانية** من [موقع Aspose](https://purchase.aspose.com/temporary-license/).
- بدلاً من ذلك، يمكنك التفكير في شراء الإصدار الكامل إذا كنت بحاجة إلى ميزات ودعم موسع.
### التهيئة الأساسية
بعد التثبيت، قم بتهيئة بيئتك عن طريق استيراد Aspose.Slides:
```python
import aspose.slides as slides
```
سيؤدي هذا إلى إعداد مشروعك لبدء إنشاء عروض تقديمية باستخدام انتقالات التحويل.
## دليل التنفيذ
الآن، دعنا نستعرض الخطوات اللازمة لتنفيذ انتقال الشكل بين شريحتين في PowerPoint باستخدام Aspose.Slides.
### الخطوة 1: إنشاء عرض تقديمي جديد وإضافة الأشكال
ابدأ بإعداد كائن عرض تقديمي جديد:
```python
with slides.Presentation() as presentation:
    # أضف شكلًا تلقائيًا (مستطيلًا) مع النص إلى الشريحة الأولى.
    auto_shape = presentation.slides[0].shapes.add_auto_shape(
        slides.ShapeType.RECTANGLE, 100, 100, 400, 100
    )
    auto_shape.text_frame.text = "Test text"
```
**توضيح**ننشئ شريحة جديدة ونضيف شكلًا تلقائيًا - مستطيلًا مع نص. هذا يُمثل نقطة انطلاق لانتقالنا إلى الشكل المتغير.
### الخطوة 2: استنساخ الشريحة
بعد ذلك، قم باستنساخ الشريحة الأولى لإجراء التعديلات:
```python
    # استنسخ الشريحة الأولى لإنشاء شريحة ثانية.
presentation.slides.add_clone(presentation.slides[0])
```
**توضيح**:من خلال استنساخ الشريحة الأولية، نقوم بإعدادها للتعديل وتطبيق انتقال الشكل.
### الخطوة 3: تعديل موضع الشكل والحجم
ضبط الشكل على الشريحة المستنسخة:
```python
    # تعديل موضع وحجم الشكل على الشريحة الثانية.
presentation.slides[1].shapes[0].x += 100\presentation.slides[1].shapes[0].y += 50\presentation.slides[1].shapes[0].width -= 200\presentation.slides[1].shapes[0].height -= 10
```
**توضيح**:إن تغيير أبعاد الشكل وموضعه يسمح لنا بتصور تأثير التحول بين الشرائح.
### الخطوة 4: تطبيق Morph Transition
وأخيرًا، قم بتطبيق انتقال الشكل:
```python
    # قم بتطبيق انتقال الشكل على الشريحة الثانية.
presentation.slides[1].slide_show_transition.type = slides.slideshow.TransitionType.MORPH
```
**توضيح**:هذه الخطوة مهمة لأنها تؤدي إلى تحريك الرسوم المتحركة بسلاسة بين الشريحتين.
### الخطوة 5: حفظ العرض التقديمي
احفظ عملك:
```python
    # احفظ العرض التقديمي في دليل الإخراج المحدد.
presentation.save("YOUR_OUTPUT_DIRECTORY/transition_SupportOfMorphTransition_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}