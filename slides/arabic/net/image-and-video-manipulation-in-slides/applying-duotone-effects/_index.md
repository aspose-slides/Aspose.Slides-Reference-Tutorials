---
title: إتقان تأثيرات الفرز الثنائي في Aspose.Slides لـ .NET
linktitle: تطبيق تأثيرات الفرز الثنائي في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: أنشئ شرائح عرض تقديمي جذابة باستخدام Aspose.Slides لـ .NET. تعلم كيفية تطبيق تأثيرات الفرز الثنائي خطوة بخطوة. ارفع مستوى عروضك التقديمية الآن!
weight: 18
url: /ar/net/image-and-video-manipulation-in-slides/applying-duotone-effects/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان تأثيرات الفرز الثنائي في Aspose.Slides لـ .NET

## مقدمة
يعد إنشاء شرائح عرض تقديمي مذهلة بصريًا أمرًا ضروريًا لجذب جمهورك. إحدى الطرق الفعالة لتحسين شرائحك هي تطبيق تأثيرات الفرز الثنائي. في هذا البرنامج التعليمي، سنرشدك خلال عملية تطبيق تأثيرات الفرز الثنائي في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Slides لمكتبة .NET: قم بتنزيل وتثبيت مكتبة Aspose.Slides من[هنا](https://releases.aspose.com/slides/net/).
2. ملف الوسائط: قم بإعداد ملف الوسائط (على سبيل المثال، "aspose-logo.jpg") الذي تريد استخدامه للتأثير الثنائي.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، قم باستيراد مساحات الأسماء الضرورية:
```csharp
using System;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
using Aspose.Slides.Effects;
```
## الخطوة 1: إنشاء عرض تقديمي
ابدأ بإنشاء عرض تقديمي جديد باستخدام مقتطف التعليمات البرمجية التالي:
```csharp
using (Presentation presentation = new Presentation())
{
    // الكود الخاص بك لإنشاء عرض تقديمي موجود هنا
}
```
## الخطوة 2: إضافة صورة إلى العرض التقديمي
حدد المسار إلى ملف الوسائط الخاص بك وأضفه إلى العرض التقديمي:
```csharp
string imagePath = "Your Media Directory" + "aspose-logo.jpg";
IPPImage backgroundImage = presentation.Images.AddImage(Image.FromFile(imagePath));
```
## الخطوة 3: تعيين الخلفية في الشريحة الأولى
اضبط خلفية الشريحة الأولى على الصورة المضافة:
```csharp
presentation.Slides[0].Background.Type = BackgroundType.OwnBackground;
presentation.Slides[0].Background.FillFormat.FillType = FillType.Picture;
presentation.Slides[0].Background.FillFormat.PictureFillFormat.Picture.Image = backgroundImage;
```
## الخطوة 4: إضافة تأثير Duotone إلى الخلفية
أضف تأثير اللون الثنائي إلى خلفية الشريحة الأولى:
```csharp
IDuotone duotone = presentation.Slides[0].Background.FillFormat.PictureFillFormat.Picture.ImageTransform.AddDuotoneEffect();
```
## الخطوة 5: تعيين خصائص الفرز الثنائي
حدد الألوان للتأثير الثنائي:
```csharp
duotone.Color1.ColorType = ColorType.Scheme;
duotone.Color1.SchemeColor = SchemeColor.Accent1;
duotone.Color2.ColorType = ColorType.Scheme;
duotone.Color2.SchemeColor = SchemeColor.Dark2;
```
## الخطوة 6: احصل على القيم الفعالة
استرجاع القيم الفعالة للتأثير الثنائي:
```csharp
IDuotoneEffectiveData duotoneEffective = duotone.GetEffective();
```
## الخطوة 7: إظهار القيم الفعالة
عرض الألوان الثنائية الفعالة في وحدة التحكم:
```csharp
Console.WriteLine("Duotone effective color1: " + duotoneEffective.Color1);
Console.WriteLine("Duotone effective color2: " + duotoneEffective.Color2);
```
كرر هذه الخطوات لشرائح إضافية إذا لزم الأمر.
## خاتمة
يؤدي تحسين شرائح العرض التقديمي باستخدام تأثيرات الفرز الثنائي إلى إضافة لمسة ديناميكية واحترافية. مع Aspose.Slides for .NET، تصبح هذه العملية سلسة، مما يسمح لك بإنشاء عروض تقديمية جذابة دون عناء.
## الأسئلة الشائعة
### هل يمكنني تطبيق تأثيرات الفرز الثنائي على شرائح معينة فقط؟
نعم، يمكنك تطبيق تأثيرات الفرز الثنائي على شرائح محددة عن طريق تعديل الكود وفقًا لذلك.
### هل هناك تأثيرات أخرى لتحويل الصور متوفرة في Aspose.Slides؟
يوفر Aspose.Slides مجموعة من تأثيرات تحويل الصور، بما في ذلك التدرج الرمادي والبني الداكن والمزيد. تحقق من الوثائق للحصول على التفاصيل.
### هل Aspose.Slides متوافق مع أحدث إطار عمل .NET؟
نعم، يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث إصدارات إطار عمل .NET.
### هل يمكنني تخصيص نظام الألوان الثنائي بشكل أكبر؟
قطعاً. استكشف وثائق Aspose.Slides للتعرف على خيارات التخصيص المتقدمة.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
