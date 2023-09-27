---
title: تحريك عناصر السلسلة في شرائح جافا
linktitle: تحريك عناصر السلسلة في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحريك عناصر السلسلة في شرائح PowerPoint باستخدام Aspose.Slides لـ Java. اتبع هذا الدليل الشامل خطوة بخطوة مع الكود المصدري لتحسين عروضك التقديمية.
type: docs
weight: 12
url: /ar/java/animation-and-layout/animating-series-elements-java-slides/
---

## مقدمة لتحريك عناصر السلسلة في شرائح جافا

في هذا البرنامج التعليمي، سنرشدك عبر تحريك عناصر السلسلة في شرائح PowerPoint باستخدام Aspose.Slides for Java. الرسوم المتحركة يمكن أن تجعل العروض التقديمية الخاصة بك أكثر جاذبية وغنية بالمعلومات. في هذا المثال، سنركز على تحريك المخطط في شريحة PowerPoint.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لمكتبة Java.
- عرض تقديمي موجود في PowerPoint يحتوي على مخطط تريد تحريكه.
- إعداد بيئة تطوير جافا.

## الخطوة 1: قم بتحميل العرض التقديمي

أولاً، تحتاج إلى تحميل عرض PowerPoint التقديمي الذي يحتوي على المخطط الذي تريد تحريكه. يستبدل`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## الخطوة 2: احصل على مرجع للمخطط

بمجرد تحميل العرض التقديمي، احصل على مرجع للمخطط الذي تريد تحريكه. في هذا المثال، نفترض أن المخطط موجود في الشريحة الأولى.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## الخطوة 3: إضافة تأثيرات الرسوم المتحركة

 الآن، دعونا نضيف تأثيرات الحركة إلى عناصر المخطط. سوف نستخدم`slide.getTimeline().getMainSequence().addEffect()` طريقة لتحديد كيفية تحريك المخطط.

```java
// تحريك المخطط بأكمله
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// تحريك عناصر السلسلة الفردية (يمكنك تخصيص هذا الجزء)
for (int seriesIndex = 0; seriesIndex < chart.getChartData().getSeries().size(); seriesIndex++) {
    for (int pointIndex = 0; pointIndex < chart.getChartData().getSeries().get_Item(seriesIndex).getPoints().size(); pointIndex++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, pointIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

في الكود أعلاه، نقوم أولاً بتحريك المخطط بأكمله باستخدام تأثير "التلاشي". بعد ذلك، نمر عبر السلسلة والنقاط داخل المخطط ونطبق تأثير "الظهور" على كل عنصر. يمكنك تخصيص نوع الرسوم المتحركة وتشغيلها حسب الحاجة.

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدل مع الرسوم المتحركة في ملف جديد.

```java
presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لتحريك عناصر السلسلة في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بتحميل عرض تقديمي
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// الحصول على مرجع لكائن المخطط
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
	// اكتب ملف العرض التقديمي على القرص
	presentation.save(dataDir + "AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

لقد تعلمت كيفية تحريك عناصر السلسلة في شرائح PowerPoint باستخدام Aspose.Slides لـ Java. يمكن للرسوم المتحركة تحسين العروض التقديمية الخاصة بك وجعلها أكثر جاذبية. قم بتخصيص تأثيرات الرسوم المتحركة والمشغلات لتناسب احتياجاتك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص الرسوم المتحركة لعناصر المخطط الفردية؟

يمكنك تخصيص الرسوم المتحركة لعناصر المخطط الفردية عن طريق تعديل نوع الرسوم المتحركة وتشغيلها في التعليمات البرمجية. في مثالنا، استخدمنا تأثير "الظهور"، ولكن يمكنك الاختيار من بين أنواع الرسوم المتحركة المختلفة مثل "Fade" أو "Fly In" وما إلى ذلك، وتحديد مشغلات مختلفة مثل "عند النقر" أو "بعد السابق" أو "مع سابقة."

### هل يمكنني تطبيق الرسوم المتحركة على كائنات أخرى في شريحة PowerPoint؟

نعم، يمكنك تطبيق الرسوم المتحركة على كائنات مختلفة في شريحة PowerPoint، وليس فقط المخططات. استخدم ال`addEffect` طريقة لتحديد الكائن الذي تريد تحريكه وخصائص الحركة المطلوبة.

### كيف يمكنني دمج Aspose.Slides for Java في مشروعي؟

لدمج Aspose.Slides for Java في مشروعك، تحتاج إلى تضمين المكتبة في مسار البناء الخاص بك أو استخدام أدوات إدارة التبعية مثل Maven أو Gradle. راجع وثائق Aspose.Slides للحصول على تعليمات مفصلة حول التكامل.

### هل هناك طريقة لمعاينة الرسوم المتحركة في تطبيق PowerPoint؟

نعم، بعد حفظ العرض التقديمي، يمكنك فتحه في تطبيق PowerPoint لمعاينة الرسوم المتحركة وإجراء المزيد من التعديلات إذا لزم الأمر. يوفر PowerPoint وضع المعاينة لهذا الغرض.

### هل تتوفر المزيد من خيارات الرسوم المتحركة المتقدمة في Aspose.Slides لـ Java؟

نعم، يقدم Aspose.Slides for Java نطاقًا واسعًا من خيارات الرسوم المتحركة المتقدمة، بما في ذلك مسارات الحركة والتوقيت والرسوم المتحركة التفاعلية. يمكنك استكشاف الوثائق والأمثلة المقدمة من Aspose.Slides لتنفيذ الرسوم المتحركة المتقدمة في العروض التقديمية الخاصة بك.