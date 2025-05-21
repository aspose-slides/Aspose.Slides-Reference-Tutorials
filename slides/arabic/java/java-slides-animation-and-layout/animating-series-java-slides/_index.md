---
"description": "حسّن عروضك التقديمية باستخدام الرسوم المتحركة المتسلسلة في Aspose.Slides لجافا. اتبع دليلنا خطوة بخطوة مع أمثلة من الكود المصدري لإنشاء رسوم متحركة جذابة على PowerPoint."
"linktitle": "سلسلة الرسوم المتحركة في شرائح جافا"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "سلسلة الرسوم المتحركة في شرائح جافا"
"url": "/ar/java/animation-and-layout/animating-series-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# سلسلة الرسوم المتحركة في شرائح جافا


## مقدمة إلى تحريك المسلسلات في Aspose.Slides لـ Java

في هذا الدليل، سنشرح لك عملية تحريك سلاسل العروض التقديمية في شرائح جافا باستخدام Aspose.Slides لواجهة برمجة تطبيقات جافا. تتيح لك هذه المكتبة العمل مع عروض PowerPoint التقديمية برمجيًا.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.Slides لمكتبة Java.
- تم إعداد بيئة تطوير Java.

## الخطوة 1: تحميل العرض التقديمي

أولاً، نحتاج إلى تحميل عرض تقديمي موجود في PowerPoint يحتوي على مخطط. استبدل `"Your Document Directory"` مع المسار الفعلي لملف العرض التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة عرض تقديمي تمثل ملف عرض تقديمي 
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## الخطوة 2: الوصول إلى الرسم البياني

بعد ذلك، سنصل إلى الرسم البياني داخل العرض التقديمي. في هذا المثال، نفترض أن الرسم البياني موجود في الشريحة الأولى وهو الشكل الأول فيها.

```java
// الحصول على مرجع لكائن الرسم البياني
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## الخطوة 3: إضافة الرسوم المتحركة

الآن، لنُضِف رسومًا متحركة إلى السلسلة داخل الرسم البياني. سنستخدم تأثير التلاشي التدريجي، ونجعل كل سلسلة تظهر واحدة تلو الأخرى.

```java
// تحريك الرسم البياني بأكمله
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// أضف رسومًا متحركة لكل سلسلة (على افتراض وجود 4 سلاسل)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

في الكود أعلاه، نستخدم تأثير التلاشي للرسم البياني بأكمله ثم نستخدم حلقة لإضافة تأثير "الظهور" إلى كل سلسلة واحدة تلو الأخرى.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدّل على القرص.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## الكود المصدري الكامل لتحريك المسلسلات في Aspose.Slides لـ Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة عرض تقديمي تمثل ملف عرض تقديمي 
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// الحصول على مرجع لكائن الرسم البياني
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// تحريك المسلسل
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None,
			EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 0,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 1,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 2,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 3,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// اكتب العرض التقديمي المعدل على القرص 
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

لقد نجحت في تحريك سلسلة من العروض التقديمية في مخطط PowerPoint باستخدام Aspose.Slides لجافا. هذا يجعل عروضك التقديمية أكثر جاذبية وجاذبية بصريًا. استكشف المزيد من خيارات التحريك، وحسّن عروضك التقديمية حسب الحاجة.

## الأسئلة الشائعة

### كيف يمكنني التحكم في ترتيب الرسوم المتحركة للمسلسلات؟

للتحكم في ترتيب الرسوم المتحركة المتسلسلة، استخدم `EffectTriggerType.AfterPrevious` عند إضافة التأثيرات، سيبدأ كل رسم متحرك متسلسل بعد انتهاء سابقه.

### هل يمكنني تطبيق رسوم متحركة مختلفة لكل سلسلة؟

نعم، يمكنك تطبيق رسوم متحركة مختلفة على كل سلسلة من خلال تحديد `EffectType` و `EffectSubtype` القيم عند إضافة التأثيرات.

### ماذا لو كان عرضي التقديمي يحتوي على أكثر من أربع سلاسل؟

يمكنك تمديد الحلقة في الخطوة 3 لإضافة رسوم متحركة لجميع السلاسل في مخططك. ما عليك سوى ضبط حالة الحلقة وفقًا لذلك.

### كيف يمكنني تخصيص مدة الرسوم المتحركة والتأخير؟

يمكنك تخصيص مدة الرسوم المتحركة وتأخيرها من خلال ضبط خصائص تأثيرات الرسوم المتحركة. راجع وثائق Aspose.Slides لجافا لمزيد من التفاصيل حول خيارات التخصيص المتاحة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}