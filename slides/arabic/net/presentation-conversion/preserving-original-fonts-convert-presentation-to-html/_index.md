---
title: الحفاظ على الخطوط الأصلية - تحويل العرض التقديمي إلى HTML
linktitle: الحفاظ على الخطوط الأصلية - تحويل العرض التقديمي إلى HTML
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية الحفاظ على الخطوط الأصلية أثناء تحويل العروض التقديمية إلى HTML باستخدام Aspose.Slides for .NET. ضمان اتساق الخط والتأثير البصري دون عناء.
weight: 14
url: /ar/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


في هذا الدليل الشامل، سنرشدك خلال عملية الحفاظ على الخطوط الأصلية عند تحويل العرض التقديمي إلى HTML باستخدام Aspose.Slides for .NET. سنزودك بكود مصدر C# الضروري وسنشرح كل خطوة بالتفصيل. بحلول نهاية هذا البرنامج التعليمي، ستتمكن من التأكد من أن الخطوط الموجودة في مستند HTML المحول تظل مطابقة للعرض التقديمي الأصلي.

## 1 المقدمة

عند تحويل عروض PowerPoint التقديمية إلى HTML، من الضروري الحفاظ على الخطوط الأصلية لضمان الاتساق المرئي للمحتوى الخاص بك. يوفر Aspose.Slides for .NET حلاً قويًا لتحقيق ذلك. في هذا البرنامج التعليمي، سنرشدك خلال الخطوات اللازمة للحفاظ على الخطوط الأصلية أثناء عملية التحويل.

## 2. المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio على جهازك.
- تمت إضافة Aspose.Slides لمكتبة .NET إلى مشروعك.

## 3. إعداد مشروعك

للبدء، قم بإنشاء مشروع جديد في Visual Studio وأضف Aspose.Slides لمكتبة .NET كمرجع.

## 4. تحميل العرض التقديمي

استخدم الكود التالي لتحميل عرض PowerPoint التقديمي الخاص بك:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // الرمز الخاص بك هنا
}
```

 يستبدل`"Your Document Directory"` مع المسار إلى ملف العرض التقديمي الخاص بك.

## 5. باستثناء الخطوط الافتراضية

لاستبعاد الخطوط الافتراضية مثل Calibri وArial، استخدم الكود التالي:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

يمكنك تخصيص هذه القائمة حسب الحاجة.

## 6. تضمين كافة الخطوط

بعد ذلك، سنقوم بتضمين كافة الخطوط في مستند HTML. وهذا يضمن الحفاظ على الخطوط الأصلية. استخدم الكود التالي:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. الحفظ بصيغة HTML

الآن، احفظ العرض التقديمي كمستند HTML مع الخطوط المضمنة:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 يستبدل`"output.html"` مع اسم ملف الإخراج المطلوب.

## 8. الاستنتاج

لقد أوضحنا في هذا البرنامج التعليمي كيفية الحفاظ على الخطوط الأصلية عند تحويل عرض PowerPoint التقديمي إلى HTML باستخدام Aspose.Slides for .NET. باتباع هذه الخطوات، يمكنك التأكد من أن مستند HTML المحول يحافظ على التكامل المرئي للعرض التقديمي الأصلي.

## 9. الأسئلة الشائعة

### س1: هل يمكنني تخصيص قائمة الخطوط المستبعدة؟

 نعم يمكنك ذلك. تعديل`fontNameExcludeList`مجموعة لتضمين أو استبعاد خطوط معينة وفقًا لمتطلباتك.

### س2: ماذا لو لم أرغب في تضمين كافة الخطوط؟

إذا كنت تريد تضمين خطوط محددة فقط، فيمكنك تعديل التعليمات البرمجية وفقًا لذلك. راجع Aspose.Slides للحصول على وثائق .NET لمزيد من التفاصيل.

### س3: هل هناك أي متطلبات ترخيص لاستخدام Aspose.Slides لـ .NET؟

نعم، قد تحتاج إلى ترخيص صالح لاستخدام Aspose.Slides for .NET في مشاريعك. ارجع إلى موقع Aspose للحصول على معلومات الترخيص.

### س4: هل يمكنني تحويل تنسيقات ملفات أخرى إلى HTML باستخدام Aspose.Slides لـ .NET؟

يركز Aspose.Slides for .NET بشكل أساسي على عروض PowerPoint التقديمية. لتحويل تنسيقات ملفات أخرى إلى HTML، قد تحتاج إلى استكشاف منتجات Aspose الأخرى المصممة خصيصًا لتلك التنسيقات.

### س5: أين يمكنني الوصول إلى الموارد الإضافية والدعم؟

 يمكنك العثور على المزيد من الوثائق والبرامج التعليمية والدعم على موقع Aspose. يزور[Aspose.Slides لتوثيق .NET](https://reference.aspose.com/slides/net/) للحصول على معلومات مفصلة.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
