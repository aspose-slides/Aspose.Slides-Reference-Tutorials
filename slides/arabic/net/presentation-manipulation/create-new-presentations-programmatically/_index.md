---
title: إنشاء عروض تقديمية جديدة برمجياً
linktitle: إنشاء عروض تقديمية جديدة برمجياً
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء العروض التقديمية برمجيًا باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع الكود المصدري للتشغيل الآلي الفعال.
weight: 10
url: /ar/net/presentation-manipulation/create-new-presentations-programmatically/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


إذا كنت تتطلع إلى إنشاء عروض تقديمية برمجيًا في .NET، فإن Aspose.Slides for .NET هي أداة قوية تساعدك على تحقيق هذه المهمة بكفاءة. سيرشدك هذا البرنامج التعليمي خطوة بخطوة خلال عملية إنشاء عروض تقديمية جديدة باستخدام كود المصدر المقدم.

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة قوية تسمح للمطورين بالعمل مع عروض PowerPoint التقديمية برمجياً. سواء كنت بحاجة إلى إنشاء تقارير، أو أتمتة العروض التقديمية، أو التعامل مع الشرائح، فإن Aspose.Slides يوفر مجموعة واسعة من الميزات لتسهيل مهمتك.

## الخطوة 1: إعداد بيئتك

قبل أن نتعمق في التعليمات البرمجية، ستحتاج إلى إعداد بيئة التطوير الخاصة بك. تأكد من أن لديك المتطلبات الأساسية التالية:

- Visual Studio أو أي بيئة تطوير .NET.
-  Aspose.Slides لمكتبة .NET (يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/)).

## الخطوة 2: إنشاء عرض تقديمي

لنبدأ بإنشاء عرض تقديمي جديد باستخدام الكود التالي:

```csharp
// إنشاء عرض تقديمي
Presentation pres = new Presentation();
```

يقوم هذا الرمز بتهيئة كائن عرض تقديمي جديد، والذي يعمل كأساس لملف PowerPoint الخاص بك.

## الخطوة 3: إضافة شريحة عنوان

في معظم العروض التقديمية، تكون الشريحة الأولى عبارة عن شريحة عنوان. إليك كيفية إضافة واحدة:

```csharp
// أضف شريحة العنوان
Slide slide = pres.AddTitleSlide();
```

يضيف هذا الرمز شريحة عنوان إلى العرض التقديمي الخاص بك.

## الخطوة 4: تحديد العنوان والعنوان الفرعي

الآن، لنقم بتعيين العنوان والعنوان الفرعي لشريحة العنوان الخاصة بك:

```csharp
// قم بتعيين نص العنوان
((TextHolder)slide.Placeholders[0]).Text = "Slide Title Heading";

// قم بتعيين نص الترجمة
((TextHolder)slide.Placeholders[1]).Text = "Slide Title Sub-Heading";
```

استبدل "عنوان عنوان الشريحة" و"العنوان الفرعي لعنوان الشريحة" بالعناوين التي تريدها.

## الخطوة 5: حفظ العرض التقديمي الخاص بك

أخيرًا، لنحفظ عرضك التقديمي في ملف:

```csharp
// كتابة الإخراج إلى القرص
pres.Write("outAsposeSlides.ppt");
```

يحفظ هذا الرمز العرض التقديمي الخاص بك باسم "outAsposeSlides.ppt" في دليل المشروع الخاص بك.

## خاتمة

تهانينا! لقد قمت للتو بإنشاء عرض تقديمي لـ PowerPoint برمجيًا باستخدام Aspose.Slides لـ .NET. تمنحك هذه المكتبة القوية المرونة اللازمة لأتمتة عروضك التقديمية وتخصيصها بسهولة.

الآن، يمكنك البدء في دمج هذا الرمز في مشاريع .NET الخاصة بك لإنشاء عروض تقديمية ديناميكية مصممة خصيصًا لتلبية احتياجاتك الخاصة.

## الأسئلة الشائعة

1. ### هل Aspose.Slides لـ .NET مجاني للاستخدام؟
    لا، Aspose.Slides for .NET هي مكتبة تجارية. يمكنك العثور على معلومات التسعير والترخيص[هنا](https://purchase.aspose.com/buy).

2. ### هل أحتاج إلى أي أذونات خاصة لاستخدام Aspose.Slides لـ .NET في مشاريعي؟
    ستحتاج إلى ترخيص صالح لاستخدام Aspose.Slides لـ .NET. يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) للتقييم.

3. ### أين يمكنني العثور على دعم لـ Aspose.Slides لـ .NET؟
    للحصول على المساعدة الفنية والمناقشات، يمكنك زيارة منتدى Aspose.Slides[هنا](https://forum.aspose.com/).

4. ### هل يمكنني تجربة Aspose.Slides لـ .NET قبل الشراء؟
    نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ .NET[هنا](https://releases.aspose.com/). الإصدار التجريبي له قيود، لذا تأكد من التحقق مما إذا كان يلبي متطلباتك.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
