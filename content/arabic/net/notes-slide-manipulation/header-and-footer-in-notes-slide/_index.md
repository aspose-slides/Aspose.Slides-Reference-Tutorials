---
title: إدارة الرأس والتذييل في شريحة الملاحظات
linktitle: إدارة الرأس والتذييل في شريحة الملاحظات
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تخصيص الرأس والتذييل في شرائح الملاحظات باستخدام Aspose.Slides لـ .NET. يوفر هذا الدليل خطوة بخطوة أمثلة على التعليمات البرمجية المصدر ويغطي الوصول إلى عناصر التصميم وتعديلها.
type: docs
weight: 11
url: /ar/net/notes-slide-manipulation/header-and-footer-in-notes-slide/
---

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة قوية تتيح للمطورين العمل مع ملفات Microsoft PowerPoint برمجيًا. فهو يتيح معالجة وإنشاء العروض التقديمية والشرائح والأشكال والعناصر المختلفة داخلها. سنركز في هذا الدليل على كيفية إدارة عناصر الرأس والتذييل في شريحة الملاحظات باستخدام Aspose.Slides for .NET.

## إضافة شريحة ملاحظات إلى العرض التقديمي

 للبدء، تأكد من تثبيت Aspose.Slides for .NET. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/net/). بعد التثبيت، قم بإنشاء مشروع جديد في بيئة التطوير .NET المفضلة لديك.

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

class Program
{
    static void Main(string[] args)
    {
        // قم بتحميل العرض التقديمي
        using (Presentation presentation = new Presentation())
        {
            // أضف شريحة جديدة
            ISlide slide = presentation.Slides.AddEmptySlide();
            
            // إضافة شريحة الملاحظات إلى الشريحة الحالية
            INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
            
            // سيتم وضع التعليمات البرمجية الخاصة بك لمعالجة عناصر الرأس والتذييل هنا
            
            // احفظ العرض التقديمي المعدل
            presentation.Save("output.pptx", SaveFormat.Pptx);
        }
    }
}
```

## الوصول إلى عناصر الرأس والتذييل

بمجرد إضافة شريحة ملاحظات إلى العرض التقديمي، يمكنك الوصول إلى عناصر الرأس والتذييل للتخصيص. يمكن أن تتضمن عناصر الرأس والتذييل النص والتاريخ وأرقام الشرائح. استخدم الكود التالي للوصول إلى هذه العناصر:

```csharp
INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
INotesHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

// الوصول إلى نص الرأس
string headerText = headerFooterManager.HeaderText;

// الوصول إلى نص التذييل
string footerText = headerFooterManager.FooterText;

// الوصول إلى التاريخ والوقت
bool isDateTimeVisible = headerFooterManager.IsDateTimeVisible;

//الوصول إلى رقم الشريحة
bool isSlideNumberVisible = headerFooterManager.IsSlideNumberVisible;
```

## تعديل نص الرأس والتذييل

يمكنك بسهولة تعديل نص الرأس والتذييل لتوفير السياق أو أي معلومات أخرى ضرورية. استخدم الكود التالي لتحديث نص الرأس والتذييل:

```csharp
headerFooterManager.SetText(HeaderFooterType.Header, "Your header text");
headerFooterManager.SetText(HeaderFooterType.Footer, "Your footer text");
```

## عناصر تصميم الرأس والتذييل

يتيح لك Aspose.Slides for .NET أيضًا تصميم عناصر الرأس والتذييل وفقًا لتصميم العرض التقديمي الخاص بك. يمكنك تغيير الخط والحجم واللون والمحاذاة. فيما يلي مثال لكيفية تصميم العناصر:

```csharp
ITextStyle textStyle = presentation.Slides[0].TextStyle;
textStyle.FontHeight = 14;
textStyle.FontColor.Color = Color.Blue;
textStyle.Alignment = TextAlignment.Center;

