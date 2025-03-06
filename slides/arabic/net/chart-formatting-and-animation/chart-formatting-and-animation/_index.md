---
title: تنسيق المخطط والرسوم المتحركة في Aspose.Slides
linktitle: تنسيق المخطط والرسوم المتحركة في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تنسيق الرسوم البيانية وتحريكها في Aspose.Slides لـ .NET، مما يعزز عروضك التقديمية من خلال عناصر مرئية جذابة.
weight: 10
url: /ar/net/chart-formatting-and-animation/chart-formatting-and-animation/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


يمكن أن يؤدي إنشاء عروض تقديمية جذابة باستخدام المخططات الديناميكية والرسوم المتحركة إلى تعزيز تأثير رسالتك بشكل كبير. يمكّنك Aspose.Slides for .NET من تحقيق ذلك. في هذا البرنامج التعليمي، سنرشدك خلال عملية تنشيط المخططات وتنسيقها باستخدام Aspose.Slides for .NET. سنقوم بتقسيم الخطوات إلى أقسام يمكن التحكم فيها للتأكد من فهمك للمفهوم بشكل كامل.

## المتطلبات الأساسية

قبل أن تتعمق في تنسيق المخططات والرسوم المتحركة باستخدام Aspose.Slides، ستحتاج إلى ما يلي:

1.  Aspose.Slides لـ .NET: تأكد من تثبيت Aspose.Slides لـ .NET. إذا لم تكن قد فعلت ذلك بالفعل، يمكنك ذلك[قم بتنزيله هنا](https://releases.aspose.com/slides/net/).

2. العرض التقديمي الحالي: احصل على عرض تقديمي موجود يحتوي على مخطط تريد تنسيقه وتحريكه.

3. المعرفة الأساسية بـ C#: الإلمام بـ C# سيكون مفيدًا في تنفيذ الخطوات.

الآن، دعونا نبدأ.

## استيراد مساحات الأسماء

للبدء، ستحتاج إلى استيراد مساحات الأسماء الضرورية للوصول إلى ميزات Aspose.Slides. في مشروعك C#، قم بإضافة ما يلي:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## تحريك عناصر الفئات في الرسم البياني

### الخطوة 1: قم بتحميل العرض التقديمي والوصول إلى المخطط

أولاً، قم بتحميل العرض التقديمي الحالي الخاص بك والوصول إلى المخطط الذي تريد تحريكه. يفترض هذا المثال أن المخطط موجود في الشريحة الأولى من العرض التقديمي.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### الخطوة 2: إضافة الرسوم المتحركة إلى عناصر الفئات

الآن، دعونا نضيف الرسوم المتحركة إلى عناصر الفئات. في هذا المثال، نستخدم تأثير التلاشي.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### الخطوة 3: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدل على القرص.

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## سلسلة الرسوم المتحركة في الرسم البياني

### الخطوة 1: قم بتحميل العرض التقديمي والوصول إلى المخطط

وكما هو الحال في المثال السابق، ستقوم بتحميل العرض التقديمي والوصول إلى المخطط.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### الخطوة 2: إضافة الرسوم المتحركة إلى السلسلة

الآن، دعونا نضيف الرسوم المتحركة إلى سلسلة المخططات. نحن نستخدم تأثير التلاشي هنا أيضًا.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### الخطوة 3: احفظ العرض التقديمي

احفظ العرض التقديمي المعدل مع سلسلة الرسوم المتحركة.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## تحريك عناصر السلسلة في الرسم البياني

### الخطوة 1: قم بتحميل العرض التقديمي والوصول إلى المخطط

كما كان من قبل، قم بتحميل العرض التقديمي والوصول إلى المخطط.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### الخطوة 2: إضافة الرسوم المتحركة إلى عناصر السلسلة

في هذه الخطوة، ستقوم بإضافة رسوم متحركة إلى عناصر السلسلة، مما يؤدي إلى إنشاء تأثير بصري مثير للإعجاب.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int seriesIndex = 0; seriesIndex < chart.ChartData.Series.Count; seriesIndex++)
{
    for (int elementIndex = 0; elementIndex < chart.ChartData.Categories.Count; elementIndex++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, elementIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

### الخطوة 3: احفظ العرض التقديمي

لا تنس حفظ العرض التقديمي مع عناصر سلسلة الرسوم المتحركة.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

تهانينا! لقد تعلمت الآن كيفية تنسيق وتحريك المخططات في Aspose.Slides لـ .NET. يمكن لهذه التقنيات أن تجعل عروضك التقديمية أكثر جاذبية وغنية بالمعلومات.

## خاتمة

يوفر Aspose.Slides for .NET أدوات قوية لتنسيق المخططات والرسوم المتحركة، مما يسمح لك بإنشاء عروض تقديمية جذابة بصريًا تأسر جمهورك. باتباع هذا الدليل المفصّل خطوة بخطوة، يمكنك إتقان فن الرسوم المتحركة للرسوم البيانية وتحسين عروضك التقديمية.

## الأسئلة الشائعة

### 1. أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟

 يمكنك الوصول إلى الوثائق في[https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. كيف يمكنني تنزيل Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides لـ .NET من[https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. هل هناك نسخة تجريبية مجانية متاحة؟

 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET على[https://releases.aspose.com/](https://releases.aspose.com/).

### 4. هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟

 نعم، يمكنك شراء ترخيص مؤقت من[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. أين يمكنني الحصول على الدعم أو طرح الأسئلة حول Aspose.Slides for .NET؟

 للحصول على الدعم والأسئلة، قم بزيارة منتدى Aspose.Slides على[https://forum.aspose.com/](https://forum.aspose.com/).


{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
