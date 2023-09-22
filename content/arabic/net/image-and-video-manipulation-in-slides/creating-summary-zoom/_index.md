---
title: إنشاء تكبير ملخص في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: إنشاء تكبير ملخص في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء شرائح عرض تقديمي جذابة مع تكبير الملخص باستخدام Aspose.Slides for .NET. يوفر دليلنا خطوة بخطوة التعليمات البرمجية المصدر ونصائح التخصيص لتعزيز التفاعل.
type: docs
weight: 16
url: /ar/net/image-and-video-manipulation-in-slides/creating-summary-zoom/
---

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة شاملة تمكن المطورين من العمل مع عروض PowerPoint التقديمية في تطبيقات .NET الخاصة بهم. فهو يوفر مجموعة واسعة من الميزات، بما في ذلك إنشاء الشرائح والأشكال والنصوص والصور وتحريرها ومعالجتها والمزيد. في هذا الدليل، سنركز على استخدام Aspose.Slides for .NET لإنشاء شرائح تكبير ملخصة في مجموعات العروض التقديمية.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Visual Studio.
- تم تثبيت .NET Framework أو .NET Core.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## تهيئة بيئة التطوير

1. قم بإنشاء مشروع .NET جديد في Visual Studio.
2. أضف مرجعًا إلى مكتبة Aspose.Slides في مشروعك.

## تحميل عرض تقديمي

للبدء، لنقم بتحميل عرض PowerPoint تقديمي موجود:

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
using var presentation = new Presentation("path_to_your_presentation.pptx");
```

## إضافة شرائح إلى تكبير الملخص

تسمح لك شرائح التكبير/التصغير الموجزة بتقديم نظرة عامة على شرائح متعددة في شريحة واحدة. دعونا نضيف الشرائح التي نريد تلخيصها:

```csharp
// أضف الشرائح المراد تلخيصها
var slideIndexes = new[] { 2, 3, 4 };
var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);
```

## إنشاء شرائح تكبير ملخصة

الآن، لنقم بإنشاء شريحة التكبير/التصغير الموجزة الفعلية التي ستعرض نظرة عامة على الشرائح التي أضفناها سابقًا:

```csharp
//قم بإنشاء شريحة تكبير ملخصة
var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });
```

## تخصيص ملخص سلوك التكبير/التصغير

يمكنك تخصيص سلوك تكبير الملخص، مثل التخطيط والمظهر:

```csharp
// تخصيص إعدادات تكبير الملخص
var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
if (zoomFrame != null)
{
    zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
    zoomFrame.Nodes[0].IsHidden = true; // إخفاء العنوان
    zoomFrame.Nodes[1].IsHidden = true; // إخفاء المحتوى
}
```

## إضافة كود المصدر كمرجع

من أجل راحتك، إليك الكود المصدري الكامل لإنشاء شرائح تكبير ملخصة:

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        using var presentation = new Presentation("path_to_your_presentation.pptx");

        var slideIndexes = new[] { 2, 3, 4 };
        var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);

        var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });

        var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
        if (zoomFrame != null)
        {
            zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
            zoomFrame.Nodes[0].IsHidden = true;
            zoomFrame.Nodes[1].IsHidden = true;
        }

        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## خاتمة

في هذا الدليل، اكتشفنا كيفية استخدام Aspose.Slides لـ .NET لإنشاء شرائح تكبير/تصغير ملخصة في مجموعات العروض التقديمية. يمكن لهذه الميزة القوية أن تعزز التفاعل والمشاركة في العروض التقديمية الخاصة بك، مما يوفر لمسة احترافية للمحتوى الخاص بك.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides لـ .NET من[موقع Aspose.Slides](https://releases.aspose.com/slides/net/).

### هل يمكنني تخصيص مظهر شرائح التكبير/التصغير الموجزة؟

نعم، يمكنك تخصيص مظهر شرائح التكبير/التصغير التلخيصية باستخدام الخصائص المتنوعة التي توفرها مكتبة Aspose.Slides.

### هل Aspose.Slides متوافق مع كل من .NET Framework و.NET Core؟

نعم، يدعم Aspose.Slides كلاً من .NET Framework و.NET Core، مما يمنحك المرونة في اختيار منصة التطوير الخاصة بك.

### هل يمكنني إنشاء شرائح تكبير ملخصة لنطاقات شرائح محددة؟

قطعاً! يمكنك تحديد الشرائح التي تريد تضمينها في تكبير/تصغير الملخص باستخدام فهارس الشرائح الخاصة بها.

### كيف يمكنني إخفاء العنوان والمحتوى في شريحة تكبير الملخص؟

 يمكنك استخدام ال`IsHidden` خاصية عقد SmartArt لإخفاء العنوان والمحتوى الموجود على شريحة تكبير/تصغير الملخص.