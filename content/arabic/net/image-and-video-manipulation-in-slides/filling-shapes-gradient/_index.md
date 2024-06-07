---
title: قم بإنشاء تدرجات مذهلة في برنامج PowerPoint باستخدام Aspose.Slides
linktitle: تعبئة الأشكال بالتدرج في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: عزز عروضك التقديمية باستخدام Aspose.Slides لـ .NET! تعرف على عملية ملء الأشكال بالتدرجات خطوة بخطوة. تحميل النسخة التجريبية المجانية من الآن!
type: docs
weight: 21
url: /ar/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---
## مقدمة
يعد إنشاء شرائح العرض التقديمي الجذابة بصريًا أمرًا ضروريًا لجذب انتباه جمهورك والحفاظ عليه. في هذا البرنامج التعليمي، سنرشدك خلال عملية تحسين الشرائح الخاصة بك عن طريق ملء شكل بيضاوي بتدرج باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio على جهازك.
-  Aspose.Slides لمكتبة .NET. تنزيله[هنا](https://releases.aspose.com/slides/net/).
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
    // الكود الخاص بك يذهب هنا ...
}
```
## الخطوة 2: إضافة شكل القطع الناقص
قم بإدراج شكل بيضاوي في الشريحة الأولى من العرض التقديمي:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## الخطوة 3: تطبيق تنسيق التدرج
حدد أنه يجب ملء الشكل بتدرج وحدد خصائص التدرج:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## الخطوة 4: إضافة توقفات التدرج
تحديد ألوان ومواضع توقفات التدرج:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## الخطوة 5: احفظ العرض التقديمي
احفظ العرض التقديمي الخاص بك بالشكل المملوء بالتدرج المضاف حديثًا:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
كرر هذه الخطوات في كود C# الخاص بك، مع التأكد من التسلسل الصحيح وقيم المعلمات. سيؤدي هذا إلى ملف عرض تقديمي ذو شكل بيضاوي جذاب ومملوء بتدرج.
## خاتمة
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## الأسئلة الشائعة
### س: هل يمكنني تطبيق التدرجات على أشكال أخرى غير علامات الحذف؟
ج: بالتأكيد! يدعم Aspose.Slides for .NET التعبئة المتدرجة لمختلف الأشكال مثل المستطيلات والمضلعات والمزيد.
### س: أين يمكنني العثور على أمثلة إضافية ووثائق مفصلة؟
 ج: اكتشف[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/) للحصول على أدلة وأمثلة شاملة.
### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
 ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على دعم Aspose.Slides لـ .NET؟
ج: اطلب المساعدة والتفاعل مع المجتمع بشأن[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 ج: بالتأكيد يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).