---
"description": "حوّل عروض PowerPoint التقديمية إلى HTML بخطوط مُضمنة باستخدام Aspose.Slides لـ .NET. حافظ على أصالتها بسلاسة."
"linktitle": "تحويل العروض التقديمية إلى HTML باستخدام الخطوط المضمنة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تحويل العروض التقديمية إلى HTML باستخدام الخطوط المضمنة"
"url": "/ar/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل العروض التقديمية إلى HTML باستخدام الخطوط المضمنة


في عصرنا الرقمي، أصبحت مشاركة العروض التقديمية والمستندات عبر الإنترنت ممارسة شائعة. ومع ذلك، فإن أحد التحديات التي تظهر غالبًا هو ضمان عرض الخطوط بشكل صحيح عند تحويل العروض التقديمية إلى HTML. سيرشدك هذا البرنامج التعليمي خطوة بخطوة خلال عملية استخدام Aspose.Slides for .NET لتحويل العروض التقديمية إلى HTML باستخدام خطوط مدمجة، مما يضمن ظهور مستنداتك كما تريدها تمامًا.

## مقدمة إلى Aspose.Slides لـ .NET

قبل الخوض في هذا البرنامج التعليمي، دعونا نُقدّم بإيجاز Aspose.Slides لـ .NET. إنها مكتبة فعّالة تُمكّن المطورين من العمل مع عروض PowerPoint التقديمية في تطبيقات .NET. باستخدام Aspose.Slides، يُمكنك إنشاء ملفات PowerPoint وتعديلها وتحويلها برمجيًا.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.Slides لـ .NET: يجب أن تكون مكتبة Aspose.Slides مثبتة في مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).

## الخطوة 1: إعداد مشروعك

1. قم بإنشاء مشروع جديد أو افتح مشروعًا موجودًا في بيئة تطوير .NET المفضلة لديك.

2. أضف مرجعًا إلى مكتبة Aspose.Slides في مشروعك.

3. استيراد المساحات الأسماء الضرورية في الكود الخاص بك:

   ```csharp
   using Aspose.Slides;
   ```

## الخطوة 2: تحميل العرض التقديمي الخاص بك

للبدء، عليك تحميل العرض التقديمي الذي تريد تحويله إلى HTML. استبدل `"Your Document Directory"` مع الدليل الفعلي الذي يوجد به ملف العرض التقديمي الخاص بك.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // الكود الخاص بك يذهب هنا
}
```

## الخطوة 3: استبعاد خطوط العرض التقديمي الافتراضية

في هذه الخطوة، يمكنك تحديد أي خطوط عرض تقديمي افتراضية ترغب في استبعادها من التضمين. سيساعد هذا في تحسين حجم ملف HTML الناتج.

```csharp
string[] fontNameExcludeList = { };
```

## الخطوة 4: اختيار وحدة تحكم HTML

الآن، لديك خياران لتضمين الخطوط في HTML:

### الخيار 1: تضمين جميع الخطوط

لتضمين جميع الخطوط المستخدمة في العرض التقديمي، استخدم `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### الخيار 2: ربط جميع الخطوط

لربط جميع الخطوط المستخدمة في العرض التقديمي، استخدم `LinkAllFontsHtmlController`يجب عليك تحديد الدليل الذي توجد فيه الخطوط على نظامك.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## الخطوة 5: تحديد خيارات HTML

إنشاء `HtmlOptions` الكائن وتعيين منسق HTML إلى المنسق الذي حددته في الخطوة السابقة.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // استخدم embedFontsController لتضمين جميع الخطوط
};
```

## الخطوة 6: الحفظ بصيغة HTML

أخيرًا، احفظ العرض التقديمي كملف HTML. يمكنك اختيار أيٍّ مما يلي: `SaveFأوmat.Html` or `SaveFormat.Html5` اعتمادا على متطلباتك.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## خاتمة

تهانينا! لقد نجحت في تحويل عرضك التقديمي إلى HTML مع خطوط مُضمنة باستخدام Aspose.Slides لـ .NET. هذا يضمن عرض خطوطك بشكل صحيح عند مشاركة عروضك التقديمية عبر الإنترنت.

الآن، يمكنك بسهولة مشاركة عروضك التقديمية المنسقة بشكل جميل وبكل ثقة، مع العلم أن جمهورك سوف يشاهدها بالضبط كما كنت تقصد.

لمزيد من المعلومات والمراجع التفصيلية لواجهة برمجة التطبيقات، راجع [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/).

## الأسئلة الشائعة

### 1. هل يمكنني تحويل عروض PowerPoint إلى HTML باستخدام Aspose.Slides لـ .NET في وضع الدفعة؟

نعم، يمكنك تحويل عروض تقديمية متعددة إلى HTML باستخدام Aspose.Slides لـ .NET عن طريق التكرار عبر ملفات العرض التقديمي وتطبيق عملية التحويل على كل منها.

### 2. هل هناك طريقة لتخصيص مظهر مخرجات HTML؟

بالتأكيد! يوفر Aspose.Slides لـ .NET خيارات متنوعة لتخصيص مظهر وتنسيق مُخرجات HTML، مثل ضبط الألوان والخطوط والتخطيط.

### 3. هل هناك أي قيود على تضمين الخطوط في HTML باستخدام Aspose.Slides لـ .NET؟

مع أن Aspose.Slides لـ .NET يوفر إمكانيات ممتازة لتضمين الخطوط، إلا أن حجم ملفات HTML قد يزداد عند تضمين الخطوط. تأكد من تحسين اختيارك للخطوط لاستخدامها على الويب.

### 4. هل يمكنني تحويل عروض PowerPoint إلى تنسيقات أخرى باستخدام Aspose.Slides لـ .NET؟

نعم، يدعم Aspose.Slides for .NET مجموعة واسعة من تنسيقات الإخراج، بما في ذلك PDF والصور وغيرها. يمكنك بسهولة تحويل عروضك التقديمية إلى التنسيق الذي تريده.

### 5. أين يمكنني العثور على موارد ودعم إضافي لـ Aspose.Slides لـ .NET؟

يمكنك الوصول إلى مجموعة كبيرة من الموارد، بما في ذلك الوثائق، على [مرجع Aspose.Slides لـ .NET API](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}