---
"description": "حسّن عروض PowerPoint التقديمية بروابط تشعبية قابلة للتغيير باستخدام Aspose.Slides لـ .NET. تفاعل مع جمهورك بشكل غير مسبوق!"
"linktitle": "إنشاء ارتباط تشعبي قابل للتغيير"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء ارتباط تشعبي قابل للتغيير في Aspose.Slides لـ .NET"
"url": "/ar/net/hyperlink-manipulation/mutable-hyperlink/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء ارتباط تشعبي قابل للتغيير في Aspose.Slides لـ .NET


في عالم تطوير البرمجيات الحديث، يُعد إنشاء عروض تقديمية ديناميكية بروابط تفاعلية أمرًا بالغ الأهمية لجذب جمهورك. يُعد Aspose.Slides for .NET أداة فعّالة تتيح لك إدارة عروض PowerPoint التقديمية وتخصيصها، بما في ذلك إنشاء روابط قابلة للتغيير. في هذا الدليل التفصيلي، سنشرح لك عملية إنشاء روابط قابلة للتغيير باستخدام Aspose.Slides for .NET. 

## المتطلبات الأساسية

قبل أن نتعمق في عالم الروابط التشعبية القابلة للتغيير، هناك بعض المتطلبات الأساسية التي يجب أن تتوفر لديك:

### 1. Aspose.Slides لـ .NET
تأكد من تثبيت Aspose.Slides لـ .NET وإعداده في بيئة التطوير لديك. يمكنك تنزيله. [هنا](https://releases.aspose.com/slides/net/).

### 2. إطار عمل .NET
تأكد من تثبيت .NET Framework على جهازك. يتطلب Aspose.Slides for .NET إطار عمل .NET ليعمل.

### 3. بيئة التطوير المتكاملة (IDE)
سوف تحتاج إلى IDE مثل Visual Studio لكتابة وتنفيذ كود .NET.

الآن بعد أن أصبحت لديك المتطلبات الأساسية اللازمة، دعنا ننتقل إلى إنشاء ارتباطات تشعبية قابلة للتغيير في Aspose.Slides لـ .NET.

## إنشاء ارتباط تشعبي قابل للتغيير

### الخطوة 1: إعداد مشروعك
أولاً، أنشئ مشروعًا جديدًا أو افتح مشروعًا موجودًا في بيئة التطوير المتكاملة (IDE) لديك. تأكد من أن ملف Aspose.Slides for .NET مُشار إليه بشكل صحيح في مشروعك.

### الخطوة 2: استيراد مساحات الأسماء
في ملف التعليمات البرمجية الخاص بك، قم باستيراد المساحات الأساسية اللازمة للعمل مع Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Shape;
```

### الخطوة 3: إنشاء عرض تقديمي جديد
لإنشاء عرض تقديمي جديد في PowerPoint، استخدم الكود التالي:

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation())
{
    // يذهب الكود الخاص بك لإنشاء العرض التقديمي ومعالجته هنا
    presentation.Save(dataDir + "presentation-out.pptx", SaveFormat.Pptx);
}
```

### الخطوة 4: إضافة شكل مرتبط تشعبيًا
الآن، لنُضِف شكلاً إلى عرضك التقديمي مع رابط تشعبي. في هذا المثال، سنُنشئ شكلاً مستطيلاً مع رابط تشعبي لموقع Aspose الإلكتروني:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

في هذه الخطوة، أضفنا شكلًا مستطيلًا يحمل النص "Aspose: واجهات برمجة تطبيقات تنسيق الملفات" ورابطًا تشعبيًا قابلًا للنقر. يمكنك تخصيص الشكل والنص والرابط التشعبي حسب احتياجاتك.

### الخطوة 5: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الخاص بك في ملف باستخدام الكود التالي:

```csharp
presentation.Save(dataDir + "presentation-out.pptx", SaveFormat.Pptx);
```

الآن أصبح عرض الارتباط التشعبي القابل للتغيير جاهزًا!

## خاتمة

يُسهّل Aspose.Slides for .NET إنشاء روابط تشعبية قابلة للتغيير في عروض PowerPoint التقديمية. باتباع الخطوات البسيطة الموضحة في هذا الدليل، يمكنك إنشاء عروض تقديمية ديناميكية وتفاعلية تجذب جمهورك. سواء كنت مطورًا تعمل على عروض تقديمية للشركات أو مواد تعليمية، يُمكّنك Aspose.Slides من إضافة روابط تشعبية وتحسين محتواك بسهولة.

لمزيد من المعلومات والوثائق المتعمقة، يرجى الرجوع إلى [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/).

## الأسئلة الشائعة

### 1. ما هي إصدارات .NET Framework التي يدعمها Aspose.Slides لـ .NET؟
يدعم Aspose.Slides for .NET إصدارات متعددة من .NET Framework، بما في ذلك 2.0، و3.5، و4.x، والمزيد.

### 2. هل يمكنني إنشاء ارتباطات تشعبية لمواقع ويب خارجية في عروض PowerPoint الخاصة بي باستخدام Aspose.Slides لـ .NET؟
نعم، يمكنك إنشاء روابط تشعبية لمواقع ويب خارجية كما هو موضح في هذا الدليل. يتيح لك Aspose.Slides for .NET ربط صفحات الويب أو الملفات أو الموارد الأخرى.

### 3. هل هناك أي خيارات ترخيص متاحة لـ Aspose.Slides لـ .NET؟
نعم، يوفر Aspose خيارات ترخيص لمختلف حالات الاستخدام. يمكنك استكشاف وشراء التراخيص. [هنا](https://purchase.aspose.com/buy) أو الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### 4. هل يمكنني تخصيص مظهر الروابط التشعبية في العرض التقديمي الخاص بي؟
بالتأكيد. يوفر Aspose.Slides لـ .NET خيارات واسعة لتخصيص مظهر الارتباط التشعبي، بما في ذلك النص واللون والنمط.

### 5. هل برنامج Aspose.Slides for .NET مناسب لإنشاء محتوى تعليمي إلكتروني تفاعلي؟
نعم، Aspose.Slides for .NET هي أداة متعددة الاستخدامات يمكن استخدامها لإنشاء محتوى تعليمي إلكتروني تفاعلي، بما في ذلك الارتباطات التشعبية والاختبارات وعناصر الوسائط المتعددة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}