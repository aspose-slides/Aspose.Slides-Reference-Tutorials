---
"description": "تعلّم كيفية الحفاظ على الخطوط الأصلية أثناء تحويل العروض التقديمية إلى HTML باستخدام Aspose.Slides لـ .NET. تمتع بتناسق الخطوط وتأثيرها البصري بسلاسة."
"linktitle": "الحفاظ على الخطوط الأصلية - تحويل العرض التقديمي إلى HTML"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "الحفاظ على الخطوط الأصلية - تحويل العرض التقديمي إلى HTML"
"url": "/ar/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الحفاظ على الخطوط الأصلية - تحويل العرض التقديمي إلى HTML


في هذا الدليل الشامل، سنشرح لك عملية الحفاظ على الخطوط الأصلية عند تحويل عرض تقديمي إلى HTML باستخدام Aspose.Slides لـ .NET. سنزودك بشيفرة المصدر C# اللازمة، وسنشرح كل خطوة بالتفصيل. بنهاية هذا البرنامج التعليمي، ستتمكن من ضمان تطابق الخطوط في مستند HTML المُحوّل مع العرض التقديمي الأصلي.

## 1. المقدمة

عند تحويل عروض PowerPoint التقديمية إلى HTML، من الضروري الحفاظ على الخطوط الأصلية لضمان التناسق البصري للمحتوى. يوفر Aspose.Slides for .NET حلاً فعالاً لتحقيق ذلك. في هذا البرنامج التعليمي، سنرشدك خلال الخطوات اللازمة للحفاظ على الخطوط الأصلية أثناء عملية التحويل.

## 2. المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio على جهازك.
- تمت إضافة مكتبة Aspose.Slides لـ .NET إلى مشروعك.

## 3. إعداد مشروعك

للبدء، قم بإنشاء مشروع جديد في Visual Studio وأضف مكتبة Aspose.Slides for .NET كمرجع.

## 4. تحميل العرض التقديمي

استخدم الكود التالي لتحميل عرض PowerPoint الخاص بك:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // الكود الخاص بك هنا
}
```

يستبدل `"Your Document Directory"` مع المسار إلى ملف العرض التقديمي الخاص بك.

## 5. استبعاد الخطوط الافتراضية

لاستبعاد الخطوط الافتراضية مثل Calibri و Arial، استخدم الكود التالي:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

يمكنك تخصيص هذه القائمة حسب الحاجة.

## 6. تضمين جميع الخطوط

بعد ذلك، سنُضمّن جميع الخطوط في مستند HTML. هذا يضمن الحفاظ على الخطوط الأصلية. استخدم الكود التالي:

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

يستبدل `"output.html"` مع اسم ملف الإخراج المطلوب.

## 8. الخاتمة

في هذا البرنامج التعليمي، شرحنا كيفية الحفاظ على الخطوط الأصلية عند تحويل عرض تقديمي من PowerPoint إلى HTML باستخدام Aspose.Slides لـ .NET. باتباع هذه الخطوات، يمكنك ضمان الحفاظ على سلامة عرضك التقديمي الأصلي من حيث المظهر.

## 9. الأسئلة الشائعة

### س1: هل يمكنني تخصيص قائمة الخطوط المستبعدة؟

نعم، يمكنك ذلك. عدّل `fontNameExcludeList` مصفوفة لتضمين أو استبعاد خطوط معينة وفقًا لمتطلباتك.

### س2: ماذا لو لم أرغب في تضمين كافة الخطوط؟

إذا كنت ترغب في تضمين خطوط محددة فقط، يمكنك تعديل الكود وفقًا لذلك. راجع وثائق Aspose.Slides لـ .NET لمزيد من التفاصيل.

### س3: هل هناك أي متطلبات ترخيص لاستخدام Aspose.Slides لـ .NET؟

نعم، قد تحتاج إلى ترخيص صالح لاستخدام Aspose.Slides لـ .NET في مشاريعك. راجع موقع Aspose الإلكتروني للاطلاع على معلومات الترخيص.

### س4: هل يمكنني تحويل تنسيقات الملفات الأخرى إلى HTML باستخدام Aspose.Slides لـ .NET؟

يُركّز Aspose.Slides for .NET بشكل أساسي على عروض PowerPoint التقديمية. لتحويل تنسيقات ملفات أخرى إلى HTML، قد تحتاج إلى استكشاف منتجات Aspose الأخرى المُصمّمة خصيصًا لهذه التنسيقات.

### س5: أين يمكنني الوصول إلى الموارد والدعم الإضافي؟

يمكنك العثور على المزيد من الوثائق والبرامج التعليمية والدعم على موقع Aspose الإلكتروني. تفضل بزيارة [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/) لمزيد من المعلومات التفصيلية.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}