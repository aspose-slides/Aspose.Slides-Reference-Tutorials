---
title: كيفية تحويل شرائح العرض التقديمي الفردية
linktitle: كيفية تحويل شرائح العرض التقديمي الفردية
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحويل شرائح العرض التقديمي الفردية بسهولة باستخدام Aspose.Slides for .NET. إنشاء الشرائح ومعالجتها وحفظها برمجياً.
weight: 12
url: /ar/net/presentation-conversion/how-to-convert-individual-presentation-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة عن Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة غنية بالميزات تمكن المطورين من العمل مع عروض PowerPoint التقديمية برمجياً. فهو يوفر مجموعة واسعة من الفئات والأساليب التي تسمح لك بإنشاء ملفات العرض التقديمي ومعالجتها وتحويلها بتنسيقات مختلفة.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Slides for .NET: تأكد من تثبيت Aspose.Slides for .NET وتكوينه في بيئة التطوير الخاصة بك. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/slides/net/).

- ملف العرض التقديمي: ستحتاج إلى ملف عرض تقديمي لـ PowerPoint (PPTX) يحتوي على الشرائح التي تريد تحويلها. تأكد من أن ملف العرض التقديمي اللازم جاهز.

- محرر التعليمات البرمجية: استخدم محرر التعليمات البرمجية المفضل لديك لتنفيذ التعليمات البرمجية المصدر المتوفرة. سيكون أي محرر أكواد يدعم C# كافيًا.

## تهيئة البيئة
لنبدأ بإعداد بيئة التطوير الخاصة بك لإعداد مشروعك لتحويل الشرائح الفردية. اتبع الخطوات التالية:

1. افتح محرر التعليمات البرمجية الخاص بك وقم بإنشاء مشروع جديد أو افتح مشروعًا موجودًا حيث تريد تنفيذ وظيفة تحويل الشرائح.

2. أضف مرجعًا إلى مكتبة Aspose.Slides for .NET في مشروعك. يمكنك عادةً القيام بذلك عن طريق النقر بزر الماوس الأيمن على مشروعك في "مستكشف الحلول"، وتحديد "إضافة"، ثم "مرجع". استعرض للوصول إلى ملف Aspose.Slides DLL الذي قمت بتنزيله مسبقًا وأضفه كمرجع.

3. أنت الآن جاهز لدمج كود المصدر المقدم في مشروعك. تأكد من أن الكود المصدري لديك جاهز للخطوة التالية.

## جارٍ تحميل العرض التقديمي
يركز القسم الأول من الكود على تحميل عرض PowerPoint التقديمي. هذه الخطوة ضرورية للوصول إلى الشرائح والعمل معها داخل العرض التقديمي.

```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx"))
{
    // رمز تحويل الشرائح موجود هنا
}
```

 تأكد من استبدال`"Your Document Directory"` باستخدام مسار الدليل الفعلي حيث يوجد ملف العرض التقديمي الخاص بك.

## خيارات تحويل HTML
يناقش هذا الجزء من التعليمات البرمجية خيارات تحويل HTML. ستتعلم كيفية تخصيص هذه الخيارات لتتناسب مع متطلباتك.

