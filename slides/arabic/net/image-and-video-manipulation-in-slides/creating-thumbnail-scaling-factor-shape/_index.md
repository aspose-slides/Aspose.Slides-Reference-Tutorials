---
title: إنشاء صورة مصغرة مع عامل القياس للشكل في Aspose.Slides
linktitle: إنشاء صورة مصغرة مع عامل القياس للشكل في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعلم كيفية إنشاء صور مصغرة لـ PowerPoint بحدود محددة باستخدام Aspose.Slides for .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 12
url: /ar/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
مرحبًا بك في دليلنا الشامل حول إنشاء صور مصغرة ذات حدود للأشكال في Aspose.Slides لـ .NET. Aspose.Slides هي مكتبة قوية تمكن المطورين من العمل بسلاسة مع عروض PowerPoint التقديمية في تطبيقات .NET الخاصة بهم. في هذا البرنامج التعليمي، سوف نتعمق في عملية إنشاء صور مصغرة ذات حدود محددة للأشكال داخل العرض التقديمي باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Slides for .NET: تأكد من تثبيت مكتبة Aspose.Slides. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).
- بيئة التطوير: تمتع ببيئة تطوير مناسبة لـ .NET، مثل Visual Studio، تم إعدادها على جهازك.
## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Slides:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## الخطوة 1: إعداد العرض التقديمي
ابدأ بإنشاء مثيل لفئة العرض التقديمي التي تمثل ملف العرض التقديمي لـ PowerPoint الذي تريد العمل معه:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // الكود الخاص بك لإنشاء الصور المصغرة موجود هنا
}
```
## الخطوة 2: إنشاء صورة كاملة الحجم
ضمن قالب العرض التقديمي، قم بإنشاء صورة كاملة الحجم للشكل الذي تريد إنشاء صورة مصغرة له:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    // الكود الخاص بك لحفظ الصورة موجود هنا
}
```
## الخطوة 3: احفظ الصورة على القرص
احفظ الصورة التي تم إنشاؤها على القرص، مع تحديد التنسيق (في هذه الحالة، PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إنشاء صور مصغرة ذات حدود للأشكال باستخدام Aspose.Slides لـ .NET. يمكن أن تكون هذه الميزة مفيدة بشكل لا يصدق عندما تحتاج إلى إنشاء صور ذات حجم محدد للأشكال داخل عروض PowerPoint التقديمية الخاصة بك برمجياً.
## أسئلة مكررة
### س1: هل يمكنني استخدام Aspose.Slides مع أطر عمل .NET أخرى؟
نعم، Aspose.Slides متوافق مع أطر عمل .NET المختلفة، مما يوفر المرونة للتكامل في أنواع مختلفة من التطبيقات.
### س2: هل هناك نسخة تجريبية متاحة لـ Aspose.Slides؟
 نعم، يمكنك استكشاف وظائف Aspose.Slides عن طريق تنزيل الإصدار التجريبي[هنا](https://releases.aspose.com/).
### س3: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 يمكنك الحصول على ترخيص مؤقت لـ Aspose.Slides من خلال زيارة[هذا الرابط](https://purchase.aspose.com/temporary-license/).
### س4: أين يمكنني العثور على دعم إضافي لـ Aspose.Slides؟
 لأية استفسارات أو مساعدة، لا تتردد في زيارة منتدى دعم Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).
### س5: هل يمكنني شراء Aspose.Slides لـ .NET؟
 بالتأكيد! لشراء Aspose.Slides لـ .NET، يرجى زيارة صفحة الشراء[هنا](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
