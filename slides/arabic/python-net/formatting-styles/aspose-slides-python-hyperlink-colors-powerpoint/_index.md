---
"date": "2025-04-23"
"description": "تعرّف على كيفية تخصيص ألوان الروابط التشعبية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Python. حسّن عروضك التقديمية بكفاءة باستخدام أنماط روابط مخصصة."
"title": "كيفية تعيين ألوان الارتباطات التشعبية في PowerPoint باستخدام Aspose.Slides لـ Python"
"url": "/ar/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تعيين ألوان الارتباطات التشعبية في PowerPoint باستخدام Aspose.Slides لـ Python

## مقدمة

تحسين المظهر المرئي لعروض PowerPoint التقديمية من خلال تخصيص ألوان الروابط التشعبية أمر سهل مع Aspose.Slides لـ Python. سيرشدك هذا الدليل إلى كيفية ضبط ألوان الروابط التشعبية في شرائحك باستخدام Python.

**ما سوف تتعلمه:**
- كيفية تعيين لون الارتباط التشعبي داخل أشكال النص في PowerPoint.
- الخطوات المتبعة لإنشاء عرض تقديمي جذاب بصريًا.
- الميزات الرئيسية لـ Aspose.Slides لـ Python التي تسهل هذا التخصيص.

دعونا نلقي نظرة على المتطلبات الأساسية اللازمة قبل أن نبدأ.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن بيئتك جاهزة بما يلي:
- **المكتبات والإصدارات:** ثَبَّتَ `aspose.slides` المكتبة. تأكد من تثبيت Python على جهازك.
- **متطلبات إعداد البيئة:** يفترض هذا البرنامج التعليمي إعدادًا أساسيًا لـ Python على أنظمة Windows أو Mac أو Linux.
- **المتطلبات المعرفية:** ستكون المعرفة ببرمجة بايثون مفيدة.

## إعداد Aspose.Slides لـ Python

لبدء استخدام Aspose.Slides لـ Python، قم بتثبيت الحزمة عبر pip:

```bash
pip install aspose.slides
```

**خطوات الحصول على الترخيص:**
- **نسخة تجريبية مجانية:** تنزيل النسخة التجريبية من [صفحة إصدار Aspose](https://releases.aspose.com/slides/python-net/).
- **رخصة مؤقتة:** طلب ترخيص مؤقت على [صفحة الشراء](https://purchase.aspose.com/temporary-license/) للوصول الموسع.
- **شراء:** لفتح الميزات بالكامل دون قيود، فكر في شراء ترخيص من [صفحة شراء Aspose](https://purchase.aspose.com/buy).

**التهيئة الأساسية:**
بمجرد التثبيت والترخيص، قم باستيراد Aspose.Slides في البرنامج النصي الخاص بك:

```python
import aspose.slides as slides
```

## دليل التنفيذ

يرشدك هذا القسم خلال عملية تعيين ألوان الارتباط التشعبي ضمن عرض تقديمي في PowerPoint.

### تعيين ميزة لون الارتباط التشعبي

#### ملخص

خصّص لون الروابط التشعبية المُضمّنة في أشكال النصوص باستخدام Aspose.Slides لبايثون. يُحسّن هذا من سهولة القراءة والجاذبية البصرية.

##### الخطوة 1: إنشاء عرض تقديمي جديد

إنشاء مثيل للعرض التقديمي:

```python
with slides.Presentation() as presentation:
    # الكود الخاص بك هنا
```

##### الخطوة 2: إضافة شكل مع نص

أضف شكل مستطيل إلى الشريحة الأولى وأدرج نصًا يتضمن ارتباطًا تشعبيًا.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### الخطوة 3: تعيين خصائص الارتباط التشعبي

تعيين الرابط التشعبي وتعيين لونه. `hyperlink_click` تحدد الخاصية المكان الذي يجب أن ينتقل إليه الرابط عند النقر فوقه.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# قم بتعيين مصدر اللون لرابط التشعبات إلى تنسيق الجزء وحدد نوع التعبئة واللون.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### الخطوة 4: حفظ العرض التقديمي

احفظ العرض التقديمي الخاص بك في الدليل المحدد:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}