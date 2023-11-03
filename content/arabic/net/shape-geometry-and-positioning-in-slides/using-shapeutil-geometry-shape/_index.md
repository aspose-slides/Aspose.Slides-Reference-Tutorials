---
title: استخدام ShapeUtil للأشكال الهندسية في شرائح العرض التقديمي
linktitle: استخدام ShapeUtil للأشكال الهندسية في شرائح العرض التقديمي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين عروض PowerPoint التقديمية باستخدام Aspose.Slides. استكشف ShapeUtil لمعالجة الأشكال الهندسية. دليل خطوة بخطوة مع كود مصدر .NET. تحسين العروض التقديمية بشكل فعال.
type: docs
weight: 17
url: /ar/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---
عندما يتعلق الأمر بإنشاء عروض تقديمية جذابة وغنية بالمعلومات، فإن Aspose.Slides هي أداة قوية توفر للمطورين القدرة على التعامل مع الجوانب المختلفة للعروض التقديمية برمجيًا. أحد الجوانب الأساسية للعروض التقديمية هو استخدام الأشكال، التي تلعب دورًا حاسمًا في نقل المعلومات بشكل فعال. في هذا البرنامج التعليمي، سوف نتعمق في استخدام ShapeUtil للتعامل مع الأشكال الهندسية في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. بحلول نهاية هذا الدليل، سيكون لديك فهم قوي لكيفية التعامل مع الأشكال الهندسية وتحسين العروض التقديمية الخاصة بك بسهولة.

## مقدمة إلى Aspose.Slides وShapeUtil

Aspose.Slides هي مكتبة .NET قوية تمكن المطورين من إنشاء عروض PowerPoint التقديمية وتحريرها ومعالجتها برمجيًا. يعد ShapeUtil جزءًا من مكتبة Aspose.Slides التي توفر مجموعة من الأدوات المساعدة للعمل بشكل خاص مع الأشكال داخل العروض التقديمية.

## تهيئة بيئة التطوير

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides في مشروع .NET الخاص بك. يمكنك استخدام NuGet لإضافة المكتبة إلى مشروعك بسهولة.

```csharp
// قم بتثبيت Aspose.Slides عبر NuGet
Install-Package Aspose.Slides
```

## إنشاء عرض تقديمي جديد

لنبدأ بإنشاء عرض تقديمي جديد وإضافة شرائح إليه.

```csharp
// إنشاء عرض تقديمي جديد
Presentation presentation = new Presentation();
ISlide slide = presentation.Slides.AddEmptySlide();
```

## إضافة أشكال هندسية إلى الشرائح

لإضافة أشكال هندسية إلى الشرائح، يمكنك استخدام فئة ShapeUtil.

```csharp
// أضف شكل مستطيل إلى الشريحة
IShape rectangle = ShapeUtil.AddRectangle(slide, 100, 100, 200, 150);
```

## تعديل خصائص الأشكال الهندسية

يمكنك تعديل خصائص مختلفة للأشكال الهندسية، مثل الموضع والحجم والتدوير.

```csharp
// تعديل موضع المستطيل
rectangle.X = 300;
rectangle.Y = 200;

// تغيير حجم المستطيل
rectangle.Width = 250;
rectangle.Height = 100;

// تدوير المستطيل
rectangle.Rotation = 45;
```

## ترتيب ومحاذاة الأشكال الهندسية

يوفر ShapeUtil أيضًا طرقًا لترتيب الأشكال ومحاذاتها على الشرائح.

```csharp
// ترتيب الأشكال أفقيا
ShapeUtil.ArrangeHorizontally(slide.Shapes);

// محاذاة الأشكال إلى المركز
ShapeUtil.AlignToCenter(slide.Shapes);
```

## تجميع وفك تجميع الأشكال

يمكنك تجميع أشكال متعددة معًا باستخدام ShapeUtil.

