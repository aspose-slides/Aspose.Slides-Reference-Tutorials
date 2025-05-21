---
"description": "حسّن عروضك التقديمية مع Aspose.Slides لـ .NET! تعلّم خطوة بخطوة كيفية ملء الأشكال بالتدرجات اللونية. حمّل نسختك التجريبية المجانية الآن!"
"linktitle": "ملء الأشكال بالتدرج اللوني في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء تدرجات لونية مذهلة في PowerPoint باستخدام Aspose.Slides"
"url": "/ar/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تدرجات لونية مذهلة في PowerPoint باستخدام Aspose.Slides

## مقدمة
يُعدّ تصميم شرائح عرض تقديمي جذابة بصريًا أمرًا أساسيًا لجذب انتباه جمهورك والحفاظ عليه. في هذا البرنامج التعليمي، سنشرح لك عملية تحسين شرائحك عن طريق ملء شكل بيضاوي بتدرج لوني باستخدام Aspose.Slides لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio على جهازك.
- مكتبة Aspose.Slides لـ .NET. حمّلها [هنا](https://releases.aspose.com/slides/net/).
- دليل المشروع لتنظيم ملفاتك.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، قم بتضمين مساحات الأسماء المطلوبة لـ Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إنشاء عرض تقديمي
ابدأ بإنشاء عرض تقديمي جديد باستخدام مكتبة Aspose.Slides:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك يذهب هنا...
}
```
## الخطوة 2: إضافة شكل بيضاوي
قم بإدراج شكل بيضاوي في الشريحة الأولى من العرض التقديمي الخاص بك:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## الخطوة 3: تطبيق تنسيق التدرج
حدد أن الشكل يجب أن يُملأ بتدرج لوني، ثم قم بتعريف خصائص التدرج اللوني:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## الخطوة 4: إضافة توقفات التدرج
قم بتحديد الألوان ومواضع توقف التدرج:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي الخاص بك باستخدام الشكل المليء بالتدرج اللوني المضاف حديثًا:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
كرّر هذه الخطوات في شيفرة C#، مع التأكد من صحة التسلسل وقيم المعلمات. سيؤدي هذا إلى إنشاء ملف عرض تقديمي ذي شكل بيضاوي جذاب، مملوء بتدرج لوني.
## خاتمة
مع Aspose.Slides لـ .NET، يمكنك بسهولة تحسين جماليات عروضك التقديمية. باتباع هذا الدليل، ستتعلم كيفية ملء الأشكال بالتدرجات اللونية، مما يمنح شرائحك مظهرًا احترافيًا وجذابًا.
---
## الأسئلة الشائعة
### س: هل يمكنني تطبيق التدرجات اللونية على أشكال أخرى غير القطع الناقص؟
ج: بالتأكيد! يدعم Aspose.Slides لـ .NET التعبئة المتدرجة لمختلف الأشكال، مثل المستطيلات والمضلعات وغيرها.
### س: أين يمكنني العثور على أمثلة إضافية ووثائق مفصلة؟
أ: استكشف [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/) للحصول على أدلة وأمثلة شاملة.
### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
أ: اطلب المساعدة وتواصل مع المجتمع بشأن [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
ج: بالتأكيد يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}