---
title: إتقان إرجاع الرسوم المتحركة في العروض التقديمية باستخدام Aspose.Slides
linktitle: إرجاع الرسوم المتحركة على الشريحة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إرجاع الرسوم المتحركة على شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. اتبع هذا الدليل خطوة بخطوة مع أمثلة التعليمات البرمجية المصدر الكاملة.
type: docs
weight: 13
url: /ar/net/slide-animation-control/rewind-animation-on-slide/
---
## مقدمة
في عالم العروض التقديمية الديناميكي، يمكن أن يؤدي دمج الرسوم المتحركة الجذابة إلى تعزيز المشاركة بشكل كبير. يوفر Aspose.Slides for .NET مجموعة أدوات قوية لإضفاء الحيوية على عروضك التقديمية. إحدى الميزات المثيرة للاهتمام هي القدرة على إرجاع الرسوم المتحركة على الشرائح. في هذا الدليل الشامل، سنرشدك خلال العملية خطوة بخطوة، مما يسمح لك بالاستفادة من الإمكانات الكاملة لإرجاع الرسوم المتحركة باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
-  Aspose.Slides for .NET: تأكد من تثبيت المكتبة. إذا لم يكن الأمر كذلك، قم بتنزيله من[Aspose.Slides لتوثيق .NET](https://reference.aspose.com/slides/net/).
- بيئة تطوير .NET: تأكد من إعداد بيئة تطوير .NET صالحة للعمل.
- المعرفة الأساسية لـ C#: تعرف على أساسيات لغة البرمجة C#.
## استيراد مساحات الأسماء
في كود C# الخاص بك، ستحتاج إلى استيراد مساحات الأسماء الضرورية للاستفادة من الوظائف التي يوفرها Aspose.Slides لـ .NET. إليك مقتطف لإرشادك:
```csharp
using System;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## الخطوة 1: قم بإعداد مشروعك
قم بإنشاء مشروع جديد في بيئة التطوير .NET المفضلة لديك. قم بإعداد دليل لمستنداتك إذا لم يكن موجودًا.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## الخطوة 2: قم بتحميل العرض التقديمي
 إنشاء مثيل`Presentation` class لتمثيل ملف العرض التقديمي الخاص بك.
```csharp
using (Presentation presentation = new Presentation(dataDir + "AnimationRewind.pptx"))
{
    // الكود الخاص بك للخطوات اللاحقة موجود هنا
}
```
## الخطوة 3: الوصول إلى تسلسل التأثيرات
استرداد تسلسل التأثيرات للشريحة الأولى.
```csharp
ISequence effectsSequence = presentation.Slides[0].Timeline.MainSequence;
```
## الخطوة 4: تعديل توقيت التأثير
الوصول إلى التأثير الأول للتسلسل الرئيسي وتعديل توقيته لتمكين الترجيع.
```csharp
IEffect effect = effectsSequence[0];
Console.WriteLine("\nEffect Timing/Rewind in source presentation is {0}", effect.Timing.Rewind);
effect.Timing.Rewind = true;
```
## الخطوة 5: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل.
```csharp
presentation.Save(RunExamples.OutPath + "AnimationRewind-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
## الخطوة 6: التحقق من تأثير الترجيع في عرض الوجهة
قم بتحميل العرض التقديمي المعدل وتحقق من تطبيق تأثير الترجيع.
```csharp
using (Presentation pres = new Presentation(RunExamples.OutPath + "AnimationRewind-out.pptx"))
{
    effectsSequence = pres.Slides[0].Timeline.MainSequence;
    effect = effectsSequence[0];
    Console.WriteLine("Effect Timing/Rewind in destination presentation is {0}\n", effect.Timing.Rewind);
}
```
كرر هذه الخطوات لشرائح إضافية أو قم بتخصيص العملية وفقًا لبنية العرض التقديمي الخاص بك.
## خاتمة
Unlocking the rewind animation feature in Aspose.Slides for .NET opens up exciting possibilities for creating dynamic and engaging presentations. By following this step-by-step guide, you can seamlessly integrate animation rewind into your projects, enhancing the visual appeal of your slides.
---
## الأسئلة الشائعة
### هل يتوافق Aspose.Slides for .NET مع أحدث إصدار من .NET Framework؟
 يتم تحديث Aspose.Slides for .NET بانتظام لضمان التوافق مع أحدث إصدارات إطار عمل .NET. افحص ال[توثيق](https://reference.aspose.com/slides/net/) للحصول على تفاصيل التوافق.
### هل يمكنني تطبيق حركة الترجيع على كائنات محددة داخل الشريحة؟
نعم، يمكنك تخصيص التعليمات البرمجية لتطبيق الرسوم المتحركة الترجيع بشكل انتقائي على كائنات أو عناصر محددة داخل الشريحة.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك استكشاف الميزات من خلال الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على دعم Aspose.Slides لـ .NET؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لطلب المساعدة والتفاعل مع المجتمع.
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 نعم يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).