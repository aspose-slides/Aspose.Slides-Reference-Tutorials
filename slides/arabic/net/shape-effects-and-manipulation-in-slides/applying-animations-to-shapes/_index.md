---
title: أصبحت الرسوم المتحركة للأشكال سهلة باستخدام Aspose.Slides
linktitle: تطبيق الرسوم المتحركة على الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بإنشاء عروض تقديمية مذهلة باستخدام Aspose.Slides لـ .NET. تعرف على كيفية تطبيق الرسوم المتحركة على الأشكال في هذا الدليل التفصيلي خطوة بخطوة. ارفع شرائحك الآن!
weight: 21
url: /ar/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في عالم العروض التقديمية الديناميكية، يمكن أن تؤدي إضافة الرسوم المتحركة إلى الأشكال إلى تحسين المظهر المرئي والتفاعل مع شرائحك بشكل كبير. يوفر Aspose.Slides for .NET مجموعة أدوات قوية لتحقيق ذلك بسلاسة. في هذا البرنامج التعليمي، سنرشدك خلال عملية تطبيق الرسوم المتحركة على الأشكال باستخدام Aspose.Slides، مما يسمح لك بإنشاء عروض تقديمية جذابة تترك انطباعًا دائمًا.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1.  Aspose.Slides for .NET: تأكد من تثبيت المكتبة وجاهزيتها للاستخدام. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
2. بيئة التطوير: قم بإعداد بيئة التطوير المفضلة لديك بالتكوينات اللازمة.
3. دليل المستندات: قم بإنشاء دليل لتخزين ملفات العرض التقديمي الخاص بك.
## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، ابدأ باستيراد مساحات الأسماء المطلوبة:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## الخطوة 1: إنشاء عرض تقديمي
 ابدأ بإنشاء عرض تقديمي جديد باستخدام`Presentation` فصل:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك لإنشاء عرض تقديمي موجود هنا.
}
```
## الخطوة 2: إضافة شكل متحرك
الآن، دعنا نضيف شكلاً متحركًا إلى الشريحة الأولى من العرض التقديمي الخاص بك:
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
## الخطوة 4: إنشاء زر الزناد
قم بإنشاء زر يؤدي إلى تشغيل الرسوم المتحركة:
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## الخطوة 5: تحديد مسار المستخدم المخصص
تحديد مسار مستخدم مخصص للرسوم المتحركة:
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
// احفظ العرض التقديمي بتنسيق PPTX على القرص
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
يكمل هذا الدليل خطوة بخطوة لتطبيق الرسوم المتحركة على الأشكال باستخدام Aspose.Slides for .NET.
## خاتمة
يضيف دمج الرسوم المتحركة في عروضك التقديمية عنصرًا ديناميكيًا يجذب انتباه جمهورك. باستخدام Aspose.Slides، لديك أداة قوية لدمج هذه التأثيرات بسلاسة والارتقاء بعروضك التقديمية إلى المستوى التالي.
## أسئلة مكررة
### هل يمكنني تطبيق رسوم متحركة متعددة على شكل واحد؟
نعم، يتيح لك Aspose.Slides إضافة تأثيرات رسوم متحركة متعددة إلى شكل واحد، مما يوفر المرونة في إنشاء رسوم متحركة معقدة.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
يضمن Aspose.Slides التوافق مع إصدارات PowerPoint المختلفة، مما يضمن عمل العروض التقديمية الخاصة بك بسلاسة عبر منصات مختلفة.
### أين يمكنني العثور على موارد إضافية ودعم لـ Aspose.Slides؟
 اكتشف ال[توثيق](https://reference.aspose.com/slides/net/) وطلب المساعدة في[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### هل أحتاج إلى ترخيص Aspose.Slides لاستخدام المكتبة؟
 نعم، يمكنك الحصول على ترخيص[هنا](https://purchase.aspose.com/buy) لفتح الإمكانات الكاملة لـ Aspose.Slides.
### هل يمكنني تجربة Aspose.Slides قبل الشراء؟
 بالتأكيد! الاستفادة من[تجربة مجانية](https://releases.aspose.com/) لتجربة قدرات Aspose.Slides قبل الالتزام.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
