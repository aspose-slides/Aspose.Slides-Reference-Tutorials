---
title: إنشاء شكل بيضاوي بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: إنشاء شكل بيضاوي بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء شكل بيضاوي بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. يوفر هذا الدليل خطوة بخطوة التعليمات البرمجية المصدرية والتعليمات الخاصة بإضافة أشكال القطع الناقص وتخصيصها وحفظها.
type: docs
weight: 11
url: /ar/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

## مقدمة لإنشاء شكل بيضاوي بسيط في شرائح العرض التقديمي

إذا كنت تتطلع إلى تحسين شرائح العرض التقديمي الخاص بك عن طريق إضافة أشكال جذابة بصريًا، فإن Aspose.Slides for .NET يوفر حلاً قويًا لتحقيق ذلك. في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال عملية إنشاء شكل بيضاوي بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio أو أي بيئة تطوير .NET أخرى.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## إعداد مشروعك

1. قم بإنشاء مشروع Visual Studio جديد أو افتح مشروعًا موجودًا.
2. أضف مرجعًا إلى مكتبة Aspose.Slides for .NET في مشروعك.

## إنشاء عرض تقديمي

للبدء، دعونا ننشئ عرضًا تقديميًا جديدًا حيث سنضيف الشكل البيضاوي الخاص بنا.

```csharp
using Aspose.Slides;

// إنشاء عرض تقديمي جديد
Presentation presentation = new Presentation();
```

## إضافة شكل القطع الناقص

الآن وبعد أن أصبح عرضنا التقديمي جاهزًا، فلنضيف شكلًا بيضاويًا إلى الشريحة.

```csharp
// الوصول إلى الشريحة الأولى من العرض التقديمي
ISlide slide = presentation.Slides[0];

// تحديد أبعاد القطع الناقص وموقعه
float x = 100;   // إحداثي X
float y = 100;   // الإحداثي ص
float width = 200;  // عرض
float height = 100; // ارتفاع

// أضف شكل القطع الناقص إلى الشريحة
IAutoShape ellipseShape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, x, y, width, height);
```

## تخصيص القطع الناقص

يمكنك تخصيص مظهر الشكل البيضاوي باستخدام خصائص مختلفة.

```csharp
// تعيين لون التعبئة للقطع الناقص
ellipseShape.FillFormat.SolidFillColor.Color = Color.Blue;

// اضبط لون المخطط التفصيلي وعرضه
ellipseShape.LineFormat.FillFormat.SolidFillColor.Color = Color.Red;
ellipseShape.LineFormat.Width = 2;

// إضافة إطار نص إلى القطع الناقص
ITextFrame textFrame = ellipseShape.TextFrame;
textFrame.Text = "Hello, Aspose.Slides!";
```

## حفظ العرض التقديمي

بعد إضافة شكل القطع الناقص وتخصيصه، حان الوقت لحفظ العرض التقديمي.

```csharp
// احفظ العرض التقديمي
presentation.Save("EllipsePresentation.pptx", SaveFormat.Pptx);
```

## خاتمة

تهانينا! لقد نجحت في إنشاء شكل بيضاوي بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. يغطي هذا الدليل عملية إعداد مشروعك، وإنشاء عرض تقديمي، وإضافة شكل بيضاوي، وتخصيص مظهره، وحفظ العرض التقديمي النهائي.

## الأسئلة الشائعة

### كيف يمكنني تغيير موضع الشكل البيضاوي؟

 يمكنك تعديل`x` و`y` الإحداثيات عند إضافة الشكل البيضاوي لضبط موضعه على الشريحة.

### هل يمكنني تغيير لون الخطوط العريضة للقطع الناقص؟

 نعم، يمكنك ضبط لون المخطط التفصيلي باستخدام`LineFormat.FillFormat.SolidFillColor.Color` ملكية.

### هل من الممكن إضافة نص داخل القطع الناقص؟

 قطعاً! يمكنك إضافة نص إلى شكل القطع الناقص باستخدام`TextFrame.Text` ملكية.

### ما الأشكال الأخرى التي يمكنني إنشاؤها باستخدام Aspose.Slides لـ .NET؟

يدعم Aspose.Slides for .NET الأشكال المختلفة، بما في ذلك المستطيلات والخطوط والأسهم والمزيد.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ .NET؟

 للحصول على وثائق وأمثلة مفصلة، راجع[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).