```csharp
// أشكال المجموعة
IShape[] shapesToGroup = new IShape[] { shape1, shape2, shape3 };
IShape groupedShape = ShapeUtil.GroupShapes(slide, shapesToGroup);

// فك تجميع الأشكال
ShapeUtil.UngroupShape(slide, groupedShape);
```

## تطبيق التنسيق على الأشكال الهندسية

يتيح لك ShapeUtil تطبيق التنسيق على الأشكال، بما في ذلك أنماط التعبئة والخطوط.

```csharp
//تطبيق لون التعبئة
ShapeUtil.ApplyFillColor(shape, Color.Blue);

// تطبيق لون الخط والأسلوب
ShapeUtil.ApplyLineColor(shape, Color.Black, LineStyle.Single);
```

## إضافة نص إلى الأشكال الهندسية

يمكنك إضافة نص إلى الأشكال الهندسية باستخدام ShapeUtil أيضًا.

```csharp
// إضافة نص إلى الشكل
ShapeUtil.AddTextToShape(shape, "Hello, Aspose.Slides!", new Font("Arial", 12), Color.Black);
```

## العمل مع الارتباطات التشعبية في الأشكال

يمكّنك ShapeUtil من إضافة ارتباطات تشعبية إلى الأشكال.

```csharp
// إضافة ارتباط تشعبي إلى الشكل
string url = "https://www.example.com";
ShapeUtil.AddHyperlinkToShape(shape, url);
```

## إدارة الترتيب Z للأشكال

يوفر ShapeUtil طرقًا لإدارة الترتيب z للأشكال.

```csharp
// جلب الشكل إلى الأمام
ShapeUtil.BringToFront(shape);

// إرسال الشكل إلى الخلف
ShapeUtil.SendToBack(shape);
```

## حفظ وتصدير العرض التقديمي

بمجرد إجراء كافة التغييرات اللازمة، يمكنك حفظ العرض التقديمي وتصديره.

```csharp
// احفظ العرض التقديمي
presentation.Save("Presentation.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا إمكانيات Aspose.Slides وShapeUtil للعمل مع الأشكال الهندسية في شرائح العرض التقديمي باستخدام .NET. لقد قمنا بتغطية عملية إنشاء عرض تقديمي جديد، وإضافة أشكال هندسية، وتعديل خصائصها، وتطبيق التنسيق، وإضافة نص، وإدارة الارتباطات التشعبية، والمزيد. من خلال الاستفادة من ميزات Aspose.Slides وShapeUtil، يمكنك تحسين المظهر البصري وفعالية العروض التقديمية الخاصة بك.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides عبر NuGet؟

لتثبيت Aspose.Slides عبر NuGet، استخدم الأمر التالي في وحدة تحكم NuGet Package Manager:

```csharp
Install-Package Aspose.Slides
```

### هل يمكنني إضافة ارتباطات تشعبية إلى الأشكال باستخدام ShapeUtil؟

 نعم، يمكنك إضافة ارتباطات تشعبية إلى الأشكال باستخدام ShapeUtil. الاستفادة من`AddHyperlinkToShape` طريقة لربط ارتباط تشعبي بالشكل.

### هل من الممكن تجميع الأشكال وفك تجميعها برمجياً؟

 قطعاً! يمكنك استخدام أساليب ShapeUtil`GroupShapes` و`UngroupShape` لتجميع الأشكال وفك تجميعها برمجياً.

### كيف يمكنني تطبيق التنسيق على الأشكال الهندسية؟

باستخدام ShapeUtil، يمكنك تطبيق التنسيق على الأشكال الهندسية باستخدام طرق مثل`ApplyFillColor` و`ApplyLineColor` لتعيين ألوان التعبئة وأنماط الخطوط.

### ما هو الغرض من الترتيب Z في الأشكال؟

 يحدد الترتيب Z ترتيب تراص الأشكال على الشريحة. يمكنك استخدام أساليب ShapeUtil مثل`BringToFront` و`SendToBack` لإدارة الترتيب Z للأشكال.