---
title: معالجة الارتباط التشعبي في Aspose.Slides
linktitle: معالجة الارتباط التشعبي في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة الارتباطات التشعبية وإزالتها في Aspose.Slides لـ .NET. قم بتحسين عروضك التقديمية باستخدام الروابط التفاعلية بسهولة.
weight: 10
url: /ar/net/hyperlink-manipulation/hyperlink-manipulation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# معالجة الارتباط التشعبي في Aspose.Slides


تعد الارتباطات التشعبية عناصر أساسية في العروض التقديمية، لأنها توفر طريقة ملائمة للتنقل بين الشرائح أو الوصول إلى الموارد الخارجية. يوفر Aspose.Slides for .NET ميزات قوية لإضافة الارتباطات التشعبية وإزالتها في شرائح العرض التقديمي. في هذا البرنامج التعليمي، سنرشدك خلال عملية معالجة الارتباط التشعبي باستخدام Aspose.Slides لـ .NET. سنغطي إضافة الارتباطات التشعبية إلى الشريحة وإزالة الارتباطات التشعبية من الشريحة. لذا، دعونا نتعمق!

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Slides for .NET: يجب أن تكون مكتبة Aspose.Slides for .NET مثبتة وإعدادها. يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/slides/net/) وتحميلها من[هذا الرابط](https://releases.aspose.com/slides/net/).

2. دليل المستندات الخاص بك: أنت بحاجة إلى دليل حيث سيتم تخزين ملفات العرض التقديمي الخاص بك. تأكد من تحديد المسار إلى هذا الدليل في التعليمات البرمجية الخاصة بك.

3. المعرفة الأساسية بـ C#: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا لبرمجة C#.

الآن بعد أن اكتملت متطلباتك الأساسية، دعنا ننتقل إلى الدليل التفصيلي خطوة بخطوة لمعالجة الارتباط التشعبي باستخدام Aspose.Slides for .NET.

## إضافة ارتباطات تشعبية إلى شريحة

### الخطوة 1: تهيئة العرض التقديمي

للبدء، تحتاج إلى تهيئة العرض التقديمي باستخدام Aspose.Slides. يمكنك القيام بذلك باستخدام الكود التالي:

```csharp
using (Presentation presentation = new Presentation())
{
    // الرمز الخاص بك هنا
}
```

### الخطوة 2: إضافة إطار النص

الآن، دعونا نضيف إطار نص إلى الشريحة. يقوم هذا الكود بإنشاء شكل مستطيل مع النص:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### الخطوة 3: إضافة ارتباط تشعبي

بعد ذلك، ستضيف ارتباطًا تشعبيًا إلى النص في الشكل الذي قمت بإنشائه. وإليك كيف يمكنك القيام بذلك:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي الخاص بك باستخدام الارتباط التشعبي المُضاف:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

تهانينا! لقد نجحت في إضافة ارتباط تشعبي إلى شريحة باستخدام Aspose.Slides لـ .NET.

## إزالة الارتباطات التشعبية من الشريحة

### الخطوة 1: تهيئة العرض التقديمي

لإزالة الارتباطات التشعبية من شريحة ما، تحتاج إلى فتح عرض تقديمي موجود:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### الخطوة 2: إزالة الارتباطات التشعبية

الآن، قم بإزالة كافة الارتباطات التشعبية من العرض التقديمي باستخدام الكود التالي:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### الخطوة 3: حفظ العرض التقديمي

بعد إزالة الارتباطات التشعبية، احفظ العرض التقديمي:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

وهذا كل شيء! لقد نجحت في إزالة الارتباطات التشعبية من شريحة باستخدام Aspose.Slides لـ .NET.

في الختام، يوفر Aspose.Slides for .NET طريقة فعالة للتعامل مع الارتباطات التشعبية في العروض التقديمية الخاصة بك، مما يسمح لك بإنشاء شرائح تفاعلية وجذابة. سواء كنت ترغب في إضافة ارتباطات تشعبية إلى موارد خارجية أو إزالتها، فإن Aspose.Slides يبسط العملية ويعزز قدرات بناء العرض التقديمي لديك.

 نشكرك على انضمامك إلينا في هذا البرنامج التعليمي حول معالجة الارتباطات التشعبية في Aspose.Slides لـ .NET. إذا كانت لديك أي أسئلة أو كنت بحاجة إلى مزيد من المساعدة، فلا تتردد في استكشاف[Aspose.Slides الوثائق](https://reference.aspose.com/slides/net/) أو التواصل مع مجتمع Aspose على[منتدى الدعم](https://forum.aspose.com/).

---

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية التعامل مع الارتباطات التشعبية في العروض التقديمية باستخدام Aspose.Slides for .NET. لقد قمنا بتغطية كل من إضافة الارتباطات التشعبية وإزالتها، مما يتيح لك إنشاء عروض تقديمية ديناميكية وتفاعلية. يعمل Aspose.Slides على تبسيط العملية، مما يجعل من السهل تحسين شرائحك باستخدام الارتباطات التشعبية للموارد الخارجية.

هل لديك أي أسئلة أخرى حول العمل مع Aspose.Slides أو الجوانب الأخرى لتصميم العرض التقديمي؟ تحقق من الأسئلة الشائعة أدناه للحصول على مزيد من الأفكار.

## الأسئلة الشائعة (الأسئلة المتداولة)

### ما هي المزايا الرئيسية لاستخدام Aspose.Slides لـ .NET؟
يقدم Aspose.Slides for .NET مجموعة واسعة من الميزات لإنشاء العروض التقديمية ومعالجتها وتحويلها. فهو يوفر مجموعة شاملة من الأدوات لإضافة المحتوى والرسوم المتحركة والتفاعلات إلى الشرائح الخاصة بك.

### هل يمكنني إضافة ارتباطات تشعبية إلى كائنات أخرى غير النص في Aspose.Slides؟
نعم، يتيح لك Aspose.Slides إضافة ارتباطات تشعبية إلى كائنات مختلفة، بما في ذلك الأشكال والصور والنص، مما يمنحك المرونة في إنشاء عروض تقديمية تفاعلية.

### هل Aspose.Slides متوافق مع تنسيقات ملفات PowerPoint المختلفة؟
قطعاً. يدعم Aspose.Slides تنسيقات PowerPoint المتنوعة، بما في ذلك PPT وPPTX وPPS والمزيد. ويضمن التوافق مع إصدارات مختلفة من Microsoft PowerPoint.

### أين يمكنني العثور على موارد إضافية ودعم لـ Aspose.Slides؟
 للحصول على وثائق متعمقة ودعم المجتمع، قم بزيارة[Aspose.Slides الوثائق](https://reference.aspose.com/slides/net/) و ال[Aspose منتدى الدعم](https://forum.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 إذا كنت بحاجة إلى ترخيص مؤقت لـ Aspose.Slides، فيمكنك الحصول على واحد[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
