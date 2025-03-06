---
title: تحريك سلسلة الرسوم البيانية باستخدام Aspose.Slides لـ .NET
linktitle: سلسلة الرسوم المتحركة في الرسم البياني
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحريك سلسلة المخططات باستخدام Aspose.Slides لـ .NET. قم بإشراك جمهورك من خلال العروض التقديمية الديناميكية. نبدأ الآن!
weight: 12
url: /ar/net/chart-formatting-and-animation/animating-series/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


هل تتطلع إلى إضافة بعض الإثارة إلى عروضك التقديمية باستخدام الرسوم البيانية المتحركة؟ Aspose.Slides for .NET موجود هنا لإضفاء الحيوية على مخططاتك. في هذا الدليل خطوة بخطوة، سنوضح لك كيفية تحريك السلسلة في مخطط باستخدام Aspose.Slides for .NET. ولكن قبل أن نتعمق في العمل، دعونا نغطي المتطلبات الأساسية.

## المتطلبات الأساسية

لتحريك سلسلة بنجاح في مخطط باستخدام Aspose.Slides لـ .NET، ستحتاج إلى ما يلي:

### 1. Aspose.Slides لمكتبة .NET

 تأكد من تثبيت Aspose.Slides لمكتبة .NET. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيله من[Aspose.Slides لموقع ويب .NET](https://releases.aspose.com/slides/net/).

### 2. العرض التقديمي الموجود مع الرسم البياني

قم بإعداد عرض تقديمي لـ PowerPoint (PPTX) باستخدام مخطط موجود تريد تحريكه.

الآن وبعد أن قمنا بتغطية المتطلبات الأساسية، فلنقسم العملية إلى سلسلة من الخطوات لتحريك سلسلة المخططات.


## الخطوة 1: استيراد مساحات الأسماء الضرورية

ستحتاج إلى استيراد مساحات الأسماء المطلوبة في كود C# الخاص بك للعمل مع Aspose.Slides لـ .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## الخطوة 2: قم بتحميل العرض التقديمي الحالي

في هذه الخطوة، قم بتحميل عرض PowerPoint التقديمي (PPTX) الموجود لديك والذي يحتوي على المخطط الذي تريد تحريكه.

```csharp
// المسار إلى دليل المستندات
string dataDir = "Your Document Directory";

// إنشاء فئة العرض التقديمي التي تمثل ملف العرض التقديمي
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // الكود الخاص بك يذهب هنا
}
```

## الخطوة 3: الحصول على مرجع لكائن المخطط

للعمل مع المخطط في العرض التقديمي الخاص بك، ستحتاج إلى الحصول على مرجع لكائن المخطط:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## الخطوة 4: تحريك السلسلة

حان الوقت الآن لإضافة تأثيرات الرسوم المتحركة إلى سلسلة المخططات الخاصة بك. سنقوم بإضافة تأثير التلاشي إلى المخطط بأكمله ونجعل كل سلسلة تظهر واحدة تلو الأخرى.

```csharp
// تحريك الرسم البياني
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// أضف الرسوم المتحركة إلى كل سلسلة
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## الخطوة 5: احفظ العرض التقديمي المعدل

بمجرد إضافة تأثيرات الرسوم المتحركة إلى المخطط الخاص بك، احفظ العرض التقديمي المعدل على القرص.

```csharp
//احفظ العرض التقديمي المعدل
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في رسم سلسلة متحركة في مخطط باستخدام Aspose.Slides لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، قمنا بإرشادك خلال عملية تحريك السلسلة في مخطط باستخدام Aspose.Slides for .NET. باستخدام هذه المكتبة القوية، يمكنك إنشاء عروض تقديمية جذابة وديناميكية تأسر جمهورك.

 إذا كانت لديك أي أسئلة أو كنت بحاجة إلى مزيد من المساعدة، فلا تتردد في التواصل مع مجتمع Aspose.Slides على[منتدى الدعم](https://forum.aspose.com/).

## الأسئلة الشائعة

### هل يمكنني تحريك عناصر المخطط الأخرى إلى جانب السلسلة باستخدام Aspose.Slides لـ .NET؟
نعم، يمكنك تحريك عناصر المخطط المختلفة، بما في ذلك نقاط البيانات والمحاور ووسائل الإيضاح، باستخدام Aspose.Slides لـ .NET.

### هل يتوافق Aspose.Slides for .NET مع أحدث إصدارات PowerPoint؟
يدعم Aspose.Slides for .NET إصدارات PowerPoint المختلفة، بما في ذلك PowerPoint 2007 والإصدارات الأحدث، مما يضمن التوافق مع أحدث الإصدارات.

### هل يمكنني تخصيص تأثيرات الرسوم المتحركة لكل سلسلة مخططات على حدة؟
نعم، يمكنك تخصيص تأثيرات الرسوم المتحركة لكل سلسلة مخططات لإنشاء عروض تقديمية فريدة وجذابة.

### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ .NET؟
 نعم يمكنك تجربة المكتبة مع النسخة التجريبية المجانية من[Aspose.Slides لموقع ويب .NET](https://releases.aspose.com/).

### أين يمكنني شراء ترخيص Aspose.Slides لـ .NET؟
 يمكنك الحصول على ترخيص Aspose.Slides لـ .NET من صفحة الشراء[هنا](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
