---
"description": "أنشئ عروضًا تقديمية مذهلة باستخدام Aspose.Slides لـ .NET. تعلّم كيفية إضافة رسوم متحركة إلى الأشكال في هذا الدليل المفصل. ارتقِ بعروضك التقديمية الآن!"
"linktitle": "تطبيق الرسوم المتحركة على الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء رسوم متحركة للأشكال بسهولة باستخدام Aspose.Slides"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء رسوم متحركة للأشكال بسهولة باستخدام Aspose.Slides

## مقدمة
في عالم العروض التقديمية الديناميكية، تُحسّن إضافة الرسوم المتحركة إلى الأشكال من جاذبية شرائحك البصرية وتفاعلها بشكل ملحوظ. يوفر Aspose.Slides for .NET مجموعة أدوات فعّالة لتحقيق ذلك بسلاسة. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة الرسوم المتحركة إلى الأشكال باستخدام Aspose.Slides، مما يتيح لك إنشاء عروض تقديمية آسرة تترك انطباعًا دائمًا.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. Aspose.Slides لـ .NET: تأكد من تثبيت المكتبة وجاهزيتها للاستخدام. يمكنك تنزيلها. [هنا](https://releases.aspose.com/slides/net/).
2. بيئة التطوير: قم بإعداد بيئة التطوير المفضلة لديك باستخدام التكوينات الضرورية.
3. دليل المستندات: قم بإنشاء دليل لتخزين ملفات العرض التقديمي الخاصة بك.
## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، ابدأ باستيراد المساحات المطلوبة:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## الخطوة 1: إنشاء عرض تقديمي
ابدأ بإنشاء عرض تقديمي جديد باستخدام `Presentation` فصل:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // يذهب رمز إنشاء العرض التقديمي الخاص بك هنا.
}
```
## الخطوة 2: إضافة شكل متحرك
الآن، دعنا نضيف شكلًا متحركًا إلى الشريحة الأولى من العرض التقديمي الخاص بك:
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## الخطوة 3: تطبيق تأثير الرسوم المتحركة
أضف تأثير الرسوم المتحركة "PathFootball" إلى الشكل الذي تم إنشاؤه:
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## الخطوة 4: إنشاء زر التشغيل
إنشاء زر لتشغيل الرسوم المتحركة:
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## الخطوة 5: تحديد مسار المستخدم المخصص
قم بتحديد مسار مستخدم مخصص للرسوم المتحركة:
```csharp
ISequence seqInter = pres.Slides[0].Timeline.InteractiveSequences.Add(shapeTrigger);
IEffect fxUserPath = seqInter.AddEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
IMotionEffect motionBhv = ((IMotionEffect)fxUserPath.Behaviors[0]);
PointF[] pts = new PointF[1];
pts[0] = new PointF(0.076f, 0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new PointF(-0.076f, -0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.Path.Add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
// حفظ العرض التقديمي بصيغة PPTX على القرص
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
يُكمل هذا الدليل خطوة بخطوة لتطبيق الرسوم المتحركة على الأشكال باستخدام Aspose.Slides لـ .NET.
## خاتمة
يُضفي دمج الرسوم المتحركة في عروضك التقديمية لمسةً ديناميكيةً تجذب انتباه جمهورك. مع Aspose.Slides، لديك أداةٌ فعّالةٌ لدمج هذه التأثيرات بسلاسةٍ والارتقاء بعروضك التقديمية إلى مستوىً جديد.
## الأسئلة الشائعة
### هل يمكنني تطبيق رسوم متحركة متعددة على شكل واحد؟
نعم، يسمح لك Aspose.Slides بإضافة تأثيرات رسوم متحركة متعددة إلى شكل واحد، مما يوفر المرونة في إنشاء رسوم متحركة معقدة.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
يضمن Aspose.Slides التوافق مع إصدارات PowerPoint المختلفة، مما يضمن عمل العروض التقديمية الخاصة بك بسلاسة عبر منصات مختلفة.
### أين يمكنني العثور على موارد ودعم إضافي لـ Aspose.Slides؟
استكشف [التوثيق](https://reference.aspose.com/slides/net/) وطلب المساعدة في [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### هل أحتاج إلى ترخيص لـ Aspose.Slides لاستخدام المكتبة؟
نعم يمكنك الحصول على ترخيص [هنا](https://purchase.aspose.com/buy) لإطلاق العنان للإمكانات الكاملة لـ Aspose.Slides.
### هل يمكنني تجربة Aspose.Slides قبل الشراء؟
بالتأكيد! استخدم [نسخة تجريبية مجانية](https://releases.aspose.com/) لتجربة إمكانيات Aspose.Slides قبل اتخاذ أي التزام.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}