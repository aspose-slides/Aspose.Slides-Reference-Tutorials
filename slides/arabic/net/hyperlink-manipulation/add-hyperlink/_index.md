---
title: إضافة الارتباطات التشعبية إلى الشرائح في .NET باستخدام Aspose.Slides
linktitle: إضافة ارتباط تشعبي إلى الشريحة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة ارتباطات تشعبية إلى شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. تعزيز العروض التقديمية الخاصة بك مع العناصر التفاعلية.
weight: 12
url: /ar/net/hyperlink-manipulation/add-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


في عالم العروض الرقمية، يعد التفاعل أمرًا أساسيًا. يمكن أن تؤدي إضافة الارتباطات التشعبية إلى الشرائح الخاصة بك إلى جعل العرض التقديمي الخاص بك أكثر جاذبية وغني بالمعلومات. Aspose.Slides for .NET هي مكتبة قوية تسمح لك بإنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها برمجياً. سنوضح لك في هذا البرنامج التعليمي كيفية إضافة ارتباطات تشعبية إلى شرائحك باستخدام Aspose.Slides for .NET. 

## المتطلبات الأساسية

قبل أن نتعمق في إضافة الارتباطات التشعبية إلى الشرائح، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio: يجب أن يكون Visual Studio مثبتًا على جهاز الكمبيوتر الخاص بك لكتابة كود .NET وتنفيذه.

2. Aspose.Slides لـ .NET: أنت بحاجة إلى تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

3. المعرفة الأساسية بـ C#: الإلمام ببرمجة C# سيكون مفيدًا.

## استيراد مساحات الأسماء

للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية في مشروع C# الخاص بك. في هذه الحالة، ستحتاج إلى مساحات الأسماء التالية من مكتبة Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

الآن، دعونا نقسم عملية إضافة الارتباطات التشعبية إلى الشرائح إلى خطوات متعددة.

## الخطوة 1: تهيئة العرض التقديمي

أولاً، قم بإنشاء عرض تقديمي جديد باستخدام Aspose.Slides. وإليك كيف يمكنك القيام بذلك:

```csharp
using (Presentation presentation = new Presentation())
{
    // الكود الخاص بك يذهب هنا
}
```

يقوم هذا الرمز بتهيئة عرض تقديمي جديد لـ PowerPoint.

## الخطوة 2: إضافة إطار النص

الآن، دعنا نضيف إطار نص إلى شريحتك. سيكون إطار النص هذا بمثابة العنصر القابل للنقر في شريحتك. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

يقوم التعليمة البرمجية أعلاه بإنشاء شكل تلقائي مستطيل ويضيف إطار نص يحتوي على النص "Aspose: File Format APIs."

## الخطوة 3: إضافة ارتباط تشعبي

بعد ذلك، دعنا نضيف ارتباطًا تشعبيًا إلى إطار النص الذي قمت بإنشائه. وهذا سيجعل النص قابلاً للنقر.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

في هذه الخطوة، قمنا بتعيين عنوان URL للارتباط التشعبي على "https://www.aspose.com/" ونقدم تلميحًا للحصول على معلومات إضافية. يمكنك أيضًا تنسيق مظهر الارتباط التشعبي، كما هو موضح أعلاه.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي الخاص بك باستخدام الارتباط التشعبي المُضاف.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

يحفظ هذا الرمز العرض التقديمي باسم "presentation-out.pptx."

لقد نجحت الآن في إضافة ارتباط تشعبي إلى شريحة باستخدام Aspose.Slides لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية إضافة ارتباطات تشعبية إلى الشرائح في عروض PowerPoint التقديمية باستخدام Aspose.Slides for .NET. باتباع هذه الخطوات، يمكنك جعل عروضك التقديمية أكثر تفاعلية وجاذبية، وتوفير روابط قيمة لموارد أو معلومات إضافية.

 لمزيد من المعلومات التفصيلية والوثائق، قم بزيارة[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).

## الأسئلة الشائعة

### 1. هل يمكنني إضافة ارتباطات تشعبية إلى أشكال أخرى إلى جانب إطارات النص؟

نعم، يمكنك إضافة ارتباطات تشعبية إلى أشكال مختلفة مثل المستطيلات والصور والمزيد باستخدام Aspose.Slides for .NET.

### 2. كيف يمكنني إزالة ارتباط تشعبي من شكل في شريحة PowerPoint؟

 يمكنك إزالة ارتباط تشعبي من الشكل عن طريق تعيين`HyperlinkClick` الملكية ل`null`.

### 3. هل يمكنني تغيير عنوان URL للارتباط التشعبي ديناميكيًا في الكود الخاص بي؟

 قطعاً! يمكنك تحديث عنوان URL للارتباط التشعبي في أي نقطة في التعليمات البرمجية الخاصة بك عن طريق تعديل`Hyperlink` ملكية.

### 4. ما هي العناصر التفاعلية الأخرى التي يمكنني إضافتها إلى شرائح PowerPoint باستخدام Aspose.Slides؟

يقدم Aspose.Slides مجموعة واسعة من الميزات التفاعلية، بما في ذلك أزرار الإجراءات وعناصر الوسائط المتعددة والرسوم المتحركة.

### 5. هل Aspose.Slides متاح للغات البرمجة الأخرى؟

نعم، Aspose.Slides متاح للعديد من لغات البرمجة، بما في ذلك Java وPython.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
