---
"description": "تعلّم كيفية نسخ شريحة من عرض تقديمي في PowerPoint وإضافتها إلى عرض آخر باستخدام Aspose.Slides لـ .NET. يوفر هذا الدليل خطوة بخطوة شفرة المصدر وتعليمات واضحة للتعامل مع الشرائح بسلاسة."
"linktitle": "تكرار الشريحة في نهاية العرض التقديمي المنفصل"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تكرار الشريحة في نهاية العرض التقديمي المنفصل"
"url": "/ar/net/slide-access-and-manipulation/clone-slide-end-of-another-presentation/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تكرار الشريحة في نهاية العرض التقديمي المنفصل


## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة تُمكّن مطوري .NET من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجيًا. توفر مجموعة واسعة من الميزات للتعامل مع الشرائح والأشكال والنصوص والصور والرسوم المتحركة وغيرها.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio.
- المعرفة الأساسية بلغة C# و.NET.
- مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).

## تحميل العروض التقديمية ومعالجتها

1. إنشاء مشروع C# جديد في Visual Studio.
2. قم بتثبيت مكتبة Aspose.Slides لـ .NET عبر NuGet.
3. استيراد مساحات الأسماء الضرورية:
   
   ```csharp
   using Aspose.Slides;
   ```

4. قم بتحميل العرض التقديمي المصدر الذي يحتوي على الشريحة التي تريد تكرارها:

   ```csharp
   using (Presentation sourcePresentation = new Presentation("source.pptx"))
   {
       // الكود الخاص بك للتلاعب بالعرض المصدر
   }
   ```

## تكرار الشريحة

1. حدد الشريحة التي تريد تكرارها استنادًا إلى فهرسها:

   ```csharp
   ISlide sourceSlide = sourcePresentation.Slides[index];
   ```

2. استنسخ الشريحة المصدر لإنشاء نسخة طبق الأصل:

   ```csharp
   ISlide replicatedSlide = sourcePresentation.Slides.AddClone(sourceSlide);
   ```

## إضافة الشريحة المنسوخة إلى عرض تقديمي آخر

1. قم بإنشاء عرض تقديمي جديد تريد إضافة الشريحة المكررة إليه:

   ```csharp
   using (Presentation targetPresentation = new Presentation())
   {
       // الكود الخاص بك للتلاعب بالعرض التقديمي المستهدف
   }
   ```

2. أضف الشريحة المكررة إلى العرض التقديمي المستهدف:

   ```csharp
   targetPresentation.Slides.AddClone(replicatedSlide);
   ```

## حفظ العرض التقديمي الناتج

1. احفظ العرض التقديمي المستهدف مع الشريحة المكررة:

   ```csharp
   targetPresentation.Save("result.pptx", SaveFormat.Pptx);
   ```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية نسخ شريحة من عرض تقديمي وإضافتها إلى نهاية عرض تقديمي آخر باستخدام Aspose.Slides لـ .NET. تُبسّط هذه المكتبة الفعّالة عملية العمل مع عروض PowerPoint التقديمية برمجيًا.

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ .NET؟

يمكنك تنزيل مكتبة Aspose.Slides لـ .NET من [هذا الرابط](https://releases.aspose.com/slides/net/)تأكد من اتباع تعليمات التثبيت الواردة في الوثائق الخاصة بها.

### هل يمكنني تكرار شرائح متعددة في وقت واحد؟

نعم، يمكنك تكرار شرائح متعددة من خلال التكرار عبر مجموعة شرائح العرض التقديمي المصدر وإضافة نسخ مكررة إلى العرض التقديمي المستهدف.

### هل Aspose.Slides for .NET متوافق مع تنسيقات PowerPoint المختلفة؟

نعم، يدعم Aspose.Slides for .NET تنسيقات PowerPoint متنوعة، بما في ذلك PPTX وPPT وPPSX وPPS وغيرها. يمكنك التحويل بسهولة بين هذه التنسيقات باستخدام المكتبة.

### هل يمكنني تعديل محتوى الشريحة المكررة قبل إضافتها إلى العرض التقديمي المستهدف؟

بالتأكيد! يمكنك تعديل محتوى الشريحة المنسوخة كأي شريحة أخرى. عدّل النصوص والصور والأشكال والعناصر الأخرى حسب الحاجة قبل إضافتها إلى العرض التقديمي المستهدف.

### هل يعمل Aspose.Slides for .NET مع الشرائح فقط؟

لا، يوفر Aspose.Slides لـ .NET إمكانيات واسعة تتجاوز الشرائح. يمكنك العمل مع الأشكال والرسوم البيانية والرسوم المتحركة، وحتى استخراج النصوص والصور من العروض التقديمية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}