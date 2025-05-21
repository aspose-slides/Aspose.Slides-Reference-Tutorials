---
"description": "تعلّم كيفية تحويل عروض PowerPoint التقديمية إلى صيغة SWF باستخدام Aspose.Slides لـ .NET. أنشئ محتوى ديناميكيًا بكل سهولة!"
"linktitle": "تحويل العرض التقديمي إلى تنسيق SWF"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تحويل العرض التقديمي إلى تنسيق SWF"
"url": "/ar/net/presentation-conversion/convert-presentation-to-swf-format/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل العرض التقديمي إلى تنسيق SWF


في عصرنا الرقمي، تُعدّ العروض التقديمية متعددة الوسائط وسيلة تواصل فعّالة. قد ترغب أحيانًا في مشاركة عروضك التقديمية بطريقة أكثر ديناميكية، مثل تحويلها إلى صيغة SWF (Shockwave Flash). سيرشدك هذا الدليل خلال عملية تحويل عرض تقديمي إلى صيغة SWF باستخدام Aspose.Slides لـ .NET.

## ما ستحتاجه

قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:

- Aspose.Slides لـ .NET: إذا لم يكن لديك بالفعل، فيمكنك [قم بتحميله هنا](https://releases.aspose.com/slides/net/).

- ملف العرض التقديمي: ستحتاج إلى ملف عرض تقديمي بتنسيق PowerPoint الذي تريد تحويله إلى تنسيق SWF.

## الخطوة 1: إعداد البيئة الخاصة بك

للبدء، أنشئ مجلدًا لمشروعك. لنسمِّه "مجلد مشروعك". داخل هذا المجلد، ستحتاج إلى وضع الكود المصدري التالي:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// إنشاء كائن عرض تقديمي يمثل ملف عرض تقديمي
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    SwfOptions swfOptions = new SwfOptions();
    swfOptions.ViewerIncluded = false;

    INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
    notesOptions.NotesPosition = NotesPositions.BottomFull;

    // حفظ صفحات العرض التقديمي والملاحظات
    presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
    swfOptions.ViewerIncluded = true;
    presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
```

تأكد من استبدال `"Your Document Directory"` و `"Your Output Directory"` مع المسارات الفعلية التي يوجد بها ملف العرض التقديمي الخاص بك والمكان الذي تريد حفظ ملفات SWF فيه.

## الخطوة 2: تحميل العرض التقديمي

في هذه الخطوة، نقوم بتحميل عرض PowerPoint باستخدام Aspose.Slides:

```csharp
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
```

يستبدل `"HelloWorld.pptx"` مع اسم ملف العرض التقديمي الخاص بك.

## الخطوة 3: تكوين خيارات تحويل SWF

نقوم بتكوين خيارات تحويل SWF لتخصيص الإخراج:

```csharp
SwfOptions swfOptions = new SwfOptions();
swfOptions.ViewerIncluded = false;

INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

يمكنك تعديل هذه الخيارات وفقًا لمتطلباتك.

## الخطوة 4: الحفظ بتنسيق SWF

الآن، نقوم بحفظ العرض التقديمي كملف SWF:

```csharp
presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

سيؤدي هذا السطر إلى حفظ العرض التقديمي الرئيسي كملف SWF.

## الخطوة 5: الحفظ باستخدام الملاحظات

إذا كنت تريد تضمين ملاحظات، استخدم هذا الكود:

```csharp
swfOptions.ViewerIncluded = true;
presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

يحفظ هذا الكود العرض التقديمي مع الملاحظات بتنسيق SWF.

## خاتمة

تهانينا! لقد نجحت في تحويل عرض تقديمي من PowerPoint إلى صيغة SWF باستخدام Aspose.Slides لـ .NET. يُعد هذا مفيدًا بشكل خاص عند مشاركة عروضك التقديمية عبر الإنترنت أو تضمينها في صفحات الويب.

لمزيد من المعلومات والوثائق التفصيلية، يمكنك زيارة [Aspose.Slides مرجع لـ .NET](https://reference.aspose.com/slides/net/).

## الأسئلة الشائعة

### ما هو تنسيق SWF؟
SWF (Shockwave Flash) هو تنسيق الوسائط المتعددة المستخدم في الرسوم المتحركة والألعاب والمحتوى التفاعلي على الويب.

### هل استخدام Aspose.Slides لـ .NET مجاني؟
يُقدّم Aspose.Slides لـ .NET نسخة تجريبية مجانية، ولكن للاستفادة الكاملة من الميزات، قد تحتاج إلى شراء ترخيص. يمكنك الاطلاع على تفاصيل الأسعار والترخيص. [هنا](https://purchase.aspose.com/buy).

### هل يمكنني تجربة Aspose.Slides لـ .NET قبل شراء الترخيص؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET [هنا](https://releases.aspose.com/).

### هل أحتاج إلى مهارات البرمجة لاستخدام Aspose.Slides لـ .NET؟
نعم، يجب أن يكون لديك بعض المعرفة ببرمجة C# لاستخدام Aspose.Slides بشكل فعال.

### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
إذا كان لديك أي أسئلة أو تحتاج إلى مساعدة، يمكنك زيارة [منتدى Aspose.Slides لـ .NET](https://forum.aspose.com/) للحصول على الدعم والمساعدة المجتمعية.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}