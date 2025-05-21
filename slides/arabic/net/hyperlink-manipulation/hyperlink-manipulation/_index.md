---
"description": "تعرّف على كيفية إضافة وإزالة الروابط التشعبية في Aspose.Slides لـ .NET. حسّن عروضك التقديمية بروابط تفاعلية بسهولة."
"linktitle": "معالجة الارتباطات التشعبية في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "معالجة الارتباطات التشعبية في Aspose.Slides"
"url": "/ar/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# معالجة الارتباطات التشعبية في Aspose.Slides


الروابط التشعبية عناصر أساسية في العروض التقديمية، إذ تُتيح طريقةً سهلةً للتنقل بين الشرائح أو الوصول إلى الموارد الخارجية. يُقدّم Aspose.Slides for .NET ميزاتٍ فعّالة لإضافة الروابط التشعبية وإزالتها من شرائح العرض التقديمي. في هذا البرنامج التعليمي، سنرشدك خلال عملية معالجة الروابط التشعبية باستخدام Aspose.Slides for .NET. سنتناول إضافة الروابط التشعبية إلى الشريحة وإزالتها. هيا بنا!

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. Aspose.Slides لـ .NET: يجب تثبيت مكتبة Aspose.Slides لـ .NET وإعدادها. يمكنك العثور على الوثائق. [هنا](https://reference.aspose.com/slides/net/) وتنزيله من [هذا الرابط](https://releases.aspose.com/slides/net/).

2. مجلد مستنداتك: ستحتاج إلى مجلد لتخزين ملفات العرض التقديمي. تأكد من تحديد مسار هذا المجلد في الكود.

3. المعرفة الأساسية بلغة C#: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا لبرمجة C#.

الآن بعد أن أصبحت لديك المتطلبات الأساسية في مكانها، دعنا ننتقل إلى الدليل خطوة بخطوة لمعالجة الارتباط التشعبي باستخدام Aspose.Slides لـ .NET.

## إضافة ارتباطات تشعبية إلى شريحة

### الخطوة 1: تهيئة العرض التقديمي

للبدء، عليك تهيئة عرض تقديمي باستخدام Aspose.Slides. يمكنك القيام بذلك باستخدام الكود التالي:

```csharp
using (Presentation presentation = new Presentation())
{
    // الكود الخاص بك هنا
}
```

### الخطوة 2: إضافة إطار نصي

الآن، لنُضِف إطارًا نصيًا إلى الشريحة. يُنشئ هذا الكود شكلًا مستطيلًا يحتوي على نص:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### الخطوة 3: إضافة ارتباط تشعبي

بعد ذلك، ستضيف رابطًا تشعبيًا إلى النص في الشكل الذي أنشأته. إليك كيفية القيام بذلك:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ عرضك التقديمي باستخدام الرابط التشعبي المضاف:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

تهانينا! لقد نجحت في إضافة رابط تشعبي إلى شريحة باستخدام Aspose.Slides لـ .NET.

## إزالة الارتباطات التشعبية من الشريحة

### الخطوة 1: تهيئة العرض التقديمي

لإزالة الارتباطات التشعبية من شريحة، يجب عليك فتح عرض تقديمي موجود:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### الخطوة 2: إزالة الارتباطات التشعبية

الآن، قم بإزالة جميع الارتباطات التشعبية من العرض التقديمي باستخدام الكود التالي:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### الخطوة 3: حفظ العرض التقديمي

بعد إزالة الارتباطات التشعبية، احفظ العرض التقديمي:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

وهذا كل شيء! لقد نجحت في إزالة الروابط التشعبية من الشريحة باستخدام Aspose.Slides لـ .NET.

في الختام، يوفر Aspose.Slides لـ .NET طريقة فعّالة لإدارة الروابط التشعبية في عروضك التقديمية، مما يسمح لك بإنشاء شرائح تفاعلية وجذابة. سواءً أردت إضافة روابط تشعبية إلى موارد خارجية أو إزالتها، يُبسّط Aspose.Slides العملية ويُحسّن قدراتك على إنشاء العروض التقديمية.

شكرًا لانضمامك إلينا في هذا البرنامج التعليمي حول معالجة الروابط التشعبية في Aspose.Slides لـ .NET. إذا كانت لديك أي أسئلة أو كنت بحاجة إلى مزيد من المساعدة، فلا تتردد في استكشاف [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/) أو تواصل مع مجتمع Aspose على [منتدى الدعم](https://forum.aspose.com/).

---

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية التعامل مع الروابط التشعبية في العروض التقديمية باستخدام Aspose.Slides لـ .NET. تناولنا إضافة الروابط التشعبية وإزالتها، مما يتيح لك إنشاء عروض تقديمية ديناميكية وتفاعلية. يُبسط Aspose.Slides العملية، مما يُسهّل تحسين شرائحك بروابط تشعبية لموارد خارجية.

هل لديك أي أسئلة أخرى حول استخدام Aspose.Slides أو جوانب أخرى من تصميم العروض التقديمية؟ اطلع على الأسئلة الشائعة أدناه لمزيد من المعلومات.

## الأسئلة الشائعة

### ما هي المزايا الرئيسية لاستخدام Aspose.Slides لـ .NET؟
يوفر Aspose.Slides for .NET مجموعة واسعة من الميزات لإنشاء العروض التقديمية ومعالجتها وتحويلها. كما يوفر مجموعة شاملة من الأدوات لإضافة المحتوى والرسوم المتحركة والتفاعلات إلى شرائحك.

### هل يمكنني إضافة ارتباطات تشعبية إلى كائنات أخرى غير النص في Aspose.Slides؟
نعم، يسمح لك Aspose.Slides بإضافة ارتباطات تشعبية إلى كائنات مختلفة، بما في ذلك الأشكال والصور والنصوص، مما يمنحك المرونة في إنشاء عروض تقديمية تفاعلية.

### هل Aspose.Slides متوافق مع تنسيقات ملفات PowerPoint المختلفة؟
بالتأكيد. يدعم Aspose.Slides تنسيقات PowerPoint متنوعة، بما في ذلك PPT وPPTX وPPS وغيرها. ويضمن التوافق مع مختلف إصدارات Microsoft PowerPoint.

### أين يمكنني العثور على موارد ودعم إضافي لـ Aspose.Slides؟
للحصول على توثيق متعمق ودعم المجتمع، قم بزيارة [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/) و ال [منتدى دعم Aspose](https://forum.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
إذا كنت بحاجة إلى ترخيص مؤقت لـ Aspose.Slides، فيمكنك الحصول على واحد [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}