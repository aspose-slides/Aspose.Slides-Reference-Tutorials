---
title: إنشاء شكل مستطيل بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: إنشاء شكل مستطيل بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء شكل مستطيل بسيط في شرائح PowerPoint باستخدام Aspose.Slides for .NET. يوفر هذا الدليل خطوة بخطوة التعليمات البرمجية المصدرية والتعليمات لإضافة العروض التقديمية وتخصيصها وتحسينها برمجيًا.
type: docs
weight: 12
url: /ar/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة قوية تمكن المطورين من العمل مع عروض PowerPoint التقديمية برمجياً. فهو يوفر مجموعة واسعة من الميزات لإنشاء عناصر العرض التقديمي ومعالجتها وإدارتها، بما في ذلك الشرائح والأشكال والنصوص والصور والمزيد. في هذا الدليل، سوف نركز على إنشاء شكل مستطيل بسيط ضمن شريحة العرض التقديمي باستخدام إمكانيات Aspose.Slides for .NET.

## تهيئة بيئة التطوير

قبل أن نتعمق في الكود، فلنقم بإعداد بيئة التطوير الخاصة بنا. اتبع الخطوات التالية:

1.  تنزيل Aspose.Slides لـ .NET: قم بزيارة[صفحة التحميل](https://releases.aspose.com/slides/net/) واختر الإصدار المتوافق مع مشروعك.

2. تثبيت Aspose.Slides: بعد التنزيل، قم بتثبيت Aspose.Slides عن طريق إضافة مرجع DLL إلى مشروعك.

3. إنشاء مشروع جديد: قم بإنشاء مشروع .NET جديد باستخدام بيئة التطوير المفضلة لديك (Visual Studio، على سبيل المثال).

## إنشاء عرض تقديمي جديد

لنبدأ بإنشاء عرض تقديمي جديد لـ PowerPoint باستخدام Aspose.Slides لـ .NET.

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // إنشاء عرض تقديمي جديد
        Presentation presentation = new Presentation();

        // أضف شريحة فارغة إلى العرض التقديمي
        Slide slide = presentation.Slides.AddEmptySlide();

        // سيتم وضع الكود الخاص بك لإضافة الشكل المستطيل هنا

        // احفظ العرض التقديمي
        presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
    }
}
```

## إضافة شكل مستطيل إلى الشريحة

الآن بعد أن أصبح لدينا شريحة العرض التقديمي جاهزة، فلنتابع لإضافة شكل مستطيل إليها.

```csharp
// أضف شكل مستطيل إلى الشريحة
double x = 100; // الإحداثي X للشكل
double y = 100; // الإحداثي Y للشكل
double width = 200; // عرض الشكل
double height = 100; // ارتفاع الشكل

slide.Shapes.AddRectangle(x, y, width, height);
```

## تخصيص شكل المستطيل

يمكنك تخصيص جوانب مختلفة من الشكل المستطيل، مثل لون التعبئة ونمط الحدود والمزيد.

```csharp
// الحصول على الشكل المضاف (المستطيل)
IShape rectangle = slide.Shapes[0];

// تخصيص لون التعبئة
rectangle.FillFormat.SolidFillColor.Color = Color.Blue;

// تخصيص الحدود
rectangle.LineFormat.Width = 2; // عرض الحدود
rectangle.LineFormat.DashStyle = LineDashStyle.DashDot; // نمط الحدود
rectangle.LineFormat.FillFormat.SolidFillColor.Color = Color.Red; // لون الحدود
```

## حفظ العرض التقديمي

بمجرد إضافة الشكل المستطيل وتخصيصه، فقد حان الوقت لحفظ العرض التقديمي.

```csharp
// احفظ العرض التقديمي
presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا الدليل، اكتشفنا كيفية إنشاء شكل مستطيل بسيط داخل شريحة العرض التقديمي باستخدام Aspose.Slides for .NET. لقد قمنا بتغطية الخطوات الأساسية لإعداد بيئة التطوير وإنشاء عرض تقديمي جديد وإضافة شكل مستطيل وتخصيص مظهره وحفظ العرض التقديمي النهائي. باستخدام Aspose.Slides for .NET، يمكنك بسهولة أتمتة عروض PowerPoint التقديمية وتحسينها، مما يضيف طبقة من الديناميكية والتفاعل.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ .NET؟

لتثبيت Aspose.Slides لـ .NET، اتبع الخطوات التالية:

1.  قم بزيارة[صفحة التحميل](https://releases.aspose.com/slides/net/).
2. اختر الإصدار المتوافق مع مشروعك.
3. قم بإضافة مرجع Aspose.Slides DLL إلى مشروع .NET الخاص بك.

### هل يمكنني تخصيص لون التعبئة للشكل المستطيل؟

 نعم، يمكنك تخصيص لون التعبئة للشكل المستطيل باستخدام`FillFormat` ملكية. ما عليك سوى الوصول إلى الشكل`FillFormat` وتعيين المطلوب`SolidFillColor`.

### كيف أحفظ العرض التقديمي بعد إضافة الشكل المستطيل؟

يمكنك حفظ العرض التقديمي باستخدام`Save` طريقة`Presentation` فصل. قم بتوفير اسم الملف المطلوب وتنسيق الحفظ المطلوب (مثل`SaveFormat.Pptx`).

### هل Aspose.Slides for .NET مناسب للأشكال المستطيلة فقط؟

لا، يدعم Aspose.Slides for .NET نطاقًا واسعًا من الأشكال وعناصر العرض التقديمي. يمكنك إنشاء أشكال ومعالجتها مثل المستطيلات والدوائر والأسهم والمزيد.

### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ .NET؟

 يمكنك العثور على الوثائق التفصيلية ومراجع واجهة برمجة التطبيقات لـ Aspose.Slides لـ .NET على الموقع[صفحة التوثيق](https://reference.aspose.com/slides/net/).