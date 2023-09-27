---
title: التحكم في الرسوم المتحركة للشرائح في Aspose.Slides
linktitle: التحكم في الرسوم المتحركة للشرائح في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية التحكم في الرسوم المتحركة للشرائح في عروض PowerPoint التقديمية باستخدام Aspose.Slides for .NET. يوفر هذا الدليل خطوة بخطوة أمثلة على التعليمات البرمجية المصدر لإضافة الرسوم المتحركة وتخصيصها وإدارتها، مما يعزز المظهر المرئي لعروضك التقديمية.
type: docs
weight: 10
url: /ar/net/slide-animation-control/slide-animation-control/
---

## مقدمة إلى الرسوم المتحركة للشرائح باستخدام Aspose.Slides

تبث الرسوم المتحركة للشرائح الحياة في عروضك التقديمية من خلال تقديم الحركة والانتقالات بين الشرائح وعناصر الشرائح. يمكّنك Aspose.Slides for .NET من التحكم في هذه الرسوم المتحركة برمجيًا، مما يمنحك تحكمًا دقيقًا في أنواعها ومددها وخصائصها الأخرى.

## إعداد بيئة التطوير الخاصة بك

قبل أن نتعمق في التعليمات البرمجية، تأكد من تثبيت Aspose.Slides for .NET في مشروعك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/net/) . بعد التنزيل، اتبع تعليمات التثبيت الموجودة في[توثيق](https://reference.aspose.com/slides/net/).

## الخطوة 1: إضافة الشرائح إلى العرض التقديمي

أولاً، لنقم بإنشاء عرض تقديمي جديد وإضافة شرائح إليه. إليك مقتطف الشفرة للبدء:

```csharp
using Aspose.Slides;
using System;

class Program
{
    static void Main()
    {
        // إنشاء عرض تقديمي جديد
        using (Presentation presentation = new Presentation())
        {
            // أضف شرائح
            ISlideCollection slides = presentation.Slides;
            slides.AddEmptySlide(SlideLayoutType.TitleSlide);
            slides.AddEmptySlide(SlideLayoutType.TitleAndContent);

            // احفظ العرض التقديمي
            presentation.Save("presentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## الخطوة 2: تطبيق الرسوم المتحركة للدخول

الآن، دعونا نطبق الرسوم المتحركة للمدخل على عناصر الشريحة. يتم تطبيق الرسوم المتحركة للمدخل عندما تظهر عناصر الشريحة على الشاشة لأول مرة. فيما يلي مثال على إضافة رسم متحرك خافت إلى شكل:

```csharp
// بافتراض أن لديك شكلًا يسمى "RectangleShape" على الشريحة
IShape rectangleShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
EffectFormat entranceEffect = rectangleShape.AnimationSettings.AddEntranceEffect(EffectType.Fade);
entranceEffect.Timing.TriggerType = EffectTriggerType.AfterPrevious;
```

## الخطوة 3: تخصيص تأثيرات الرسوم المتحركة

يمكنك تخصيص تأثيرات الرسوم المتحركة لتناسب احتياجات العرض التقديمي الخاص بك. لنقم بتعديل الرسوم المتحركة المتلاشية للحصول على مدة وتأخير مختلفين:

```csharp
entranceEffect.Timing.Duration = 2000; // مدة الرسوم المتحركة بالمللي ثانية
entranceEffect.Timing.Delay = 1000;    // التأخير قبل بدء الرسوم المتحركة بالمللي ثانية
```

## الخطوة 4: إدارة توقيت الرسوم المتحركة

يتيح لك Aspose.Slides التحكم في توقيت الرسوم المتحركة. يمكنك ضبط الرسوم المتحركة للبدء تلقائيًا أو تشغيلها بنقرة واحدة. فيما يلي كيفية تغيير مشغل الرسوم المتحركة:

```csharp
entranceEffect.Timing.TriggerType = EffectTriggerType.OnClick; // تبدأ الرسوم المتحركة عند النقر
```

## الخطوة 5: إزالة الرسوم المتحركة

إذا كنت تريد إزالة الرسوم المتحركة من عنصر الشريحة، فيمكنك القيام بذلك باستخدام الكود التالي:

```csharp
rectangleShape.AnimationSettings.RemoveAllAnimations();
```

## الخطوة 6: تصدير العرض التقديمي المتحرك

بمجرد إضافة الرسوم المتحركة وتخصيصها، يمكنك تصدير العرض التقديمي إلى تنسيقات مختلفة. فيما يلي مثال للتصدير إلى PDF:

```csharp
presentation.Save("animated_presentation.pdf", SaveFormat.Pdf);
```

## خاتمة

في هذا الدليل، اكتشفنا كيفية الاستفادة من Aspose.Slides لـ .NET للتحكم في الرسوم المتحركة للشرائح في عروض PowerPoint التقديمية. لقد قمنا بتغطية كل شيء بدءًا من إعداد بيئة التطوير الخاصة بك وحتى تطبيق الرسوم المتحركة وتخصيصها وإدارتها. باتباع هذه الخطوات واستخدام أمثلة التعليمات البرمجية المصدر المتوفرة، يمكنك إنشاء عروض تقديمية ديناميكية وجذابة تأسر جمهورك.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides لـ .NET من[هذا الرابط](https://releases.aspose.com/slides/net/)واتبع تعليمات التثبيت الواردة في[توثيق](https://reference.aspose.com/slides/net/).

### هل يمكنني تطبيق الرسوم المتحركة على عناصر شريحة معينة؟

نعم، يمكنك تطبيق الرسوم المتحركة على عناصر الشرائح الفردية مثل الأشكال والصور باستخدام Aspose.Slides for .NET.

### هل من الممكن تصدير العرض التقديمي المتحرك إلى تنسيقات مختلفة؟

قطعاً! يدعم Aspose.Slides تصدير العروض التقديمية المتحركة إلى تنسيقات مختلفة، بما في ذلك PDF وPPTX والمزيد.

### كيف يمكنني التحكم في مدة كل رسوم متحركة؟

 يمكنك التحكم في مدة الرسوم المتحركة عن طريق ضبط`entranceEffect.Timing.Duration` الملكية في التعليمات البرمجية الخاصة بك.

### هل يدعم Aspose.Slides إضافة المؤثرات الصوتية إلى الرسوم المتحركة؟

نعم، يتيح لك Aspose.Slides إضافة مؤثرات صوتية إلى الرسوم المتحركة لتحسين تجربة الوسائط المتعددة لعروضك التقديمية.