---
title: تحريك عناصر السلسلة في الرسم البياني
linktitle: تحريك عناصر السلسلة في الرسم البياني
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعلم كيفية تحريك سلسلة المخططات باستخدام Aspose.Slides لـ .NET. قم بإنشاء عروض تقديمية جذابة باستخدام صور ديناميكية. دليل الخبراء مع أمثلة التعليمات البرمجية.
weight: 13
url: /ar/net/chart-formatting-and-animation/animating-series-elements/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


هل تتطلع إلى تحسين عروض PowerPoint التقديمية الخاصة بك باستخدام المخططات والرسوم المتحركة الجذابة؟ يمكن أن يساعدك Aspose.Slides for .NET على تحقيق ذلك. في هذا البرنامج التعليمي خطوة بخطوة، سنوضح لك كيفية تحريك عناصر السلسلة في مخطط باستخدام Aspose.Slides for .NET. تسمح لك هذه المكتبة القوية بإنشاء عروض PowerPoint التقديمية ومعالجتها وتخصيصها برمجياً، مما يوفر لك التحكم الكامل في شرائحك ومحتواها.

## المتطلبات الأساسية

قبل أن نتعمق في عالم الرسوم المتحركة للمخططات باستخدام Aspose.Slides for .NET، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Slides لـ .NET: تحتاج إلى تثبيت Aspose.Slides لـ .NET. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيله من[صفحة التحميل](https://releases.aspose.com/slides/net/).

2. عرض PowerPoint التقديمي الحالي: يجب أن يكون لديك عرض تقديمي PowerPoint موجود مع مخطط تريد تحريكه. إذا لم يكن لديك واحد، قم بإنشاء عرض تقديمي لـ PowerPoint باستخدام مخطط.

الآن بعد أن حصلت على المتطلبات الأساسية اللازمة، فلنبدأ بتحريك عناصر السلسلة في مخطط باستخدام Aspose.Slides for .NET.

## استيراد مساحات الأسماء

قبل البدء في البرمجة، تحتاج إلى استيراد مساحات الأسماء المطلوبة للعمل مع Aspose.Slides لـ .NET. ستوفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب الضرورية لإنشاء الرسوم المتحركة.

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## الخطوة 1: قم بتحميل العرض التقديمي

 أولاً، تحتاج إلى تحميل عرض PowerPoint التقديمي الموجود لديك والذي يحتوي على المخطط الذي تريد تحريكه. تأكد من استبدال`"Your Document Directory"` بالمسار الفعلي لملف العرض التقديمي الخاص بك.

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    //سيتم وضع الكود الخاص بك للرسوم المتحركة للمخطط هنا.
    // سنغطي ذلك في الخطوات اللاحقة.
    
    // احفظ العرض التقديمي بالرسوم المتحركة
    presentation.Save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
```

## الخطوة 2: الحصول على مرجع لكائن المخطط

تحتاج إلى الوصول إلى المخطط داخل العرض التقديمي الخاص بك. للقيام بذلك، الحصول على مرجع إلى كائن التخطيط. نحن نفترض أن المخطط موجود في الشريحة الأولى، ولكن يمكنك ضبط ذلك إذا كان المخطط الخاص بك موجودًا في شريحة مختلفة.

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## الخطوة 3: تحريك عناصر السلسلة

الآن يأتي الجزء المثير - تحريك عناصر السلسلة في المخطط الخاص بك. يمكنك إضافة رسوم متحركة لجعل العناصر تظهر أو تختفي بطريقة جذابة بصريًا. في هذا المثال، سنجعل العناصر تظهر واحدًا تلو الآخر.

```csharp
// قم بتحريك المخطط بالكامل ليتلاشى بعد الرسم المتحرك السابق.
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// تحريك العناصر داخل السلسلة. اضبط الفهارس حسب الحاجة.
for (int i = 0; i < chart.Series.Count; i++)
{
    for (int j = 0; j < chart.Series[i].DataPoints.Count; j++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تحريك عناصر السلسلة في مخطط باستخدام Aspose.Slides لـ .NET. باستخدام هذه المعرفة، يمكنك إنشاء عروض PowerPoint تقديمية ديناميكية وجذابة تأسر جمهورك.

 Aspose.Slides for .NET هي أداة قوية للعمل مع ملفات PowerPoint برمجيًا، وتفتح عالمًا من الإمكانيات لإنشاء عروض تقديمية احترافية. لا تتردد في استكشاف[توثيق](https://reference.aspose.com/slides/net/)لمزيد من الميزات المتقدمة وخيارات التخصيص.

## أسئلة مكررة

### 1. هل Aspose.Slides for .NET مجاني للاستخدام؟

 Aspose.Slides for .NET هي مكتبة تجارية، ولكن يمكنك استكشافها من خلال نسخة تجريبية مجانية. للاستخدام الكامل، سوف تحتاج إلى شراء ترخيص من[هنا](https://purchase.aspose.com/buy).

### 2. هل يمكنني تحريك العناصر الأخرى في PowerPoint باستخدام Aspose.Slides لـ .NET؟

نعم، يسمح لك Aspose.Slides for .NET بتحريك عناصر PowerPoint المختلفة، بما في ذلك الأشكال والنصوص والصور والمخططات، كما هو موضح في هذا البرنامج التعليمي.

### 3. هل البرمجة باستخدام Aspose.Slides لـ .NET مناسبة للمبتدئين؟

في حين أن الفهم الأساسي لـ C# وPowerPoint مفيد، فإن Aspose.Slides for .NET يوفر وثائق وأمثلة موسعة لمساعدة المستخدمين على جميع مستويات المهارة.

### 4. هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات .NET الأخرى، مثل VB.NET؟

نعم، يمكن استخدام Aspose.Slides for .NET مع العديد من لغات .NET، بما في ذلك C# وVB.NET.

### 5. كيف يمكنني الحصول على دعم المجتمع أو المساعدة فيما يتعلق بـ Aspose.Slides لـ .NET؟

 إذا كانت لديك أسئلة أو كنت بحاجة إلى المساعدة، يمكنك زيارة[Aspose.Slides لمنتدى .NET](https://forum.aspose.com/) لدعم المجتمع.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
