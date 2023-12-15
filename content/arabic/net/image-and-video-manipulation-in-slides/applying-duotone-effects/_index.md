---
title: تطبيق تأثيرات الفرز الثنائي في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: تطبيق تأثيرات الفرز الثنائي في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين شرائح العرض التقديمي الخاص بك باستخدام تأثيرات الفرز الثنائي الجذابة باستخدام Aspose.Slides for .NET. اتبع دليلنا خطوة بخطوة مع كود المصدر الكامل لإنشاء شرائح مذهلة بصريًا تجذب انتباه جمهورك. قم بتخصيص الألوان الثنائية، وتطبيق التأثيرات على الصور والنصوص، واحفظ عرضك التقديمي المعدل بسلاسة.
type: docs
weight: 18
url: /ar/net/image-and-video-manipulation-in-slides/applying-duotone-effects/
---

## مقدمة لتأثيرات الفرز الثنائي

تتضمن تأثيرات الفرز الثنائي استخدام لونين، عادةً لون داكن ولون فاتح، لإنشاء صور ورسومات جذابة بصريًا. تضيف هذه التقنية عمقًا وتباينًا إلى شرائحك، مما يجعلها أكثر جاذبية ولا تُنسى.

## إعداد بيئة التطوير الخاصة بك

قبل أن نبدأ، تأكد من تثبيت الأدوات اللازمة:

- Visual Studio (أو أي .NET IDE)
- Aspose.Slides لمكتبة .NET

 يمكنك تنزيل مكتبة Aspose.Slides من[هنا](https://releases.aspose.com/slides/net/).

## تحميل عرض تقديمي

1. قم بإنشاء مشروع C# جديد في Visual Studio.
2. قم بتثبيت حزمة Aspose.Slides NuGet.
3. قم باستيراد مساحات الأسماء الضرورية:

```csharp
using Aspose.Slides;
using Aspose.Slides.Util;
```

4. تحميل عرض تقديمي موجود:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // الكود الخاص بك لمعالجة العرض التقديمي موجود هنا
}
```

## تطبيق تأثيرات الفرز الثنائي على الصور

1. حدد الصور التي تريد تطبيق تأثيرات الفرز الثنائي عليها.
2. قم بالتمرير عبر الصور وقم بتطبيق تأثيرات الفرز الثنائي:

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    if (shape is IAutoShape autoShape && autoShape.PictureFormat != null)
    {
        // تطبيق تأثيرات الفرز الثنائي
        DuotoneEffectParameters duotoneEffect = new DuotoneEffectParameters();
        duotoneEffect.FirstColor = Color.Black;
        duotoneEffect.SecondColor = Color.White;
        autoShape.PictureFormat.ImageColorMode = ImageColorMode.Duotone;
        autoShape.PictureFormat.DuotoneEffect = duotoneEffect;
    }
}
```

## إضافة النصوص Duotone

1. حدد أشكال النص التي تريد تطبيق تأثيرات الفرز الثنائي عليها.
2. قم بالمرور عبر أشكال النص وقم بتطبيق تأثيرات الفرز الثنائي:

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    if (shape is IAutoShape autoShape && autoShape.TextFrame != null)
    {
        //تطبيق تأثيرات الفرز الثنائي على النص
        DuotoneEffectParameters duotoneEffect = new DuotoneEffectParameters();
        duotoneEffect.FirstColor = Color.Black;
        duotoneEffect.SecondColor = Color.White;
        autoShape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.DuotoneEffect = duotoneEffect;
    }
}
```

## تخصيص ألوان الفرز الثنائي

 يمكنك تخصيص ألوان الفرز الثنائي وفقًا لتفضيلات التصميم الخاصة بك. ببساطة استبدل`FirstColor` و`SecondColor` القيم مع الألوان المطلوبة.

## حفظ وتصدير العرض التقديمي المعدل

بعد تطبيق تأثيرات الفرز الثنائي، احفظ العرض التقديمي المعدل وقم بتصديره:

```csharp
string outputPath = "path_to_save_modified_presentation.pptx";
presentation.Save(outputPath, SaveFormat.Pptx);
```

## خاتمة

يمكن أن يؤدي تحسين شرائح العرض التقديمي باستخدام تأثيرات الفرز الثنائي إلى تحسين تأثيرها البصري بشكل كبير وجذب انتباه جمهورك. باستخدام Aspose.Slides for .NET، يصبح تطبيق تأثيرات الفرز الثنائي برمجيًا عملية سلسة، مما يسمح لك بإنشاء عروض تقديمية مذهلة ومتميزة.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لمكتبة .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides من[هنا](https://releases.aspose.com/slides/net/).

### هل يمكنني تطبيق تأثيرات الفرز الثنائي على كل من الصور والنص في نفس الشريحة؟

نعم، يمكنك تطبيق تأثيرات الفرز الثنائي على كل من الصور والنص داخل نفس الشريحة، كما هو موضح في الدليل.

### هل من الممكن استخدام ألوان مختلفة لتأثيرات الفرز الثنائي؟

قطعاً! يمكنك تخصيص ألوان الفرز الثنائي لتتناسب مع تفضيلات التصميم الخاصة بك وإنشاء تأثيرات بصرية فريدة.

### هل أحتاج إلى مهارات برمجة متقدمة لاستخدام Aspose.Slides لـ .NET؟

في حين أن بعض المعرفة البرمجية مفيدة، فقد تم تصميم مقتطفات التعليمات البرمجية المقدمة لتكون واضحة وسهلة الفهم، حتى بالنسبة للمبتدئين.

### كيف يمكنني معرفة المزيد حول Aspose.Slides لـ .NET؟

 لمزيد من المعلومات التفصيلية والوثائق، يمكنك الرجوع إلى[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).