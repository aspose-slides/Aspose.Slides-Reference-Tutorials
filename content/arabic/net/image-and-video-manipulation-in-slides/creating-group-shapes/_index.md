---
title: Aspose.Slides - إنشاء أشكال المجموعة في .NET
linktitle: إنشاء أشكال جماعية في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء أشكال جماعية في PowerPoint باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة للحصول على عروض تقديمية جذابة بصريًا.
type: docs
weight: 11
url: /ar/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## مقدمة
إذا كنت تتطلع إلى تحسين المظهر المرئي لشرائح العرض التقديمي وتنظيم المحتوى بشكل أكثر كفاءة، فإن دمج أشكال المجموعة يعد حلاً فعالاً. يوفر Aspose.Slides for .NET طريقة سلسة لإنشاء أشكال المجموعة ومعالجتها في عروض PowerPoint التقديمية. في هذا البرنامج التعليمي، سنتعرف على عملية إنشاء أشكال جماعية باستخدام Aspose.Slides، وتقسيمها إلى خطوات سهلة المتابعة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
-  Aspose.Slides for .NET: تأكد من تثبيت مكتبة Aspose.Slides. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة عمل باستخدام IDE متوافق مع .NET، مثل Visual Studio.
- المعرفة الأساسية بـ C#: تعرف على أساسيات لغة البرمجة C#.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## الخطوة 1: إنشاء فئة العرض التقديمي

 إنشاء مثيل لـ`Presentation` فئة وحدد الدليل حيث يتم تخزين المستندات الخاصة بك:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // تابع الخطوات التالية ضمن كتلة الاستخدام هذه
}
```

## الخطوة 2: الوصول إلى الشريحة الأولى

استرجاع الشريحة الأولى من العرض التقديمي:

```csharp
ISlide sld = pres.Slides[0];
```

## الخطوة 3: الوصول إلى مجموعة الأشكال

الوصول إلى مجموعة الأشكال الموجودة على الشريحة:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## الخطوة 4: إضافة شكل المجموعة

إضافة شكل مجموعة إلى الشريحة:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## الخطوة 5: إضافة الأشكال داخل شكل المجموعة

تعبئة شكل المجموعة بأشكال فردية:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## الخطوة 6: إضافة إطار شكل المجموعة

تحديد الإطار لشكل المجموعة بأكملها:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## الخطوة 7: احفظ العرض التقديمي

احفظ العرض التقديمي المعدل في الدليل المحدد الخاص بك:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

كرر هذه الخطوات في تطبيق C# الخاص بك لإنشاء أشكال جماعية بنجاح في شرائح العرض التقديمي باستخدام Aspose.Slides.

## خاتمة
في هذا البرنامج التعليمي، استكشفنا عملية إنشاء أشكال جماعية باستخدام Aspose.Slides لـ .NET. باتباع هذه الخطوات، يمكنك تحسين المظهر المرئي وتنظيم عروض PowerPoint التقديمية.
## أسئلة مكررة
### هل Aspose.Slides متوافق مع أحدث إصدار من .NET؟
 نعم، يتم تحديث Aspose.Slides بانتظام لدعم أحدث إصدارات .NET. افحص ال[توثيق](https://reference.aspose.com/slides/net/) للحصول على تفاصيل التوافق.
### هل يمكنني تجربة Aspose.Slides قبل الشراء؟
 قطعاً! يمكنك تنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
 قم بزيارة Aspose.Slides[المنتدى](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء ترخيص كامل لـ Aspose.Slides؟
 يمكنك شراء ترخيص من[صفحة الشراء](https://purchase.aspose.com/buy).
