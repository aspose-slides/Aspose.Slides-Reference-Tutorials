---
title: عرض تأثيرات ثلاثية الأبعاد في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: عرض تأثيرات ثلاثية الأبعاد في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة تأثيرات ثلاثية الأبعاد جذابة إلى شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. يغطي دليلنا خطوة بخطوة كل شيء بدءًا من إعداد بيئتك وحتى تطبيق الرسوم المتحركة وتصدير النتيجة النهائية.
type: docs
weight: 13
url: /ar/net/printing-and-rendering-in-slides/rendering-3d-effects/
---

## مقدمة إلى التأثيرات ثلاثية الأبعاد في شرائح العرض التقديمي

يمكن أن تؤدي إضافة تأثيرات ثلاثية الأبعاد إلى شرائح العرض التقديمي إلى جعل المحتوى الخاص بك أكثر جاذبية وديناميكية. يوفر Aspose.Slides for .NET منصة قوية لدمج هذه التأثيرات بسلاسة. سنستكشف كيفية استخدام المكتبة لإنشاء كائنات ثلاثية الأبعاد ومعالجتها وعرضها في شرائحك.

## إعداد بيئة التطوير الخاصة بك

قبل أن نتعمق في عملية البرمجة، فلنقم بإعداد بيئة التطوير الخاصة بنا. إليك ما تحتاجه:

- تم تثبيت Visual Studio مع Aspose.Slides لمكتبة .NET
- الفهم الأساسي للبرمجة C#

## إنشاء عرض تقديمي جديد

لنبدأ بإنشاء عرض تقديمي جديد باستخدام Aspose.Slides. يوضح مقتطف التعليمات البرمجية التالي كيفية تحقيق ذلك:

```csharp
using Aspose.Slides;

// إنشاء عرض تقديمي جديد
Presentation presentation = new Presentation();
```

## إضافة نماذج ثلاثية الأبعاد إلى الشرائح

الآن وبعد أن أصبح عرضنا التقديمي جاهزًا، فلنضيف نموذجًا ثلاثي الأبعاد إلى الشريحة. يمكنك الاختيار من بين مجموعة متنوعة من التنسيقات مثل OBJ أو STL أو FBX. إليك كيفية إضافة نموذج ثلاثي الأبعاد إلى الشريحة:

```csharp
// قم بتحميل شريحة
ISlide slide = presentation.Slides.AddEmptySlide();

// قم بتحميل النموذج ثلاثي الأبعاد
string modelPath = "path/to/your/3d/model.obj";
byte[] modelBytes = File.ReadAllBytes(modelPath);
IEmbeddingResult embeddingResult = presentation.EmbedExternalFile(modelBytes);

// أضف النموذج ثلاثي الأبعاد إلى الشريحة
slide.Shapes.AddEmbedded3DModelFrame(embeddingResult);
```

## ضبط التأثيرات والخصائص ثلاثية الأبعاد

بمجرد إضافة النموذج ثلاثي الأبعاد، يمكنك ضبط تأثيراته وخصائصه. يتضمن ذلك التدوير والقياس وتحديد المواقع. فيما يلي مثال لكيفية تحقيق ذلك:

```csharp
// احصل على إطار النموذج ثلاثي الأبعاد
I3DModelFrame modelFrame = (I3DModelFrame)slide.Shapes[0];

// تدوير النموذج
modelFrame.RotationX = 30;
modelFrame.RotationY = 45;
modelFrame.RotationZ = 0;

// مقياس النموذج
modelFrame.ScaleX = 1.5;
modelFrame.ScaleY = 1.5;
modelFrame.ScaleZ = 1.5;

// ضع النموذج
modelFrame.X = 100;
modelFrame.Y = 100;
```

## إضافة الرسوم المتحركة إلى كائنات ثلاثية الأبعاد

