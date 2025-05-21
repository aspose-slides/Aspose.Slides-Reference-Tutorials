---
"description": "تعلّم كيفية إرجاع الرسوم المتحركة إلى الوراء على شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. اتبع هذا الدليل خطوة بخطوة مع أمثلة كاملة على الكود المصدري."
"linktitle": "إرجاع الرسوم المتحركة على الشريحة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إتقان الرسوم المتحركة التراجعية في العروض التقديمية باستخدام Aspose.Slides"
"url": "/ar/net/slide-animation-control/rewind-animation-on-slide/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إتقان الرسوم المتحركة التراجعية في العروض التقديمية باستخدام Aspose.Slides

## مقدمة
في عالم العروض التقديمية المتغير باستمرار، يُعزز دمج الرسوم المتحركة الجذابة التفاعل بشكل كبير. يوفر Aspose.Slides for .NET مجموعة أدوات فعّالة لإضفاء الحيوية على عروضك التقديمية. ومن الميزات المثيرة للاهتمام إمكانية إرجاع الرسوم المتحركة على الشرائح. في هذا الدليل الشامل، سنشرح العملية خطوة بخطوة، مما يتيح لك الاستفادة الكاملة من إمكانات إرجاع الرسوم المتحركة باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من تثبيت المكتبة. إذا لم تكن مثبتة، فقم بتنزيلها من [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/).
- بيئة تطوير .NET: تأكد من إعداد بيئة تطوير .NET عاملة.
- المعرفة الأساسية بلغة C#: تعرف على أساسيات لغة البرمجة C#.
## استيراد مساحات الأسماء
في شيفرة C# الخاصة بك، ستحتاج إلى استيراد مساحات الأسماء اللازمة للاستفادة من وظيفة Aspose.Slides لـ .NET. إليك بعض الإرشادات:
```csharp
using System;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد مشروعك
أنشئ مشروعًا جديدًا في بيئة تطوير .NET المُفضّلة لديك. أنشئ مجلدًا لمستنداتك إذا لم يكن موجودًا.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## الخطوة 2: تحميل العرض التقديمي
إنشاء مثيل `Presentation` الفئة لتمثيل ملف العرض التقديمي الخاص بك.
```csharp
using (Presentation presentation = new Presentation(dataDir + "AnimationRewind.pptx"))
{
    // الكود الخاص بك للخطوات اللاحقة يذهب هنا
}
```
## الخطوة 3: الوصول إلى تسلسل التأثيرات
استرداد تسلسل التأثيرات للشريحة الأولى.
```csharp
ISequence effectsSequence = presentation.Slides[0].Timeline.MainSequence;
```
## الخطوة 4: تعديل توقيت التأثير
قم بالوصول إلى التأثير الأول للتسلسل الرئيسي وتعديل توقيته لتمكين التراجع.
```csharp
IEffect effect = effectsSequence[0];
Console.WriteLine("\nEffect Timing/Rewind in source presentation is {0}", effect.Timing.Rewind);
effect.Timing.Rewind = true;
```
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل.
```csharp
presentation.Save(RunExamples.OutPath + "AnimationRewind-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
## الخطوة 6: التحقق من تأثير التراجع في العرض التقديمي الوجهة
قم بتحميل العرض التقديمي المعدل وتحقق مما إذا كان تأثير التراجع مطبقًا.
```csharp
using (Presentation pres = new Presentation(RunExamples.OutPath + "AnimationRewind-out.pptx"))
{
    effectsSequence = pres.Slides[0].Timeline.MainSequence;
    effect = effectsSequence[0];
    Console.WriteLine("Effect Timing/Rewind in destination presentation is {0}\n", effect.Timing.Rewind);
}
```
كرر هذه الخطوات للشرائح الإضافية أو قم بتخصيص العملية وفقًا لهيكل العرض التقديمي الخاص بك.
## خاتمة
يتيح لك تفعيل ميزة الرسوم المتحركة الخلفية في Aspose.Slides لـ .NET إمكانيات رائعة لإنشاء عروض تقديمية ديناميكية وجذابة. باتباع هذا الدليل المفصل، يمكنك دمج الرسوم المتحركة الخلفية بسلاسة في مشاريعك، مما يعزز المظهر البصري لشرائحك.
---
## الأسئلة الشائعة
### هل Aspose.Slides for .NET متوافق مع أحدث إصدار من .NET Framework؟
يتم تحديث Aspose.Slides لـ .NET بانتظام لضمان توافقه مع أحدث إصدارات إطار عمل .NET. تحقق من [التوثيق](https://reference.aspose.com/slides/net/) للحصول على تفاصيل التوافق.
### هل يمكنني تطبيق الرسوم المتحركة التراجعية على كائنات محددة داخل شريحة؟
نعم، يمكنك تخصيص الكود لتطبيق الرسوم المتحركة التراجعية بشكل انتقائي على كائنات أو عناصر محددة ضمن شريحة.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ .NET؟
نعم، يمكنك استكشاف الميزات من خلال الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لطلب المساعدة والتفاعل مع المجتمع.
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
نعم يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}