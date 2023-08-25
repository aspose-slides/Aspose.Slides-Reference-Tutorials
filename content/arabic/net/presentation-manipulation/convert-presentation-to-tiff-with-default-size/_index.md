---
title: تحويل العرض التقديمي إلى TIFF بالحجم الافتراضي
linktitle: تحويل العرض التقديمي إلى TIFF بالحجم الافتراضي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحويل العروض التقديمية إلى صور TIFF بحجمها الافتراضي بسهولة باستخدام Aspose.Slides for .NET.
type: docs
weight: 27
url: /ar/net/presentation-manipulation/convert-presentation-to-tiff-with-default-size/
---

## مقدمة

Aspose.Slides for .NET هي مكتبة قوية توفر وظائف شاملة لإنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجيًا. إحدى ميزاته الرائعة هي القدرة على تحويل العروض التقديمية إلى تنسيقات صور مختلفة، بما في ذلك TIFF.

## المتطلبات الأساسية

قبل أن نتعمق في عملية الترميز، عليك التأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio أو أي بيئة تطوير .NET أخرى
-  Aspose.Slides لمكتبة .NET (التنزيل من[هنا](https://downloads.aspose.com/slides/net)
- المعرفة الأساسية ببرمجة C#

## تثبيت Aspose.Slides لـ .NET

للبدء، اتبع الخطوات التالية لتثبيت Aspose.Slides لمكتبة .NET:

1.  قم بتنزيل مكتبة Aspose.Slides for .NET من[هنا](https://downloads.aspose.com/slides/net).
2. قم باستخراج ملف ZIP الذي تم تنزيله إلى موقع مناسب على نظامك.
3. افتح مشروع Visual Studio الخاص بك.

## جارٍ تحميل العرض التقديمي

بمجرد دمج مكتبة Aspose.Slides في مشروعك، يمكنك البدء في البرمجة. ابدأ بتحميل ملف العرض التقديمي الذي تريد تحويله إلى TIFF. فيما يلي مثال لكيفية القيام بذلك:

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
using var presentation = new Presentation("your-presentation.pptx");
```

## التحويل إلى TIFF بالحجم الافتراضي

بعد تحميل العرض التقديمي، فإن الخطوة التالية هي تحويله إلى تنسيق صورة TIFF مع الحفاظ على الحجم الافتراضي. وهذا يضمن الحفاظ على تخطيط المحتوى وتصميمه. وإليك كيف يمكنك تحقيق ذلك:

```csharp
// تحويل إلى TIFF بالحجم الافتراضي
var options = new TiffOptions(TiffCompression.Default);
presentation.Save("output.tiff", SaveFormat.Tiff, options);
```

## حفظ صورة TIFF

 أخيرًا، احفظ صورة TIFF التي تم إنشاؤها في الموقع المطلوب باستخدام ملف`Save` طريقة:

```csharp
// احفظ صورة TIFF
presentation.Save("output.tiff", SaveFormat.Tiff);
```

## خاتمة

في هذا البرنامج التعليمي، تناولنا عملية تحويل العرض التقديمي إلى تنسيق TIFF مع الحفاظ على حجمه الافتراضي باستخدام Aspose.Slides for .NET. لقد قمنا بتغطية تحميل العرض التقديمي وإجراء التحويل وحفظ صورة TIFF الناتجة. يعمل Aspose.Slides على تبسيط المهام المعقدة مثل هذه وتمكين المطورين من العمل بكفاءة مع ملفات PowerPoint برمجيًا.

## الأسئلة الشائعة

### كيف يمكنني ضبط جودة صورة TIFF أثناء التحويل؟

يمكنك التحكم في جودة صورة TIFF عن طريق تعديل خيارات الضغط. اضبط مستويات ضغط مختلفة لتحقيق جودة الصورة المطلوبة.

### هل يمكنني تحويل شرائح معينة بدلاً من العرض التقديمي بأكمله؟

 نعم، يمكنك تحويل شرائح معينة بشكل انتقائي إلى تنسيق TIFF باستخدام`SlideEx` للوصول إلى الشرائح الفردية ثم تحويلها وحفظها كصور TIFF.

### هل يتوافق Aspose.Slides for .NET مع الإصدارات المختلفة من PowerPoint؟

نعم، يضمن Aspose.Slides for .NET التوافق عبر تنسيقات PowerPoint المتنوعة، بما في ذلك PPT وPPTX والمزيد.

### هل يمكنني تخصيص إعدادات تحويل TIFF بشكل أكبر؟

قطعاً! يوفر Aspose.Slides for .NET نطاقًا واسعًا من الخيارات لتخصيص عملية تحويل TIFF، مثل تعديل الدقة وأوضاع الألوان والمزيد.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ .NET؟

 للحصول على وثائق وأمثلة شاملة، قم بزيارة[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net).