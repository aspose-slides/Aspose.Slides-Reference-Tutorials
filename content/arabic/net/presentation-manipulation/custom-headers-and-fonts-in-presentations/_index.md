---
title: الرؤوس والخطوط المخصصة في العروض التقديمية
linktitle: الرؤوس والخطوط المخصصة في العروض التقديمية
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تخصيص الرؤوس والخطوط في العروض التقديمية باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية. تعزيز الجاذبية البصرية والعلامة التجارية دون عناء.
type: docs
weight: 11
url: /ar/net/presentation-manipulation/custom-headers-and-fonts-in-presentations/
---

## مقدمة

تلعب العروض التقديمية دورًا حيويًا في نقل المعلومات بشكل فعال. يؤدي تخصيص الرؤوس والخطوط إلى تحسين المظهر المرئي والعلامة التجارية لعروضك التقديمية. يعمل Aspose.Slides على تبسيط هذه العملية من خلال تقديم مجموعة شاملة من الميزات لمعالجة ملفات PowerPoint برمجيًا.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio: أنت بحاجة إلى تثبيت Visual Studio على جهازك.
-  Aspose.Slides for .NET: قم بتنزيل وتثبيت Aspose.Slides for .NET Library من[هنا](https://downloads.aspose.com/slides/net).
- المعرفة الأساسية بـ C#: الإلمام بأساسيات لغة البرمجة C#.

## إضافة رؤوس مخصصة

## إنشاء رأس

توفر الرؤوس طريقة متسقة لعرض المعلومات عبر الشرائح. لنقم بإنشاء رأس مخصص لعرضنا التقديمي.

```csharp
// قم بتحميل العرض التقديمي
Presentation presentation = new Presentation();

// الوصول إلى الشريحة الرئيسية
SlideMaster slideMaster = presentation.Masters[0] as SlideMaster;

// أضف عنصرًا نائبًا للرأس
slideMaster.HeadersFootersManager.SetHeaderFooterVisibility(HeaderFooterType.Header, true);

// تخصيص نص الرأس والتنسيق
TextHolder header = slideMaster.HeadersFootersManager.GetHeaderFooter(HeaderFooterType.Header);
header.Text = "Your Custom Header Text";
```

## إعداد نص الرأس

بمجرد إنشاء الرأس، يمكنك ضبط نصه لنقل الرسالة المطلوبة.

```csharp
// قم بالوصول إلى الشريحة التي تريد تعيين الرأس فيها
Slide slide = presentation.Slides[0];

// قم بتعيين نص الرأس للشريحة
TextFrame headerTextFrame = slide.HeadersFooters.AddHeader(HeaderFooterType.Header);
headerTextFrame.Text = "Slide-Specific Header Text";
```

## تضمين الخطوط المخصصة

يمكن أن يؤدي استخدام الخطوط الفريدة في العرض التقديمي الخاص بك إلى تحسين جاذبيته المرئية بشكل كبير. إليك كيفية تضمين الخطوط المخصصة باستخدام Aspose.Slides.

```csharp
// قم بتحميل الخط المخصص
FontDefinition fontDefinition = new FontDefinition(FontSources.FontFiles("path/to/your/font.ttf"));

// تضمين الخط
presentation.FontsManager.EmbeddedFonts.Add(fontDefinition);
```

## تطبيق الخطوط على النص

قم بتطبيق الخط المخصص على نص محدد داخل الشرائح الخاصة بك.

```csharp
// الوصول إلى الشريحة
Slide slide = presentation.Slides[0];

// أضف مربع نص
ITextFrame textFrame = slide.Shapes.AddTextFrame("Your Text Here");

// تطبيق الخط المخصص على النص
textFrame.Paragraphs[0].Portions[0].PortionFormat.LatinFont = fontDefinition;
```

## خاتمة

تلعب الرؤوس والخطوط المخصصة دورًا مهمًا في جعل عروضك التقديمية جذابة ومتماسكة بصريًا. باستخدام Aspose.Slides for .NET، يمكنك بسهولة إضافة الرؤوس وتخصيصها، بالإضافة إلى تضمين الخطوط المخصصة وتطبيقها لتحسين المظهر العام لعروضك التقديمية.

## الأسئلة الشائعة

## كيف يمكنني تنزيل Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides لـ .NET من[هذا الرابط](https://downloads.aspose.com/slides/net).

## هل يمكنني استخدام خطوط مختلفة لشرائح مختلفة؟

نعم، يمكنك تطبيق خطوط مختلفة على شرائح مختلفة باستخدام Aspose.Slides for .NET. ما عليك سوى اتباع الأمثلة المقدمة لتخصيص الخطوط لنص معين داخل الشرائح الخاصة بك.

## هل يتم الاحتفاظ بالخط المخصص المضمن عند مشاركة العرض التقديمي؟

نعم، سيتم الاحتفاظ بالخطوط المخصصة المضمنة عند مشاركة العرض التقديمي. لا يحتاج المستلم إلى تثبيت الخط على نظامه لعرض العرض التقديمي بشكل صحيح.

## هل يمكنني إضافة رؤوس إلى الشرائح الفردية؟

قطعاً! يمكنك إضافة رؤوس إلى شرائح فردية باستخدام التقنيات المذكورة في المقالة. يمكن أن يكون لكل شريحة نص رأس مخصص خاص بها.

## كيف يمكنني الوصول إلى رأس/تذييل الشريحة الرئيسية؟

 يمكنك الوصول إلى رأس/تذييل الشريحة الرئيسية باستخدام الملف`HeadersFootersManager` فئة مقدمة من Aspose.Slides لـ .NET. يتيح لك ذلك التحكم في محتوى الرأس والتذييل وتخصيصه لشرائحك.