headerFooterManager.SetTextStyle(HeaderFooterType.Header, textStyle);
headerFooterManager.SetTextStyle(HeaderFooterType.Footer, textStyle);
```

## تحديث التاريخ ورقم الشريحة

لتحديث التاريخ ورقم الشريحة تلقائيا، استخدم الكود التالي:

```csharp
headerFooterManager.SetDateTimeVisible(true);
headerFooterManager.SetSlideNumberVisible(true);
```

## حفظ العرض التقديمي المعدل

بعد تخصيص عناصر الرأس والتذييل في شريحة الملاحظات، يمكنك حفظ العرض التقديمي المعدل في ملف:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل

إليك الكود المصدري الكامل لإدارة عناصر الرأس والتذييل في شريحة الملاحظات باستخدام Aspose.Slides for .NET:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

class Program
{
    static void Main(string[] args)
    {
        using (Presentation presentation = new Presentation())
        {
            ISlide slide = presentation.Slides.AddEmptySlide();
            INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
            INotesHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

            // تخصيص عناصر الرأس والتذييل
            headerFooterManager.SetText(HeaderFooterType.Header, "Your header text");
            headerFooterManager.SetText(HeaderFooterType.Footer, "Your footer text");

            ITextStyle textStyle = presentation.Slides[0].TextStyle;
            textStyle.FontHeight = 14;
            textStyle.FontColor.Color = Color.Blue;
            textStyle.Alignment = TextAlignment.Center;

            headerFooterManager.SetTextStyle(HeaderFooterType.Header, textStyle);
            headerFooterManager.SetTextStyle(HeaderFooterType.Footer, textStyle);

            headerFooterManager.SetDateTimeVisible(true);
            headerFooterManager.SetSlideNumberVisible(true);

            // احفظ العرض التقديمي المعدل
            presentation.Save("modified.pptx", SaveFormat.Pptx);
        }
    }
}
```

## خاتمة

في هذا الدليل، اكتشفنا كيفية استخدام Aspose.Slides لـ .NET لإدارة عناصر الرأس والتذييل في شريحة الملاحظات الخاصة بالعرض التقديمي. لقد تعلمت كيفية إضافة شريحة ملاحظات والوصول إلى عناصر الرأس والتذييل وتعديل النص وعناصر النمط وتاريخ التحديث وأرقام الشرائح. تتيح هذه المكتبة القوية إمكانية التخصيص السلس، مما يعزز تجربة العرض التقديمي بشكل عام.

## الأسئلة الشائعة

### كيف يمكنني الوصول إلى عناصر الرأس والتذييل في شريحة الملاحظات؟

 للوصول إلى عناصر الرأس والتذييل، يمكنك استخدام`INotesHeaderFooterManager` الواجهة المقدمة من Aspose.Slides لـ .NET.

### هل يمكنني تصميم نص الرأس والتذييل؟

 نعم، يمكنك تصميم نص الرأس والتذييل باستخدام`SetTextStyle` طريقة. يمكنك تخصيص حجم الخط واللون والمحاذاة والخصائص الأخرى.

### كيف أقوم بتحديث التاريخ ورقم الشريحة تلقائيًا؟

 يمكنك استخدام ال`SetDateTimeVisible` و`SetSlideNumberVisible` طرق لعرض التاريخ ورقم الشريحة تلقائيًا في الرأس والتذييل.

### هل يتوافق Aspose.Slides for .NET مع ملفات PowerPoint؟

نعم، Aspose.Slides for .NET متوافق تمامًا مع ملفات PowerPoint، مما يسمح لك بمعالجة العروض التقديمية وإنشائها برمجيًا.

### أين يمكنني العثور على كود المصدر الكامل لتخصيص الرأس والتذييل؟

يمكنك العثور على مثال التعليمات البرمجية المصدر الكامل في هذا الدليل. راجع قسم "رمز المصدر الكامل" للاطلاع على مقتطف الشفرة.