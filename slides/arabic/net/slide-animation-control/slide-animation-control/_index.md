---
"description": "ارتقِ بعروضك التقديمية مع Aspose.Slides لـ .NET! تعلم كيفية التحكم في تحريك الشرائح بسهولة. حمّل المكتبة الآن!"
"linktitle": "التحكم في تحريك الشرائح في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "رسوم متحركة للشرائح الرئيسية باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/slide-animation-control/slide-animation-control/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# رسوم متحركة للشرائح الرئيسية باستخدام Aspose.Slides لـ .NET

## مقدمة
إن تحسين عروضك التقديمية برسوم متحركة جذابة للشرائح يُعزز بشكل كبير من تأثيرها على جمهورك. في هذا البرنامج التعليمي، سنستكشف كيفية التحكم في الرسوم المتحركة للشرائح باستخدام Aspose.Slides لـ .NET. Aspose.Slides مكتبة فعّالة تُمكّن من التعامل بسلاسة مع عروض PowerPoint التقديمية في بيئة .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي في مكانه:
1. Aspose.Slides لمكتبة .NET: قم بتنزيل المكتبة وتثبيتها من [صفحة التحميل](https://releases.aspose.com/slides/net/).
2. دليل المستندات: أنشئ دليلاً لتخزين ملفات العرض التقديمي. حدّث `dataDir` متغير في مقتطف التعليمات البرمجية مع المسار إلى دليل المستند الخاص بك.
## استيراد مساحات الأسماء
تأكد من استيراد المساحات الأساسية اللازمة في بداية ملف .NET الخاص بك:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides.SlideShow;
```
الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: إنشاء نسخة العرض التقديمي
إنشاء مثيل `Presentation` الفئة التي تمثل ملف العرض التقديمي الخاص بك:
```csharp
using (Presentation pres = new Presentation(dataDir + "BetterSlideTransitions.pptx"))
{
    // يظهر رمز الرسوم المتحركة للشرائح هنا
}
```
## الخطوة 2: تطبيق انتقال نوع الدائرة
قم بتطبيق انتقال من نوع الدائرة على الشريحة الأولى:
```csharp
pres.Slides[0].SlideShowTransition.Type = TransitionType.Circle;
```
ضبط وقت الانتقال إلى 3 ثوان:
```csharp
pres.Slides[0].SlideShowTransition.AdvanceOnClick = true;
pres.Slides[0].SlideShowTransition.AdvanceAfterTime = 3000;
```
## الخطوة 3: تطبيق انتقال نوع المشط
قم بتطبيق انتقال من نوع المشط على الشريحة الثانية:
```csharp
pres.Slides[1].SlideShowTransition.Type = TransitionType.Comb;
```
ضبط وقت الانتقال إلى 5 ثوانٍ:
```csharp
pres.Slides[1].SlideShowTransition.AdvanceOnClick = true;
pres.Slides[1].SlideShowTransition.AdvanceAfterTime = 5000;
```
## الخطوة 4: تطبيق انتقال نوع التكبير
قم بتطبيق انتقال نوع التكبير على الشريحة الثالثة:
```csharp
pres.Slides[2].SlideShowTransition.Type = TransitionType.Zoom;
```
ضبط وقت الانتقال إلى 7 ثوان:
```csharp
pres.Slides[2].SlideShowTransition.AdvanceOnClick = true;
pres.Slides[2].SlideShowTransition.AdvanceAfterTime = 7000;
```
## الخطوة 5: حفظ العرض التقديمي
اكتب العرض التقديمي المعدل مرة أخرى على القرص:
```csharp
pres.Save(dataDir + "SampleTransition_out.pptx", SaveFormat.Pptx);
```
لقد قمت الآن بالتحكم بنجاح في رسوم متحركة للشرائح باستخدام Aspose.Slides لـ .NET!
## خاتمة
يُضفي تحريك الشرائح في عروضك التقديمية لمسةً ديناميكية، مما يجعل محتواك أكثر جاذبية. مع Aspose.Slides لـ .NET، تُصبح العملية سهلة، مما يُتيح لك إنشاء عروض تقديمية جذابة بصريًا دون عناء.
## الأسئلة الشائعة
### هل يمكنني تخصيص تأثيرات الانتقال بشكل أكبر؟
نعم، يوفر Aspose.Slides مجموعة واسعة من أنواع الانتقالات وخصائص إضافية للتخصيص. راجع [التوثيق](https://reference.aspose.com/slides/net/) لمزيد من التفاصيل.
### هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك استكشاف Aspose.Slides باستخدام [نسخة تجريبية مجانية](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
### كيف أحصل على ترخيص مؤقت؟
يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء Aspose.Slides لـ .NET؟
شراء المكتبة [هنا](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}