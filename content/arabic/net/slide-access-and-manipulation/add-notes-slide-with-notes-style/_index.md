---
title: أضف شريحة ملاحظات بتنسيق ملاحظات أنيق
linktitle: أضف شريحة ملاحظات بتنسيق ملاحظات أنيق
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين عروض PowerPoint التقديمية بتنسيق ملاحظات أنيق باستخدام Aspose.Slides for .NET. يغطي هذا الدليل التفصيلي خطوة بخطوة إضافة شريحة ملاحظات وتطبيق تنسيق جذاب والمزيد.
type: docs
weight: 14
url: /ar/net/slide-access-and-manipulation/add-notes-slide-with-notes-style/
---

## مقدمة إلى Aspose.Slides لـ .NET:

Aspose.Slides for .NET هي مكتبة شاملة تسمح للمطورين بالعمل مع عروض PowerPoint التقديمية في تطبيقات .NET الخاصة بهم. فهو يوفر مجموعة واسعة من الميزات، بما في ذلك إنشاء وقراءة وكتابة ومعالجة الشرائح والأشكال والنصوص والصور والمزيد. في هذا البرنامج التعليمي، سنركز على إضافة شريحة ملاحظات وتطبيق تنسيق أنيق على الملاحظات.

## المتطلبات الأساسية:

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio أو أي بيئة تطوير .NET أخرى.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## إعداد المشروع:

1. قم بإنشاء مشروع .NET جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.Slides for .NET في مشروعك.

## إنشاء عرض تقديمي:

لنبدأ بإنشاء عرض تقديمي جديد لـ PowerPoint باستخدام Aspose.Slides لـ .NET. سنقوم بعد ذلك بإضافة شريحة ملاحظات إلى هذا العرض التقديمي.

```csharp
using Aspose.Slides;
using System;

namespace NotesSlideTutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            // إنشاء عرض تقديمي جديد
            Presentation presentation = new Presentation();

            // احفظ العرض التقديمي
            presentation.Save("MyPresentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## إضافة شريحة ملاحظات:

بعد ذلك، سنضيف شريحة ملاحظات إلى العرض التقديمي. تحتوي شريحة الملاحظات عادةً على معلومات إضافية أو ملاحظات المتحدث المتعلقة بمحتوى الشريحة الرئيسية.

```csharp
// أضف شريحة ملاحظات بعد الشريحة الأولى
NotesSlide notesSlide = presentation.Slides[0].NotesSlideManager.AddNotesSlide();

// أضف محتوى إلى شريحة الملاحظات
notesSlide.NotesTextFrame.Text = "These are the speaker notes for the first slide.";
```

## تنسيق أنيق للملاحظات:

لجعل الملاحظات أكثر جاذبية من الناحية المرئية، يمكننا تطبيق تنسيق أنيق باستخدام Aspose.Slides for .NET. يتضمن ذلك تغيير الخط واللون والحجم وخيارات التنسيق الأخرى.

```csharp
// قم بالوصول إلى إطار النص الخاص بشريحة الملاحظات
ITextFrame notesTextFrame = notesSlide.NotesTextFrame;

// تطبيق التنسيق على النص
IParagraph paragraph = notesTextFrame.Paragraphs[0];
IPortion portion = paragraph.Portions[0];

// تغيير الخط وحجم الخط واللون
portion.PortionFormat.LatinFont = new FontData("Arial");
portion.PortionFormat.FontHeight = 14;
portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.DarkBlue;
```

## خاتمة:

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.Slides لـ .NET لإضافة شريحة ملاحظات بتنسيق أنيق إلى عرض PowerPoint التقديمي. لقد قمنا بتغطية إنشاء عرض تقديمي وإضافة شريحة ملاحظات وتطبيق التنسيق على محتوى الملاحظات. يوفر Aspose.Slides for .NET للمطورين مجموعة أدوات قوية لتحسين عروض PowerPoint التقديمية الخاصة بهم برمجيًا.

## الأسئلة الشائعة

### كيف يمكنني تغيير موضع الملاحظات في شريحة الملاحظات؟

 يمكنك ضبط موضع إطار نص الملاحظات باستخدام`notesSlide.NotesTextFrame.X` و`notesSlide.NotesTextFrame.Y` ملكيات.

### هل يمكنني إضافة صور إلى شريحة الملاحظات؟

 نعم، يمكنك إضافة صور إلى شريحة الملاحظات باستخدام`notesSlide.Shapes.AddPicture()` طريقة.

### هل يتوافق Aspose.Slides for .NET مع تنسيقات PowerPoint المختلفة؟

نعم، يدعم Aspose.Slides for .NET تنسيقات PowerPoint المتنوعة، بما في ذلك PPTX وPPT والمزيد.

### كيف يمكنني تطبيق التنسيق على أجزاء معينة من نص الملاحظات؟

 يمكنك الوصول إلى الأجزاء الموجودة في الفقرة وتطبيق التنسيق باستخدام`portion.PortionFormat` ملكية.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ .NET؟

 للحصول على وثائق وأمثلة مفصلة، يمكنك زيارة[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).