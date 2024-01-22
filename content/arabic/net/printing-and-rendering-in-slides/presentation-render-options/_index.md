---
title: خيارات عرض Aspose.Slides - ارتقِ بعروضك التقديمية
linktitle: استكشاف خيارات العرض لشرائح العرض التقديمي في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: استكشف Aspose.Slides لخيارات عرض .NET. قم بتخصيص الخطوط والتخطيط والمزيد للعروض التقديمية الجذابة. تعزيز الشرائح الخاصة بك دون عناء.
type: docs
weight: 15
url: /ar/net/printing-and-rendering-in-slides/presentation-render-options/
---
غالبًا ما يتضمن إنشاء عروض تقديمية مذهلة ضبطًا دقيقًا لخيارات العرض لتحقيق التأثير المرئي المطلوب. في هذا البرنامج التعليمي، سوف نتعمق في عالم خيارات العرض لشرائح العرض التقديمي باستخدام Aspose.Slides for .NET. تابع معنا لاكتشاف كيفية تحسين عروضك التقديمية من خلال الخطوات والأمثلة التفصيلية.
## المتطلبات الأساسية
قبل الشروع في مغامرة العرض هذه، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Slides for .NET: قم بتنزيل وتثبيت مكتبة Aspose.Slides. يمكنك العثور على المكتبة في[هذا الرابط](https://releases.aspose.com/slides/net/).
- دليل المستندات: قم بإعداد دليل لمستنداتك وتذكر المسار. سوف تحتاج إليها لأمثلة التعليمات البرمجية.
## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للوصول إلى وظيفة Aspose.Slides.
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;
```
## الخطوة 1: تحميل العرض التقديمي وتحديد خيارات العرض
ابدأ بتحميل العرض التقديمي الخاص بك وتحديد خيارات العرض. في المثال المذكور، نستخدم ملف PowerPoint المسمى "RenderingOptions.pptx".
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
اضبط تخطيط الملاحظات في الشرائح الخاصة بك. في هذا المثال، قمنا بتعيين موضع الملاحظات إلى "BottomTruncated".
```csharp
NotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
notesOptions.NotesPosition = NotesPositions.BottomTruncated;
renderingOpts.SlidesLayoutOptions = notesOptions;
```
## الخطوة 3: إنشاء صور مصغرة بخطوط مختلفة
اكتشف تأثير الخطوط المختلفة على العرض التقديمي الخاص بك. قم بإنشاء صور مصغرة بإعدادات خط محددة.
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
## الخطوة 3.3: الخط الافتراضي الضيق Arial
```csharp
renderingOpts.DefaultRegularFont = "Arial Narrow";
pres.Slides[0].GetThumbnail(renderingOpts, 4 / 3f, 4 / 3f).Save(Path.Combine(RunExamples.OutPath, "RenderingOptions-Slide1-ArialNarrowDefault.png"), ImageFormat.Png);
```
قم بتجربة خطوط مختلفة للعثور على الخط الذي يكمل أسلوب العرض التقديمي الخاص بك.
## خاتمة
يوفر تحسين خيارات العرض في Aspose.Slides for .NET طريقة قوية لتحسين المظهر المرئي لعروضك التقديمية. قم بتجربة إعدادات مختلفة لتحقيق النتيجة المرجوة وجذب انتباه جمهورك.
## أسئلة مكررة
### س: هل يمكنني تخصيص موضع الملاحظات في جميع الشرائح؟
 ج: نعم، عن طريق ضبط`NotesPosition` الممتلكات في`NotesCommentsLayoutingOptions`.
### س: كيف يمكنني تغيير الخط الافتراضي للعرض التقديمي بأكمله؟
 ج: تعيين`DefaultRegularFont` الخاصية في خيارات التقديم إلى الخط الذي تريده.
### س: هل هناك المزيد من خيارات التخطيط المتاحة للشرائح؟
ج: نعم، استكشف وثائق Aspose.Slides للحصول على قائمة شاملة بخيارات التخطيط.
### س: هل يمكنني استخدام خطوط مخصصة غير مثبتة على نظامي؟
 ج: نعم، حدد مسار ملف الخط باستخدام ملف`AddFonts` الطريقة في`FontsLoader` فصل.
### س: أين يمكنني طلب المساعدة أو التواصل مع المجتمع؟
 ج: قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للدعم والمشاركة المجتمعية.