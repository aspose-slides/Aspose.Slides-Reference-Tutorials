---
title: ضبط أرقام الشرائح للعروض التقديمية باستخدام Aspose.Slides
linktitle: ضبط أرقام الشرائح للعروض التقديمية باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة أرقام الشرائح وتخصيصها في عروض PowerPoint التقديمية باستخدام Aspose.Slides for .NET. يوفر هذا الدليل خطوة بخطوة أمثلة على التعليمات البرمجية المصدر لإعداد المشروع وتحميل عرض تقديمي وإضافة أرقام الشرائح وتخصيص تنسيقها وضبط موضعها.
type: docs
weight: 16
url: /ar/net/printing-and-rendering-in-slides/setting-slide-numbers/
---

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة متعددة الاستخدامات تمكن مطوري .NET من إنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها برمجيًا. فهو يوفر مجموعة واسعة من الميزات للتفاعل مع العناصر المختلفة للعروض التقديمية، بما في ذلك الشرائح والأشكال والنصوص والصور والمزيد. في هذا الدليل، سنركز على إضافة أرقام الشرائح وتخصيصها باستخدام Aspose.Slides لـ .NET.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio (أو أي بيئة تطوير .NET أخرى)
-  Aspose.Slides لمكتبة .NET (التنزيل من[هنا](https://releases.aspose.com/slides/net/)

## إعداد المشروع

1. قم بإنشاء مشروع Visual Studio جديد (تطبيق وحدة التحكم، على سبيل المثال).
2. قم بإضافة مرجع إلى Aspose.Slides لمكتبة .NET.

## تحميل عرض تقديمي

للبدء، لنقم بتحميل عرض PowerPoint تقديمي موجود:

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## إضافة أرقام الشرائح

بعد ذلك، دعونا نضيف أرقام الشرائح إلى كل شريحة في العرض التقديمي:

```csharp
// تمكين أرقام الشرائح
foreach (ISlide slide in presentation.Slides)
{
    // إضافة شكل رقم الشريحة
    IAutoShape slideNumberShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 10, 10, 50, 20);
    slideNumberShape.TextFrame.Text = (slide.SlideNumber).ToString();
}
```

## تخصيص تنسيق رقم الشريحة

يمكنك تخصيص مظهر أرقام الشرائح عن طريق ضبط الخط واللون والحجم والمزيد:

```csharp
foreach (IAutoShape shape in presentation.Slides[0].Shapes.OfType<IAutoShape>())
{
    // تخصيص الخط واللون
    ITextFrame textFrame = shape.TextFrame;
    IParagraph paragraph = textFrame.Paragraphs[0];
    IPortion portion = paragraph.Portions[0];
    
    portion.PortionFormat.FontHeight = 12;
    portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
}
```

## تحديث موضع رقم الشريحة

يمكنك أيضًا ضبط موضع أرقام الشرائح في كل شريحة:

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IAutoShape shape in slide.Shapes.OfType<IAutoShape>())
    {
        shape.Left = slide.SlideSize.Size.Width - shape.Width - 10;
        shape.Top = slide.SlideSize.Size.Height - shape.Height - 10;
    }
}
```

## حفظ العرض التقديمي المعدل

بمجرد إضافة أرقام الشرائح وتخصيصها، احفظ العرض التقديمي المعدل:

```csharp
presentation.Save("output-presentation.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا الدليل، اكتشفنا كيفية تحسين العروض التقديمية الخاصة بك عن طريق إضافة أرقام الشرائح وتخصيصها باستخدام Aspose.Slides for .NET. باتباع الخطوات المقدمة وأمثلة التعليمات البرمجية، يمكنك أتمتة عملية إضافة أرقام الشرائح وإنشاء عروض تقديمية ذات مظهر احترافي.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides for .NET من[هنا](https://releases.aspose.com/slides/net/). بعد التنزيل، قم بإضافة مرجع إلى المكتبة في مشروع .NET الخاص بك.

### هل يمكنني تخصيص مظهر أرقام الشرائح؟

نعم، يمكنك تخصيص الخط واللون والحجم والسمات الأخرى لأرقام الشرائح باستخدام أمثلة التعليمات البرمجية المتوفرة.

### كيف يمكنني ضبط موضع أرقام الشرائح في كل شريحة؟

يمكنك ضبط موضع أرقام الشرائح عن طريق تعديل إحداثيات أشكال أرقام الشرائح، كما هو موضح في أمثلة التعليمات البرمجية.

### هل Aspose.Slides for .NET مخصص فقط لإضافة أرقام الشرائح؟

لا، يقدم Aspose.Slides for .NET نطاقًا واسعًا من الميزات بخلاف إضافة أرقام الشرائح. يسمح لك بإنشاء وتعديل ومعالجة عناصر مختلفة من عروض PowerPoint التقديمية برمجياً.

### هل يمكن التراجع عن التعديلات إذا أردت إزالة أرقام الشرائح لاحقًا؟

نعم، يمكنك بسهولة إزالة أرقام الشرائح عن طريق إزالة الأشكال المقابلة من الشرائح باستخدام مكتبة Aspose.Slides.