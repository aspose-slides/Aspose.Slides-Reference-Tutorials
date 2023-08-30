---
title: محاذاة الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: محاذاة الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية محاذاة الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. يوفر هذا الدليل خطوة بخطوة أمثلة على التعليمات البرمجية المصدر، ويغطي المحاذاة الأفقية والرأسية، وتوزيع الأشكال، ومحاذاة المجموعات، والمزيد.
type: docs
weight: 10
url: /ar/net/shape-alignment-and-formatting-in-slides/aligning-shapes/
---

## مقدمة لمحاذاة الأشكال في شرائح العرض التقديمي

في عالم تصميم العروض التقديمية، تلعب المحاذاة الصحيحة للأشكال داخل الشرائح دورًا محوريًا في نقل المعلومات بشكل فعال. قد يكون تحقيق المحاذاة الدقيقة في بعض الأحيان مهمة شاقة، خاصة عند التعامل مع العروض التقديمية المعقدة. ولحسن الحظ، يأتي Aspose.Slides for .NET للإنقاذ بفضل إمكاناته القوية لمحاذاة الأشكال بسلاسة. سيرشدك هذا الدليل خطوة بخطوة خلال عملية محاذاة الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET، مع استكمال أمثلة التعليمات البرمجية المصدر.

## المتطلبات الأساسية

قبل الغوص في الدليل التفصيلي، تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio: ستحتاج إلى تثبيت برنامج Visual Studio لتطوير .NET.
-  Aspose.Slides لـ .NET: قم بتنزيل Aspose.Slides لـ .NET وتثبيته من[هنا](https://releases.aspose.com/slides/net/).

## إعداد المشروع

1. قم بإنشاء مشروع جديد في Visual Studio باستخدام إطار عمل .NET.
2. أضف مرجعًا إلى مجموعة Aspose.Slides في مشروعك.

## تحميل عرض تقديمي

للبدء، قم بتحميل العرض التقديمي الذي تريد العمل معه باستخدام الكود التالي:

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
Presentation presentation = new Presentation("your-presentation.pptx");
```

## الوصول إلى الأشكال في الشرائح

قبل محاذاة الأشكال، تحتاج إلى الوصول إليها. وإليك كيف يمكنك القيام بذلك:

```csharp
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.Slides[0];

// الوصول إلى الأشكال عن طريق الفهرس
IShape shape1 = slide.Shapes[0];
IShape shape2 = slide.Shapes[1];
```

## المحاذاة الأفقية

 يمكنك محاذاة الأشكال أفقيًا باستخدام`HorizontalAlignment` ملكية. هنا مثال:

```csharp
// محاذاة الأشكال أفقيا
shape1.TextFrame.Paragraphs[0].ParagraphFormat.Alignment = TextAlignment.Center;
shape2.TextFrame.Paragraphs[0].ParagraphFormat.Alignment = TextAlignment.Center;
```

## انحياز عمودي

 يمكن تحقيق المحاذاة العمودية باستخدام`VerticalAlignment` ملكية:

```csharp
// محاذاة الأشكال عموديا
shape1.TextFrame.TextFrameFormat.AnchoringType = TextAnchorType.Top;
shape2.TextFrame.TextFrameFormat.AnchoringType = TextAnchorType.Top;
```

## محاذاة إلى الشريحة

 لمحاذاة الأشكال فيما يتعلق بالشريحة، يمكنك استخدام`AlignToSlide` طريقة:

```csharp
// محاذاة الأشكال إلى الشريحة
shape1.AlignToSlide(ShapesAlignmentType.Bottom);
shape2.AlignToSlide(ShapesAlignmentType.Bottom);
```

## توزيع الأشكال

يعد توزيع الأشكال بالتساوي أمرًا ضروريًا للحفاظ على تخطيط نظيف. إليك كيفية توزيع الأشكال أفقيًا:

```csharp
// توزيع الأشكال أفقيا
slide.Shapes.DistributeHorizontally();
```

## تطبيق المحاذاة على المجموعات

إذا كان العرض التقديمي يحتوي على أشكال مجمعة، فيمكنك محاذاة المجموعة بأكملها:

```csharp
//الوصول إلى شكل مجمع
IGroupShape groupShape = (IGroupShape)slide.Shapes[2];

// قم بمحاذاة المجموعة أفقيًا
groupShape.Align(ShapesAlignmentType.Center);
```

## حفظ العرض التقديمي المعدل

بعد محاذاة الأشكال، احفظ العرض التقديمي المعدل:

```csharp
// احفظ العرض التقديمي المعدل
presentation.Save("aligned-presentation.pptx", SaveFormat.Pptx);
```

## خاتمة

يوفر Aspose.Slides for .NET مجموعة شاملة من الأدوات لمحاذاة الأشكال في شرائح العرض التقديمي بسهولة. بدءًا من المحاذاة الأفقية والرأسية وحتى توزيع الأشكال ومحاذاة المجموعات، يمكنك تحسين المظهر المرئي لعروضك التقديمية دون عناء.

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل وتثبيت Aspose.Slides لـ .NET من[هنا](https://releases.aspose.com/slides/net/).

### هل يمكنني محاذاة الأشكال أفقيًا وعموديًا في وقت واحد؟

نعم، يمكنك محاذاة الأشكال أفقيًا وعموديًا لتحقيق موضع دقيق داخل الشرائح.

### هل من الممكن محاذاة الأشكال داخل كائن مجمع؟

قطعاً! يسمح لك Aspose.Slides for .NET بمحاذاة الأشكال داخل الكائنات المجمعة، مما يجعل الترتيبات المعقدة أمرًا سهلاً.

### هل يدعم Aspose.Slides for .NET محاذاة الأشكال في تخطيطات الشرائح المختلفة؟

نعم، يمكنك محاذاة الأشكال في تخطيطات الشرائح المختلفة، مما يضمن الاتساق والاحترافية عبر العرض التقديمي بأكمله.

### كيف يمكنني توزيع الأشكال بالتساوي عبر الشريحة؟

يمكنك توزيع الأشكال بالتساوي أفقيًا أو رأسيًا باستخدام الطرق المناسبة التي يوفرها Aspose.Slides لـ .NET.