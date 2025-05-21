---
"description": "تعرّف على كيفية نسخ شريحة وإضافة أخرى إلى نهاية عرض تقديمي موجود في PowerPoint باستخدام Aspose.Slides لـ .NET. يوفر هذا الدليل التفصيلي أمثلة على الكود المصدري، ويغطي الإعداد، ونسخ الشريحة، والتعديل، والمزيد."
"linktitle": "تكرار الشريحة إلى نهاية العرض التقديمي الحالي"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تكرار الشريحة إلى نهاية العرض التقديمي الحالي"
"url": "/ar/net/slide-access-and-manipulation/clone-slide-within-same-presentation-to-end/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تكرار الشريحة إلى نهاية العرض التقديمي الحالي


## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي واجهة برمجة تطبيقات فعّالة تُمكّن المطورين من العمل مع عروض PowerPoint التقديمية بطرق مُختلفة، بما في ذلك إنشاء الشرائح وتعديلها ومعالجتها برمجيًا. تدعم هذه الواجهة مجموعة واسعة من الميزات، مما يجعلها خيارًا شائعًا لأتمتة المهام المُتعلقة بالعروض التقديمية.

## الخطوة 1: إعداد المشروع

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [رابط التحميل](https://releases.aspose.com/slides/net/). قم بإنشاء مشروع Visual Studio جديد وأضف مرجعًا إلى مكتبة Aspose.Slides التي تم تنزيلها.

## الخطوة 2: تحميل عرض تقديمي موجود

في هذه الخطوة، سنحمّل عرضًا تقديميًا موجودًا على PowerPoint باستخدام Aspose.Slides لـ .NET. يمكنك استخدام مقتطف الكود التالي كمرجع:

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // تحميل العرض التقديمي الحالي
        Presentation presentation = new Presentation("existing-presentation.pptx");
    }
}
```

يستبدل `"existing-presentation.pptx"` مع المسار إلى ملف العرض التقديمي الفعلي الخاص بك في PowerPoint.

## الخطوة 3: تكرار الشريحة

لتكرار شريحة، علينا أولاً تحديد الشريحة التي نريد تكرارها. ثم نستنسخها لإنشاء نسخة مطابقة. إليك كيفية القيام بذلك:

```csharp
// حدد الشريحة التي تريد تكرارها (يبدأ الفهرس من 0)
ISlide sourceSlide = presentation.Slides[0];

// استنساخ الشريحة المحددة
ISlide duplicatedSlide = presentation.Slides.InsertClone(1, sourceSlide);
```

في هذا المثال، نقوم بمضاعفة الشريحة الأولى وإدراج الشريحة المكررة في الفهرس 1 (الموضع 2).

## الخطوة 4: إضافة الشريحة المكررة إلى النهاية

الآن وقد أصبح لدينا شريحة مكررة، لنُضيفها إلى نهاية العرض التقديمي. يمكنك استخدام الكود التالي:

```csharp
// أضف الشريحة المكررة إلى نهاية العرض التقديمي
presentation.Slides.AddClone(duplicatedSlide);
```

تضيف مقتطفات التعليمات البرمجية هذه الشريحة المكررة إلى نهاية العرض التقديمي.

## الخطوة 5: حفظ العرض التقديمي المعدّل

بعد إضافة الشريحة المكررة، علينا حفظ العرض التقديمي المُعدَّل. إليك الطريقة:

```csharp
// حفظ العرض التقديمي المعدل
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

يستبدل `"modified-presentation.pptx"` مع الاسم المطلوب للعرض التقديمي المعدل.

## خاتمة

في هذا الدليل، استكشفنا كيفية نسخ شريحة وإضافتها إلى نهاية عرض تقديمي موجود في PowerPoint باستخدام Aspose.Slides لـ .NET. تُبسّط هذه المكتبة الفعّالة عملية العمل مع العروض التقديمية برمجيًا، مُقدّمةً مجموعة واسعة من الميزات لمهام مُختلفة.

## الأسئلة الشائعة

### كيف يمكنني الحصول على Aspose.Slides لـ .NET؟

يمكنك الحصول على مكتبة Aspose.Slides لـ .NET من [رابط التحميل](https://releases.aspose.com/slides/net/)تأكد من اتباع تعليمات التثبيت المقدمة على الموقع الإلكتروني.

### هل يمكنني تكرار شرائح متعددة في وقت واحد؟

نعم، يمكنك نسخ عدة شرائح دفعةً واحدةً عن طريق تكرارها ونسخها حسب الحاجة. عدّل الكود بما يتناسب مع متطلباتك.

### هل استخدام Aspose.Slides لـ .NET مجاني؟

لا، Aspose.Slides لـ .NET هي مكتبة تجارية تتطلب ترخيصًا صالحًا للاستخدام. يمكنك الاطلاع على تفاصيل الأسعار على موقع Aspose الإلكتروني.

### هل يدعم Aspose.Slides تنسيقات الملفات الأخرى؟

نعم، يدعم Aspose.Slides تنسيقات PowerPoint متنوعة، بما في ذلك PPT وPPTX وPPS وغيرها. راجع الوثائق للاطلاع على قائمة كاملة بالتنسيقات المدعومة.

### هل يمكنني تعديل محتوى الشريحة باستخدام Aspose.Slides؟

بالتأكيد! يتيح لك Aspose.Slides ليس فقط نسخ الشرائح، بل أيضًا معالجة محتواها، مثل النصوص والصور والأشكال والرسوم المتحركة، برمجيًا.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}