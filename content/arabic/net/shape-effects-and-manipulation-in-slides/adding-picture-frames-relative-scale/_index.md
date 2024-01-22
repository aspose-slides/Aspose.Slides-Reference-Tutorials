---
title: إضافة برنامج تعليمي لإطارات الصور باستخدام Aspose.Slides .NET
linktitle: إضافة إطارات صور ذات ارتفاع نسبي في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعلم كيفية إضافة إطارات صور ذات ارتفاع نسبي في Aspose.Slides لـ .NET. اتبع هذا الدليل المفصّل خطوة بخطوة للحصول على عروض تقديمية سلسة.
type: docs
weight: 17
url: /ar/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---
## مقدمة
Aspose.Slides for .NET هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها في تطبيقات .NET الخاصة بهم دون عناء. في هذا البرنامج التعليمي، سوف نتعمق في عملية إضافة إطارات صور ذات ارتفاع نسبي للمقياس باستخدام Aspose.Slides for .NET. اتبع هذا الدليل المفصّل خطوة بخطوة لتعزيز مهاراتك في إنشاء العروض التقديمية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio أو أي بيئة تطوير مفضلة أخرى لـ C#.
- تمت إضافة Aspose.Slides لمكتبة .NET إلى مشروعك.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية إلى كود C# الخاص بك. تضمن هذه الخطوة أن لديك إمكانية الوصول إلى الفئات والوظائف التي توفرها مكتبة Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## الخطوة 1: قم بإعداد مشروعك
ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك. تأكد من إضافة مكتبة Aspose.Slides for .NET إلى مشروعك من خلال الرجوع إليها.
## الخطوة 2: تحميل العرض التقديمي والصورة
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // قم بتحميل الصورة المراد إضافتها إلى مجموعة صور العرض التقديمي
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
في هذه الخطوة، نقوم بإنشاء كائن عرض تقديمي جديد ونقوم بتحميل الصورة التي نريد إضافتها إلى العرض التقديمي.
## الخطوة 3: إضافة إطار الصورة إلى الشريحة
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
الآن، قم بإضافة إطار صورة إلى الشريحة الأولى من العرض التقديمي. اضبط المعلمات مثل نوع الشكل والموضع والأبعاد وفقًا لمتطلباتك.
## الخطوة 4: تعيين العرض والارتفاع النسبي
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
قم بتعيين ارتفاع وعرض المقياس النسبي لإطار الصورة لتحقيق تأثير القياس المطلوب.
## الخطوة 5: حفظ العرض التقديمي
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
وأخيرًا، احفظ العرض التقديمي مع إطار الصورة المضاف بتنسيق الإخراج المحدد.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة إطارات صور بارتفاع مقياس نسبي باستخدام Aspose.Slides لـ .NET. قم بتجربة صور ومواضع ومقاييس مختلفة لإنشاء عروض تقديمية جذابة بصريًا ومصممة خصيصًا لتلبية احتياجاتك.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات البرمجة الأخرى؟
يدعم Aspose.Slides بشكل أساسي لغات .NET، ولكن يمكنك استكشاف منتجات Aspose الأخرى للتوافق مع الأنظمة الأساسية المختلفة.
### أين يمكنني العثور على وثائق مفصلة عن Aspose.Slides لـ .NET؟
 الرجوع إلى[توثيق](https://reference.aspose.com/slides/net/) للحصول على معلومات وأمثلة شاملة.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
 نعم يمكنك الحصول على[تجربة مجانية](https://releases.aspose.com/) لتقييم إمكانيات المكتبة.
### كيف يمكنني الحصول على دعم Aspose.Slides لـ .NET؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لطلب المساعدة من المجتمع وخبراء Aspose.
### أين يمكنني شراء Aspose.Slides لـ .NET؟
 يمكنك شراء Aspose.Slides لـ .NET من[صفحة الشراء](https://purchase.aspose.com/buy).