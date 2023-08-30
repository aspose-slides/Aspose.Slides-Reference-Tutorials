---
title: تعبئة الأشكال بالتدرج في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: تعبئة الأشكال بالتدرج في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين شرائح العرض التقديمي الخاص بك باستخدام التدرجات الجذابة باستخدام Aspose.Slides for .NET. اتبع هذا الدليل خطوة بخطوة مع التعليمات البرمجية المصدر الكاملة لملء الأشكال بالتدرجات، من الخطي إلى الشعاعي، مما يضيف العمق والأبعاد.
type: docs
weight: 21
url: /ar/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة قوية تمكن المطورين من إنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجياً. فهو يقدم مجموعة واسعة من الميزات للعمل مع الشرائح والأشكال والنصوص والصور والمزيد. في هذا الدليل، سنركز على كيفية استخدام Aspose.Slides لتطبيق التدرجات اللونية على الأشكال داخل العرض التقديمي.

## إضافة الأشكال إلى الشرائح

قبل أن نتعمق في التدرجات، فلنبدأ بإضافة أشكال إلى الشرائح باستخدام Aspose.Slides. فيما يلي مثال أساسي لإضافة شكل مستطيل إلى شريحة:

```csharp
// أضف شكل مستطيل جديد إلى الشريحة
var slide = presentation.Slides[0];
var rectangle = slide.Shapes.AddRectangle(100, 100, 200, 150);
```

## فهم التدرجات

التدرجات عبارة عن مزيج تدريجي من لونين أو أكثر مما يؤدي إلى إنشاء انتقال سلس بينهما. يمكن أن تكون خطية أو شعاعية، وتضيف عمقًا وبعدًا إلى الأشكال.

## تعبئة الأشكال بالتدرجات الخطية

 لملء شكل بتدرج خطي باستخدام Aspose.Slides، تحتاج إلى إنشاء ملف`LinearGradientFill` الكائن وتطبيقه على الشكل. هنا مثال:

```csharp
// إنشاء تعبئة متدرجة خطية
var gradientFill = new LinearGradientFill();
gradientFill.Angle = 45; // ضبط زاوية التدرج

// إضافة توقفات التدرج
gradientFill.GradientStops.Add(0, Color.Blue);
gradientFill.GradientStops.Add(1, Color.White);

// قم بتطبيق تعبئة متدرجة على الشكل
rectangle.FillFormat.FillType = FillType.Gradient;
rectangle.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
rectangle.FillFormat.GradientFormat.LinearGradientFormat = gradientFill;
```

## تطبيق التدرجات الشعاعية على الأشكال

تنشئ التدرجات الشعاعية مزيجًا دائريًا من الألوان، يشع من نقطة مركزية. إليك كيفية تطبيق تعبئة متدرجة نصف قطرية باستخدام Aspose.Slides:

```csharp
// إنشاء تعبئة متدرجة شعاعي
var gradientFill = new RadialGradientFill();

// إضافة توقفات التدرج
gradientFill.GradientStops.Add(0, Color.Green);
gradientFill.GradientStops.Add(1, Color.Yellow);

// قم بتطبيق تعبئة متدرجة على الشكل
rectangle.FillFormat.FillType = FillType.Gradient;
rectangle.FillFormat.GradientFormat.GradientShape = GradientShape.Radial;
rectangle.FillFormat.GradientFormat.RadialGradientFormat = gradientFill;
```

## الجمع بين التدرجات والشفافية

يمكنك تحسين التأثير المرئي للتدرجات اللونية من خلال تطبيق الشفافية على الشكل. يؤدي هذا إلى إنشاء مزيج أنيق من الألوان ويسمح للخلفية بالظهور قليلاً.

```csharp
// تطبيق الشفافية على الشكل
rectangle.FillFormat.Transparency = 0.5; //ضبط مستوى الشفافية
```

## العمل مع توقفات متدرجة متعددة

تحدد علامات التوقف المتدرجة الألوان والمواضع داخل التدرج. من خلال إضافة نقاط توقف متدرجة متعددة، يمكنك إنشاء تدرجات أكثر تعقيدًا وجاذبية من الناحية المرئية.

```csharp
// إضافة نقاط توقف متدرجة متعددة
gradientFill.GradientStops.Add(0, Color.Red);
gradientFill.GradientStops.Add(0.5, Color.Yellow);
gradientFill.GradientStops.Add(1, Color.Blue);
```

## إضافة كود المصدر إلى مشروعك

 لاستخدام Aspose.Slides لـ .NET، تحتاج إلى إضافة المكتبة إلى مشروعك. يمكنكم تحميل المكتبة من الموقع:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net/).

## تجميع وتشغيل المشروع

بمجرد إضافة مكتبة Aspose.Slides إلى مشروعك، يمكنك البدء في كتابة التعليمات البرمجية لإنشاء شرائح العرض التقديمي ومعالجتها. تأكد من تضمين مساحات الأسماء الضرورية:

```csharp
using Aspose.Slides;
using Aspose.Slides.Fill;
```

## تخصيصات وتأثيرات إضافية

 يقدم Aspose.Slides خيارات وتأثيرات تخصيص متنوعة يمكنك تطبيقها على الأشكال والتدرجات اللونية. استكشف الوثائق للحصول على المزيد من الميزات المتقدمة:[Aspose.Slides لتوثيق .NET](https://reference.aspose.com/slides/net/).

## تصدير العرض التقديمي

بعد تطبيق التدرجات والتخصيصات على العرض التقديمي الخاص بك، يمكنك حفظه بتنسيقات مختلفة، مثل PPTX أو PDF:

```csharp
// احفظ العرض التقديمي في ملف
presentation.Save("MyPresentation.pptx", SaveFormat.Pptx);
```

## خاتمة

يمكن أن يؤدي ملء الأشكال بالتدرجات إلى زيادة المظهر البصري لشرائح العرض التقديمي، مما يجعلها أكثر جاذبية وإبهارًا بصريًا. يوفر Aspose.Slides for .NET الأدوات التي تحتاجها لتطبيق التدرجات اللونية بسهولة، مما يسمح لك بإنشاء عروض تقديمية مذهلة تأسر جمهورك.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لـ .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides لـ .NET من صفحة الإصدارات:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net/).

### هل يمكنني تطبيق الشفافية على الأشكال المملوءة بالتدرج؟

 نعم، يمكنك تطبيق الشفافية على الأشكال المملوءة بالتدرجات اللونية باستخدام`Transparency` ملكية`FillFormat`.

### هل التدرجات الشعاعية أفضل من التدرجات الخطية؟

يعتمد الاختيار بين التدرجات الشعاعية والخطية على التصميم والتأثير الذي تريد تحقيقه. تُنشئ التدرجات الشعاعية مزيجًا دائريًا، بينما تُنشئ التدرجات الخطية انتقالًا خطيًا سلسًا بين الألوان.

### هل يمكنني تخصيص موضع توقفات التدرج؟

نعم، يمكنك تخصيص موضع ولون توقفات التدرج ضمن تعبئة متدرجة. يتيح لك هذا إنشاء تأثيرات متدرجة فريدة ومعقدة.

### هل Aspose.Slides مناسب لمعالجات PowerPoint الأخرى؟

نعم، يقدم Aspose.Slides مجموعة واسعة من الميزات للعمل مع عروض PowerPoint التقديمية، بما في ذلك إضافة الشرائح والنصوص والصور والرسوم المتحركة والمزيد.