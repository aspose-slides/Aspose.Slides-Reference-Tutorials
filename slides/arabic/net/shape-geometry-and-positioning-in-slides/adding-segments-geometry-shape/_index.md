---
title: إتقان العناصر المرئية - إضافة شرائح باستخدام Aspose.Slides في .NET
linktitle: إضافة شرائح إلى الشكل الهندسي في العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين تطبيقات .NET الخاصة بك باستخدام Aspose.Slides. يرشدك هذا البرنامج التعليمي إلى كيفية إضافة شرائح إلى الأشكال الهندسية لتقديم عروض تقديمية جذابة.
weight: 13
url: /ar/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في عالم تطوير .NET، يعد إنشاء عروض تقديمية جذابة بصريًا مطلبًا شائعًا. Aspose.Slides for .NET هي مكتبة قوية تسهل التكامل السلس لإمكانيات إنشاء العروض التقديمية القوية في تطبيقات .NET الخاصة بك. يركز هذا البرنامج التعليمي على جانب محدد من تصميم العرض التقديمي - إضافة شرائح إلى الأشكال الهندسية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio على جهازك.
- تم تنزيل Aspose.Slides لمكتبة .NET والإشارة إليها في مشروعك.
## استيراد مساحات الأسماء
في كود C# الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Slides. أضف الأسطر التالية إلى الكود الخاص بك:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
الآن، دعونا نقسم المثال إلى خطوات متعددة.
## الخطوة 1: قم بإعداد مشروعك
ابدأ بإنشاء مشروع C# جديد في Visual Studio. تأكد من أن لديك مكتبة Aspose.Slides المشار إليها في مشروعك.
## الخطوة 2: إنشاء عرض تقديمي
قم بتهيئة كائن عرض تقديمي جديد باستخدام مكتبة Aspose.Slides. سيكون هذا بمثابة قماش للشكل الهندسي الخاص بك.
```csharp
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك لإنشاء عرض تقديمي موجود هنا
}
```
## الخطوة 3: إضافة شكل هندسي
إنشاء شكل هندسي داخل العرض التقديمي. على سبيل المثال، دعونا نضيف مستطيلاً إلى الشريحة الأولى.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## الخطوة 4: الحصول على مسار الهندسة
استرجع المسار الهندسي للشكل الذي تم إنشاؤه لمعالجة أجزاءه.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## الخطوة 5: إضافة شرائح
إضافة شرائح (خطوط) إلى المسار الهندسي. في هذا المثال، تتم إضافة سطرين إلى المسار.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## الخطوة 6: تعيين مسار هندسي محرر
قم بتعيين المسار الهندسي المعدل مرة أخرى إلى الشكل لتطبيق التغييرات.
```csharp
shape.SetGeometryPath(geometryPath);
```
## الخطوة 7: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل في الموقع المطلوب.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
من خلال هذه الخطوات، تكون قد نجحت في إضافة شرائح إلى شكل هندسي في عرض تقديمي باستخدام Aspose.Slides for .NET.
## خاتمة
يعمل Aspose.Slides for .NET على تمكين المطورين من تحسين تطبيقاتهم من خلال إمكانيات إنشاء العروض التقديمية المتقدمة. توفر إضافة شرائح إلى الأشكال الهندسية وسيلة لتخصيص العناصر المرئية لعروضك التقديمية.
### أسئلة مكررة
### هل يمكنني إضافة أنواع مختلفة من الأشكال باستخدام Aspose.Slides؟
نعم، يدعم Aspose.Slides أنواع الأشكال المختلفة، بما في ذلك المستطيلات والدوائر والأشكال الهندسية المخصصة.
### هل الترخيص مطلوب لاستخدام Aspose.Slides في مشروعي؟
نعم، هناك حاجة إلى ترخيص ساري المفعول. يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار أو شراء ترخيص كامل للإنتاج.
### كيف يمكنني الحصول على الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
### هل هناك برامج تعليمية أخرى متاحة لـ Aspose.Slides؟
 اكتشف ال[توثيق](https://reference.aspose.com/slides/net/) للحصول على أدلة وأمثلة شاملة.
### هل يمكنني تجربة Aspose.Slides مجانًا قبل الشراء؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
