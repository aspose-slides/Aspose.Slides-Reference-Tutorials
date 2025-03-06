---
title: إتقان التدوير ثلاثي الأبعاد في العروض التقديمية باستخدام Aspose.Slides لـ .NET
linktitle: تطبيق تأثير التدوير ثلاثي الأبعاد على الأشكال في شرائح العرض التقديمي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: عزز عروضك التقديمية باستخدام Aspose.Slides لـ .NET! تعلم كيفية تطبيق تأثيرات التدوير ثلاثية الأبعاد على الأشكال في هذا البرنامج التعليمي. قم بإنشاء عرض تقديمي ديناميكي ومذهل بصريًا.
weight: 23
url: /ar/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان التدوير ثلاثي الأبعاد في العروض التقديمية باستخدام Aspose.Slides لـ .NET

## مقدمة
يعد إنشاء شرائح عرض تقديمي جذابة وديناميكية جانبًا أساسيًا للتواصل الفعال. يوفر Aspose.Slides for .NET مجموعة قوية من الأدوات لتحسين العروض التقديمية، بما في ذلك القدرة على تطبيق تأثيرات التدوير ثلاثية الأبعاد على الأشكال. في هذا البرنامج التعليمي، سنتعرف على عملية تطبيق تأثير التدوير ثلاثي الأبعاد على الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET، مثل Visual Studio، لكتابة التعليمات البرمجية وتشغيلها.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، قم باستيراد مساحات الأسماء الضرورية للاستفادة من وظائف Aspose.Slides. قم بتضمين مساحات الأسماء التالية في بداية التعليمات البرمجية الخاصة بك:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## الخطوة 1: قم بإعداد مشروعك
قم بإنشاء مشروع جديد في بيئة التطوير .NET المفضلة لديك. تأكد من أنك قمت بإضافة مرجع Aspose.Slides إلى مشروعك.
## الخطوة 2: تهيئة العرض التقديمي
قم بإنشاء مثيل لفصل العرض التقديمي لبدء العمل باستخدام الشرائح:
```csharp
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة الشكل التلقائي
قم بإضافة شكل تلقائي إلى الشريحة، مع تحديد نوعها وموضعها وأبعادها:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## الخطوة 4: ضبط تأثير التدوير ثلاثي الأبعاد
تكوين تأثير التدوير ثلاثي الأبعاد للشكل التلقائي:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## الخطوة 5: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل باستخدام تأثير التدوير ثلاثي الأبعاد المطبق:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## الخطوة 6: كرر للأشكال الأخرى
إذا كان لديك أشكال إضافية، كرر الخطوات من 3 إلى 5 لكل شكل.
## خاتمة
يمكن أن تؤدي إضافة تأثيرات التدوير ثلاثية الأبعاد إلى الأشكال الموجودة في شرائح العرض التقديمي إلى تحسين جاذبيتها المرئية بشكل كبير. مع Aspose.Slides for .NET، تصبح هذه العملية واضحة ومباشرة، مما يسمح لك بإنشاء عروض تقديمية جذابة.
## الأسئلة الشائعة
### هل يمكنني تطبيق التدوير ثلاثي الأبعاد على مربعات النص في Aspose.Slides لـ .NET؟
نعم، يمكنك تطبيق تأثيرات التدوير ثلاثي الأبعاد على أشكال مختلفة، بما في ذلك مربعات النص، باستخدام Aspose.Slides.
### هل تتوفر نسخة تجريبية من Aspose.Slides لـ .NET؟
 نعم، يمكنك الوصول إلى النسخة التجريبية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على دعم Aspose.Slides لـ .NET؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 نعم يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على وثائق مفصلة عن Aspose.Slides لـ .NET؟
 الوثائق متاحة[هنا](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
