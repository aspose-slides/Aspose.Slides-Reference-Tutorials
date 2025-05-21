---
"description": "تعرّف على كيفية التحكم في تأثيرات الرسوم المتحركة اللاحقة في شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. عزّز عروضك التقديمية بعناصر بصرية ديناميكية."
"linktitle": "التحكم بعد نوع الرسوم المتحركة في الشريحة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إتقان تأثيرات After-Animation في PowerPoint باستخدام Aspose.Slides"
"url": "/ar/net/slide-animation-control/control-after-animation-type/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إتقان تأثيرات After-Animation في PowerPoint باستخدام Aspose.Slides

## مقدمة
يُعدّ تحسين عروضك التقديمية باستخدام الرسوم المتحركة الديناميكية جانبًا أساسيًا لجذب جمهورك. يوفر Aspose.Slides for .NET حلاً فعّالاً للتحكم في تأثيرات الرسوم المتحركة اللاحقة في الشرائح. في هذا البرنامج التعليمي، سنرشدك خلال عملية استخدام Aspose.Slides for .NET للتحكم في نوع الرسوم المتحركة اللاحقة على الشرائح. باتباع هذا الدليل التفصيلي، ستتمكن من إنشاء عروض تقديمية أكثر تفاعلية وجاذبية بصريًا.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة C# و.NET.
- تم تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها. [هنا](https://releases.aspose.com/slides/net/).
- بيئة تطوير متكاملة (IDE) مثل Visual Studio.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء اللازمة للوصول إلى وظائف Aspose.Slides. أضف الأسطر التالية إلى الكود الخاص بك:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
الآن، دعنا نقسم الكود المقدم إلى خطوات متعددة لفهم أفضل:
## الخطوة 1: إعداد دليل المستندات
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
تأكد من وجود الدليل المحدد، أو قم بإنشائه إذا لم يكن موجودًا.
## الخطوة 2: تحديد مسار ملف الإخراج
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
حدد مسار ملف الإخراج للعرض التقديمي المعدل.
## الخطوة 3: تحميل العرض التقديمي
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
إنشاء فئة العرض التقديمي وتحميل العرض التقديمي الحالي.
## الخطوة 4: تعديل تأثيرات الرسوم المتحركة على الشريحة 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
استنسخ الشريحة الأولى، ثم قم بالوصول إلى تسلسل الجدول الزمني الخاص بها، ثم اضبط تأثير الرسوم المتحركة اللاحقة على "إخفاء عند النقر بالماوس التالي".
## الخطوة 5: تعديل تأثيرات الرسوم المتحركة على الشريحة 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
استنسخ الشريحة الأولى مرة أخرى، هذه المرة قم بتغيير تأثير الرسوم المتحركة اللاحقة إلى "لون" باللون الأخضر.
## الخطوة 6: تعديل تأثيرات ما بعد الرسوم المتحركة على الشريحة 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
استنسخ الشريحة الأولى مرة أخرى، واضبط تأثير ما بعد الرسوم المتحركة على "إخفاء بعد الرسوم المتحركة".
## الخطوة 7: حفظ العرض التقديمي المعدّل
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدّل باستخدام مسار ملف الإخراج المحدد.
## خاتمة
تهانينا! لقد نجحت في تعلم كيفية التحكم بتأثيرات الرسوم المتحركة اللاحقة على الشرائح باستخدام Aspose.Slides لـ .NET. جرّب أنواعًا مختلفة من الرسوم المتحركة اللاحقة لإنشاء عروض تقديمية أكثر ديناميكية وجاذبية.
## الأسئلة الشائعة
### هل يمكنني تطبيق تأثيرات مختلفة بعد الرسوم المتحركة على عناصر فردية ضمن شريحة؟
نعم، يمكنك ذلك. كرّر عملية التكرار بين العناصر واضبط تأثيراتها اللاحقة وفقًا لذلك.
### هل Aspose.Slides متوافق مع أحدث إصدارات .NET؟
نعم، يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث إصدارات .NET Framework.
### كيف يمكنني إضافة رسوم متحركة مخصصة إلى الشرائح باستخدام Aspose.Slides؟
راجع الوثائق [هنا](https://reference.aspose.com/slides/net/) للحصول على معلومات مفصلة حول إضافة الرسوم المتحركة المخصصة.
### ما هي تنسيقات الملفات التي يدعمها Aspose.Slides لحفظ العروض التقديمية؟
يدعم Aspose.Slides تنسيقات متنوعة، بما في ذلك PPTX وPPT وPDF وغيرها. راجع الوثائق للاطلاع على القائمة الكاملة.
### أين يمكنني الحصول على الدعم أو طرح الأسئلة المتعلقة بـ Aspose.Slides؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على الدعم والتفاعل المجتمعي.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}