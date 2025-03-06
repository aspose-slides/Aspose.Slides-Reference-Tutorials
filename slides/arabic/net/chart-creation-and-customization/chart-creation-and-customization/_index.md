---
title: إنشاء المخطط وتخصيصه في Aspose.Slides
linktitle: إنشاء المخطط وتخصيصه في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء المخططات وتخصيصها في PowerPoint باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة لإنشاء عروض تقديمية ديناميكية.
weight: 10
url: /ar/net/chart-creation-and-customization/chart-creation-and-customization/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء المخطط وتخصيصه في Aspose.Slides


## مقدمة

في عالم عرض البيانات، تلعب الوسائل البصرية دورًا حاسمًا في نقل المعلومات بشكل فعال. تُستخدم عروض PowerPoint التقديمية على نطاق واسع لهذا الغرض، وتعد Aspose.Slides for .NET مكتبة قوية تتيح لك إنشاء الشرائح وتخصيصها برمجيًا. في هذا الدليل التفصيلي، سنستكشف كيفية إنشاء المخططات وتخصيصها باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية

قبل أن نتعمق في إنشاء المخططات وتخصيصها، ستحتاج إلى توفر المتطلبات الأساسية التالية:

1.  Aspose.Slides for .NET: تأكد من تثبيت مكتبة Aspose.Slides for .NET. يمكنك تنزيله من[صفحة التحميل](https://releases.aspose.com/slides/net/).

2. ملف العرض التقديمي: قم بإعداد ملف عرض تقديمي لـ PowerPoint حيث تريد إضافة المخططات وتخصيصها.

الآن، دعونا نقسم العملية إلى خطوات متعددة للحصول على برنامج تعليمي شامل.

## الخطوة 1: إضافة شرائح التخطيط إلى العرض التقديمي

```csharp
string FilePath = @"..\..\..\Sample Files\";
string FileName = FilePath + "Adding Layout Slides.pptx";

using (Presentation p = new Presentation(FileName))
{
    // حاول البحث حسب نوع شريحة التخطيط
    IMasterLayoutSlideCollection layoutSlides = p.Masters[0].LayoutSlides;
    ILayoutSlide layoutSlide =
        layoutSlides.GetByType(SlideLayoutType.TitleAndObject) ??
        layoutSlides.GetByType(SlideLayoutType.Title);

    if (layoutSlide == null)
    {
        //الموقف عندما لا يحتوي العرض التقديمي على نوع ما من التخطيطات.
        // ...

        // إضافة شريحة فارغة مع شريحة التخطيط المضافة
        p.Slides.InsertEmptySlide(0, layoutSlide);

        // حفظ العرض التقديمي
        p.Save(FileName, SaveFormat.Pptx);
    }
}
```

في هذه الخطوة، نقوم بإنشاء عرض تقديمي جديد، والبحث عن شريحة تخطيط مناسبة، وإضافة شريحة فارغة باستخدام Aspose.Slides.

## الخطوة 2: احصل على مثال للعنصر النائب الأساسي

```csharp
string presentationName = Path.Combine("Your Document Directory", "placeholder.pptx");

using (Presentation presentation = new Presentation(presentationName))
{
    ISlide slide = presentation.Slides[0];
    IShape shape = slide.Shapes[0];

    // ...

    IShape masterShape = layoutShape.GetBasePlaceholder();

    // ...
}
```

تتضمن هذه الخطوة فتح عرض تقديمي موجود واستخراج العناصر النائبة الأساسية، مما يسمح لك بالعمل مع العناصر النائبة في الشرائح الخاصة بك.

## الخطوة 3: إدارة الرأس والتذييل في الشرائح

```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation(dataDir + "presentation.ppt"))
{
    IBaseSlideHeaderFooterManager headerFooterManager = presentation.Slides[0].HeaderFooterManager;

    // ...

    presentation.Save(dataDir + "Presentation.ppt", SaveFormat.Ppt);
}
```

في هذه الخطوة الأخيرة، نقوم بإدارة الرؤوس والتذييلات في الشرائح عن طريق تبديل رؤيتها وتعيين النص وتخصيص العناصر النائبة للتاريخ والوقت.

الآن بعد أن قمنا بتقسيم كل مثال إلى خطوات متعددة، يمكنك استخدام Aspose.Slides for .NET لإنشاء عروض PowerPoint التقديمية وتخصيصها وإدارتها برمجيًا. توفر هذه المكتبة القوية مجموعة واسعة من الإمكانات، مما يتيح لك إنشاء عروض تقديمية جذابة وغنية بالمعلومات بسهولة.

## خاتمة

يؤدي إنشاء المخططات وتخصيصها في Aspose.Slides لـ .NET إلى فتح عالم من الإمكانيات للعروض التقديمية الديناميكية والمعتمدة على البيانات. باستخدام هذه الإرشادات خطوة بخطوة، يمكنك تسخير الإمكانات الكاملة لهذه المكتبة لتحسين عروض PowerPoint التقديمية ونقل المعلومات بشكل فعال.

## الأسئلة الشائعة

### ما هي إصدارات .NET التي يدعمها Aspose.Slides لـ .NET؟
يدعم Aspose.Slides for .NET نطاقًا واسعًا من إصدارات .NET، بما في ذلك .NET Framework و.NET Core. تحقق من الوثائق للحصول على تفاصيل محددة.

### هل يمكنني إنشاء مخططات معقدة باستخدام Aspose.Slides لـ .NET؟
نعم، يمكنك إنشاء أنواع مختلفة من المخططات، بما في ذلك المخططات الشريطية، والمخططات الدائرية، والمخططات الخطية، مع خيارات تخصيص واسعة النطاق.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من موقع Aspose[هنا](https://releases.aspose.com/).

### أين يمكنني العثور على دعم وموارد إضافية لـ Aspose.Slides لـ .NET؟
 قم بزيارة منتدى الدعم Aspose[هنا](https://forum.aspose.com/) لأية أسئلة أو مساعدة قد تحتاجها.

### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
نعم يمكنك الحصول على ترخيص مؤقت من موقع Aspose[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
