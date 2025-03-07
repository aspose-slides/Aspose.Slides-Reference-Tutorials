---
title: قم بتكرار الشريحة في نهاية العرض التقديمي المنفصل
linktitle: قم بتكرار الشريحة في نهاية العرض التقديمي المنفصل
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية نسخ شريحة من عرض تقديمي لـ PowerPoint وإضافتها إلى أخرى باستخدام Aspose.Slides for .NET. يوفر هذا الدليل التفصيلي التعليمات البرمجية المصدرية والتعليمات الواضحة للتعامل السلس مع الشرائح.
weight: 17
url: /ar/net/slide-access-and-manipulation/clone-slide-end-of-another-presentation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتكرار الشريحة في نهاية العرض التقديمي المنفصل


## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة تتيح لمطوري .NET إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجيًا. فهو يوفر مجموعة واسعة من الميزات للعمل مع الشرائح والأشكال والنصوص والصور والرسوم المتحركة والمزيد.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio.
- المعرفة الأساسية بـ C# و.NET.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## تحميل العروض التقديمية ومعالجتها

1. قم بإنشاء مشروع C# جديد في Visual Studio.
2. قم بتثبيت Aspose.Slides لمكتبة .NET عبر NuGet.
3. قم باستيراد مساحات الأسماء الضرورية:
   
   ```csharp
   using Aspose.Slides;
   ```

4. قم بتحميل العرض التقديمي المصدر الذي يحتوي على الشريحة التي تريد نسخها:

   ```csharp
   using (Presentation sourcePresentation = new Presentation("source.pptx"))
   {
       // التعليمات البرمجية الخاصة بك لمعالجة العرض التقديمي المصدر
   }
   ```

## تكرار الشريحة

1. حدد الشريحة التي تريد نسخها بناءً على فهرسها:

   ```csharp
   ISlide sourceSlide = sourcePresentation.Slides[index];
   ```

2. انسخ الشريحة المصدر لإنشاء نسخة طبق الأصل:

   ```csharp
   ISlide replicatedSlide = sourcePresentation.Slides.AddClone(sourceSlide);
   ```

## إضافة الشريحة المنسوخة إلى عرض تقديمي آخر

1. قم بإنشاء عرض تقديمي جديد تريد إضافة الشريحة المنسوخة إليه:

   ```csharp
   using (Presentation targetPresentation = new Presentation())
   {
       // التعليمات البرمجية الخاصة بك لمعالجة العرض التقديمي المستهدف
   }
   ```

2. أضف الشريحة المنسوخة إلى العرض التقديمي المستهدف:

   ```csharp
   targetPresentation.Slides.AddClone(replicatedSlide);
   ```

## حفظ العرض التقديمي الناتج

1. احفظ العرض التقديمي المستهدف بالشريحة المنسوخة:

   ```csharp
   targetPresentation.Save("result.pptx", SaveFormat.Pptx);
   ```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية نسخ شريحة من عرض تقديمي وإضافتها إلى نهاية عرض تقديمي آخر باستخدام Aspose.Slides for .NET. تعمل هذه المكتبة القوية على تبسيط عملية العمل مع عروض PowerPoint التقديمية برمجياً.

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides for .NET من[هذا الرابط](https://releases.aspose.com/slides/net/)تأكد من اتباع تعليمات التثبيت المتوفرة في الوثائق الخاصة بهم.

### هل يمكنني تكرار شرائح متعددة في وقت واحد؟

نعم، يمكنك نسخ شرائح متعددة عن طريق التكرار عبر مجموعة شرائح العرض التقديمي المصدر وإضافة النسخ إلى العرض التقديمي المستهدف.

### هل يتوافق Aspose.Slides for .NET مع تنسيقات PowerPoint المختلفة؟

نعم، يدعم Aspose.Slides for .NET تنسيقات PowerPoint المتنوعة، بما في ذلك PPTX وPPT وPPSX وPPS والمزيد. يمكنك التحويل بسهولة بين هذه التنسيقات باستخدام المكتبة.

### هل يمكنني تعديل محتوى الشريحة المنسوخة قبل إضافتها إلى العرض التقديمي المستهدف؟

قطعاً! يمكنك التعامل مع محتوى الشريحة المنسوخة تمامًا مثل أي شريحة أخرى. قم بتعديل النص والصور والأشكال والعناصر الأخرى حسب الحاجة قبل إضافتها إلى العرض التقديمي المستهدف.

### هل يعمل Aspose.Slides for .NET مع الشرائح فقط؟

لا، يوفر Aspose.Slides for .NET إمكانات واسعة النطاق تتجاوز الشرائح. يمكنك العمل مع الأشكال والمخططات والرسوم المتحركة وحتى استخراج النصوص والصور من العروض التقديمية.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
