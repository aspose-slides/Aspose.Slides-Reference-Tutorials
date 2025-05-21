---
"description": "تعلم كيفية تحريك عناصر المخططات في PowerPoint باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة لعروض تقديمية رائعة."
"linktitle": "تحريك عناصر الفئات في الرسم البياني"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "رسوم متحركة قوية للمخططات باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/chart-formatting-and-animation/animating-categories-elements/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# رسوم متحركة قوية للمخططات باستخدام Aspose.Slides لـ .NET


في عالم العروض التقديمية، تُضفي الرسوم المتحركة حيويةً على محتواك، خاصةً عند التعامل مع المخططات البيانية. يُقدم Aspose.Slides for .NET مجموعةً من الميزات الفعّالة التي تُمكّنك من إنشاء رسوم متحركة رائعة لمخططاتك البيانية. في هذا الدليل المُفصّل، سنشرح لك عملية تحريك عناصر الفئات في المخطط البياني باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي، يجب أن يكون لديك المتطلبات الأساسية التالية:

- Aspose.Slides لـ .NET: تأكد من تثبيت Aspose.Slides لـ .NET في بيئة التطوير لديك. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيله من [هنا](https://releases.aspose.com/slides/net/).

- عرض تقديمي موجود: يجب أن يكون لديك عرض تقديمي على PowerPoint مع مخطط ترغب في تحريكه. إذا لم يكن لديك واحد، فأنشئ عرضًا تقديميًا نموذجيًا مع مخطط لأغراض الاختبار.

الآن بعد أن أصبح كل شيء في مكانه، فلنبدأ في تحريك عناصر الرسم البياني تلك!

## استيراد مساحات الأسماء

الخطوة الأولى هي استيراد مساحات الأسماء اللازمة للوصول إلى وظائف Aspose.Slides. أضف مساحات الأسماء التالية إلى مشروعك:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## الخطوة 1: تحميل العرض التقديمي

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // الحصول على مرجع لكائن الرسم البياني
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

في هذه الخطوة، نقوم بتحميل عرض PowerPoint الحالي الذي يحتوي على المخطط الذي نريد تحريكه. ثم نصل إلى عنصر المخطط في الشريحة الأولى.

## الخطوة 2: تحريك عناصر الفئات

```csharp
// تحريك عناصر الفئات
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

تضيف هذه الخطوة تأثير الرسوم المتحركة "التلاشي" إلى الرسم البياني بأكمله، مما يجعله يظهر بعد الرسوم المتحركة السابقة.

بعد ذلك، سنضيف رسومًا متحركة لعناصر كل فئة من فئات المخطط. وهنا يكمن السر الحقيقي.

## الخطوة 3: تحريك العناصر الفردية

سنقوم بتقسيم الرسوم المتحركة للعناصر الفردية ضمن كل فئة إلى الخطوات التالية:

### الخطوة 3.1: تحريك العناصر في الفئة 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

هنا، نقوم بتحريك عناصر فردية ضمن الفئة ٠ من الرسم البياني، بحيث تظهر الواحدة تلو الأخرى. يُستخدم تأثير "الظهور" في هذه التحريك.

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

تستمر نفس العملية بالنسبة للفئة 2، مع تحريك عناصرها بشكل فردي.

## الخطوة 4: حفظ العرض التقديمي

```csharp
// كتابة ملف العرض التقديمي على القرص
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

في الخطوة الأخيرة، نحفظ العرض التقديمي مع الرسوم المتحركة المضافة حديثًا. الآن، ستتحرك عناصر مخططك بشكل رائع عند تشغيل العرض التقديمي.

## خاتمة

يُمكن لتحريك عناصر الفئات في المخطط أن يُحسّن المظهر المرئي لعروضك التقديمية. مع Aspose.Slides لـ .NET، تُصبح هذه العملية سهلة وفعّالة. لقد تعلّمت كيفية استيراد مساحات الأسماء، وتحميل العرض التقديمي، وإضافة الرسوم المتحركة إلى المخطط بأكمله وعناصره الفردية. أطلق العنان لإبداعك واجعل عروضك التقديمية أكثر تشويقًا مع Aspose.Slides لـ .NET.

## الأسئلة الشائعة

### 1. كيف يمكنني تنزيل Aspose.Slides لـ .NET؟
يمكنك تنزيل Aspose.Slides لـ .NET من [هذا الرابط](https://releases.aspose.com/slides/net/).

### 2. هل أحتاج إلى خبرة في البرمجة لاستخدام Aspose.Slides لـ .NET؟
على الرغم من أن الخبرة في البرمجة مفيدة، فإن Aspose.Slides for .NET يوفر توثيقًا وأمثلة شاملة لمساعدة المستخدمين في جميع مستويات المهارة.

### 3. هل يمكنني استخدام Aspose.Slides لـ .NET مع أي إصدار من PowerPoint؟
تم تصميم Aspose.Slides for .NET للعمل مع إصدارات PowerPoint المختلفة، مما يضمن التوافق.

### 4. كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
يمكنك الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET [هنا](https://purchase.aspose.com/temporary-license/).

### 5. هل يوجد منتدى مجتمعي لدعم Aspose.Slides لـ .NET؟
نعم، يمكنك العثور على منتدى مجتمعي داعم لـ Aspose.Slides لـ .NET [هنا](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}