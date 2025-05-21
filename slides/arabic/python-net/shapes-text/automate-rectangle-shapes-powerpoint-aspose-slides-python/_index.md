---
"date": "2025-04-23"
"description": "تعلّم كيفية أتمتة إنشاء وتنسيق أشكال المستطيلات في PowerPoint باستخدام Aspose.Slides للغة بايثون. طوّر مهاراتك في العروض التقديمية بسهولة."
"title": "أتمتة أشكال المستطيل في PowerPoint باستخدام Aspose.Slides لـ Python"
"url": "/ar/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء شكل مستطيل وتنسيقه في PowerPoint باستخدام Aspose.Slides لـ Python
## مقدمة
هل سبق لك أن وجدت نفسك بحاجة إلى إضافة أشكال مخصصة بسرعة إلى عروض PowerPoint التقديمية ولكنك تعاني من نقص الأتمتة؟ إذا مللت من تنسيق المستطيلات يدويًا شريحةً تلو الأخرى، فهذا البرنامج التعليمي هنا لإنقاذك. باستخدام "Aspose.Slides for Python"، سنُؤتمت إضافة شكل مستطيل وتصميمه في بضعة أسطر برمجية فقط. بنهاية هذا الدليل، ستتقن:
- إنشاء شكل مستطيل برمجيًا
- تطبيق خيارات التنسيق مثل اللون ونمط الخط
- حفظ العرض التقديمي الخاص بك بسهولة
دعونا نتعمق في كيفية تحويل عملية إنشاء الشريحة الخاصة بك!
### المتطلبات الأساسية
قبل أن نبدأ في الترميز، تأكد من أن لديك ما يلي جاهزًا:
- **بايثون** تم تثبيته على جهازك (يوصى بالإصدار 3.6 أو أعلى)
- **Aspose.Slides لـ Python** المكتبة التي تسمح لنا بالتلاعب بعروض PowerPoint
- فهم أساسي لمفاهيم برمجة بايثون والتعرف على تثبيت الحزم باستخدام pip
## إعداد Aspose.Slides لـ Python
### تثبيت
لتثبيت حزمة Aspose.Slides، افتح المحطة الطرفية أو موجه الأوامر وقم بتشغيل:
```bash
pip install aspose.slides
```
يقوم هذا الأمر بجلب أحدث إصدار من Aspose.Slides لـ Python من PyPI وتثبيته.
### الحصول على الترخيص
Aspose.Slides منتج تجاري، ولكن يمكنك البدء باستخدامه باستخدام نسخة تجريبية مجانية. إليك كيفية الحصول عليها:
1. **نسخة تجريبية مجانية:** يزور [نسخة تجريبية مجانية من Aspose](https://releases.aspose.com/slides/python-net/) والتسجيل للحصول على التقييم.
2. **رخصة مؤقتة:** لإجراء اختبارات أكثر شمولاً دون قيود، اطلب ترخيصًا مؤقتًا على [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).
3. **شراء:** عندما تكون مستعدًا للبث المباشر، قم بشراء ترخيص من خلال [صفحة شراء Aspose](https://purchase.aspose.com/buy).
بمجرد الحصول عليها، اتبع الوثائق لتطبيق الترخيص في مشروعك.
### التهيئة الأساسية
إليك كيفية تهيئة Aspose.Slides لـ Python:
```python
import aspose.slides as slides
\# تهيئة فئة العرض التقديمي
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
يؤدي هذا المقطع إلى إنشاء عرض تقديمي جديد ويؤكد أنه جاهز للتلاعب به.
## دليل التنفيذ
### إنشاء شكل المستطيل
#### ملخص
في هذا القسم، سنركز على إضافة شكل مستطيل إلى شريحة PowerPoint باستخدام Aspose.Slides لـ Python.
#### خطوات إنشاء الشكل
1. **فتح أو إنشاء عرض تقديمي:**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # سنضيف المستطيل الخاص بنا هنا
   ```
2. **الوصول إلى الشريحة:**
   استرجاع الشريحة الأولى التي نريد إضافة الشكل إليها.
   ```python
   slide = pres.slides[0]
   ```
3. **إضافة شكل مستطيل:**
   استخدم `add_auto_shape` طريقة إنشاء مستطيل على الشريحة.
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - حدود: `ShapeType.RECTANGLE`، موضع x (50)، موضع y (150)، العرض (150)، الارتفاع (50).
### تنسيق المستطيل
#### ملخص
بعد ذلك، سنطبق التنسيق على شكل المستطيل الخاص بنا، بما في ذلك لون التعبئة ونمط الخط.
#### خطوات التنسيق
1. **لون التعبئة:**
   قم بتعيين تعبئة صلبة بلون محدد لخلفية المستطيل.
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **نمط الخط:**
   تخصيص خط المستطيل، بما في ذلك لونه وعرضه.
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **حفظ العرض التقديمي:**
   وأخيرًا، احفظ العرض التقديمي في ملف.
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}