---
title: التحكم بعد الرسوم المتحركة اكتب في الشريحة
linktitle: التحكم بعد الرسوم المتحركة اكتب في الشريحة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية التحكم في أنواع الرسوم المتحركة في شرائح PowerPoint باستخدام Aspose.Slides for .NET. يوفر هذا الدليل خطوة بخطوة أمثلة على التعليمات البرمجية المصدر ويغطي التثبيت وتنفيذ التعليمات البرمجية وتعديل تأثيرات الرسوم المتحركة.
type: docs
weight: 11
url: /ar/net/slide-animation-control/control-after-animation-type/
---

## مقدمة للتحكم بعد أنواع الرسوم المتحركة في الشرائح

قبل أن نتعمق في التعليمات البرمجية، دعونا نفهم بسرعة مفهوم أنواع الرسوم المتحركة في الشرائح. تضيف تأثيرات الرسوم المتحركة جاذبية بصرية إلى عروضك التقديمية، مما يجعلها أكثر تفاعلية وجاذبية. يوفر Aspose.Slides أنواعًا مختلفة من الرسوم المتحركة، مثل الرسوم المتحركة للدخول والخروج والتأكيد ومسار الحركة، حيث يخدم كل منها غرضًا فريدًا.

## إعداد بيئة التطوير الخاصة بك

للبدء، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio أو أي بيئة تطوير .NET متوافقة.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## إضافة المراجع والواردات

1. قم بإنشاء مشروع .NET جديد في بيئة التطوير الخاصة بك.
2. أضف مرجعًا إلى مكتبة Aspose.Slides لـ .NET التي تم تنزيلها.
3. استيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Slides;
using Aspose.Slides.Animation;
```

## تحميل ملف العرض التقديمي

للعمل مع العروض التقديمية، تحتاج إلى تحميل ملف PowerPoint باستخدام Aspose.Slides. وإليك كيف يمكنك القيام بذلك:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (var presentation = new Presentation(presentationPath))
{
    // سيتم وضع الكود الخاص بك للتحكم في الرسوم المتحركة للشرائح هنا
}
```

## الوصول إلى الرسوم المتحركة للشرائح

يمكن أن تحتوي كل شريحة في العرض التقديمي على رسوم متحركة مختلفة. للوصول إلى الرسوم المتحركة للشرائح، ستحتاج إلى التكرار عبر الشرائح والوصول إلى خصائص الرسوم المتحركة الخاصة بها:

```csharp
foreach (var slide in presentation.Slides)
{
    ISequence sequence = slide.Timeline.MainSequence;
    foreach (Effect effect in sequence)
    {
        // سيتم وضع الكود الخاص بك للتحكم في الرسوم المتحركة هنا
    }
}
```

## التحكم في أنواع الرسوم المتحركة

لنفترض أنك تريد تغيير نوع الرسوم المتحركة لتأثير معين للتأكيد على المحتوى. وإليك كيف يمكنك تحقيق ذلك:

```csharp
foreach (Effect effect in sequence)
{
    if (effect is EntranceEffect entranceEffect)
    {
        entranceEffect.Type = EntranceAnimationType.Zoom;
    }
    else if (effect is EmphasisEffect emphasisEffect)
    {
        emphasisEffect.Type = EmphasisAnimationType.GrowWithColor;
    }
    // يمكنك التعامل مع أنواع الرسوم المتحركة الأخرى بالمثل
}
```

## معاينة وحفظ العرض التقديمي المعدل

بمجرد قيامك بتعديل أنواع الرسوم المتحركة، فمن الممارسات الجيدة معاينة التغييرات قبل حفظ العرض التقديمي:

```csharp
presentation.Slides[0].SlideShowTransition.AdvanceOnClick = true;
presentation.Slides[0].SlideShowTransition.AdvanceAfterTime = 3000; // 3 ثوان

presentation.Save("modified_presentation.pptx", SaveFormat.Pptx);
```

## مثال على كود المصدر الكامل

فيما يلي مثال التعليمات البرمجية المصدر الكامل للتحكم في أنواع الرسوم المتحركة في الشرائح باستخدام Aspose.Slides لـ .NET:

```csharp
using Aspose.Slides;
using Aspose.Slides.Animation;

class Program
{
    static void Main()
    {
        string presentationPath = "path_to_your_presentation.pptx";
        using (var presentation = new Presentation(presentationPath))
        {
            foreach (var slide in presentation.Slides)
            {
                ISequence sequence = slide.Timeline.MainSequence;
                foreach (Effect effect in sequence)
                {
                    if (effect is EntranceEffect entranceEffect)
                    {
                        entranceEffect.Type = EntranceAnimationType.Zoom;
                    }
                    else if (effect is EmphasisEffect emphasisEffect)
                    {
                        emphasisEffect.Type = EmphasisAnimationType.GrowWithColor;
                    }
                    //التعامل مع أنواع الرسوم المتحركة الأخرى بالمثل
                }
            }

            presentation.Slides[0].SlideShowTransition.AdvanceOnClick = true;
            presentation.Slides[0].SlideShowTransition.AdvanceAfterTime = 3000;

            presentation.Save("modified_presentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## خاتمة

لقد زودك هذا الدليل الشامل بالخبرة اللازمة لتسخير قوة Aspose.Slides لـ .NET والتحكم بشكل فعال في أنواع الرسوم المتحركة داخل عروض PowerPoint التقديمية. بفضل الفهم القوي لإمكانيات المكتبة والتعليمات المقدمة خطوة بخطوة، أنت الآن مستعد جيدًا لإنشاء عروض شرائح ديناميكية وجذابة تأسر جمهورك. من خلال الاستفادة من ميزات Aspose.Slides، يمكنك تعديل تأثيرات الرسوم المتحركة بسلاسة، وتعزيز الجاذبية البصرية، وزيادة تأثير العروض التقديمية الخاصة بك. احتضن الإمكانيات التي توفرها هذه الأداة متعددة الاستخدامات، وابدأ في رحلة لصياغة عروض تقديمية أكثر جاذبية وتفاعلية.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لمكتبة .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides for .NET من[هنا](https://releases.aspose.com/slides/net/).

### هل يمكنني تعديل الرسوم المتحركة لمسار الحركة باستخدام Aspose.Slides؟

 نعم، يمكنك تعديل الرسوم المتحركة لمسار الحركة باستخدام Aspose.Slides عن طريق الوصول إلى`MotionPathEffect` الخصائص وتعديلها وفقًا لذلك.

### هل من الممكن إضافة رسوم متحركة مخصصة إلى العناصر الموجودة في الشريحة؟

قطعاً! يسمح لك Aspose.Slides بإنشاء وإضافة رسوم متحركة مخصصة إلى العناصر الموجودة في الشريحة من خلال العمل مع خصائص الرسوم المتحركة وتأثيراتها.

### ما هي التنسيقات التي يمكنني حفظ العرض التقديمي المعدل بها؟

يمكنك حفظ العرض التقديمي المعدل بتنسيقات مختلفة، بما في ذلك PPTX وPPT وPDF والمزيد، وفقًا لمتطلباتك.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ .NET؟

يمكنك العثور على وثائق وأمثلة مفصلة في[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).