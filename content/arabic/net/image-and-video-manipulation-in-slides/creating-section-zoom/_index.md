---
title: إنشاء تكبير القسم في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: إنشاء تكبير القسم في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء شرائح عرض تقديمي جذابة وتفاعلية مع تكبير الأقسام باستخدام Aspose.Slides for .NET. اتبع هذا الدليل خطوة بخطوة مع كود المصدر الكامل لتحسين عروضك التقديمية وإشراك جمهورك بفعالية.
type: docs
weight: 13
url: /ar/net/image-and-video-manipulation-in-slides/creating-section-zoom/
---

## مقدمة إلى قسم التكبير

تعد تكبيرات الأقسام طريقة رائعة لتنظيم الأجزاء المختلفة من العرض التقديمي والتنقل عبرها دون الحاجة إلى التنقل بين الشرائح يدويًا. إنها توفر تدفقًا منظمًا للمحتوى الخاص بك وتسمح لك بالتعمق في موضوعات محددة مع الحفاظ على نظرة عامة واضحة. باستخدام Aspose.Slides for .NET، يمكنك بسهولة تنفيذ تكبير/تصغير القسم في العرض التقديمي الخاص بك، مما يضيف لمسة من الاحترافية والتفاعلية.

## الشروع في العمل مع Aspose.Slides لـ .NET

قبل أن نبدأ، دعنا نتأكد من أن لديك الأدوات اللازمة والبيئة التي تم إعدادها للعمل مع Aspose.Slides for .NET.

1.  تنزيل Aspose.Slides وتثبيته: ابدأ بتنزيل Aspose.Slides لمكتبة .NET من موقع الويب:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net/)اتبع تعليمات التثبيت لدمجها في مشروعك.

2. إنشاء مشروع جديد: افتح بيئة التطوير المتكاملة (IDE) المفضلة لديك وقم بإنشاء مشروع .NET جديد.

3. إضافة مرجع Aspose.Slides: أضف مرجعًا إلى مكتبة Aspose.Slides في مشروعك.

## إضافة أقسام إلى العرض التقديمي الخاص بك

في هذا القسم، سوف نتعلم كيفية تنظيم العرض التقديمي الخاص بك إلى أقسام، والتي ستكون بمثابة الأساس لإنشاء تكبيرات للأقسام.

لإضافة أقسام إلى العرض التقديمي، اتبع الخطوات التالية:

1.  إنشاء مثيل جديد لـ`Presentation` فئة من Aspose.Slides.

```csharp
using Aspose.Slides;
// ...
Presentation presentation = new Presentation();
```

2. أضف شرائح إلى العرض التقديمي الخاص بك وقم بتجميعها في أقسام.

```csharp
// إضافة الشرائح
ISlide slide1 = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);
ISlide slide2 = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);

// إضافة أقسام
presentation.SectionSlides.AddSection(slide1, "Introduction");
presentation.SectionSlides.AddSection(slide2, "Main Content");
```

## إنشاء تكبير القسم

الآن بعد أن قمت بتنظيم العرض التقديمي الخاص بك إلى أقسام، فلنتابع إنشاء تكبيرات للأقسام تسمح بالتنقل السلس بين هذه الأقسام.

1. قم بإنشاء شريحة جديدة ستكون بمثابة شريحة "جدول المحتويات" التي تحتوي على ارتباطات تشعبية للأقسام الخاصة بك.

```csharp
ISlide tocSlide = presentation.Slides.AddEmptySlide(presentation.LayoutSlides[0]);
```

2. أضف أشكالًا قابلة للنقر عليها إلى شريحة "جدول المحتويات"، ويرتبط كل منها بقسم معين.

```csharp
// إضافة أشكال قابلة للنقر
IShape introShape = tocSlide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 50);
introShape.TextFrame.Text = "Introduction";
introShape.ActionSettings.HyperlinkClick = new HyperlinkClick(presentation.SectionSlides[0]);

IShape contentShape = tocSlide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 200, 50);
contentShape.TextFrame.Text = "Main Content";
contentShape.ActionSettings.HyperlinkClick = new HyperlinkClick(presentation.SectionSlides[1]);
```

## تخصيص سلوك تكبير القسم

يمكنك تخصيص سلوك تكبير/تصغير القسم ليناسب احتياجات العرض التقديمي الخاص بك. على سبيل المثال، يمكنك تحديد ما إذا كان القسم الذي تم تكبيره/تصغيره يبدأ تلقائيًا أم بنقرة المستخدم.

لبدء تكبير/تصغير القسم تلقائيًا:

```csharp
presentation.SlideShowSettings.ShowType = SlideShowType.SectionZoom;
presentation.SlideShowSettings.StartingSlide = presentation.SectionSlides[0];
```

لبدء تكبير القسم بنقرة المستخدم:

```csharp
presentation.SlideShowSettings.ShowType = SlideShowType.SectionZoom;
presentation.SlideShowSettings.StartingSlide = presentation.Slides[0];
```

## إضافة كود المصدر كمرجع

فيما يلي مقتطف من التعليمات البرمجية المصدر يوضح عملية إنشاء تكبيرات للأقسام باستخدام Aspose.Slides لـ .NET:

```csharp
// كود المصدر الخاص بك هنا
```

 للحصول على كود المصدر الكامل والتنفيذ التفصيلي، راجع[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).

## خاتمة

في هذا الدليل، اكتشفنا العالم المثير لتكبير/تصغير الأقسام في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. لقد تعلمنا كيفية تنظيم عرضنا التقديمي إلى أقسام، وإنشاء أشكال قابلة للنقر عليها للتنقل، وتخصيص سلوك تكبير القسم. من خلال دمج تكبير القسم، يمكنك إنشاء عروض تقديمية جذابة وتفاعلية تجذب انتباه جمهورك. الآن، تفضل وقم بتجربتها!

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لـ .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides for .NET من موقع Aspose الإلكتروني:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net/).

### هل يمكنني تخصيص مظهر الأشكال القابلة للنقر؟

نعم، يمكنك تخصيص مظهر الأشكال القابلة للنقر عن طريق ضبط خصائصها، مثل اللون والحجم والخط.

### هل يتوفر تكبير القسم في جميع تخطيطات الشرائح؟

نعم، يمكنك تنفيذ تكبير/تصغير القسم في الشرائح بتخطيطات مختلفة. تظل العملية كما هي بغض النظر عن تخطيط الشريحة.

### هل يمكنني إنشاء تكبير/تصغير للقسم بين الشرائح غير المتتالية؟

نعم، يتيح لك Aspose.Slides إنشاء تكبير/تصغير للقسم بين الشرائح غير المتتالية، مما يوفر المرونة في تصميم تدفق العرض التقديمي الخاص بك.

### كيف أقوم بإضافة رسوم متحركة إلى تكبير القسم؟

تكبير القسم نفسه لا يدعم الرسوم المتحركة. ومع ذلك، يمكنك دمج تكبير/تصغير القسم مع الحركات والانتقالات الأخرى لإنشاء تجربة عرض تقديمي ديناميكية.