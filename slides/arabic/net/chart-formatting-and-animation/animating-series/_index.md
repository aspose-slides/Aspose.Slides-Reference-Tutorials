---
"description": "تعلّم كيفية تحريك سلسلة من الرسوم البيانية باستخدام Aspose.Slides لـ .NET. أشرك جمهورك بعروض تقديمية ديناميكية. ابدأ الآن!"
"linktitle": "سلسلة الرسوم المتحركة في الرسم البياني"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تحريك سلسلة الرسوم البيانية باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/chart-formatting-and-animation/animating-series/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحريك سلسلة الرسوم البيانية باستخدام Aspose.Slides لـ .NET


هل ترغب في إضافة لمسة مميزة إلى عروضك التقديمية باستخدام الرسوم البيانية المتحركة؟ Aspose.Slides for .NET هنا لجعل رسومك البيانية تنبض بالحياة. في هذا الدليل المفصل، سنوضح لك كيفية تحريك سلسلة من الرسوم البيانية باستخدام Aspose.Slides for .NET. ولكن قبل الخوض في التفاصيل، دعونا نتناول المتطلبات الأساسية.

## المتطلبات الأساسية

لتحريك سلسلة بنجاح في مخطط باستخدام Aspose.Slides لـ .NET، ستحتاج إلى ما يلي:

### 1. مكتبة Aspose.Slides لـ .NET

تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. إذا لم تكن مثبتة، يمكنك تنزيلها من [Aspose.Slides لموقع .NET](https://releases.aspose.com/slides/net/).

### 2. عرض تقديمي موجود مع مخطط

قم بإعداد عرض تقديمي في PowerPoint (PPTX) باستخدام مخطط موجود تريد تحريكه.

الآن بعد أن قمنا بتغطية المتطلبات الأساسية، دعنا نقسم العملية إلى سلسلة من الخطوات لتحريك سلسلة المخططات.


## الخطوة 1: استيراد مساحات الأسماء الضرورية

سوف تحتاج إلى استيراد المساحات المطلوبة في كود C# الخاص بك للعمل مع Aspose.Slides لـ .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## الخطوة 2: تحميل العرض التقديمي الحالي

في هذه الخطوة، قم بتحميل عرض PowerPoint التقديمي (PPTX) الموجود لديك والذي يحتوي على المخطط الذي تريد تحريكه.

```csharp
// المسار إلى دليل المستندات
string dataDir = "Your Document Directory";

// إنشاء فئة عرض تقديمي تمثل ملف عرض تقديمي 
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // الكود الخاص بك يذهب هنا
}
```

## الخطوة 3: الحصول على مرجع لكائن الرسم البياني

للعمل مع الرسم البياني في العرض التقديمي الخاص بك، ستحتاج إلى الحصول على مرجع إلى كائن الرسم البياني:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## الخطوة 4: تحريك السلسلة

الآن، حان وقت إضافة تأثيرات الرسوم المتحركة إلى سلسلة مخططاتك. سنضيف تأثير التلاشي إلى المخطط بأكمله، ونجعل كل سلسلة تظهر واحدة تلو الأخرى.

```csharp
// تحريك الرسم البياني
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// أضف الرسوم المتحركة إلى كل سلسلة
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## الخطوة 5: حفظ العرض التقديمي المعدّل

بمجرد إضافة تأثيرات الرسوم المتحركة إلى الرسم البياني الخاص بك، احفظ العرض التقديمي المعدل على القرص.

```csharp
// حفظ العرض التقديمي المعدل
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في تحريك سلسلة من الرسوم البيانية باستخدام Aspose.Slides لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، شرحنا لك عملية تحريك سلسلة من العروض التقديمية في مخطط بياني باستخدام Aspose.Slides لـ .NET. باستخدام هذه المكتبة القوية، يمكنك إنشاء عروض تقديمية جذابة وديناميكية تجذب جمهورك.

إذا كانت لديك أي أسئلة أو كنت بحاجة إلى مزيد من المساعدة، فلا تتردد في التواصل مع مجتمع Aspose.Slides على [منتدى الدعم](https://forum.aspose.com/).

## الأسئلة الشائعة

### هل يمكنني تحريك عناصر مخطط أخرى بالإضافة إلى السلسلة باستخدام Aspose.Slides لـ .NET؟
نعم، يمكنك تحريك عناصر المخطط المختلفة، بما في ذلك نقاط البيانات، والمحاور، والأساطير، باستخدام Aspose.Slides لـ .NET.

### هل Aspose.Slides for .NET متوافق مع أحدث إصدارات PowerPoint؟
يدعم Aspose.Slides for .NET إصدارات PowerPoint المختلفة، بما في ذلك PowerPoint 2007 والإصدارات الأحدث، مما يضمن التوافق مع أحدث الإصدارات.

### هل يمكنني تخصيص تأثيرات الرسوم المتحركة لكل سلسلة مخططات على حدة؟
نعم، يمكنك تخصيص تأثيرات الرسوم المتحركة لكل سلسلة من الرسوم البيانية لإنشاء عروض تقديمية فريدة وجذابة.

### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ .NET؟
نعم يمكنك تجربة المكتبة من خلال النسخة التجريبية المجانية من [Aspose.Slides لموقع .NET](https://releases.aspose.com/).

### أين يمكنني شراء ترخيص لـ Aspose.Slides لـ .NET؟
يمكنك الحصول على ترخيص لـ Aspose.Slides لـ .NET من صفحة الشراء [هنا](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}