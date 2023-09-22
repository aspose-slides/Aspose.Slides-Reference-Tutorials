---
title: تحويل عرض HTML مع الصور المضمنة
linktitle: تحويل عرض HTML مع الصور المضمنة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بتحويل عروض HTML التقديمية مع الصور المضمنة بسهولة باستخدام Aspose.Slides لـ .NET. قم بإنشاء ملفات PowerPoint وتخصيصها وحفظها بسلاسة.
type: docs
weight: 11
url: /ar/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---

## 1 المقدمة

يوفر Aspose.Slides for .NET طريقة ملائمة لتحويل عروض PowerPoint التقديمية إلى تنسيق HTML5 مع الحفاظ على الصور المضمنة. يمكن أن يكون هذا مفيدًا بشكل لا يصدق لعرض العروض التقديمية على مواقع الويب أو في تطبيقات الويب.

## 2. المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio أو أي بيئة تطوير C#.
- Aspose.Slides لمكتبة .NET.
- نموذج لعرض PowerPoint التقديمي مع الصور المضمنة.
- المعرفة الأساسية ببرمجة C#.

## 3. إعداد مشروعك

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك. تأكد من أن مكتبة Aspose.Slides for .NET تمت الإشارة إليها بشكل صحيح في مشروعك.

## 4. تحميل العرض التقديمي المصدر

```csharp
string dataDir = "Your Document Directory";
string presentationName = Path.Combine(dataDir, "PresentationDemo.pptx");

using (Presentation pres = new Presentation(presentationName))
{
    // الكود الخاص بك لمعالجة العرض التقديمي موجود هنا
}
```

## 5. تكوين خيارات تحويل HTML

 لتكوين خيارات تحويل HTML، يمكنك استخدام`Html5Options` فصل. فيما يلي مثال لكيفية تعيين بعض الخيارات:

```csharp
Html5Options options = new Html5Options()
{
    EmbedImages = false, // لا تقم بحفظ الصور في مستند HTML5
    OutputPath = "Your Output Directory" // ضبط المسار للصور الخارجية
};
```

## 6. إنشاء دليل الإخراج

قبل حفظ العرض التقديمي بتنسيق HTML5، من الممارسات الجيدة إنشاء دليل الإخراج إذا لم يكن موجودًا بالفعل:

```csharp
string outFilePath = Path.Combine(outPath, "HTMLConversion");

if (!Directory.Exists(outFilePath))
{
    Directory.CreateDirectory(outFilePath);
}
```

## 7. حفظ العرض التقديمي بتنسيق HTML5

الآن، لنحفظ العرض التقديمي بتنسيق HTML5:

```csharp
pres.Save(Path.Combine(outFilePath, "pres.html"), SaveFormat.Html5, options);
```

## 8. الاستنتاج

تهانينا! لقد نجحت في تحويل عرض تقديمي لـ PowerPoint يحتوي على صور مضمنة إلى تنسيق HTML5 باستخدام Aspose.Slides لـ .NET. يمكن أن تكون هذه أداة قيمة لمشاركة عروضك التقديمية عبر الإنترنت.

## 9. الأسئلة الشائعة

**Q1: Can I customize the appearance of the HTML5 presentation?**
نعم، يمكنك تخصيص المظهر عن طريق تعديل ملفات HTML وCSS التي تم إنشاؤها بواسطة Aspose.Slides.

**Q2: Does Aspose.Slides for .NET support other output formats?**
نعم، فهو يدعم تنسيقات الإخراج المختلفة، بما في ذلك PDF والصور والمزيد.

**Q3: Are there any limitations to converting presentations with embedded images?**
على الرغم من قوة Aspose.Slides for .NET، فقد تواجه بعض القيود في العروض التقديمية شديدة التعقيد.

**Q4: Is Aspose.Slides for .NET compatible with the latest PowerPoint versions?**
نعم، فهو متوافق مع ملفات PowerPoint من إصدارات مختلفة، بما في ذلك الإصدارات الأحدث.

**Q5: Where can I find more documentation and resources for Aspose.Slides for .NET?**
 للحصول على وثائق وموارد شاملة، قم بزيارة[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).