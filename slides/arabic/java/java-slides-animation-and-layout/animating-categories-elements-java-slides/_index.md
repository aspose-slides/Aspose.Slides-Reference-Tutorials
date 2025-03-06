---
title: تحريك عناصر الفئات في شرائح جافا
linktitle: تحريك عناصر الفئات في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين عروض Java التقديمية باستخدام Aspose.Slides لـ Java. تعرف على كيفية تحريك عناصر الفئة في شرائح PowerPoint خطوة بخطوة.
weight: 10
url: /ar/java/animation-and-layout/animating-categories-elements-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لتحريك عناصر الفئات في شرائح جافا

في هذا البرنامج التعليمي، سنرشدك خلال عملية تحريك عناصر الفئة في شرائح Java باستخدام Aspose.Slides for Java. سيزودك هذا الدليل التفصيلي بكود المصدر والشروحات لمساعدتك في تحقيق تأثير الرسوم المتحركة هذا.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لـ Java API.
- عرض تقديمي PowerPoint موجود يحتوي على مخطط. سوف تقوم بتحريك عناصر الفئة في هذا المخطط.

## الخطوة 1: استيراد مكتبة Aspose.Slides

للبدء، قم باستيراد مكتبة Aspose.Slides إلى مشروع Java الخاص بك. يمكنك تنزيل المكتبة وإضافتها إلى مسار الفصل الخاص بمشروعك. تأكد من إعداد التبعيات اللازمة.

## الخطوة 2: قم بتحميل العرض التقديمي

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

 في هذا الكود، نقوم بتحميل عرض PowerPoint تقديمي موجود يحتوي على المخطط الذي تريد تحريكه. يستبدل`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 3: الحصول على مرجع لكائن المخطط

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

نحصل على إشارة إلى كائن المخطط في الشريحة الأولى من العرض التقديمي. ضبط فهرس الشريحة (`get_Item(0)`) ومؤشر الشكل (`get_Item(0)`) حسب الحاجة للوصول إلى المخطط المحدد الخاص بك.

## الخطوة 4: تحريك عناصر الفئات

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

نقوم بتحريك عناصر الفئات داخل المخطط. يضيف هذا الرمز تأثير التلاشي إلى المخطط بأكمله ثم يضيف تأثير "الظهور" إلى كل عنصر داخل كل فئة. اضبط نوع التأثير والنوع الفرعي حسب الحاجة.

## الخطوة 5: احفظ العرض التقديمي

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

 وأخيرًا، احفظ العرض التقديمي المعدل مع المخطط المتحرك في ملف جديد. يستبدل`"AnimatingCategoriesElements_out.pptx"` مع اسم ملف الإخراج المطلوب.


## كود المصدر الكامل لتحريك عناصر الفئات في شرائح جافا
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// الحصول على مرجع لكائن المخطط
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// تحريك عناصر الفئات
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// اكتب ملف العرض التقديمي على القرص
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

لقد نجحت في تحريك عناصر الفئة في شريحة Java باستخدام Aspose.Slides for Java. يزودك هذا الدليل خطوة بخطوة بالكود المصدري والشروحات اللازمة لتحقيق تأثير الرسوم المتحركة هذا في عروض PowerPoint التقديمية. قم بتجربة تأثيرات وإعدادات مختلفة لتخصيص الرسوم المتحركة الخاصة بك بشكل أكبر.

## الأسئلة الشائعة

### كيف يمكنني تخصيص تأثيرات الرسوم المتحركة؟

 يمكنك تخصيص تأثيرات الرسوم المتحركة عن طريق تغيير`EffectType` و`EffectSubtype` المعلمات عند إضافة تأثيرات إلى عناصر المخطط. راجع وثائق Aspose.Slides for Java للحصول على مزيد من التفاصيل حول تأثيرات الرسوم المتحركة المتوفرة.

### هل يمكنني تطبيق هذه الرسوم المتحركة على أنواع أخرى من الرسوم البيانية؟

نعم، يمكنك تطبيق رسوم متحركة مماثلة على أنواع أخرى من المخططات عن طريق تعديل التعليمات البرمجية لاستهداف عناصر المخطط المحددة التي تريد تحريكها. اضبط بنية الحلقة والمعلمات وفقًا لذلك.

### كيف يمكنني معرفة المزيد حول Aspose.Slides لـ Java؟

 للحصول على وثائق شاملة وموارد إضافية، قم بزيارة[Aspose.Slides لمرجع Java API](https://reference.aspose.com/slides/java/) . يمكنك أيضًا تنزيل المكتبة من[هنا](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
