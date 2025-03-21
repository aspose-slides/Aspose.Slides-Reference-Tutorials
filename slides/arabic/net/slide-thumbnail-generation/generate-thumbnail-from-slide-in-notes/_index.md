---
title: إنشاء صورة مصغرة من Slide in Notes
linktitle: إنشاء صورة مصغرة من Slide in Notes
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء صور مصغرة من الشرائح في قسم الملاحظات في العرض التقديمي الخاص بك باستخدام Aspose.Slides for .NET. تعزيز المحتوى المرئي الخاص بك!
weight: 12
url: /ar/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة من Slide in Notes


في عالم العروض التقديمية الحديثة، المحتوى المرئي هو الملك. يعد إنشاء شرائح جذابة أمرًا ضروريًا للتواصل الفعال. تتمثل إحدى طرق تحسين العروض التقديمية في إنشاء صور مصغرة من الشرائح، خاصة عندما تريد التركيز على تفاصيل محددة أو مشاركة نظرة عامة. Aspose.Slides for .NET هي أداة قوية يمكنها مساعدتك في تحقيق ذلك بسلاسة. في هذا الدليل التفصيلي، سنرشدك خلال عملية إنشاء صور مصغرة من الشرائح في قسم الملاحظات في العرض التقديمي باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية

قبل أن نتعمق في التفاصيل، يجب أن تتوفر لديك المتطلبات الأساسية التالية:

### 1. Aspose.Slides لـ .NET

 تأكد من تثبيت Aspose.Slides for .NET وإعداده. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

### 2. بيئة الشبكة

يجب أن تكون لديك بيئة تطوير .NET جاهزة على نظامك.

### 3. ملف العرض التقديمي

 أن يكون لديك ملف عرض تقديمي (على سبيل المثال،`ThumbnailFromSlideInNotes.pptx`) الذي تريد إنشاء صور مصغرة منه.

الآن، دعونا نقسم العملية إلى خطوات:

## الخطوة 1: استيراد مساحات الأسماء

أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية للعمل مع Aspose.Slides. أضف الكود التالي في بداية البرنامج النصي C# الخاص بك:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## الخطوة 2: قم بتحميل العرض التقديمي

 بعد ذلك، ستحتاج إلى تحميل ملف العرض التقديمي الذي يحتوي على الشرائح مع الملاحظات. استخدم الكود التالي لإنشاء مثيل a`Presentation` فصل:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // الكود الخاص بك يذهب هنا
}
```

## الخطوة 3: الوصول إلى الشريحة

يمكنك اختيار الشريحة في العرض التقديمي التي تريد إنشاء صورة مصغرة لها. في هذا المثال، سنصل إلى الشريحة الأولى:

```csharp
ISlide sld = pres.Slides[0];
```

## الخطوة 4: تحديد الأبعاد المطلوبة

حدد الأبعاد (العرض والارتفاع) للصورة المصغرة التي تريد إنشاءها. على سبيل المثال:

```csharp
int desiredX = 1200; // عرض
int desiredY = 800;  // ارتفاع
```

## الخطوة 5: حساب عوامل القياس

للتأكد من أن الصورة المصغرة تناسب الأبعاد المطلوبة، قم بحساب عوامل القياس كما يلي:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## الخطوة 6: إنشاء صورة مصغرة

الآن، قم بإنشاء صورة مصغرة كاملة الحجم باستخدام عوامل القياس المحسوبة:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## الخطوة 7: احفظ الصورة المصغرة

أخيرًا، احفظ الصورة المصغرة التي تم إنشاؤها كصورة JPEG:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

هذا كل شيء! لقد نجحت في إنشاء صورة مصغرة من شريحة في قسم الملاحظات في العرض التقديمي الخاص بك باستخدام Aspose.Slides for .NET.

## خاتمة

يمكن أن يؤدي دمج الصور المصغرة في عروضك التقديمية إلى تحسين جاذبيتها البصرية وفعاليتها بشكل كبير. يجعل Aspose.Slides for .NET هذه العملية واضحة ومباشرة، مما يسمح لك بإنشاء صور مصغرة مخصصة من الشرائح الخاصة بك بسهولة.

## الأسئلة الشائعة (الأسئلة المتداولة)

### ما التنسيقات التي يمكنني حفظ الصور المصغرة التي تم إنشاؤها بها؟
يمكنك حفظ الصور المصغرة بتنسيقات مختلفة، بما في ذلك JPEG وPNG والمزيد، وفقًا لمتطلباتك.

### هل يمكنني إنشاء صور مصغرة لشرائح متعددة في وقت واحد؟
نعم، يمكنك تكرار الشرائح في العرض التقديمي الخاص بك وإنشاء صور مصغرة لكل منها.

### هل يتوافق Aspose.Slides for .NET مع أطر عمل .NET المختلفة؟
نعم، يتوافق Aspose.Slides for .NET مع أطر عمل .NET المختلفة، بما في ذلك .NET Core و.NET Framework.

### هل يمكنني تخصيص مظهر الصور المصغرة التي تم إنشاؤها؟
قطعاً! يوفر Aspose.Slides for .NET خيارات لتخصيص مظهر الصور المصغرة، مثل الأبعاد والجودة والمزيد.

### أين يمكنني الحصول على الدعم أو المساعدة الإضافية فيما يتعلق بـ Aspose.Slides لـ .NET؟
 يمكنك العثور على المساعدة والتفاعل مع مجتمع Aspose على[منتدى الدعم Aspose](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