لجعل العرض التقديمي الخاص بك أكثر جاذبية، يمكنك إضافة رسوم متحركة إلى الكائنات ثلاثية الأبعاد. يتيح لك Aspose.Slides تطبيق تأثيرات الرسوم المتحركة المتنوعة على النماذج ثلاثية الأبعاد. إليك مقتطف للتوضيح:

```csharp
// أضف الرسوم المتحركة إلى النموذج ثلاثي الأبعاد
IAnimation animation = slide.Timeline.MainSequence.AddEffect(modelFrame, EffectType.Fade);
animation.Timing.TriggerType = EffectTriggerType.OnClick;
```

## تطبيق الإضاءة والمواد

لتعزيز واقعية نماذجك ثلاثية الأبعاد، يمكنك استخدام الإضاءة والمواد. ويمكن تحقيق ذلك باستخدام خصائص الإضاءة والمواد في Aspose.Slides. وإليك كيف يمكنك القيام بذلك:

```csharp
// قم بتطبيق الإضاءة على النموذج ثلاثي الأبعاد
modelFrame.LightRig.Preset = LightRigPresetType.BrightRoom;

// تطبيق خصائص المواد
IMaterial material = modelFrame.Materials[0];
material.DiffuseColor = Color.Red;
material.SpecularColor = Color.White;
```

## تصدير العرض التقديمي

بمجرد الانتهاء من التأثيرات ثلاثية الأبعاد والرسوم المتحركة، فقد حان الوقت لتصدير العرض التقديمي الخاص بك. يوفر Aspose.Slides تنسيقات متنوعة للتصدير، مثل PPTX وPDF والمزيد. فيما يلي مقتطف لتصدير العرض التقديمي الخاص بك كملف PDF:

```csharp
// احفظ العرض التقديمي بصيغة PDF
string outputPath = "output/path/presentation.pdf";
presentation.Save(outputPath, SaveFormat.Pdf);
```

## خاتمة

في هذا البرنامج التعليمي، قمنا بالتعمق في عالم التأثيرات ثلاثية الأبعاد المثير في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. لقد تعلمت كيفية إنشاء عرض تقديمي وإضافة نماذج ثلاثية الأبعاد وضبط التأثيرات والخصائص وإضافة الرسوم المتحركة وتطبيق الإضاءة والمواد وتصدير النتيجة النهائية. باستخدام هذه المهارات، يمكنك الآن إنشاء عروض تقديمية مذهلة بصريًا تترك انطباعًا دائمًا لدى جمهورك.

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ .NET؟

 لتثبيت Aspose.Slides لـ .NET، يمكنك اتباع دليل التثبيت المتوفر في[توثيق](https://docs.aspose.com/slides/net/installation/).

### هل يمكنني إضافة نماذج ثلاثية الأبعاد متعددة إلى شريحة واحدة؟

 نعم، يمكنك إضافة نماذج ثلاثية الأبعاد متعددة إلى شريحة واحدة باستخدام`Shapes.AddEmbedded3DModelFrame()` طريقة لكل نموذج.

### هل من الممكن تصدير العرض التقديمي إلى تنسيقات أخرى؟

قطعاً! يدعم Aspose.Slides for .NET تصدير العروض التقديمية إلى تنسيقات مختلفة، بما في ذلك PPTX وPDF وTIFF والمزيد.

### كيف يمكنني إنشاء رسوم متحركة معقدة للنماذج ثلاثية الأبعاد؟

 يمكنك إنشاء رسوم متحركة معقدة باستخدام تأثيرات الرسوم المتحركة التي يوفرها Aspose.Slides. اكتشف ال[وثائق الرسوم المتحركة](https://reference.aspose.com/slides/net/aspose.slides.animation/) للحصول على معلومات مفصلة.

### أين يمكنني العثور على المزيد من أمثلة التعليمات البرمجية والموارد؟

 لمزيد من أمثلة التعليمات البرمجية والبرامج التعليمية والموارد، يمكنك زيارة[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).