```csharp
HtmlOptions htmlOptions = new HtmlOptions();
htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(new CustomFormattingController());
INotesCommentsLayoutingOptions notesOptions = htmlOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

قم بتخصيص هذه الخيارات للتحكم في تنسيق وتخطيط شرائح HTML المحولة.

## التكرار عبر الشرائح
في هذا القسم، نشرح كيفية تكرار كل شريحة في العرض التقديمي لضمان معالجة كل شريحة.

```csharp
for (int i = 0; i < presentation.Slides.Count; i++)
{
    // رمز حفظ الشرائح أثناء ظهور HTML هنا
}
```

تتكرر هذه الحلقة عبر جميع الشرائح في العرض التقديمي.

## الحفظ بتنسيق HTML
يتعامل الجزء الأخير من الكود مع حفظ كل شريحة كملف HTML فردي.

```csharp
presentation.Save(dataDir + "Individual Slide" + (i + 1) + "_out.html", new[] { i + 1 }, SaveFormat.Html, htmlOptions);
```

هنا، يحفظ الكود كل شريحة كملف HTML باسم فريد يعتمد على رقم الشريحة.

## الخطوة 5: التنسيق المخصص (اختياري)
 إذا كنت ترغب في تطبيق تنسيق مخصص على مخرجات HTML، فيمكنك استخدام`CustomFormattingController` فصل. يتيح لك هذا القسم التحكم في تنسيق الشرائح الفردية.
```csharp
public class CustomFormattingController : IHtmlFormattingController
        {
            void IHtmlFormattingController.WriteDocumentStart(IHtmlGenerator generator, IPresentation presentation)
            {}

            void IHtmlFormattingController.WriteDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
            {}

            void IHtmlFormattingController.WriteSlideStart(IHtmlGenerator generator, ISlide slide)
            {
                generator.AddHtml(string.Format(SlideHeader, generator.SlideIndex + 1));
            }

            void IHtmlFormattingController.WriteSlideEnd(IHtmlGenerator generator, ISlide slide)
            {
                generator.AddHtml(SlideFooter);
            }

            void IHtmlFormattingController.WriteShapeStart(IHtmlGenerator generator, IShape shape)
            {}

            void IHtmlFormattingController.WriteShapeEnd(IHtmlGenerator generator, IShape shape)
            {}

            private const string SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
            private const string SlideFooter = "</div>";
        }
```

## معالجة الأخطاء

تعد معالجة الأخطاء أمرًا مهمًا للتأكد من أن تطبيقك يتعامل مع الاستثناءات بأمان. يمكنك استخدام كتل محاولة الالتقاط لمعالجة الاستثناءات المحتملة التي قد تحدث أثناء عملية التحويل.

## وظائف إضافية

 يوفر Aspose.Slides for .NET نطاقًا واسعًا من الوظائف الإضافية، مثل إضافة النصوص والأشكال والرسوم المتحركة والمزيد إلى العروض التقديمية الخاصة بك. استكشف الوثائق لمزيد من المعلومات:[Aspose.Slides لتوثيق .NET](https://reference.aspose.com/slides/net).

## خاتمة

أصبح تحويل شرائح العرض التقديمي الفردية أمرًا سهلاً باستخدام Aspose.Slides for .NET. إن مجموعة الميزات الشاملة وواجهة برمجة التطبيقات (API) البديهية تجعله خيارًا مفضلاً للمطورين الذين يتطلعون إلى العمل مع عروض PowerPoint التقديمية برمجيًا. سواء كنت تقوم بإنشاء حل عرض تقديمي مخصص أو تحتاج إلى أتمتة تحويلات الشرائح، فإن Aspose.Slides for .NET يلبي احتياجاتك.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لـ .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides for .NET من موقع الويب:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net).

### هل Aspose.Slides مناسب للتطوير عبر الأنظمة الأساسية؟

نعم، يدعم Aspose.Slides for .NET التطوير عبر الأنظمة الأساسية، مما يسمح لك بإنشاء تطبيقات لأنظمة Windows وmacOS وLinux.

### هل يمكنني تحويل الشرائح إلى تنسيقات أخرى غير الصور؟

قطعاً! يدعم Aspose.Slides for .NET التحويل إلى تنسيقات مختلفة، بما في ذلك PDF وSVG والمزيد.

### هل يقدم Aspose.Slides الوثائق والأمثلة؟

 نعم، يمكنك العثور على الوثائق التفصيلية وأمثلة التعليمات البرمجية على صفحة وثائق Aspose.Slides for .NET:[Aspose.Slides لتوثيق .NET](https://reference.aspose.com/slides/net).

### هل يمكنني تخصيص تخطيطات الشرائح باستخدام Aspose.Slides؟

نعم، يمكنك تخصيص تخطيطات الشرائح وإضافة الأشكال والصور وتطبيق الرسوم المتحركة باستخدام Aspose.Slides for .NET، مما يمنحك التحكم الكامل في العروض التقديمية الخاصة بك.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
