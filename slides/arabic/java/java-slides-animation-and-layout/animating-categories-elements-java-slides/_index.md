---
"description": "حسّن عروضك التقديمية بلغة جافا باستخدام Aspose.Slides لجافا. تعلّم كيفية تحريك عناصر الفئات في شرائح PowerPoint خطوة بخطوة."
"linktitle": "تحريك عناصر الفئات في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحريك عناصر الفئات في شرائح Java"
"url": "/ar/java/animation-and-layout/animating-categories-elements-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحريك عناصر الفئات في شرائح Java


## مقدمة حول تحريك عناصر الفئات في شرائح Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية تحريك عناصر الفئات في شرائح جافا باستخدام Aspose.Slides لجافا. سيوفر لك هذا الدليل خطوة بخطوة الكود المصدري والشروحات اللازمة لتحقيق تأثير التحريك هذا.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لـ Java API.
- عرض تقديمي موجود على PowerPoint يحتوي على مخطط. سيتم تحريك عناصر الفئات في هذا المخطط.

## الخطوة 1: استيراد مكتبة Aspose.Slides

للبدء، استورد مكتبة Aspose.Slides إلى مشروعك بلغة جافا. يمكنك تنزيل المكتبة وإضافتها إلى مسار مشروعك. تأكد من إعداد التبعيات اللازمة.

## الخطوة 2: تحميل العرض التقديمي

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

في هذا الكود، نقوم بتحميل عرض تقديمي موجود في PowerPoint يحتوي على الرسم البياني الذي نريد تحريكه. استبدل `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 3: الحصول على مرجع إلى كائن الرسم البياني

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

نحصل على مرجع لكائن الرسم البياني في الشريحة الأولى من العرض التقديمي. اضبط مؤشر الشريحة (`get_Item(0)`) ومؤشر الشكل (`get_Item(0)`) حسب الحاجة للوصول إلى الرسم البياني الخاص بك.

## الخطوة 4: تحريك عناصر الفئات

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

نقوم بتحريك عناصر الفئات داخل الرسم البياني. يُضيف هذا الكود تأثير تلاشي على الرسم البياني بأكمله، ثم يُضيف تأثير "ظهور" لكل عنصر ضمن كل فئة. عدّل نوع التأثير والنوع الفرعي حسب الحاجة.

## الخطوة 5: حفظ العرض التقديمي

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

أخيرًا، احفظ العرض التقديمي المُعدَّل مع الرسم البياني المتحرك في ملف جديد. استبدل `"AnimatingCategoriesElements_out.pptx"` مع اسم ملف الإخراج المطلوب.


## الكود المصدر الكامل لتحريك عناصر الفئات في شرائح Java
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// الحصول على مرجع لكائن الرسم البياني
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
	// كتابة ملف العرض التقديمي على القرص
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

لقد نجحت في تحريك عناصر الفئات في شريحة جافا باستخدام Aspose.Slides for Java. يوفر لك هذا الدليل التفصيلي الكود المصدري والشروحات اللازمة لتحقيق هذا التأثير المتحرك في عروض PowerPoint التقديمية. جرّب تأثيرات وإعدادات مختلفة لتخصيص رسومك المتحركة بشكل أكبر.

## الأسئلة الشائعة

### كيف يمكنني تخصيص تأثيرات الرسوم المتحركة؟

يمكنك تخصيص تأثيرات الرسوم المتحركة عن طريق تغيير `EffectType` و `EffectSubtype` عند إضافة تأثيرات إلى عناصر الرسم البياني، يُرجى مراجعة وثائق Aspose.Slides لجافا لمزيد من التفاصيل حول تأثيرات الرسوم المتحركة المتاحة.

### هل يمكنني تطبيق هذه الرسوم المتحركة على أنواع أخرى من الرسوم البيانية؟

نعم، يمكنك تطبيق رسوم متحركة مماثلة على أنواع أخرى من الرسوم البيانية عن طريق تعديل الكود لاستهداف عناصر الرسم البياني المحددة التي تريد تحريكها. عدّل بنية الحلقة والمعلمات وفقًا لذلك.

### كيف يمكنني معرفة المزيد عن Aspose.Slides لـ Java؟

للحصول على توثيق شامل وموارد إضافية، قم بزيارة [مرجع واجهة برمجة تطبيقات Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/). يمكنك أيضًا تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}