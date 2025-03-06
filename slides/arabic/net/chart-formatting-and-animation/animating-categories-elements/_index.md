---
title: رسوم متحركة قوية للمخططات باستخدام Aspose.Slides لـ .NET
linktitle: تحريك عناصر الفئات في الرسم البياني
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعلم كيفية تحريك عناصر المخطط في PowerPoint باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة للحصول على عروض تقديمية مذهلة.
weight: 11
url: /ar/net/chart-formatting-and-animation/animating-categories-elements/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# رسوم متحركة قوية للمخططات باستخدام Aspose.Slides لـ .NET


في عالم العروض التقديمية، يمكن للرسوم المتحركة أن تجعل المحتوى الخاص بك ينبض بالحياة، خاصة عند التعامل مع الرسوم البيانية. يقدم Aspose.Slides for .NET مجموعة من الميزات القوية التي تسمح لك بإنشاء رسوم متحركة مذهلة لمخططاتك. في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال عملية تحريك عناصر الفئة في مخطط باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، يجب أن تتوفر لديك المتطلبات الأساسية التالية:

-  Aspose.Slides for .NET: تأكد من تثبيت Aspose.Slides for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

- العرض التقديمي الحالي: يجب أن يكون لديك عرض تقديمي لـ PowerPoint يحتوي على مخطط تريد تحريكه. إذا لم يكن لديك واحد، قم بإنشاء عرض تقديمي نموذجي مع مخطط لأغراض الاختبار.

الآن بعد أن أصبح لديك كل شيء في مكانه الصحيح، فلنبدأ في تحريك عناصر المخطط هذه!

## استيراد مساحات الأسماء

الخطوة الأولى هي استيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Slides. أضف مساحات الأسماء التالية إلى مشروعك:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## الخطوة 1: قم بتحميل العرض التقديمي

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // الحصول على مرجع لكائن المخطط
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

في هذه الخطوة، نقوم بتحميل عرض PowerPoint التقديمي الموجود والذي يحتوي على المخطط الذي تريد تحريكه. نقوم بعد ذلك بالوصول إلى كائن المخطط داخل الشريحة الأولى.

## الخطوة 2: تحريك عناصر الفئات

```csharp
// تحريك عناصر الفئات
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

تضيف هذه الخطوة تأثير الرسوم المتحركة "التلاشي" إلى المخطط بأكمله، مما يجعله يظهر بعد الرسم المتحرك السابق.

بعد ذلك، سنضيف الرسوم المتحركة إلى العناصر الفردية داخل كل فئة من فئات المخطط. هذا هو المكان الذي يحدث فيه السحر الحقيقي.

## الخطوة 3: تحريك العناصر الفردية

سنقوم بتقسيم الرسوم المتحركة للعناصر الفردية داخل كل فئة إلى الخطوات التالية:

### الخطوة 3.1: تحريك العناصر في الفئة 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

نحن هنا نقوم بتحريك العناصر الفردية ضمن الفئة 0 من المخطط، مما يجعلها تظهر واحدة تلو الأخرى. يتم استخدام تأثير "الظهور" لهذه الرسوم المتحركة.

### الخطوة 3.2: تحريك العناصر في الفئة 1

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

يتم تكرار العملية للفئة 1، مع تحريك عناصرها الفردية باستخدام تأثير "الظهور".

### الخطوة 3.3: تحريك العناصر في الفئة 2

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

وتستمر نفس العملية بالنسبة للفئة 2، حيث يتم تحريك عناصرها بشكل فردي.

## الخطوة 4: احفظ العرض التقديمي

```csharp
// اكتب ملف العرض التقديمي على القرص
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

في الخطوة الأخيرة، نقوم بحفظ العرض التقديمي مع الرسوم المتحركة المضافة حديثًا. الآن، سيتم تحريك عناصر المخطط الخاص بك بشكل جميل عند تشغيل العرض التقديمي.

## خاتمة

يمكن أن يؤدي تحريك عناصر الفئة في المخطط إلى تحسين المظهر المرئي لعروضك التقديمية. باستخدام Aspose.Slides for .NET، تصبح هذه العملية واضحة وفعالة. لقد تعلمت كيفية استيراد مساحات الأسماء، وتحميل عرض تقديمي، وإضافة رسوم متحركة إلى المخطط بأكمله وعناصره الفردية. كن مبدعًا واجعل عروضك التقديمية أكثر تفاعلاً مع Aspose.Slides for .NET.

## الأسئلة الشائعة

### 1. كيف يمكنني تنزيل Aspose.Slides لـ .NET؟
 يمكنك تنزيل Aspose.Slides لـ .NET من[هذا الرابط](https://releases.aspose.com/slides/net/).

### 2. هل أحتاج إلى خبرة في البرمجة لاستخدام Aspose.Slides لـ .NET؟
على الرغم من أن تجربة البرمجة مفيدة، إلا أن Aspose.Slides for .NET يوفر وثائق وأمثلة موسعة لمساعدة المستخدمين على جميع مستويات المهارة.

### 3. هل يمكنني استخدام Aspose.Slides لـ .NET مع أي إصدار من PowerPoint؟
تم تصميم Aspose.Slides for .NET للعمل مع إصدارات PowerPoint المختلفة، مما يضمن التوافق.

### 4. كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 يمكنك الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET[هنا](https://purchase.aspose.com/temporary-license/).

### 5. هل يوجد منتدى مجتمعي لـ Aspose.Slides لدعم .NET؟
 نعم، يمكنك العثور على منتدى مجتمعي داعم لـ Aspose.Slides for .NET[هنا](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
