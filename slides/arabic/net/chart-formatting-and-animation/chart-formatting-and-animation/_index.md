---
"description": "تعرف على كيفية تنسيق الرسوم البيانية وتحريكها في Aspose.Slides لـ .NET، وتعزيز عروضك التقديمية باستخدام صور جذابة."
"linktitle": "تنسيق المخططات والرسوم المتحركة في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تنسيق المخططات والرسوم المتحركة في Aspose.Slides"
"url": "/ar/net/chart-formatting-and-animation/chart-formatting-and-animation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تنسيق المخططات والرسوم المتحركة في Aspose.Slides


إنشاء عروض تقديمية جذابة باستخدام مخططات ورسوم متحركة ديناميكية يُعزز تأثير رسالتك بشكل كبير. يُمكّنك Aspose.Slides for .NET من تحقيق ذلك. في هذا البرنامج التعليمي، سنرشدك خلال عملية تحريك وتنسيق المخططات باستخدام Aspose.Slides for .NET. سنُقسّم الخطوات إلى أقسام سهلة الاستخدام لضمان استيعابك الكامل للمفهوم.

## المتطلبات الأساسية

قبل أن تتعمق في تنسيق المخططات والرسوم المتحركة باستخدام Aspose.Slides، ستحتاج إلى ما يلي:

1. Aspose.Slides لـ .NET: تأكد من تثبيت Aspose.Slides لـ .NET. إذا لم تكن قد قمت بذلك بالفعل، يمكنك [قم بتحميله هنا](https://releases.aspose.com/slides/net/).

2. عرض تقديمي موجود: هل لديك عرض تقديمي موجود يحتوي على مخطط ترغب في تنسيقه وتحريكه.

3. المعرفة الأساسية بلغة C#: ستكون المعرفة بلغة C# مفيدة في تنفيذ الخطوات.

الآن دعونا نبدأ.

## استيراد مساحات الأسماء

للبدء، ستحتاج إلى استيراد مساحات الأسماء اللازمة للوصول إلى ميزات Aspose.Slides. في مشروع C#، أضف ما يلي:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## تحريك عناصر الفئات في الرسم البياني

### الخطوة 1: تحميل العرض التقديمي والوصول إلى الرسم البياني

أولاً، حمّل عرضك التقديمي الحالي وافتح المخطط الذي تريد تحريكه. يفترض هذا المثال أن المخطط موجود في الشريحة الأولى من عرضك التقديمي.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### الخطوة 2: إضافة الرسوم المتحركة إلى عناصر الفئات

الآن، لنُضِفْ رسومًا متحركة لعناصر الفئات. في هذا المثال، نستخدم تأثير التلاشي.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### الخطوة 3: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدّل على القرص.

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## سلسلة الرسوم المتحركة في الرسم البياني

### الخطوة 1: تحميل العرض التقديمي والوصول إلى الرسم البياني

على غرار المثال السابق، ستقوم بتحميل العرض التقديمي والوصول إلى الرسم البياني.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### الخطوة 2: إضافة الرسوم المتحركة إلى السلسلة

الآن، لنُضِف رسومًا متحركة إلى سلسلة الرسوم البيانية. نستخدم هنا أيضًا تأثير التلاشي.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### الخطوة 3: حفظ العرض التقديمي

احفظ العرض التقديمي المعدّل مع السلسلة المتحركة.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## تحريك عناصر السلسلة في المخطط

### الخطوة 1: تحميل العرض التقديمي والوصول إلى الرسم البياني

كما في السابق، قم بتحميل العرض التقديمي والوصول إلى الرسم البياني.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### الخطوة 2: إضافة الرسوم المتحركة إلى عناصر السلسلة

في هذه الخطوة، ستضيف رسومًا متحركة إلى عناصر السلسلة، مما يؤدي إلى إنشاء تأثير بصري مثير للإعجاب.

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

### الخطوة 3: حفظ العرض التقديمي

لا تنسى حفظ العرض التقديمي باستخدام عناصر السلسلة المتحركة.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

تهانينا! لقد تعلمت الآن كيفية تنسيق الرسوم البيانية وتحريكها في Aspose.Slides لـ .NET. هذه التقنيات تجعل عروضك التقديمية أكثر تشويقًا وإثراءً بالمعلومات.

## خاتمة

يوفر Aspose.Slides for .NET أدوات فعّالة لتنسيق الرسوم البيانية وتحريكها، مما يتيح لك إنشاء عروض تقديمية جذابة بصريًا تجذب جمهورك. باتباع هذا الدليل المفصل، يمكنك إتقان فن تحريك الرسوم البيانية وتحسين عروضك التقديمية.

## الأسئلة الشائعة

### 1. أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟

يمكنك الوصول إلى الوثائق على [https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. كيف يمكنني تنزيل Aspose.Slides لـ .NET؟

يمكنك تنزيل Aspose.Slides لـ .NET من [https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. هل هناك نسخة تجريبية مجانية متاحة؟

نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET على [https://releases.aspose.com/](https://releases.aspose.com/).

### 4. هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟

نعم، يمكنك شراء ترخيص مؤقت في [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. أين يمكنني الحصول على الدعم أو طرح الأسئلة حول Aspose.Slides لـ .NET؟

للحصول على الدعم والاستفسارات، قم بزيارة منتدى Aspose.Slides على [https://forum.aspose.com/](https://forum.aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}