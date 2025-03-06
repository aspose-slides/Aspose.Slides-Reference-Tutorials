---
title: تحويل العروض التقديمية إلى HTML باستخدام الخطوط المضمنة
linktitle: تحويل العروض التقديمية إلى HTML باستخدام الخطوط المضمنة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بتحويل عروض PowerPoint التقديمية إلى HTML باستخدام الخطوط المضمنة باستخدام Aspose.Slides لـ .NET. الحفاظ على الأصالة بسلاسة.
weight: 13
url: /ar/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


في العصر الرقمي الحالي، أصبحت مشاركة العروض التقديمية والمستندات عبر الإنترنت ممارسة شائعة. ومع ذلك، أحد التحديات التي تظهر غالبًا هو ضمان عرض الخطوط بشكل صحيح عند تحويل العروض التقديمية إلى HTML. سيرشدك هذا البرنامج التعليمي خطوة بخطوة خلال عملية استخدام Aspose.Slides for .NET لتحويل العروض التقديمية إلى HTML باستخدام الخطوط المضمنة، مما يضمن ظهور مستنداتك تمامًا كما كنت تريدها.

## مقدمة إلى Aspose.Slides لـ .NET

قبل أن نتعمق في البرنامج التعليمي، دعنا نقدم بإيجاز Aspose.Slides for .NET. إنها مكتبة قوية تسمح للمطورين بالعمل مع عروض PowerPoint التقديمية في تطبيقات .NET. باستخدام Aspose.Slides، يمكنك إنشاء ملفات PowerPoint وتعديلها وتحويلها برمجيًا.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Slides for .NET: يجب أن تكون مكتبة Aspose.Slides مثبتة في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## الخطوة 1: قم بإعداد مشروعك

1. أنشئ مشروعًا جديدًا أو افتح مشروعًا موجودًا في بيئة التطوير .NET المفضلة لديك.

2. أضف مرجعًا إلى مكتبة Aspose.Slides في مشروعك.

3. قم باستيراد مساحات الأسماء الضرورية في التعليمات البرمجية الخاصة بك:

   ```csharp
   using Aspose.Slides;
   ```

## الخطوة 2: قم بتحميل العرض التقديمي الخاص بك

 للبدء، تحتاج إلى تحميل العرض التقديمي الذي تريد تحويله إلى HTML. يستبدل`"Your Document Directory"` مع الدليل الفعلي الذي يوجد به ملف العرض التقديمي الخاص بك.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // الكود الخاص بك يذهب هنا
}
```

## الخطوة 3: استبعاد خطوط العرض الافتراضية

في هذه الخطوة، يمكنك تحديد أي خطوط عرض افتراضية تريد استبعادها من التضمين. يمكن أن يساعد هذا في تحسين حجم ملف HTML الناتج.

```csharp
string[] fontNameExcludeList = { };
```

## الخطوة 4: اختر وحدة تحكم HTML

الآن، لديك خياران لتضمين الخطوط في HTML:

### الخيار 1: تضمين كافة الخطوط

 لتضمين كافة الخطوط المستخدمة في العرض التقديمي، استخدم الأمر`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### الخيار 2: ربط كافة الخطوط

 للارتباط بجميع الخطوط المستخدمة في العرض التقديمي، استخدم`LinkAllFontsHtmlController`. يجب عليك تحديد الدليل الذي توجد به الخطوط على نظامك.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## الخطوة 5: تحديد خيارات HTML

 يخترع`HtmlOptions` الكائن وقم بتعيين منسق HTML على الذي حددته في الخطوة السابقة.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // استخدم embedFontsController لتضمين كافة الخطوط
};
```

## الخطوة 6: احفظ بتنسيق HTML

 وأخيرًا، احفظ العرض التقديمي كملف HTML. يمكنك اختيار أي منهما`SaveFormat.Html` أو`SaveFormat.Html5` اعتمادا على الاحتياجات الخاصة بك.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## خاتمة

تهانينا! لقد نجحت في تحويل العرض التقديمي الخاص بك إلى HTML باستخدام الخطوط المضمنة باستخدام Aspose.Slides for .NET. وهذا يضمن أن الخطوط الخاصة بك سيتم عرضها بشكل صحيح عند مشاركة العروض التقديمية الخاصة بك عبر الإنترنت.

الآن، يمكنك بسهولة مشاركة عروضك التقديمية ذات التنسيق الجميل بكل ثقة، مع العلم أن جمهورك سوف يراها تمامًا كما تريد.

 لمزيد من المعلومات ومراجع API التفصيلية، راجع[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).

## الأسئلة الشائعة

### 1. هل يمكنني تحويل عروض PowerPoint التقديمية إلى HTML باستخدام Aspose.Slides لـ .NET في الوضع الدفعي؟

نعم، يمكنك تحويل عروض تقديمية متعددة إلى HTML دفعةً واحدة باستخدام Aspose.Slides لـ .NET من خلال تكرار ملفات العرض التقديمي وتطبيق عملية التحويل على كل منها.

### 2. هل هناك طريقة لتخصيص مظهر مخرجات HTML؟

بالتأكيد! يوفر Aspose.Slides for .NET خيارات متنوعة لتخصيص مظهر وتنسيق مخرجات HTML، مثل ضبط الألوان والخطوط والتخطيط.

### 3. هل هناك أي قيود على تضمين الخطوط في HTML باستخدام Aspose.Slides لـ .NET؟

على الرغم من أن Aspose.Slides for .NET يوفر إمكانات ممتازة لدمج الخطوط، ضع في اعتبارك أن حجم ملفات HTML قد يزيد عند تضمين الخطوط. تأكد من تحسين خيارات الخطوط الخاصة بك لاستخدام الويب.

### 4. هل يمكنني تحويل عروض PowerPoint التقديمية إلى تنسيقات أخرى باستخدام Aspose.Slides لـ .NET؟

نعم، يدعم Aspose.Slides for .NET نطاقًا واسعًا من تنسيقات الإخراج، بما في ذلك PDF والصور والمزيد. يمكنك بسهولة تحويل العروض التقديمية الخاصة بك إلى التنسيق الذي تختاره.

### 5. أين يمكنني العثور على موارد إضافية ودعم لـ Aspose.Slides لـ .NET؟

 يمكنك الوصول إلى ثروة من الموارد، بما في ذلك الوثائق، على الموقع[Aspose.Slides لمرجع .NET API](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
