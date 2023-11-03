---
title: تحويل العرض التقديمي إلى تنسيق SWF
linktitle: تحويل العرض التقديمي إلى تنسيق SWF
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحويل عروض PowerPoint التقديمية إلى تنسيق SWF باستخدام Aspose.Slides لـ .NET. أنشئ محتوى ديناميكيًا دون عناء!
type: docs
weight: 28
url: /ar/net/presentation-conversion/convert-presentation-to-swf-format/
---

في العصر الرقمي الحالي، تعد العروض التقديمية متعددة الوسائط وسيلة قوية للاتصال. في بعض الأحيان، قد ترغب في مشاركة عروضك التقديمية بطريقة أكثر ديناميكية، مثل تحويلها إلى تنسيق SWF (Shockwave Flash). سيرشدك هذا الدليل خلال عملية تحويل العرض التقديمي إلى تنسيق SWF باستخدام Aspose.Slides لـ .NET.

## ماذا ستحتاج

قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:

-  Aspose.Slides for .NET: إذا لم يكن لديك بالفعل، فيمكنك ذلك[قم بتنزيله هنا](https://releases.aspose.com/slides/net/).

- ملف العرض التقديمي: ستحتاج إلى ملف العرض التقديمي PowerPoint الذي تريد تحويله إلى تنسيق SWF.

## الخطوة 1: إعداد بيئتك

للبدء، قم بإنشاء دليل لمشروعك. دعنا نسميه "دليل مشروعك". داخل هذا الدليل، ستحتاج إلى وضع كود المصدر التالي:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف العرض التقديمي
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    SwfOptions swfOptions = new SwfOptions();
    swfOptions.ViewerIncluded = false;

    INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
    notesOptions.NotesPosition = NotesPositions.BottomFull;

    // حفظ صفحات العرض والملاحظات
    presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
    swfOptions.ViewerIncluded = true;
    presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
```

 تأكد من استبدال`"Your Document Directory"` و`"Your Output Directory"` بالمسارات الفعلية حيث يوجد ملف العرض التقديمي الخاص بك والمكان الذي تريد حفظ ملفات SWF فيه.

## الخطوة 2: تحميل العرض التقديمي

في هذه الخطوة، نقوم بتحميل عرض PowerPoint التقديمي باستخدام Aspose.Slides:

```csharp
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
```

 يستبدل`"HelloWorld.pptx"` مع اسم ملف العرض التقديمي الخاص بك.

## الخطوة 3: تكوين خيارات تحويل SWF

نقوم بتكوين خيارات تحويل SWF لتخصيص الإخراج:

```csharp
SwfOptions swfOptions = new SwfOptions();
swfOptions.ViewerIncluded = false;

INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

يمكنك ضبط هذه الخيارات وفقًا لمتطلباتك.

## الخطوة 4: احفظ بتنسيق SWF

الآن نقوم بحفظ العرض التقديمي كملف SWF:

```csharp
presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

سيحفظ هذا السطر العرض التقديمي الرئيسي كملف SWF.

## الخطوة 5: حفظ مع الملاحظات

إذا كنت تريد تضمين الملاحظات، استخدم هذا الرمز:

```csharp
swfOptions.ViewerIncluded = true;
presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

يحفظ هذا الرمز العرض التقديمي مع الملاحظات بتنسيق SWF.

## خاتمة

تهانينا! لقد نجحت في تحويل عرض PowerPoint التقديمي إلى تنسيق SWF باستخدام Aspose.Slides لـ .NET. يمكن أن يكون هذا مفيدًا بشكل خاص عندما تحتاج إلى مشاركة عروضك التقديمية عبر الإنترنت أو تضمينها في صفحات الويب.

 لمزيد من المعلومات والوثائق التفصيلية، يمكنك زيارة[Aspose.Slides كمرجع .NET](https://reference.aspose.com/slides/net/).

## الأسئلة الشائعة

### ما هو تنسيق SWF؟
SWF (Shockwave Flash) هو تنسيق وسائط متعددة يستخدم للرسوم المتحركة والألعاب والمحتوى التفاعلي على الويب.

### هل Aspose.Slides لـ .NET مجاني للاستخدام؟
 يقدم Aspose.Slides for .NET نسخة تجريبية مجانية، ولكن للحصول على الوظائف الكاملة، قد تحتاج إلى شراء ترخيص. يمكنك التحقق من تفاصيل الأسعار والترخيص[هنا](https://purchase.aspose.com/buy).

### هل يمكنني تجربة Aspose.Slides لـ .NET قبل شراء الترخيص؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET[هنا](https://releases.aspose.com/).

### هل أحتاج إلى مهارات البرمجة لاستخدام Aspose.Slides لـ .NET؟
نعم، يجب أن يكون لديك بعض المعرفة ببرمجة C# لاستخدام Aspose.Slides بشكل فعال.

### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
 إذا كان لديك أي أسئلة أو كنت بحاجة إلى المساعدة، يمكنك زيارة[Aspose.Slides لمنتدى .NET](https://forum.aspose.com/) للحصول على الدعم ومساعدة المجتمع.
