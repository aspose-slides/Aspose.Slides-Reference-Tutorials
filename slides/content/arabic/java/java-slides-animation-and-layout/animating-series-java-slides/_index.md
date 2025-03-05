---
title: سلسلة الرسوم المتحركة في شرائح جافا
linktitle: سلسلة الرسوم المتحركة في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين عروضك التقديمية باستخدام الرسوم المتحركة المتسلسلة في Aspose.Slides لـ Java. اتبع دليلنا خطوة بخطوة مع أمثلة التعليمات البرمجية المصدر لإنشاء رسوم متحركة جذابة لـ PowerPoint.
type: docs
weight: 11
url: /ar/java/animation-and-layout/animating-series-java-slides/
---

## مقدمة لسلسلة الرسوم المتحركة في Aspose.Slides لجافا

في هذا الدليل، سنرشدك خلال عملية تحريك السلسلة في شرائح Java باستخدام Aspose.Slides for Java API. تتيح لك هذه المكتبة العمل مع عروض PowerPoint التقديمية برمجياً.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.Slides لمكتبة جافا.
- إعداد بيئة تطوير جافا.

## الخطوة 1: قم بتحميل العرض التقديمي

 أولاً، نحتاج إلى تحميل عرض PowerPoint تقديمي موجود يحتوي على مخطط. يستبدل`"Your Document Directory"` بالمسار الفعلي لملف العرض التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة العرض التقديمي التي تمثل ملف العرض التقديمي
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## الخطوة 2: الوصول إلى المخطط

بعد ذلك، سوف نصل إلى المخطط ضمن العرض التقديمي. في هذا المثال، نفترض أن المخطط موجود في الشريحة الأولى وهو الشكل الأول في تلك الشريحة.

```java
// الحصول على إشارة إلى كائن المخطط
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## الخطوة 3: إضافة الرسوم المتحركة

الآن، دعونا نضيف الرسوم المتحركة إلى السلسلة داخل المخطط. سوف نستخدم تأثير التلاشي ونجعل كل سلسلة تظهر واحدة تلو الأخرى.

```java
// تحريك المخطط بأكمله
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// أضف رسومًا متحركة إلى كل سلسلة (بافتراض وجود 4 سلاسل)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

في الكود أعلاه، نستخدم تأثير التلاشي للمخطط بأكمله ثم نستخدم حلقة لإضافة تأثير "الظهور" إلى كل سلسلة واحدة تلو الأخرى.

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدل على القرص.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لسلسلة الرسوم المتحركة في Aspose.Slides لجافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة العرض التقديمي التي تمثل ملف العرض التقديمي
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// الحصول على مرجع لكائن المخطط
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// تحريك السلسلة
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

لقد نجحت في إنشاء سلسلة رسوم متحركة في مخطط PowerPoint باستخدام Aspose.Slides لـ Java. وهذا يمكن أن يجعل العروض التقديمية الخاصة بك أكثر جاذبية وجاذبية بصريًا. استكشف المزيد من خيارات الرسوم المتحركة وقم بضبط العروض التقديمية حسب الحاجة.

## الأسئلة الشائعة

### كيف أتحكم في ترتيب سلسلة الرسوم المتحركة؟

 للتحكم في ترتيب سلسلة الرسوم المتحركة، استخدم`EffectTriggerType.AfterPrevious` المعلمة عند إضافة التأثيرات. سيؤدي هذا إلى بدء كل سلسلة من الرسوم المتحركة بعد انتهاء الرسوم المتحركة السابقة.

### هل يمكنني تطبيق رسوم متحركة مختلفة على كل سلسلة؟

 نعم، يمكنك تطبيق رسوم متحركة مختلفة على كل سلسلة عن طريق تحديد مختلفة`EffectType` و`EffectSubtype` القيم عند إضافة التأثيرات.

### ماذا لو كان العرض التقديمي الخاص بي يحتوي على أكثر من أربع سلاسل؟

يمكنك تمديد الحلقة في الخطوة 3 لإضافة رسوم متحركة لجميع السلاسل في المخطط الخاص بك. ما عليك سوى ضبط حالة الحلقة وفقًا لذلك.

### كيف يمكنني تخصيص مدة الرسوم المتحركة والتأخير؟

يمكنك تخصيص مدة الرسوم المتحركة والتأخير عن طريق تعيين خصائص تأثيرات الرسوم المتحركة. تحقق من وثائق Aspose.Slides for Java للحصول على تفاصيل حول خيارات التخصيص المتاحة.