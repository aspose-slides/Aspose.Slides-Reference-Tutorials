---
title: تحويل الشرائح إلى PDF مع الملاحظات
linktitle: تحويل الشرائح إلى PDF مع الملاحظات
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بتحويل شرائح العرض التقديمي التي تحتوي على ملاحظات المتحدث بسهولة إلى PDF باستخدام Aspose.Slides for .NET. الحفاظ على المحتوى والسياق بسلاسة.
weight: 18
url: /ar/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


# اكتب دليلًا تعليميًا خطوة بخطوة حول تحويل الشرائح إلى PDF مع الملاحظات باستخدام Aspose.Slides for .NET

هل تبحث عن طريقة موثوقة لتحويل شرائح PowerPoint إلى تنسيق PDF مع الحفاظ على جميع الملاحظات المهمة؟ لا مزيد من البحث! في هذا البرنامج التعليمي الشامل، سنرشدك خلال عملية استخدام Aspose.Slides for .NET لتحقيق هذه المهمة خطوة بخطوة.

## 1 المقدمة

يمكن أن يكون تحويل شرائح PowerPoint إلى PDF مع الملاحظات أداة قيمة لمشاركة العروض التقديمية مع ضمان الاحتفاظ بالسياق والتعليقات المهمة. يوفر Aspose.Slides for .NET حلاً قويًا لهذه المهمة.

## 2. إعداد بيئتك

قبل أن نتعمق في عملية البرمجة، تأكد من إعداد البيئة اللازمة لديك. انك سوف تحتاج:

- Visual Studio أو بيئة التطوير .NET المفضلة لديك.
- تم تثبيت Aspose.Slides لمكتبة .NET.
- عرض تقديمي لـ PowerPoint يحتوي على الملاحظات التي تريد تحويلها.

## 3. تحميل العرض التقديمي

في كود C# الخاص بك، تحتاج إلى تحميل عرض PowerPoint التقديمي الذي تريد تحويله. وإليك كيف يمكنك القيام بذلك:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. استنساخ الشريحة

للتأكد من أن ملف PDF الخاص بك يتضمن جميع الشرائح الضرورية مع الملاحظات، يمكنك استنساخها من العرض التقديمي الأصلي. إليك الطريقة:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. ضبط حجم الشريحة

قد ترغب في ضبط حجم الشريحة ليناسب ملف PDF الخاص بك. يتيح لك Aspose.Slides for .NET القيام بذلك بسهولة:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. تكوين خيارات PDF

للتحكم في كيفية عرض ملاحظاتك في ملف PDF، يمكنك تكوين خيارات PDF:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. الحفظ بصيغة PDF مع الملاحظات

وأخيرًا، يمكنك حفظ العرض التقديمي الخاص بك كملف PDF مع الملاحظات:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. الاستنتاج

تهانينا! لقد نجحت في تحويل شرائح PowerPoint الخاصة بك إلى تنسيق PDF مع الحفاظ على جميع الملاحظات المهمة. يجعل Aspose.Slides for .NET هذه العملية واضحة وفعالة.

## 9. الأسئلة الشائعة

### س1: هل يمكنني تخصيص تخطيط الملاحظات في ملف PDF؟

 نعم، يمكنك تخصيص تخطيط الملاحظات باستخدام`INotesCommentsLayoutingOptions` في خيارات PDF.

### س2: هل يدعم Aspose.Slides for .NET تنسيقات الإخراج الأخرى إلى جانب PDF؟

نعم، يدعم Aspose.Slides for .NET تنسيقات الإخراج المختلفة، بما في ذلك PPTX وDOCX والمزيد.

### س3: هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ .NET؟

 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET على[https://releases.aspose.com/](https://releases.aspose.com/).

### س4: أين يمكنني الحصول على دعم Aspose.Slides لـ .NET؟

 يمكنك العثور على الدعم والمناقشات المجتمعية على[https://forum.aspose.com/](https://forum.aspose.com/).

### س5: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟

 نعم، يمكنك شراء ترخيص مؤقت من[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

في الختام، باستخدام Aspose.Slides for .NET، يمكنك بسهولة تحويل شرائح PowerPoint إلى تنسيق PDF مع الحفاظ على الملاحظات سليمة. إنها أداة قيمة للمحترفين الذين يحتاجون إلى مشاركة العروض التقديمية مع الزملاء والعملاء مع ضمان عدم فقدان السياق المهم.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
