---
title: الرسوم المتحركة للشرائح الرئيسية باستخدام Aspose.Slides لـ .NET
linktitle: التحكم في الرسوم المتحركة للشرائح في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: ارفع مستوى عروضك التقديمية باستخدام Aspose.Slides لـ .NET! تعلم كيفية التحكم في الرسوم المتحركة للشرائح دون عناء. قم بتنزيل المكتبة الآن!
weight: 10
url: /ar/net/slide-animation-control/slide-animation-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الرسوم المتحركة للشرائح الرئيسية باستخدام Aspose.Slides لـ .NET

## مقدمة
يمكن أن يؤدي تحسين عروضك التقديمية من خلال شرائح الرسوم المتحركة الجذابة إلى زيادة التأثير الإجمالي على جمهورك بشكل كبير. في هذا البرنامج التعليمي، سنستكشف كيفية التحكم في الرسوم المتحركة للشرائح باستخدام Aspose.Slides لـ .NET. Aspose.Slides هي مكتبة قوية تتيح المعالجة السلسة لعروض PowerPoint التقديمية في بيئة .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1.  Aspose.Slides لـ .NET Library: قم بتنزيل المكتبة وتثبيتها من[صفحة التحميل](https://releases.aspose.com/slides/net/).
2.  دليل المستندات: قم بإنشاء دليل لتخزين ملفات العرض التقديمي الخاص بك. تحديث`dataDir` متغير في مقتطف الشفرة مع المسار إلى دليل المستند الخاص بك.
## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء الضرورية في بداية ملف .NET الخاص بك:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides.SlideShow;
```
الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: إنشاء مثيل العرض التقديمي
 إنشاء مثيل`Presentation` فئة لتمثيل ملف العرض التقديمي الخاص بك:
```csharp
using (Presentation pres = new Presentation(dataDir + "BetterSlideTransitions.pptx"))
{
    // يتم وضع رمز الرسوم المتحركة للشرائح هنا
}
```
## الخطوة 2: تطبيق انتقال نوع الدائرة
قم بتطبيق انتقال نوع الدائرة على الشريحة الأولى:
```csharp
pres.Slides[0].SlideShowTransition.Type = TransitionType.Circle;
```
اضبط وقت الانتقال على 3 ثوانٍ:
```csharp
pres.Slides[0].SlideShowTransition.AdvanceOnClick = true;
pres.Slides[0].SlideShowTransition.AdvanceAfterTime = 3000;
```
## الخطوة 3: تطبيق انتقال نوع المشط
قم بتطبيق انتقال نوع المشط على الشريحة الثانية:
```csharp
pres.Slides[1].SlideShowTransition.Type = TransitionType.Comb;
```
اضبط وقت الانتقال على 5 ثوانٍ:
```csharp
pres.Slides[1].SlideShowTransition.AdvanceOnClick = true;
pres.Slides[1].SlideShowTransition.AdvanceAfterTime = 5000;
```
## الخطوة 4: تطبيق انتقال نوع التكبير
تطبيق انتقال نوع التكبير/التصغير على الشريحة الثالثة:
```csharp
pres.Slides[2].SlideShowTransition.Type = TransitionType.Zoom;
```
اضبط وقت الانتقال على 7 ثوانٍ:
```csharp
pres.Slides[2].SlideShowTransition.AdvanceOnClick = true;
pres.Slides[2].SlideShowTransition.AdvanceAfterTime = 7000;
```
## الخطوة 5: احفظ العرض التقديمي
قم بكتابة العرض التقديمي المعدل مرة أخرى إلى القرص:
```csharp
pres.Save(dataDir + "SampleTransition_out.pptx", SaveFormat.Pptx);
```
لقد نجحت الآن في التحكم في الرسوم المتحركة للشرائح باستخدام Aspose.Slides لـ .NET!
## خاتمة
يضيف تحريك الشرائح في عروضك التقديمية لمسة ديناميكية، مما يجعل المحتوى الخاص بك أكثر جاذبية. مع Aspose.Slides for .NET، تصبح العملية واضحة ومباشرة، مما يسمح لك بإنشاء عروض تقديمية جذابة دون عناء.
## الأسئلة الشائعة
### هل يمكنني تخصيص تأثيرات الانتقال بشكل أكبر؟
 نعم، يوفر Aspose.Slides نطاقًا واسعًا من أنواع الانتقال وخصائص إضافية للتخصيص. الرجوع إلى[توثيق](https://reference.aspose.com/slides/net/) للتفاصيل.
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك استكشاف Aspose.Slides باستخدام[تجربة مجانية](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
### كيف أحصل على ترخيص مؤقت؟
 يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء Aspose.Slides لـ .NET؟
 شراء المكتبة[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
