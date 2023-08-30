---
title: إضافة ارتباط تشعبي إلى الشريحة
linktitle: إضافة ارتباط تشعبي إلى الشريحة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة ارتباطات تشعبية إلى الشرائح في PowerPoint باستخدام Aspose.Slides لـ .NET. تعزيز العروض التقديمية بالمحتوى التفاعلي.
type: docs
weight: 12
url: /ar/net/hyperlink-manipulation/add-hyperlink/
---

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة شاملة تمكن المطورين من إنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها دون الاعتماد على Microsoft Office. فهو يوفر مجموعة واسعة من الميزات، بما في ذلك إضافة وإدارة الارتباطات التشعبية في الشرائح.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio على نظامك.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://downloads.aspose.com/slides/net).

## إضافة ارتباط تشعبي إلى نص في شريحة

1. قم بإنشاء مشروع C# جديد في Visual Studio.
2. قم بإضافة مرجع إلى Aspose.Slides DLL في مشروعك.
3. استخدم التعليمة البرمجية التالية لإضافة ارتباط تشعبي إلى نص في شريحة:

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
Presentation presentation = new Presentation("presentation.pptx");

// الوصول إلى الشريحة
ISlide slide = presentation.Slides[0];

// الوصول إلى مربع النص
ITextFrame textFrame = slide.Shapes[0] as ITextFrame;

// إضافة جزء من النص مع ارتباط تشعبي
textFrame.Paragraphs[0].Portions[0].Text = "Visit our website!";
textFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new HyperlinkInfo("https://www.example.com"، HyperlinkAction.MouseClick)؛
```

## إضافة ارتباط تشعبي إلى شكل في شريحة

1. اتبع الخطوات المذكورة أعلاه لإنشاء مشروع C# جديد وإضافة مرجع Aspose.Slides.
2. استخدم التعليمة البرمجية التالية لإضافة ارتباط تشعبي إلى شكل في شريحة:

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
Presentation presentation = new Presentation("presentation.pptx");

// الوصول إلى الشريحة
ISlide slide = presentation.Slides[0];

// الوصول إلى الشكل
IShape shape = slide.Shapes[1];

// إضافة ارتباط تشعبي إلى الشكل
shape.HyperlinkClick = new HyperlinkInfo("https://www.example.com"، HyperlinkAction.MouseClick)؛
```

## إضافة ارتباط تشعبي إلى شريحة

1. اتبع الخطوات الأولية لإعداد مشروع C# الخاص بك والرجوع إلى مكتبة Aspose.Slides.
2. استخدم التعليمة البرمجية التالية لإضافة ارتباط تشعبي إلى شريحة:

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
Presentation presentation = new Presentation("presentation.pptx");

// الوصول إلى الشريحة
ISlide slide = presentation.Slides[2];

// إضافة ارتباط تشعبي إلى الشريحة
slide.HyperlinkClick = new HyperlinkInfo("https://www.example.com"، HyperlinkAction.MouseClick)؛
```

## إضافة الارتباطات التشعبية الخارجية

وبصرف النظر عن الارتباطات التشعبية الداخلية، يمكنك أيضًا إضافة ارتباطات تشعبية خارجية إلى الشرائح الخاصة بك. استخدم نفس الطريقة المذكورة أعلاه، ولكن قم بتوفير عنوان URL الخارجي كهدف الارتباط التشعبي.

## تعديل وإزالة الارتباطات التشعبية

لتعديل ارتباط تشعبي موجود أو إزالته، يمكنك الوصول إلى خصائص الارتباط التشعبي لعنصر الشريحة المعني وإجراء التغييرات اللازمة.

## خاتمة

تعد إضافة الارتباطات التشعبية إلى الشرائح باستخدام Aspose.Slides for .NET عملية مباشرة يمكنها تحسين تفاعل العروض التقديمية بشكل كبير. سواء كنت تريد الارتباط بموارد خارجية أو إنشاء التنقل داخل الشرائح الخاصة بك، فإن Aspose.Slides يوفر الأدوات التي تحتاجها لتحقيق هذه المهام بكفاءة.

## الأسئلة الشائعة

### كيف يمكنني إزالة ارتباط تشعبي من جزء من النص؟

 لإزالة ارتباط تشعبي من جزء من النص، يمكنك ببساطة تعيين`HyperlinkClick` الملكية ل`null` لهذا الجزء.

### هل يمكنني إضافة ارتباطات تشعبية إلى أشكال أخرى غير مربعات النص؟

نعم، يمكنك إضافة ارتباطات تشعبية إلى أشكال مختلفة، بما في ذلك الصور والأشكال المخصصة، باستخدام`HyperlinkClick` ملكية.

### هل Aspose.Slides متوافق مع تنسيقات PowerPoint المختلفة؟

نعم، يدعم Aspose.Slides تنسيقات PowerPoint المتنوعة، بما في ذلك PPTX وPPT والمزيد.

### كيف يمكنني اختبار الارتباطات التشعبية في العرض التقديمي الخاص بي؟

يمكنك تشغيل العرض التقديمي في عارض أو محرر PowerPoint لاختبار وظيفة الارتباطات التشعبية.

### أين يمكنني تنزيل Aspose.Slides لمكتبة .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides for .NET من موقع Aspose الإلكتروني:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net).