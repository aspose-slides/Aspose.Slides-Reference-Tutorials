---
title: إضافة إطارات صور ذات ارتفاع نسبي في Aspose.Slides
linktitle: إضافة إطارات صور ذات ارتفاع نسبي في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين العروض التقديمية الخاصة بك عن طريق إضافة إطارات صور ذات ارتفاع نسبي للمقياس باستخدام Aspose.Slides for .NET. قم بإنشاء شرائح جذابة بصريًا دون عناء.
type: docs
weight: 17
url: /ar/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

## مقدمة

في عالم العروض التقديمية الديناميكي، تلعب العناصر المرئية دورًا محوريًا في نقل المعلومات بشكل فعال. يمكّنك Aspose.Slides for .NET من تجاوز الأساسيات ورفع مستوى العروض التقديمية الخاصة بك من خلال دمج إطارات الصور ذات الارتفاع النسبي. سيأخذك هذا الدليل خلال العملية خطوة بخطوة، ويزودك بالمهارات اللازمة لإنشاء شرائح جذابة بصريًا ومميزة. سواء كنت مطورًا متمرسًا أو بدأت للتو في Aspose.Slides، سيساعدك هذا الدليل على إتقان فن إضافة إطارات صور ذات ارتفاع نسبي.

## إضافة إطارات صور ذات ارتفاع نسبي في Aspose.Slides

عندما يتعلق الأمر بإضافة إطارات صور ذات ارتفاع نسبي في Aspose.Slides، فإن العملية تكون بديهية بشكل ملحوظ. اتبع هذه الخطوات لتحسين العروض التقديمية الخاصة بك:

### الخطوة 1: تهيئة العرض التقديمي

ابدأ بتهيئة كائن العرض التقديمي باستخدام الكود التالي:

```csharp
Presentation presentation = new Presentation();
```

### الخطوة 2: إضافة شريحة

لإضافة شريحة جديدة، استخدم مقتطف التعليمات البرمجية التالي:

```csharp
ISlide slide = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);
```

### الخطوة 3: إدراج صورة

حان الوقت الآن لإدراج الصورة في الشريحة. يوضح الكود التالي كيفية تحقيق ذلك:

```csharp
byte[] imageBytes = File.ReadAllBytes("image.jpg");
IPPImage image = presentation.Images.AddImage(imageBytes);
slide.Shapes.AddPictureFrame(ShapeType.Rectangle, 100, 100, image.Width, image.Height, image);
```

### الخطوة 4: ضبط ارتفاع المقياس

لإنشاء ارتفاع نسبي لإطار الصورة، استخدم مقتطف الكود أدناه:

```csharp
IPictureFrame pictureFrame = (IPictureFrame)slide.Shapes[0];
pictureFrame.PictureFormat.Picture.ImageScale.HeightScale = 50; // اضبط نسبة المقياس حسب الرغبة
```

## الأسئلة الشائعة

### كيف يمكنني تغيير ارتفاع مقياس إطار الصورة؟

 لتغيير ارتفاع مقياس إطار الصورة، يمكنك استخدام`PictureFormat.Picture.ImageScale.HeightScale` الخاصية وتعيينها قيمة النسبة المئوية المطلوبة.

### هل يمكنني إضافة إطارات صور متعددة إلى شريحة واحدة؟

نعم، يمكنك إضافة إطارات صور متعددة إلى شريحة واحدة عن طريق اتباع الخطوات المذكورة سابقًا لكل إطار صورة تريد إدراجه.

### هل من الممكن تحريك إطارات الصور في العرض التقديمي؟

قطعاً! يوفر Aspose.Slides إمكانات رسوم متحركة قوية. يمكنك تطبيق الرسوم المتحركة على إطارات الصور باستخدام تأثيرات الرسوم المتحركة المتنوعة المتوفرة في المكتبة.

### ما هي تنسيقات الصور المدعومة للإدراج؟

يدعم Aspose.Slides مجموعة واسعة من تنسيقات الصور، بما في ذلك JPEG وPNG وGIF وBMP والمزيد. يمكنك إدراج صور بهذه التنسيقات بسلاسة في شرائحك.

### كيف يمكنني ضبط موضع إطار الصورة على الشريحة؟

 يمكنك ضبط موضع إطار الصورة عن طريق تحديد إحداثيات X وY عند إضافة إطار الصورة باستخدام`slide.Shapes.AddPictureFrame` طريقة.

### هل من الممكن تخصيص مظهر إطار الصورة؟

نعم، يمكنك تخصيص مظهر إطار الصورة باستخدام خصائص مثل لون الحدود ولون التعبئة والمزيد. راجع وثائق Aspose.Slides للحصول على معلومات مفصلة.

## خاتمة

يمكن أن يؤدي دمج إطارات الصور ذات الحجم النسبي في عروضك التقديمية إلى تعزيز جاذبيتها البصرية ومشاركتها بشكل كبير. باستخدام Aspose.Slides for .NET، تصبح العملية واضحة وقابلة للتخصيص، مما يسمح لك بإنشاء شرائح مذهلة تترك تأثيرًا دائمًا. سواء كنت تقوم بصياغة محتوى تعليمي، أو عروض تقديمية للأعمال، أو عروض إبداعية، فإن إتقان هذه الميزة سيؤدي بلا شك إلى رفع مستوى لعبة العرض التقديمي لديك.

تذكر أن المفتاح يكمن في التجربة والإبداع. من خلال تسخير قوة Aspose.Slides، فإنك لا تقوم فقط بإنشاء شرائح؛ أنت تصنع تجارب غامرة لجمهورك.