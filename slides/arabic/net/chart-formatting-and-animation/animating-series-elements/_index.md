---
"description": "تعلم كيفية تحريك سلسلة من المخططات باستخدام Aspose.Slides لـ .NET. أنشئ عروضًا تقديمية جذابة بمؤثرات بصرية ديناميكية. دليل خبير مع أمثلة برمجية."
"linktitle": "تحريك عناصر السلسلة في المخطط"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تحريك عناصر السلسلة في المخطط"
"url": "/ar/net/chart-formatting-and-animation/animating-series-elements/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحريك عناصر السلسلة في المخطط


هل ترغب في تحسين عروض PowerPoint التقديمية بمخططات ورسوم متحركة جذابة؟ يُمكن لـ Aspose.Slides for .NET مساعدتك في تحقيق ذلك. في هذا البرنامج التعليمي المُفصّل، سنوضح لك كيفية تحريك عناصر السلسلة في مخطط باستخدام Aspose.Slides for .NET. تُتيح لك هذه المكتبة القوية إنشاء عروض PowerPoint التقديمية وتعديلها وتخصيصها برمجيًا، مما يمنحك تحكمًا كاملاً في شرائحك ومحتواها.

## المتطلبات الأساسية

قبل أن نتعمق في عالم الرسوم المتحركة للمخططات باستخدام Aspose.Slides لـ .NET، تأكد من توفر المتطلبات الأساسية التالية لديك:

1. Aspose.Slides لـ .NET: يجب تثبيت Aspose.Slides لـ .NET. إذا لم يكن مثبتًا لديك، يمكنك تنزيله من [صفحة التحميل](https://releases.aspose.com/slides/net/).

2. عرض تقديمي موجود على PowerPoint: يجب أن يكون لديك عرض تقديمي موجود على PowerPoint مع مخطط ترغب في تحريكه. إذا لم يكن لديك واحد، أنشئ عرضًا تقديميًا على PowerPoint مع مخطط.

الآن بعد أن أصبحت لديك المتطلبات الأساسية اللازمة، فلنبدأ في تحريك عناصر السلسلة في مخطط باستخدام Aspose.Slides لـ .NET.

## استيراد مساحات الأسماء

قبل البدء بالبرمجة، عليك استيراد مساحات الأسماء اللازمة للعمل مع Aspose.Slides لـ .NET. ستتيح لك هذه المساحات الوصول إلى الفئات والأساليب اللازمة لإنشاء الرسوم المتحركة.

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## الخطوة 1: تحميل العرض التقديمي

أولاً، عليك تحميل عرض PowerPoint التقديمي الحالي الذي يحتوي على المخطط الذي تريد تحريكه. تأكد من استبداله `"Your Document Directory"` مع المسار الفعلي لملف العرض التقديمي الخاص بك.

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // سيتم وضع الكود الخاص برسومات الرسوم المتحركة الخاصة بك هنا.
    // سنغطي ذلك في الخطوات اللاحقة.
    
    // حفظ العرض التقديمي مع الرسوم المتحركة
    presentation.Save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
```

## الخطوة 2: الحصول على مرجع لكائن الرسم البياني

يجب عليك الوصول إلى المخطط داخل عرضك التقديمي. للقيام بذلك، احصل على مرجع لكائن المخطط. نفترض أن المخطط موجود في الشريحة الأولى، ولكن يمكنك تعديل ذلك إذا كان المخطط موجودًا في شريحة أخرى.

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## الخطوة 3: تحريك عناصر السلسلة

الآن يأتي الجزء المثير - تحريك عناصر السلسلة في مخططك. يمكنك إضافة رسوم متحركة لجعل العناصر تظهر أو تختفي بطريقة جذابة بصريًا. في هذا المثال، سنجعل العناصر تظهر واحدًا تلو الآخر.

```csharp
// قم بتحريك الرسم البياني بأكمله ليتلاشى بعد الرسوم المتحركة السابقة.
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// حرّك عناصر السلسلة. عدّل الفهارس حسب الحاجة.
for (int i = 0; i < chart.Series.Count; i++)
{
    for (int j = 0; j < chart.Series[i].DataPoints.Count; j++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

## خاتمة

تهانينا! لقد نجحت في تعلّم كيفية تحريك عناصر السلسلة في مخطط باستخدام Aspose.Slides لـ .NET. بفضل هذه المعرفة، يمكنك إنشاء عروض تقديمية ديناميكية وجذابة على PowerPoint تجذب جمهورك.

Aspose.Slides for .NET أداة فعّالة للتعامل مع ملفات PowerPoint برمجيًا، وتفتح آفاقًا واسعة لإنشاء عروض تقديمية احترافية. لا تتردد في استكشاف [التوثيق](https://reference.aspose.com/slides/net/) لمزيد من الميزات المتقدمة وخيارات التخصيص.

## الأسئلة الشائعة

### 1. هل استخدام Aspose.Slides لـ .NET مجاني؟

Aspose.Slides لـ .NET هي مكتبة تجارية، ولكن يمكنك استكشافها بنسخة تجريبية مجانية. للاستخدام الكامل، ستحتاج إلى شراء ترخيص من [هنا](https://purchase.aspose.com/buy).

### 2. هل يمكنني تحريك عناصر أخرى في PowerPoint باستخدام Aspose.Slides لـ .NET؟

نعم، يسمح لك Aspose.Slides for .NET بتحريك عناصر PowerPoint المختلفة، بما في ذلك الأشكال والنصوص والصور والمخططات، كما هو موضح في هذا البرنامج التعليمي.

### 3. هل البرمجة باستخدام Aspose.Slides لـ .NET مناسبة للمبتدئين؟

على الرغم من أن الفهم الأساسي لـ C# و PowerPoint مفيد، فإن Aspose.Slides for .NET يوفر وثائق وأمثلة موسعة لمساعدة المستخدمين من جميع مستويات المهارة.

### 4. هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات .NET الأخرى، مثل VB.NET؟

نعم، يمكن استخدام Aspose.Slides لـ .NET مع لغات .NET المختلفة، بما في ذلك C# وVB.NET.

### 5. كيف يمكنني الحصول على دعم المجتمع أو المساعدة فيما يتعلق بـ Aspose.Slides لـ .NET؟

إذا كانت لديك أسئلة أو تحتاج إلى مساعدة، يمكنك زيارة [منتدى Aspose.Slides لـ .NET](https://forum.aspose.com/) لدعم المجتمع.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}