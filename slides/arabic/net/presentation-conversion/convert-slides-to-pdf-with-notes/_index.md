---
"description": "حوّل شرائح العرض التقديمي مع ملاحظات المتحدث إلى ملف PDF بسهولة باستخدام Aspose.Slides لـ .NET. حافظ على المحتوى والسياق بسلاسة."
"linktitle": "تحويل الشرائح إلى PDF مع الملاحظات"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تحويل الشرائح إلى PDF مع الملاحظات"
"url": "/ar/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل الشرائح إلى PDF مع الملاحظات


# اكتب دليلًا تعليميًا خطوة بخطوة حول تحويل الشرائح إلى ملف PDF مع الملاحظات باستخدام Aspose.Slides لـ .NET

هل تبحث عن طريقة موثوقة لتحويل شرائح PowerPoint إلى صيغة PDF مع الحفاظ على جميع الملاحظات المهمة؟ لا داعي للبحث أكثر! في هذا البرنامج التعليمي الشامل، سنرشدك خطوة بخطوة خلال عملية استخدام Aspose.Slides for .NET لتحقيق هذه المهمة.

## 1. المقدمة

يُمكن أن يكون تحويل شرائح PowerPoint إلى PDF مع الملاحظات أداةً قيّمةً لمشاركة العروض التقديمية مع ضمان الاحتفاظ بالسياق والتعليقات المهمة. يُوفر Aspose.Slides for .NET حلاً فعّالاً لهذه المهمة.

## 2. إعداد بيئتك

قبل الخوض في عملية البرمجة، تأكد من إعداد البيئة اللازمة. ستحتاج إلى:

- Visual Studio أو بيئة التطوير .NET المفضلة لديك.
- تم تثبيت Aspose.Slides لمكتبة .NET.
- عرض تقديمي على PowerPoint يحتوي على ملاحظات تريد تحويلها.

## 3. تحميل العرض التقديمي

في كود C# الخاص بك، عليك تحميل عرض PowerPoint التقديمي الذي تريد تحويله. إليك كيفية القيام بذلك:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. استنساخ الشريحة

لضمان احتواء ملف PDF على جميع الشرائح والملاحظات اللازمة، يمكنك استنساخها من العرض التقديمي الأصلي. إليك الطريقة:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. ضبط حجم الشريحة

قد ترغب في تعديل حجم الشريحة لتناسب ملف PDF. يتيح لك Aspose.Slides for .NET القيام بذلك بسهولة:

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

وأخيرًا، يمكنك حفظ العرض التقديمي الخاص بك بتنسيق PDF مع الملاحظات:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. الخاتمة

تهانينا! لقد نجحت في تحويل شرائح PowerPoint إلى صيغة PDF مع الحفاظ على جميع الملاحظات المهمة. يُسهّل Aspose.Slides for .NET هذه العملية ويجعلها أكثر فعالية.

## 9. الأسئلة الشائعة

### س1: هل يمكنني تخصيص تخطيط الملاحظات في ملف PDF؟

نعم، يمكنك تخصيص تخطيط الملاحظات باستخدام `INotesCommentsLayoutingOptions` في خيارات PDF.

### س2: هل يدعم Aspose.Slides for .NET تنسيقات إخراج أخرى إلى جانب PDF؟

نعم، يدعم Aspose.Slides for .NET تنسيقات إخراج مختلفة، بما في ذلك PPTX وDOCX والمزيد.

### س3: هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ .NET؟

نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET على [https://releases.aspose.com/](https://releases.aspose.com/).

### س4: أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟

يمكنك العثور على الدعم ومناقشات المجتمع في [https://forum.aspose.com/](https://forum.aspose.com/).

### س5: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟

نعم، يمكنك شراء ترخيص مؤقت في [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

في الختام، باستخدام Aspose.Slides لـ .NET، يمكنك بسهولة تحويل شرائح PowerPoint إلى صيغة PDF مع الحفاظ على الملاحظات. إنها أداة قيّمة للمحترفين الذين يحتاجون إلى مشاركة العروض التقديمية مع زملائهم وعملائهم مع ضمان حفظ السياق المهم.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}