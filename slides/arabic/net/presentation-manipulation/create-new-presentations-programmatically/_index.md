---
"description": "تعلّم كيفية إنشاء عروض تقديمية برمجيًا باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع الكود المصدري لأتمتة فعّالة."
"linktitle": "إنشاء عروض تقديمية جديدة برمجيًا"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء عروض تقديمية جديدة برمجيًا"
"url": "/ar/net/presentation-manipulation/create-new-presentations-programmatically/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء عروض تقديمية جديدة برمجيًا


إذا كنت ترغب في إنشاء عروض تقديمية برمجيًا باستخدام .NET، فإن Aspose.Slides for .NET أداة فعّالة تساعدك على إنجاز هذه المهمة بكفاءة. سيرشدك هذا الدليل خطوة بخطوة خلال عملية إنشاء عروض تقديمية جديدة باستخدام شفرة المصدر المُرفقة.

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة قوية تُمكّن المطورين من العمل مع عروض PowerPoint التقديمية برمجيًا. سواءً كنتَ بحاجة إلى إنشاء تقارير، أو أتمتة العروض التقديمية، أو معالجة الشرائح، تُوفر Aspose.Slides مجموعة واسعة من الميزات لتسهيل مهمتك.

## الخطوة 1: إعداد البيئة الخاصة بك

قبل التعمق في شرح الكود، ستحتاج إلى إعداد بيئة التطوير الخاصة بك. تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio أو أي بيئة تطوير .NET.
- مكتبة Aspose.Slides لـ .NET (يمكنك تنزيلها [هنا](https://releases.aspose.com/slides/net/)).

## الخطوة 2: إنشاء عرض تقديمي

لنبدأ بإنشاء عرض تقديمي جديد باستخدام الكود التالي:

```csharp
// إنشاء عرض تقديمي
Presentation pres = new Presentation();
```

يقوم هذا الكود بتهيئة كائن عرض تقديمي جديد، والذي يعمل كأساس لملف PowerPoint الخاص بك.

## الخطوة 3: إضافة شريحة عنوان

في معظم العروض التقديمية، تكون الشريحة الأولى هي شريحة العنوان. إليك كيفية إضافة شريحة عنوان:

```csharp
// أضف شريحة العنوان
Slide slide = pres.AddTitleSlide();
```

يضيف هذا الكود شريحة عنوان إلى العرض التقديمي الخاص بك.

## الخطوة 4: تعيين العنوان والعنوان الفرعي

الآن، دعنا نحدد العنوان والعنوان الفرعي لشريحة العنوان الخاصة بك:

```csharp
// تعيين نص العنوان
((TextHolder)slide.Placeholders[0]).Text = "Slide Title Heading";

// تعيين نص الترجمة
((TextHolder)slide.Placeholders[1]).Text = "Slide Title Sub-Heading";
```

استبدل "عنوان الشريحة الرئيسي" و"العنوان الفرعي لعنوان الشريحة" بالعناوين المطلوبة.

## الخطوة 5: حفظ العرض التقديمي الخاص بك

وأخيرًا، دعنا نحفظ عرضك التقديمي في ملف:

```csharp
// كتابة الإخراج على القرص
pres.Write("outAsposeSlides.ppt");
```

يحفظ هذا الكود العرض التقديمي الخاص بك باسم "outAsposeSlides.ppt" في دليل المشروع الخاص بك.

## خاتمة

تهانينا! لقد أنشأتَ للتو عرضًا تقديميًا لبرنامج PowerPoint باستخدام Aspose.Slides لـ .NET. تمنحك هذه المكتبة القوية مرونةً لأتمتة عروضك التقديمية وتخصيصها بسهولة.

الآن، يمكنك البدء في دمج هذا الكود في مشاريع .NET الخاصة بك لإنشاء عروض تقديمية ديناميكية مصممة خصيصًا لتلبية احتياجاتك المحددة.

## الأسئلة الشائعة

1. ### هل استخدام Aspose.Slides لـ .NET مجاني؟
   لا، Aspose.Slides لـ .NET هي مكتبة تجارية. يمكنك العثور على معلومات التسعير والترخيص. [هنا](https://purchase.aspose.com/buy).

2. ### هل أحتاج إلى أي أذونات خاصة لاستخدام Aspose.Slides لـ .NET في مشاريعي؟
   ستحتاج إلى ترخيص صالح لاستخدام Aspose.Slides لـ .NET. يمكنك الحصول على ترخيص مؤقت. [هنا](https://purchase.aspose.com/temporary-license/) للتقييم.

3. ### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ .NET؟
   للحصول على المساعدة الفنية والمناقشات، يمكنك زيارة منتدى Aspose.Slides [هنا](https://forum.aspose.com/).

4. ### هل يمكنني تجربة Aspose.Slides لـ .NET قبل الشراء؟
   نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ .NET [هنا](https://releases.aspose.com/). النسخة التجريبية لها حدود، لذا تأكد من أنها تلبي متطلباتك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}