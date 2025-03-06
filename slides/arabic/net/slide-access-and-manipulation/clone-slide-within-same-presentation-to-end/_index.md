---
title: تكرار الشريحة إلى نهاية العرض التقديمي الموجود
linktitle: تكرار الشريحة إلى نهاية العرض التقديمي الموجود
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تكرار شريحة وإضافتها إلى نهاية عرض تقديمي موجود في PowerPoint باستخدام Aspose.Slides for .NET. يوفر هذا الدليل خطوة بخطوة أمثلة على التعليمات البرمجية المصدر ويغطي الإعداد وتكرار الشرائح والتعديل والمزيد.
weight: 22
url: /ar/net/slide-access-and-manipulation/clone-slide-within-same-presentation-to-end/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET عبارة عن واجهة برمجة تطبيقات قوية تتيح للمطورين العمل مع عروض PowerPoint التقديمية بطرق مختلفة، بما في ذلك إنشاء الشرائح وتعديلها ومعالجتها برمجيًا. وهو يدعم مجموعة واسعة من الميزات، مما يجعله خيارًا شائعًا لأتمتة المهام المتعلقة بالعروض التقديمية.

## الخطوة 1: إعداد المشروع

 قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides for .NET. يمكنك تنزيله من[رابط التحميل](https://releases.aspose.com/slides/net/). قم بإنشاء مشروع Visual Studio جديد وأضف مرجعًا إلى مكتبة Aspose.Slides التي تم تنزيلها.

## الخطوة 2: تحميل عرض تقديمي موجود

في هذه الخطوة، سنقوم بتحميل عرض PowerPoint تقديمي موجود باستخدام Aspose.Slides لـ .NET. يمكنك استخدام مقتطف الشفرة التالي كمرجع:

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // قم بتحميل العرض التقديمي الموجود
        Presentation presentation = new Presentation("existing-presentation.pptx");
    }
}
```

 يستبدل`"existing-presentation.pptx"`مع المسار إلى ملف عرض PowerPoint التقديمي الفعلي الخاص بك.

## الخطوة 3: تكرار الشريحة

لتكرار شريحة، سنحتاج أولاً إلى تحديد الشريحة التي نريد تكرارها. وبعد ذلك، سنقوم باستنساخها لإنشاء نسخة مماثلة. وإليك كيف يمكنك القيام بذلك:

```csharp
// تحديد الشريحة المراد تكرارها (يبدأ الفهرس من 0)
ISlide sourceSlide = presentation.Slides[0];

// استنساخ الشريحة المحددة
ISlide duplicatedSlide = presentation.Slides.InsertClone(1, sourceSlide);
```

في هذا المثال، نقوم بتكرار الشريحة الأولى وإدراج الشريحة المكررة في الفهرس 1 (الموضع 2).

## الخطوة 4: إضافة شريحة مكررة إلى النهاية

والآن بعد أن أصبح لدينا شريحة مكررة، فلنضيفها إلى نهاية العرض التقديمي. يمكنك استخدام الكود التالي:

```csharp
// أضف الشريحة المكررة إلى نهاية العرض التقديمي
presentation.Slides.AddClone(duplicatedSlide);
```

يضيف مقتطف الكود هذا الشريحة المكررة إلى نهاية العرض التقديمي.

## الخطوة 5: حفظ العرض التقديمي المعدل

بعد إضافة الشريحة المكررة، نحتاج إلى حفظ العرض التقديمي المعدل. إليك الطريقة:

```csharp
//احفظ العرض التقديمي المعدل
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

 يستبدل`"modified-presentation.pptx"` بالاسم المطلوب للعرض التقديمي المعدل.

## خاتمة

في هذا الدليل، اكتشفنا كيفية تكرار شريحة وإضافتها إلى نهاية عرض تقديمي موجود في PowerPoint باستخدام Aspose.Slides for .NET. تعمل هذه المكتبة القوية على تبسيط عملية العمل مع العروض التقديمية برمجيًا، حيث تقدم مجموعة واسعة من الميزات لمختلف المهام.

## الأسئلة الشائعة

### كيف يمكنني الحصول على Aspose.Slides لـ .NET؟

 يمكنك الحصول على مكتبة Aspose.Slides for .NET من[رابط التحميل](https://releases.aspose.com/slides/net/). تأكد من اتباع تعليمات التثبيت المتوفرة على الموقع.

### هل يمكنني تكرار شرائح متعددة في وقت واحد؟

نعم، يمكنك تكرار شرائح متعددة مرة واحدة عن طريق التكرار عبر الشرائح واستنساخها حسب الحاجة. اضبط الكود وفقًا لمتطلباتك.

### هل Aspose.Slides لـ .NET مجاني للاستخدام؟

لا، Aspose.Slides for .NET هي مكتبة تجارية تتطلب ترخيصًا صالحًا للاستخدام. يمكنك التحقق من تفاصيل الأسعار على موقع Aspose.

### هل يدعم Aspose.Slides تنسيقات الملفات الأخرى؟

نعم، يدعم Aspose.Slides تنسيقات PowerPoint المتنوعة، بما في ذلك PPT وPPTX وPPS والمزيد. راجع الوثائق للحصول على قائمة كاملة بالتنسيقات المدعومة.

### هل يمكنني تعديل محتوى الشريحة باستخدام Aspose.Slides؟

قطعاً! لا يسمح لك Aspose.Slides بتكرار الشرائح فحسب، بل يسمح لك أيضًا بمعالجة محتواها، مثل النصوص والصور والأشكال والرسوم المتحركة، برمجيًا.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
