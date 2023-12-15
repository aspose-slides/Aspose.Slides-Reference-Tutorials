---
title: إنشاء صورة مصغرة لملاحظة SmartArt التابعة في Aspose.Slides
linktitle: إنشاء صورة مصغرة لملاحظة SmartArt التابعة في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء صور مصغرة لملاحظات SmartArt الفرعية باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع كود المصدر الكامل.
type: docs
weight: 15
url: /ar/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

## مقدمة لإنشاء صورة مصغرة لملاحظة SmartArt Child Note

في هذا البرنامج التعليمي، سنتعرف على عملية إنشاء صورة مصغرة لملاحظة SmartArt الفرعية باستخدام مكتبة Aspose.Slides في .NET. Aspose.Slides عبارة عن واجهة برمجة تطبيقات قوية تتيح للمطورين العمل مع عروض PowerPoint التقديمية برمجيًا. سنذهب خطوة بخطوة، ونوضح الكود ونشرح كل جزء من العملية.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Visual Studio (أو أي بيئة تطوير .NET أخرى).
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## إعداد المشروع

1. قم بإنشاء مشروع C# جديد في Visual Studio.
2. قم بإضافة مرجع إلى Aspose.Slides لمكتبة .NET.

## جارٍ تحميل العرض التقديمي

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // قم بتحميل العرض التقديمي
        using (Presentation presentation = new Presentation("presentation.pptx"))
        {
            // الرمز الخاص بك هنا
        }
    }
}
```

## الوصول إلى أشكال SmartArt

```csharp
// على افتراض أن لدينا شكل SmartArt على الشريحة الأولى
ISlide slide = presentation.Slides[0];
ISmartArt smartArt = (ISmartArt)slide.Shapes[0];

// الوصول إلى العقد الفرعية
ISmartArtNodeCollection nodes = smartArt.AllNodes;
```

## إنشاء صورة مصغرة لملاحظة الطفل

```csharp
foreach (ISmartArtNode node in nodes)
{
    // بافتراض أن العقدة بها عقد فرعية
    ISmartArtNodeCollection childNodes = node.ChildNodes;

    // إنشاء صورة مصغرة
    using (Bitmap thumbnail = childNodes.GenerateThumbnail(new Size(200, 150)))
    {
        //احفظ الصورة المصغرة أو قم بإجراء عمليات أخرى
        thumbnail.Save($"thumbnail_{node.Text}.png");
    }
}
```

## حفظ العرض التقديمي مع الصور المصغرة

```csharp
// احفظ العرض التقديمي بالصور المصغرة
presentation.Save("presentation_with_thumbnails.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء صور مصغرة لملاحظات SmartArt الفرعية باستخدام Aspose.Slides لـ .NET. لقد قمنا بتغطية العملية بأكملها بدءًا من تحميل العرض التقديمي وحتى الوصول إلى أشكال SmartArt وإنشاء صور مصغرة وحفظ العرض التقديمي باستخدام الصور المصغرة.

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides for .NET من موقعهم على الويب[هنا](https://releases.aspose.com/slides/net/).

### هل يمكنني إنشاء صور مصغرة لأشكال أخرى أيضًا؟

نعم، يوفر Aspose.Slides طرقًا متنوعة لإنشاء صور مصغرة لأنواع مختلفة من الأشكال، بما في ذلك الصور والمخططات والمزيد.

### هل Aspose.Slides مناسب لكل من المشاريع الشخصية والتجارية؟

نعم، يمكن استخدام Aspose.Slides في كل من المشاريع الشخصية والتجارية. ومع ذلك، تأكد من مراجعة شروط الترخيص الخاصة بهم قبل النشر.

### هل يمكنني تخصيص مظهر الصور المصغرة التي تم إنشاؤها؟

قطعاً! يتيح لك Aspose.Slides تخصيص الحجم والجودة والخصائص الأخرى للصور المصغرة التي تم إنشاؤها لتتناسب مع متطلباتك.

### هل يدعم Aspose.Slides لغات برمجة أخرى غير .NET؟

نعم، يتوفر Aspose.Slides للعديد من لغات البرمجة، بما في ذلك Java وPython والمزيد، مما يجعله متعدد الاستخدامات لبيئات التطوير المختلفة.