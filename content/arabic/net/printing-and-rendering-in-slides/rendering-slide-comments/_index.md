---
title: عرض تعليقات الشرائح في Aspose.Slides
linktitle: عرض تعليقات الشرائح في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية عرض تعليقات الشرائح في عروض PowerPoint التقديمية باستخدام Aspose.Slides for .NET. يوفر هذا الدليل خطوة بخطوة أمثلة على التعليمات البرمجية المصدر للوصول إلى التعليقات وتخصيصها وعرضها برمجيًا.
type: docs
weight: 12
url: /ar/net/printing-and-rendering-in-slides/rendering-slide-comments/
---

## مقدمة

توفر تعليقات الشرائح رؤى وتفسيرات ومناقشات قيمة تتعلق بشرائح معينة في العرض التقديمي. يمكن أن يؤدي عرض هذه التعليقات برمجيًا إلى تبسيط عملية المراجعة والتعاون. يعمل Aspose.Slides for .NET على تبسيط هذه المهمة من خلال توفير مجموعة شاملة من واجهات برمجة التطبيقات لإدارة تعليقات الشرائح وعرضها.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio على جهازك.
- الفهم الأساسي لتطوير C# و.NET.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## إعداد المشروع

1. قم بإنشاء مشروع C# جديد في Visual Studio.

2. أضف مرجعًا إلى مكتبة Aspose.Slides for .NET في مشروعك.

## تحميل عرض تقديمي

للبدء، لنقم بتحميل عرض PowerPoint التقديمي الذي يحتوي على تعليقات الشرائح:

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
using var presentation = new Presentation("presentation.pptx");
```

## الوصول إلى تعليقات الشرائح

بعد ذلك، دعنا نراجع الشرائح الموجودة في العرض التقديمي ونصل إلى التعليقات المرتبطة بكل شريحة:

```csharp
// التكرار من خلال الشرائح
foreach (var slide in presentation.Slides)
{
    // الوصول إلى تعليقات الشرائح
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // الوصول إلى خصائص التعليق
        var author = comment.Author;
        var text = comment.Text;
        
        // قم بمعالجة التعليق حسب الحاجة
    }
}
```

## تقديم التعليقات على الشرائح

الآن، دعونا نقدم التعليقات على الشرائح. سنضيف التعليقات كمربعات نصية أسفل كل شريحة:

```csharp
foreach (var slide in presentation.Slides)
{
    // الوصول إلى تعليقات الشرائح
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // إنشاء مربع نص للتعليق
        var textBox = slide.Shapes.AddTextFrame("");
        var textFrame = textBox.TextFrame;
        
        // قم بتعيين خصائص التعليق كنص
        textFrame.Text = $"{comment.Author}: {comment.Text}";
        
        // ضع مربع النص أسفل الشريحة
        textBox.Left = slide.SlideSize.Size.Width / 2;
        textBox.Top = slide.SlideSize.Size.Height + 20;
        
        // تخصيص مظهر مربع النص إذا لزم الأمر
        
        // قم بمعالجة التعليق حسب الحاجة
    }
}
```

## تخصيص عرض التعليق

يمكنك أيضًا تخصيص مظهر التعليقات المقدمة، مثل حجم الخط واللون والموضع. يتيح لك ذلك مطابقة التعليقات مع نمط العرض التقديمي الخاص بك:

```csharp
// تخصيص مظهر مربع النص
var fontHeight = 12;
var fontColor = Color.Black;
var margin = 20;

foreach (var slide in presentation.Slides)
{
    // ...
    foreach (var comment in comments)
    {
        // ...
        
        // تخصيص مظهر مربع النص
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = fontHeight;
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FillFormat.SolidFillColor.Color = fontColor;
        
        // ضبط موضع مربع النص
        textBox.Top = slide.SlideSize.Size.Height - margin;
        margin += 30; // قم بزيادة هامش التعليق التالي
    }
}
```

## حفظ العرض التقديمي المقدم

بمجرد تقديم التعليقات على الشرائح، يمكنك حفظ العرض التقديمي المعدل:

```csharp
// احفظ العرض التقديمي المعدل
presentation.Save("rendered_presentation.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا الدليل، اكتشفنا كيفية عرض تعليقات الشرائح في عروض PowerPoint التقديمية باستخدام Aspose.Slides for .NET. باتباع الخطوات الموضحة أعلاه، يمكنك الوصول إلى التعليقات وعرضها برمجيًا، مما يعزز التعاون والتواصل داخل مجموعات الشرائح الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides for .NET من[هذا الرابط](https://releases.aspose.com/slides/net/). بمجرد تنزيله، يمكنك إضافته كمرجع في مشروع Visual Studio الخاص بك.

### هل يمكنني تخصيص مظهر التعليقات المقدمة؟

نعم، يمكنك تخصيص مظهر التعليقات المقدمة، بما في ذلك حجم الخط واللون والموضع. يتيح لك هذا مطابقة التعليقات مع أسلوب العرض التقديمي الخاص بك.

### كيف يمكنني الوصول إلى خصائص التعليق الفردي؟

 يمكنك الوصول إلى خصائص التعليق مثل المؤلف والنص باستخدام الملف`Author` و`Text` خصائص كائن التعليق.

### هل يمكنني تقديم التعليقات كوسيلة شرح بدلاً من مربعات النص؟

نعم، يمكنك عرض التعليقات كوسيلة شرح عن طريق إنشاء أشكال مخصصة وإضافة نص إليها. ستحتاج إلى ضبط موضع وسائل الشرح ومظهرها وفقًا لذلك.

### هل Aspose.Slides for .NET مناسب للمهام الأخرى المتعلقة ببرنامج PowerPoint؟

قطعاً! يوفر Aspose.Slides for .NET نطاقًا واسعًا من واجهات برمجة التطبيقات للعمل مع عروض PowerPoint التقديمية. يمكنك إنشاء جوانب مختلفة من العروض التقديمية وتعديلها وتحويلها ومعالجتها برمجيًا.