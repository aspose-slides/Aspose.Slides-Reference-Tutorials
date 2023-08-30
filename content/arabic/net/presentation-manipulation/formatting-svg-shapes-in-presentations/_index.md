---
title: تنسيق أشكال SVG في العروض التقديمية
linktitle: تنسيق أشكال SVG في العروض التقديمية
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تنسيق أشكال SVG في العروض التقديمية باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع كود المصدر. ارتقِ بتصميم العرض التقديمي الخاص بك اليوم!
type: docs
weight: 13
url: /ar/net/presentation-manipulation/formatting-svg-shapes-in-presentations/
---

SVG (Scalable Vector Graphics) هو تنسيق يستخدم على نطاق واسع لتمثيل الرسومات المتجهة ثنائية الأبعاد. Aspose.Slides for .NET هي مكتبة قوية تتيح للمطورين العمل مع العروض التقديمية برمجيًا. سيوضح هذا الدليل خطوة بخطوة كيفية تنسيق أشكال SVG داخل العروض التقديمية باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio: قم بتثبيت Visual Studio أو أي بيئة تطوير أخرى لـ C#.
2.  Aspose.Slides for .NET: قم بتنزيل وتثبيت Aspose.Slides for .NET Library من[هنا](https://releases.aspose.com/slides/net/).

## دليل خطوة بخطوة

## 1. قم بإنشاء مشروع C# جديد
قم بإنشاء مشروع C# جديد في Visual Studio.

## 2. أضف مرجعًا إلى Aspose.Slides
أضف مرجعًا إلى مكتبة Aspose.Slides for .NET في مشروعك.

## 3. قم بتحميل ملف العرض التقديمي
قم بتحميل ملف العرض التقديمي PowerPoint الذي يحتوي على أشكال SVG.

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // الرمز الخاص بك هنا
}
```

## 4. الوصول إلى الشريحة وشكل SVG
قم بالوصول إلى الشريحة المحددة وشكل SVG الذي تريد تنسيقه.

```csharp
// قم بالوصول إلى الشريحة
ISlide slide = presentation.Slides[0]; // استبدل بفهرس الشريحة المناسب

// الوصول إلى شكل SVG
IShape svgShape = slide.Shapes[0]; // استبدل بفهرس الشكل المناسب
```

## 5. تطبيق التنسيق على شكل SVG
 قم بتطبيق التنسيق على شكل SVG باستخدام`ISvgShape` طرق الواجهة.

```csharp
// تحويل الشكل إلى ISvgShape
ISvgShape svg = svgShape as ISvgShape;

if (svg != null)
{
    // تطبيق التنسيق
    svg.FillFormat.SolidFillColor.Color = Color.Red;
    svg.LineFormat.Width = 2.0;
    svg.LineFormat.DashStyle = LineDashStyle.DashDot;
    
    // خيارات التنسيق الأخرى
    //svg.LineFormat.FillFormat.SolidFillColor.Color = Color.Blue;
    // svg.LineFormat.Style = LineStyle.ThickBetweenThin;
}
```

## 6. احفظ العرض التقديمي
احفظ العرض التقديمي المعدل بشكل SVG المنسق.

```csharp
string outputPath = "output_path.pptx";
presentation.Save(outputPath, SaveFormat.Pptx);
```

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ .NET؟
 يمكنك تنزيل وتثبيت مكتبة Aspose.Slides for .NET من صفحة الإصدارات:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net/)

### كيف أقوم بتحميل عرض تقديمي موجود باستخدام Aspose.Slides؟
 يمكنك تحميل العرض التقديمي باستخدام`Presentation` فصل. هنا مثال:
```csharp
using Aspose.Slides;

string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // الرمز الخاص بك هنا
}
```

### كيف يمكنني تطبيق التنسيق على شكل SVG؟
 يمكنك تنسيق شكل SVG باستخدام`ISvgShape` واجهه المستخدم. فيما يلي مثال لتطبيق التنسيق:
```csharp
IShape svgShape = slide.Shapes[0]; // الوصول إلى شكل SVG
ISvgShape svg = svgShape as ISvgShape; // الإرسال إلى ISvgShape

if (svg != null)
{
    svg.FillFormat.SolidFillColor.Color = Color.Red; // تعيين لون التعبئة
    svg.LineFormat.Width = 2.0; // ضبط عرض الخط
    svg.LineFormat.DashStyle = LineDashStyle.DashDot; // ضبط نمط شرطة الخط
    // خيارات التنسيق الأخرى
}
```

### كيف أحفظ العرض التقديمي المعدل؟
 يمكنك حفظ العرض التقديمي المعدل باستخدام`Save` طريقة. هنا مثال:
```csharp
string outputPath = "output_path.pptx";
presentation.Save(outputPath, SaveFormat.Pptx);
```

 للحصول على معلومات وخيارات أكثر تفصيلاً، راجع[Aspose.Slides لمرجع .NET API](https://reference.aspose.com/slides/net/).

## خاتمة
في هذا الدليل، تعلمت كيفية تنسيق أشكال SVG داخل العروض التقديمية باستخدام Aspose.Slides لـ .NET. لقد استكشفت تحميل العروض التقديمية، والوصول إلى أشكال SVG، وتطبيق التنسيق، وحفظ العرض التقديمي المعدل. يوفر Aspose.Slides for .NET مجموعة شاملة من الأدوات للتعامل مع العروض التقديمية برمجيًا، مما يتيح لك التحكم في كل جانب من جوانب شرائحك.