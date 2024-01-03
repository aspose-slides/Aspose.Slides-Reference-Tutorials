---
title: قم بإنشاء أشكال مرسومة مذهلة باستخدام Aspose.Slides
linktitle: إنشاء الأشكال المرسومة في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة أشكال تخطيطية إبداعية إلى شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. تعزيز الجاذبية البصرية دون عناء!
type: docs
weight: 13
url: /ar/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول إنشاء الأشكال المرسومة في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. إذا كنت تريد إضافة لمسة من الإبداع إلى عروضك التقديمية، فإن الأشكال المرسومة توفر جمالية فريدة ومرسومة يدويًا. في هذا البرنامج التعليمي، سنرشدك خلال العملية، ونقسمها إلى خطوات بسيطة لضمان تجربة سلسة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET باستخدام IDE المفضل لديك.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية في مشروع .NET الخاص بك. تضمن هذه الخطوة أن لديك إمكانية الوصول إلى الفئات والوظائف المطلوبة للعمل مع Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
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
## الخطوة 1: إعداد المشروع
ابدأ بإنشاء مشروع .NET جديد أو فتح مشروع موجود. تأكد من تضمين Aspose.Slides في مراجع مشروعك.
## الخطوة 2: تهيئة Aspose.Slides
قم بتهيئة Aspose.Slides عن طريق إضافة مقتطف التعليمات البرمجية التالي. يؤدي هذا إلى إعداد العرض التقديمي وتحديد مسارات الإخراج لملف العرض التقديمي والصورة المصغرة.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // تابع إلى الخطوات التالية...
}
```
## الخطوة 3: إضافة الشكل المرسوم
الآن، دعونا نضيف شكلاً مرسومًا إلى الشريحة. في هذا المثال، سنقوم بإضافة مستطيل مع تأثير رسم يدوي.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// تحويل الشكل إلى رسم بأسلوب مرفوع
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## الخطوة 4: إنشاء صورة مصغرة
قم بإنشاء صورة مصغرة للشريحة لتصور الشكل المرسوم. احفظ الصورة المصغرة كملف PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## الخطوة 5: حفظ العرض التقديمي
احفظ ملف العرض التقديمي بالشكل المرسوم.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
هذا كل شيء! لقد نجحت في إنشاء عرض تقديمي بأشكال مرسومة باستخدام Aspose.Slides لـ .NET.
## خاتمة
يمكن أن تؤدي إضافة الأشكال المرسومة إلى شرائح العرض التقديمي إلى تحسين المظهر المرئي وإشراك جمهورك. مع Aspose.Slides for .NET، تصبح العملية واضحة ومباشرة، مما يسمح لك بإطلاق العنان لإبداعك دون عناء.
## الأسئلة الشائعة
### 1. هل يمكنني تخصيص التأثير المرسوم؟
نعم، يوفر Aspose.Slides for .NET خيارات تخصيص متنوعة للتأثيرات المرسومة. الرجوع إلى[توثيق](https://reference.aspose.com/slides/net/) للحصول على معلومات مفصلة.
### 2. هل هناك نسخة تجريبية مجانية متاحة؟
 بالتأكيد! يمكنك استكشاف نسخة تجريبية مجانية من Aspose.Slides لـ .NET[هنا](https://releases.aspose.com/).
### 3. أين يمكنني الحصول على الدعم؟
 لأي مساعدة أو استفسار قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. كيف يمكنني شراء Aspose.Slides لـ .NET؟
 لشراء Aspose.Slides لـ .NET، قم بزيارة[صفحة الشراء](https://purchase.aspose.com/buy).
### 5. هل تقدمون تراخيص مؤقتة؟
 نعم، التراخيص المؤقتة متوفرة[هنا](https://purchase.aspose.com/temporary-license/).