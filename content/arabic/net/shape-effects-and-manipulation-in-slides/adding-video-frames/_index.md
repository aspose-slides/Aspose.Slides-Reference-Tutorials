---
title: إضافة إطارات الفيديو إلى شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: إضافة إطارات الفيديو إلى شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين العروض التقديمية الخاصة بك عن طريق إضافة إطارات فيديو باستخدام Aspose.Slides for .NET. قم بإنشاء محتوى جذاب وتفاعلي بسلاسة.
type: docs
weight: 19
url: /ar/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

## مقدمة إلى Aspose.Slides وتكامل الفيديو

Aspose.Slides هي مكتبة شاملة تمكّن المطورين من إنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجياً. من خلال دمج إطارات الفيديو في الشرائح الخاصة بك، يمكنك رفع مستوى العروض التقديمية الخاصة بك وجعلها أكثر ديناميكية وجاذبية.

## المتطلبات الأساسية لدمج مقاطع الفيديو

قبل البدء، تأكد من أن لديك ما يلي:

- Visual Studio أو أي بيئة تطوير .NET مفضلة
- تم تثبيت Aspose.Slides لمكتبة .NET
- عرض تقديمي لـ PowerPoint (PPTX) حيث تريد إضافة إطارات فيديو

## إعداد بيئة التطوير الخاصة بك

1. افتح Visual Studio وقم بإنشاء مشروع .NET جديد.
2.  قم بتثبيت حزمة Aspose.Slides NuGet:`Install-Package Aspose.Slides`.

## تحميل عرض تقديمي والوصول إلى الشرائح

للبدء، قم بتحميل عرض PowerPoint التقديمي الخاص بك باستخدام Aspose.Slides:

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
using Presentation presentation = new Presentation("your-presentation.pptx");

// الوصول إلى الشرائح
ISlideCollection slides = presentation.Slides;
```

## إضافة ملفات الفيديو إلى العرض التقديمي

1. ضع ملفات الفيديو الخاصة بك في مجلد داخل مشروعك.
2. أضف مراجع لهذه الملفات في التعليمات البرمجية الخاصة بك:

```csharp
// إضافة ملفات الفيديو
string videoPath = "path-to-your-videos-folder";
string[] videoFiles = Directory.GetFiles(videoPath, "*.mp4");
```

## وضع إطارات الفيديو على الشرائح

كرر عبر الشرائح وأضف إطارات الفيديو:

```csharp
foreach (ISlide slide in slides)
{
    foreach (string videoFile in videoFiles)
    {
        IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 320, 240, videoFile);
    }
}
```

## تخصيص خصائص إطار الفيديو

يمكنك تخصيص خصائص إطار الفيديو مثل الموضع والحجم والنمط:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.X = 200;
    videoFrame.Y = 150;
    videoFrame.Width = 480;
    videoFrame.Height = 360;
}
```

## التعامل مع خيارات التشغيل

 التحكم في تشغيل الفيديو باستخدام`VideoPlayModePreset` تعداد:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.PlayMode = VideoPlayModePreset.Auto;
}
```

## حفظ وتصدير العرض التقديمي المعدل

احفظ العرض التقديمي الخاص بك بعد إضافة إطارات الفيديو:

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## خاتمة

يؤدي دمج إطارات الفيديو في شرائح العرض التقديمي باستخدام Aspose.Slides إلى تحسين التأثير المرئي للمحتوى الخاص بك. لقد تعلمت كيفية دمج مقاطع الفيديو بسلاسة وتخصيص خصائص إطار الفيديو والتحكم في خيارات التشغيل. ابدأ في إنشاء عروض تقديمية ديناميكية وجذابة تأسر جمهورك.

## الأسئلة الشائعة

### كيف يمكنني إضافة مقاطع فيديو متعددة إلى شريحة واحدة؟

قم بالتكرار خلال ملفات الفيديو الخاصة بك وأضف إطارات الفيديو إلى الشريحة المطلوبة باستخدام الكود المقدم.

### هل يمكنني التحكم في إعدادات تشغيل الفيديو؟

 نعم يمكنك استخدام`VideoPlayModePreset` التعداد لتعيين خيارات التشغيل مثل التشغيل التلقائي.

### ما هي صيغ الفيديو المدعومة؟

يدعم Aspose.Slides العديد من تنسيقات الفيديو، بما في ذلك MP4 وAVI وWMV والمزيد.

### هل من الممكن إضافة مقاطع فيديو برمجياً بلغة C#؟

بالتأكيد، يوفر Aspose.Slides for .NET واجهة برمجة تطبيقات سهلة الاستخدام لإضافة مقاطع فيديو إلى الشرائح برمجيًا باستخدام لغة C#.

### هل يمكنني تعديل مظهر إطار الفيديو؟

نعم، يمكنك تخصيص موضع إطار الفيديو وحجمه والخصائص المرئية الأخرى وفقًا لمتطلباتك.