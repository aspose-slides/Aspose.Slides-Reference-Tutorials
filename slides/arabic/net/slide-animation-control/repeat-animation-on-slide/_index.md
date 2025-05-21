---
"description": "حسّن عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. تحكّم في الرسوم المتحركة بسهولة، وأبهر جمهورك، واترك انطباعًا لا يُنسى."
"linktitle": "تكرار الرسوم المتحركة على الشريحة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إتقان الرسوم المتحركة في PowerPoint باستخدام Aspose.Slides .NET"
"url": "/ar/net/slide-animation-control/repeat-animation-on-slide/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إتقان الرسوم المتحركة في PowerPoint باستخدام Aspose.Slides .NET

## مقدمة
في عالم العروض التقديمية المتغير باستمرار، تلعب القدرة على التحكم في الرسوم المتحركة دورًا محوريًا في جذب انتباه الجمهور ولفت انتباهه. يُمكّن Aspose.Slides for .NET المطورين من التحكم في أنواع الرسوم المتحركة داخل الشرائح، مما يتيح عرضًا تقديميًا أكثر تفاعلية وجاذبية بصرية. في هذا البرنامج التعليمي، سنستكشف كيفية التحكم في أنواع الرسوم المتحركة على الشريحة باستخدام Aspose.Slides for .NET، خطوة بخطوة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. Aspose.Slides لمكتبة .NET: قم بتنزيل المكتبة وتثبيتها من [هنا](https://releases.aspose.com/slides/net/).
2. بيئة تطوير .NET: قم بإعداد بيئة تطوير .NET على جهازك.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، ابدأ باستيراد المساحات الأساسية اللازمة للاستفادة من الوظائف التي يوفرها Aspose.Slides:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد المشروع
قم بإنشاء دليل جديد لمشروعك وقم بإنشاء فئة العرض التقديمي لتمثيل ملف العرض التقديمي.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // الكود الخاص بك يذهب هنا
}
```
## الخطوة 2: الوصول إلى تسلسل التأثيرات
استرداد تسلسل التأثيرات للشريحة الأولى باستخدام خاصية MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## الخطوة 3: الوصول إلى التأثير الأول
احصل على التأثير الأول للتسلسل الرئيسي للتلاعب بخصائصه.
```csharp
IEffect effect = effectsSequence[0];
```
## الخطوة 4: تعديل إعدادات التكرار
قم بتغيير خاصية التوقيت/التكرار الخاصة بالتأثير إلى "حتى نهاية الشريحة".
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل لتتمكن من تصور التغييرات.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
كرر هذه الخطوات للحصول على تأثيرات إضافية أو قم بتخصيصها وفقًا لمتطلبات العرض التقديمي الخاص بك.
## خاتمة
أصبح دمج الرسوم المتحركة الديناميكية في عروض PowerPoint التقديمية أسهل من أي وقت مضى مع Aspose.Slides لـ .NET. يُزودك هذا الدليل المُفصّل بالمهارات اللازمة للتحكم في أنواع الرسوم المتحركة، مما يضمن أن تترك شرائحك انطباعًا دائمًا لدى جمهورك.
## الأسئلة الشائعة
### هل يمكنني تطبيق هذه الرسوم المتحركة على كائنات محددة ضمن شريحة؟
نعم، يمكنك استهداف كائنات محددة عن طريق الوصول إلى تأثيراتها الفردية ضمن التسلسل.
### هل Aspose.Slides متوافق مع أحدث إصدارات PowerPoint؟
يوفر Aspose.Slides الدعم لمجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق مع الإصدارات القديمة والجديدة.
### أين يمكنني العثور على أمثلة وموارد إضافية؟
استكشف [التوثيق](https://reference.aspose.com/slides/net/) للحصول على أمثلة شاملة وشروحات مفصلة.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
يزور [هنا](https://purchase.aspose.com/temporary-license/) للحصول على معلومات حول الحصول على ترخيص مؤقت.
### هل تحتاج إلى مساعدة أو لديك المزيد من الأسئلة؟
تواصل مع مجتمع Aspose.Slides على [منتدى الدعم](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}