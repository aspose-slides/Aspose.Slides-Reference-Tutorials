---
title: إنشاء ارتباط تشعبي قابل للتغيير في Aspose.Slides لـ .NET
linktitle: إنشاء ارتباط تشعبي قابل للتغيير
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بتحسين عروض PowerPoint التقديمية الخاصة بك باستخدام الارتباطات التشعبية القابلة للتغيير باستخدام Aspose.Slides لـ .NET. إشراك جمهورك كما لم يحدث من قبل!
weight: 14
url: /ar/net/hyperlink-manipulation/mutable-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


في عالم تطوير البرمجيات الحديثة، يعد إنشاء عروض تقديمية ديناميكية باستخدام الارتباطات التشعبية التفاعلية أمرًا بالغ الأهمية لجذب جمهورك. Aspose.Slides for .NET هي أداة قوية تسمح لك بمعالجة عروض PowerPoint التقديمية وتخصيصها، بما في ذلك إنشاء ارتباطات تشعبية قابلة للتغيير. في هذا الدليل التفصيلي خطوة بخطوة، سنرشدك خلال عملية إنشاء ارتباطات تشعبية قابلة للتغيير باستخدام Aspose.Slides for .NET. 

## المتطلبات الأساسية

قبل أن نتعمق في عالم الارتباطات التشعبية القابلة للتغيير، هناك بعض المتطلبات الأساسية التي يجب توفرها:

### 1. Aspose.Slides لـ .NET
 تأكد من تثبيت Aspose.Slides for .NET وإعداده في بيئة التطوير لديك. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).

### 2. صافي الإطار
تأكد من تثبيت .NET Framework على جهازك. يتطلب Aspose.Slides for .NET وجود .NET Framework ليعمل.

### 3. بيئة التطوير المتكاملة (IDE)
ستحتاج إلى IDE مثل Visual Studio لكتابة وتنفيذ تعليمات NET البرمجية.

الآن بعد أن توفرت لديك المتطلبات الأساسية اللازمة، دعنا ننتقل إلى إنشاء ارتباطات تشعبية قابلة للتغيير في Aspose.Slides لـ .NET.

## إنشاء ارتباط تشعبي قابل للتغيير

### الخطوة 1: إعداد مشروعك
أولاً، قم بإنشاء مشروع جديد أو افتح مشروعًا موجودًا في IDE الخاص بك. تأكد من الإشارة إلى Aspose.Slides for .NET بشكل صحيح في مشروعك.

### الخطوة 2: استيراد مساحات الأسماء
في ملف التعليمات البرمجية الخاص بك، قم باستيراد مساحات الأسماء اللازمة للعمل مع Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Shape;
```

### الخطوة 3: إنشاء عرض تقديمي جديد
لإنشاء عرض تقديمي جديد لـ PowerPoint، استخدم الكود التالي:

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation())
{
    // الكود الخاص بك لإنشاء العرض التقديمي ومعالجته موجود هنا
    presentation.Save(dataDir + "presentation-out.pptx", SaveFormat.Pptx);
}
```

### الخطوة 4: إضافة شكل ارتباط تشعبي
الآن، دعنا نضيف شكلاً إلى العرض التقديمي الخاص بك باستخدام ارتباط تشعبي. في هذا المثال، سنقوم بإنشاء شكل مستطيل مع رابط تشعبي إلى موقع Aspose:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

في هذه الخطوة، أضفنا شكلًا مستطيلًا يحتوي على النص "Aspose: File Format APIs" وارتباط تشعبي قابل للنقر عليه. يمكنك تخصيص الشكل والنص والارتباط التشعبي وفقًا لاحتياجاتك.

### الخطوة 5: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الخاص بك في ملف باستخدام الكود التالي:

```csharp
presentation.Save(dataDir + "presentation-out.pptx", SaveFormat.Pptx);
```

عرض الارتباط التشعبي القابل للتغيير جاهز الآن!

## خاتمة

Aspose.Slides for .NET يجعل إنشاء ارتباطات تشعبية قابلة للتغيير في عروض PowerPoint التقديمية أمرًا سهلاً. باستخدام الخطوات البسيطة الموضحة في هذا الدليل، يمكنك إنشاء عروض تقديمية ديناميكية وتفاعلية تجذب جمهورك. سواء كنت مطورًا يعمل على العروض التقديمية للشركات أو المواد التعليمية، فإن Aspose.Slides يمكّنك من إضافة ارتباطات تشعبية وتحسين المحتوى الخاص بك بسهولة.

 لمزيد من المعلومات والوثائق المتعمقة، يرجى الرجوع إلى[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).

## الأسئلة الشائعة

### 1. ما هي إصدارات .NET Framework التي يدعمها Aspose.Slides لـ .NET؟
يدعم Aspose.Slides for .NET إصدارات متعددة من .NET Framework، بما في ذلك 2.0 و3.5 و4.x والمزيد.

### 2. هل يمكنني إنشاء ارتباطات تشعبية لمواقع ويب خارجية في عروض PowerPoint التقديمية الخاصة بي باستخدام Aspose.Slides for .NET؟
نعم، يمكنك إنشاء روابط تشعبية لمواقع ويب خارجية كما هو موضح في هذا الدليل. يتيح لك Aspose.Slides for .NET الارتباط بصفحات الويب أو الملفات أو الموارد الأخرى.

### 3. هل هناك أي خيارات ترخيص متاحة لـ Aspose.Slides لـ .NET؟
 نعم، يقدم Aspose خيارات الترخيص لحالات الاستخدام المختلفة. يمكنك استكشاف وشراء التراخيص[هنا](https://purchase.aspose.com/buy) أو الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

### 4. هل يمكنني تخصيص مظهر الارتباطات التشعبية في العرض التقديمي الخاص بي؟
قطعاً. يوفر Aspose.Slides for .NET خيارات شاملة لتخصيص مظهر الارتباط التشعبي، بما في ذلك النص واللون والنمط.

### 5. هل Aspose.Slides for .NET مناسب لإنشاء محتوى تعليم إلكتروني تفاعلي؟
نعم، Aspose.Slides for .NET هي أداة متعددة الاستخدامات يمكن استخدامها لإنشاء محتوى تعليم إلكتروني تفاعلي، بما في ذلك الارتباطات التشعبية والاختبارات وعناصر الوسائط المتعددة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
