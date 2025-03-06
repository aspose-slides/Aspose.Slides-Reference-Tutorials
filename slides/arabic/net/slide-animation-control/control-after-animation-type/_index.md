---
title: إتقان تأثيرات ما بعد الرسوم المتحركة في برنامج PowerPoint باستخدام Aspose.Slides
linktitle: التحكم بعد الرسوم المتحركة اكتب في الشريحة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية التحكم في تأثيرات ما بعد الرسوم المتحركة في شرائح PowerPoint باستخدام Aspose.Slides for .NET. قم بتحسين عروضك التقديمية باستخدام العناصر المرئية الديناميكية.
weight: 11
url: /ar/net/slide-animation-control/control-after-animation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان تأثيرات ما بعد الرسوم المتحركة في برنامج PowerPoint باستخدام Aspose.Slides

## مقدمة
يعد تحسين عروضك التقديمية باستخدام الرسوم المتحركة الديناميكية جانبًا مهمًا لجذب جمهورك. يوفر Aspose.Slides for .NET حلاً قويًا للتحكم في تأثيرات ما بعد الرسوم المتحركة في الشرائح. في هذا البرنامج التعليمي، سنرشدك خلال عملية استخدام Aspose.Slides لـ .NET لمعالجة نوع ما بعد الرسوم المتحركة على الشرائح. باتباع هذا الدليل التفصيلي، ستتمكن من إنشاء عروض تقديمية أكثر تفاعلية وجذابة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة C# و.NET.
-  تم تثبيت Aspose.Slides لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
- بيئة تطوير متكاملة (IDE) مثل Visual Studio.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Slides. أضف الأسطر التالية إلى الكود الخاص بك:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
الآن، دعونا نقسم الكود المقدم إلى خطوات متعددة لفهم أفضل:
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
## الخطوة 3: قم بتحميل العرض التقديمي
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
قم بإنشاء مثيل لفئة العرض التقديمي وقم بتحميل العرض التقديمي الحالي.
## الخطوة 4: تعديل تأثيرات الحركة على الشريحة 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
انسخ الشريحة الأولى، وقم بالوصول إلى تسلسل المخطط الزمني الخاص بها، واضبط تأثير ما بعد الرسوم المتحركة على "إخفاء عند النقر التالي بالماوس".
## الخطوة 5: تعديل تأثيرات الحركة على الشريحة 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
انسخ الشريحة الأولى مرة أخرى، هذه المرة قم بتغيير تأثير ما بعد الرسوم المتحركة إلى "اللون" باللون الأخضر.
## الخطوة 6: تعديل تأثيرات الحركة على الشريحة 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
انسخ الشريحة الأولى مرة أخرى، واضبط تأثير ما بعد الرسوم المتحركة على "إخفاء بعد الرسوم المتحركة".
## الخطوة 7: احفظ العرض التقديمي المعدل
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدل باستخدام مسار ملف الإخراج المحدد.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية التحكم في تأثيرات ما بعد الرسوم المتحركة على الشرائح باستخدام Aspose.Slides for .NET. قم بتجربة أنواع مختلفة من الرسوم المتحركة لإنشاء عروض تقديمية أكثر ديناميكية وجاذبية.
## الأسئلة الشائعة
### هل يمكنني تطبيق تأثيرات ما بعد الرسوم المتحركة المختلفة على العناصر الفردية داخل الشريحة؟
نعم يمكنك ذلك. كرر العناصر واضبط تأثيرات ما بعد الرسوم المتحركة وفقًا لذلك.
### هل Aspose.Slides متوافق مع أحدث إصدارات .NET؟
نعم، يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث إصدارات إطار عمل .NET.
### كيف يمكنني إضافة رسوم متحركة مخصصة إلى الشرائح باستخدام Aspose.Slides؟
 الرجوع إلى الوثائق[هنا](https://reference.aspose.com/slides/net/) للحصول على معلومات مفصلة حول إضافة الرسوم المتحركة المخصصة.
### ما تنسيقات الملفات التي يدعمها Aspose.Slides لحفظ العروض التقديمية؟
يدعم Aspose.Slides العديد من التنسيقات، بما في ذلك PPTX وPPT وPDF والمزيد. تحقق من الوثائق للحصول على القائمة الكاملة.
### أين يمكنني الحصول على الدعم أو طرح الأسئلة المتعلقة بـ Aspose.Slides؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للدعم والتفاعل المجتمعي.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
