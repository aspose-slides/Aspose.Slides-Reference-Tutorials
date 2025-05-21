---
"description": "تعلّم كيفية تحريك عناصر السلسلة في شرائح PowerPoint باستخدام Aspose.Slides لجافا. اتبع هذا الدليل الشامل خطوة بخطوة مع الكود المصدري لتحسين عروضك التقديمية."
"linktitle": "تحريك عناصر السلسلة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحريك عناصر السلسلة في شرائح Java"
"url": "/ar/java/animation-and-layout/animating-series-elements-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحريك عناصر السلسلة في شرائح Java


## مقدمة إلى تحريك عناصر السلسلة في شرائح Java

في هذا البرنامج التعليمي، سنرشدك إلى كيفية تحريك عناصر السلسلة في شرائح PowerPoint باستخدام Aspose.Slides لجافا. تُضفي الرسوم المتحركة على عروضك التقديمية طابعًا أكثر تشويقًا وإثراءً بالمعلومات. في هذا المثال، سنركز على تحريك مخطط بياني في شريحة PowerPoint.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لمكتبة Java.
- عرض تقديمي موجود في PowerPoint يحتوي على مخطط تريد تحريكه.
- تم إعداد بيئة تطوير Java.

## الخطوة 1: تحميل العرض التقديمي

أولاً، عليك تحميل عرض PowerPoint الذي يحتوي على المخطط الذي تريد تحريكه. استبدل `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## الخطوة 2: الحصول على مرجع للرسم البياني

بعد تحميل العرض التقديمي، احصل على مرجع للمخطط الذي تريد تحريكه. في هذا المثال، نفترض أن المخطط موجود في الشريحة الأولى.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## الخطوة 3: إضافة تأثيرات الرسوم المتحركة

الآن، لنُضِف تأثيرات الحركة إلى عناصر الرسم البياني. سنستخدم `slide.getTimeline().getMainSequence().addEffect()` طريقة لتحديد كيفية تحريك الرسم البياني.

```java
// تحريك الرسم البياني بأكمله
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// تحريك عناصر السلسلة الفردية (يمكنك تخصيص هذا الجزء)
for (int seriesIndex = 0; seriesIndex < chart.getChartData().getSeries().size(); seriesIndex++) {
    for (int pointIndex = 0; pointIndex < chart.getChartData().getSeries().get_Item(seriesIndex).getPoints().size(); pointIndex++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, pointIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

في الكود أعلاه، نُحرك الرسم البياني بأكمله أولاً باستخدام تأثير "التلاشي". ثم نمرر عبر السلاسل والنقاط داخل الرسم البياني ونُطبق تأثير "الظهور" على كل عنصر. يمكنك تخصيص نوع الحركة وتشغيلها حسب الحاجة.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدّل مع الرسوم المتحركة في ملف جديد.

```java
presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

## الكود المصدر الكامل لتحريك عناصر السلسلة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// تحميل عرض تقديمي
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// الحصول على مرجع لكائن الرسم البياني
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// تحريك عناصر السلسلة
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// كتابة ملف العرض التقديمي على القرص 
	presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

لقد تعلمتَ كيفية تحريك عناصر السلسلة في شرائح PowerPoint باستخدام Aspose.Slides لجافا. تُحسّن الرسوم المتحركة عروضك التقديمية وتجعلها أكثر جاذبية. خصّص تأثيرات الرسوم المتحركة ومحفّزاتها لتناسب احتياجاتك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص الرسوم المتحركة لعناصر الرسم البياني الفردية؟

يمكنك تخصيص الرسوم المتحركة لعناصر الرسم البياني الفردية بتعديل نوع الرسوم المتحركة والمشغل في الكود. في مثالنا، استخدمنا تأثير "الظهور"، ولكن يمكنك الاختيار من بين أنواع رسوم متحركة متنوعة مثل "التلاشي" و"التحرك للداخل" وغيرها، وتحديد مشغلات مختلفة مثل "عند النقر" و"بعد السابق" و"مع السابق".

### هل يمكنني تطبيق الرسوم المتحركة على كائنات أخرى في شريحة PowerPoint؟

نعم، يمكنك تطبيق رسوم متحركة على كائنات مختلفة في شريحة PowerPoint، وليس فقط على المخططات. استخدم `addEffect` طريقة لتحديد الكائن الذي تريد تحريكه وخصائص التحريك المطلوبة.

### كيف يمكنني دمج Aspose.Slides for Java في مشروعي؟

لدمج Aspose.Slides لجافا في مشروعك، عليك تضمين المكتبة في مسار البناء أو استخدام أدوات إدارة التبعيات مثل Maven أو Gradle. راجع وثائق Aspose.Slides للاطلاع على تعليمات الدمج المفصلة.

### هل هناك طريقة لمعاينة الرسوم المتحركة في تطبيق PowerPoint؟

نعم، بعد حفظ العرض التقديمي، يمكنك فتحه في تطبيق PowerPoint لمعاينة الرسوم المتحركة وإجراء تعديلات إضافية عند الحاجة. يوفر PowerPoint وضع معاينة لهذا الغرض.

### هل هناك خيارات رسوم متحركة أكثر تقدمًا متوفرة في Aspose.Slides لـ Java؟

نعم، يوفر Aspose.Slides لجافا مجموعة واسعة من خيارات الرسوم المتحركة المتقدمة، بما في ذلك مسارات الحركة والتوقيت والرسوم المتحركة التفاعلية. يمكنك استكشاف الوثائق والأمثلة التي يوفرها Aspose.Slides لتطبيق الرسوم المتحركة المتقدمة في عروضك التقديمية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}