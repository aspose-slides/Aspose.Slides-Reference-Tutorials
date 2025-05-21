---
"description": "تعلم محاذاة الأشكال بسهولة في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. حسّن مظهرك بمحاذاة دقيقة. حمّل الآن!"
"linktitle": "محاذاة الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إتقان محاذاة الأشكال باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shape-alignment-and-formatting-in-slides/aligning-shapes/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إتقان محاذاة الأشكال باستخدام Aspose.Slides لـ .NET

## مقدمة
غالبًا ما يتطلب إنشاء شرائح عرض تقديمي جذابة بصريًا محاذاة دقيقة للأشكال. يوفر Aspose.Slides for .NET حلاً فعالاً لتحقيق ذلك بسهولة. في هذا البرنامج التعليمي، سنستكشف كيفية محاذاة الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- مكتبة Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها. [هنا](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET على جهازك.
## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، قم باستيراد المساحات الأساسية اللازمة للعمل مع Aspose.Slides:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## الخطوة 1: تهيئة العرض التقديمي
ابدأ بتهيئة كائن العرض التقديمي وإضافة شريحة:
```csharp
string dataDir = "Your Document Directory";
string outpptxFile = Path.Combine(dataDir, "ShapesAlignment_out.pptx");
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
    // إنشاء بعض الأشكال
    // ...
}
```
## الخطوة 2: محاذاة الأشكال داخل الشريحة
أضف الأشكال إلى الشريحة وقم بمحاذاتها باستخدام `SlideUtil.AlignShapes` طريقة:
```csharp
slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 100, 100);
slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 200, 100, 100);
slide.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
// محاذاة كافة الأشكال داخل IBaseSlide.
SlideUtil.AlignShapes(ShapesAlignmentType.AlignBottom, true, pres.Slides[0]);
```
## الخطوة 3: محاذاة الأشكال داخل المجموعة
إنشاء شكل مجموعة، وإضافة الأشكال إليه، ومحاذاتها داخل المجموعة:
```csharp
slide = pres.Slides.AddEmptySlide(slide.LayoutSlide);
IGroupShape groupShape = slide.Shapes.AddGroupShape();
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 350, 50, 50, 50);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 450, 150, 50, 50);
// محاذاة جميع الأشكال داخل IGroupShape.
SlideUtil.AlignShapes(ShapesAlignmentType.AlignLeft, false, groupShape);
```
## الخطوة 4: محاذاة الأشكال المحددة ضمن مجموعة
محاذاة الأشكال المحددة ضمن مجموعة من خلال توفير فهارسها:
```csharp
slide = pres.Slides.AddEmptySlide(slide.LayoutSlide);
groupShape = slide.Shapes.AddGroupShape();
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 350, 50, 50, 50);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 450, 150, 50, 50);
// محاذاة الأشكال مع الفهارس المحددة داخل IGroupShape.
SlideUtil.AlignShapes(ShapesAlignmentType.AlignLeft, false, groupShape, new int[] { 0, 2 });
```
## خاتمة
حسّن مظهر شرائح عرضك التقديمي بسهولة باستخدام Aspose.Slides for .NET لمحاذاة الأشكال بدقة. هذا الدليل المفصل يزودك بالمعرفة اللازمة لتبسيط عملية المحاذاة وإنشاء عروض تقديمية احترافية.
## الأسئلة الشائعة
### هل يمكنني محاذاة الأشكال في عرض تقديمي موجود باستخدام Aspose.Slides لـ .NET؟
نعم، يمكنك تحميل عرض تقديمي موجود باستخدام `Presentation.Load` ومن ثم انتقل إلى محاذاة الأشكال.
### هل هناك خيارات محاذاة أخرى متوفرة في Aspose.Slides؟
يوفر Aspose.Slides خيارات محاذاة مختلفة، بما في ذلك AlignTop، وAlignRight، وAlignBottom، وAlignLeft، والمزيد.
### هل يمكنني محاذاة الأشكال بناءً على توزيعها في الشريحة؟
بالتأكيد! يوفر Aspose.Slides طرقًا لتوزيع الأشكال بالتساوي، أفقيًا وعموديًا.
### هل Aspose.Slides مناسب للتطوير عبر الأنظمة الأساسية؟
تم تصميم Aspose.Slides for .NET في المقام الأول لتطبيقات Windows، ولكن Aspose يوفر مكتبات لـ Java ومنصات أخرى أيضًا.
### كيف يمكنني الحصول على مزيد من المساعدة أو الدعم؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}