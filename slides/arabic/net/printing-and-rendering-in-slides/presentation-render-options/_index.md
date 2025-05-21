---
"description": "استكشف خيارات عرض Aspose.Slides لـ .NET. خصّص الخطوط والتخطيط والمزيد لعروض تقديمية آسرة. حسّن عروضك التقديمية بسهولة."
"linktitle": "استكشاف خيارات العرض لشرائح العرض التقديمي في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "خيارات عرض Aspose.Slides - ارتقِ بعروضك التقديمية"
"url": "/ar/net/printing-and-rendering-in-slides/presentation-render-options/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# خيارات عرض Aspose.Slides - ارتقِ بعروضك التقديمية

غالبًا ما يتطلب إنشاء عروض تقديمية مبهرة ضبطًا دقيقًا لخيارات العرض لتحقيق التأثير البصري المطلوب. في هذا البرنامج التعليمي، سنتعمق في عالم خيارات عرض شرائح العروض التقديمية باستخدام Aspose.Slides لـ .NET. تابع معنا لاكتشاف كيفية تحسين عروضك التقديمية بخطوات وأمثلة مفصلة.
## المتطلبات الأساسية
قبل أن نبدأ في مغامرة العرض هذه، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: نزّل وثبّت مكتبة Aspose.Slides. يمكنك العثور على المكتبة على [هذا الرابط](https://releases.aspose.com/slides/net/).
- دليل المستندات: أنشئ دليلًا لمستنداتك وتذكر مساره. ستحتاجه لأمثلة التعليمات البرمجية.
## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، ابدأ باستيراد المساحات الأساسية اللازمة للوصول إلى وظيفة Aspose.Slides.
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## الخطوة 1: تحميل العرض التقديمي وتحديد خيارات العرض
ابدأ بتحميل عرضك التقديمي وتحديد خيارات العرض. في المثال الموضح، نستخدم ملف باوربوينت باسم "RenderingOptions.pptx".
```csharp
string dataDir = "Your Document Directory";
string presPath = Path.Combine(dataDir, "RenderingOptions.pptx");
using (Presentation pres = new Presentation(presPath))
{
    IRenderingOptions renderingOpts = new RenderingOptions();
    // يمكن تعيين خيارات العرض الإضافية هنا
}
```
## الخطوة 2: تخصيص تخطيط الملاحظات
عدّل تخطيط الملاحظات في شرائحك. في هذا المثال، عيّننا موضع الملاحظات إلى "مقتطع من الأسفل".
```csharp
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderingOpts.SlidesLayoutOptions = notesOptions;
```
## الخطوة 3: إنشاء صور مصغرة باستخدام خطوط مختلفة
استكشف تأثير الخطوط المختلفة على عرضك التقديمي. أنشئ صورًا مصغّرة بإعدادات خطوط محددة.
## الخطوة 3.1: الخط الأصلي
```csharp
pres.Slides[0].GetThumbnail(renderingOpts, 4 / 3f, 4 / 3f).Save(Path.Combine(RunExamples.OutPath, "RenderingOptions-Slide1-Original.png"), ImageFormat.Png);
```
## الخطوة 3.2: الخط الافتراضي Arial Black
```csharp
renderingOpts.SlidesLayoutOptions = null;
renderingOpts.DefaultRegularFont = "Arial Black";
pres.Slides[0].GetThumbnail(renderingOpts, 4 / 3f, 4 / 3f).Save(Path.Combine(RunExamples.OutPath, "RenderingOptions-Slide1-ArialBlackDefault.png"), ImageFormat.Png);
```
## الخطوة 3.3: الخط الافتراضي Arial Narrow
```csharp
renderingOpts.DefaultRegularFont = "Arial Narrow";
pres.Slides[0].GetThumbnail(renderingOpts, 4 / 3f, 4 / 3f).Save(Path.Combine(RunExamples.OutPath, "RenderingOptions-Slide1-ArialNarrowDefault.png"), ImageFormat.Png);
```
قم بتجربة خطوط مختلفة للعثور على الخط الذي يكمل أسلوب العرض التقديمي الخاص بك.
## خاتمة
يُوفر تحسين خيارات العرض في Aspose.Slides لـ .NET طريقة فعّالة لتعزيز الجاذبية البصرية لعروضك التقديمية. جرّب إعدادات متنوعة لتحقيق النتيجة المرجوة وجذب انتباه جمهورك.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص موضع الملاحظات في كافة الشرائح؟
ج: نعم، عن طريق تعديل `NotesPosition` الممتلكات في `NotesCommentsLayoutingOptions`.
### س: كيف يمكنني تغيير الخط الافتراضي للعرض التقديمي بأكمله؟
أ: اضبط `DefaultRegularFont` الخاصية في خيارات العرض للخط المطلوب.
### س: هل هناك المزيد من خيارات التخطيط المتاحة للشرائح؟
ج: نعم، استكشف وثائق Aspose.Slides للحصول على قائمة شاملة بخيارات التخطيط.
### س: هل يمكنني استخدام الخطوط المخصصة غير المثبتة على نظامي؟
ج: نعم، حدد مسار ملف الخط باستخدام `AddFonts` الطريقة في `FontsLoader` فصل.
### س: أين يمكنني طلب المساعدة أو التواصل مع المجتمع؟
أ: قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على الدعم والمشاركة المجتمعية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}