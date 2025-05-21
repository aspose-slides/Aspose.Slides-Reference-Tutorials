---
"description": "تعلّم كيفية تحويل شرائح العروض التقديمية الفردية بسهولة باستخدام Aspose.Slides لـ .NET. أنشئ الشرائح، وعالجها، واحفظها برمجيًا."
"linktitle": "كيفية تحويل شرائح العرض التقديمي الفردية"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "كيفية تحويل شرائح العرض التقديمي الفردية"
"url": "/ar/net/presentation-conversion/how-to-convert-individual-presentation-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل شرائح العرض التقديمي الفردية


## مقدمة لـ Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة غنية بالميزات تُمكّن المطورين من العمل مع عروض PowerPoint التقديمية برمجيًا. توفر مجموعة شاملة من الفئات والأساليب التي تُمكّنك من إنشاء ملفات العروض التقديمية ومعالجتها وتحويلها بتنسيقات متنوعة.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.Slides لـ .NET: تأكد من تثبيت Aspose.Slides لـ .NET وتهيئته في بيئة التطوير لديك. يمكنك تنزيله من [موقع إلكتروني](https://releases.aspose.com/slides/net/).

- ملف العرض التقديمي: ستحتاج إلى ملف عرض تقديمي بصيغة PowerPoint (PPTX) يحتوي على الشرائح التي ترغب في تحويلها. تأكد من تجهيز ملف العرض التقديمي اللازم.

- محرر الكود: استخدم محرر الكود المفضل لديك لتنفيذ الكود المصدري المُقدَّم. أي محرر كود يدعم C# سيكون كافيًا.

## إعداد البيئة
لنبدأ بإعداد بيئة التطوير الخاصة بك لتجهيز مشروعك لتحويل الشرائح الفردية. اتبع الخطوات التالية:

1. افتح محرر التعليمات البرمجية الخاص بك وقم بإنشاء مشروع جديد أو افتح مشروعًا موجودًا حيث تريد تنفيذ وظيفة تحويل الشرائح.

2. أضف مرجعًا إلى مكتبة Aspose.Slides for .NET في مشروعك. يمكنك عادةً القيام بذلك بالنقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول، ثم اختيار "إضافة"، ثم "مرجع". انتقل إلى ملف Aspose.Slides DLL الذي نزّلته سابقًا وأضفه كمرجع.

3. أنت الآن جاهز لدمج الكود المصدري المُقدّم في مشروعك. تأكد من جاهزيته للخطوة التالية.

## تحميل العرض التقديمي
يُركّز القسم الأول من الكود على تحميل عرض PowerPoint. هذه الخطوة أساسية للوصول إلى الشرائح داخل العرض التقديمي والعمل عليها.

```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx"))
{
    // كود تحويل الشريحة يظهر هنا
}
```

تأكد من استبدال `"Your Document Directory"` مع مسار الدليل الفعلي الذي يوجد به ملف العرض التقديمي الخاص بك.

## خيارات تحويل HTML
يناقش هذا الجزء من الكود خيارات تحويل HTML. ستتعلم كيفية تخصيص هذه الخيارات لتناسب احتياجاتك.

```csharp
HtmlOptions htmlOptions = new HtmlOptions();
htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(new CustomFormattingController());
INotesCommentsLayoutingOptions notesOptions = htmlOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

قم بتخصيص هذه الخيارات للتحكم في تنسيق وتخطيط شرائح HTML المحولة.

## التكرار عبر الشرائح
في هذا القسم، نشرح كيفية المرور على كل شريحة في العرض التقديمي للتأكد من معالجة كل شريحة.

```csharp
for (int i = 0; i < presentation.Slides.Count; i++)
{
    // يظهر هنا الكود لحفظ الشرائح بصيغة HTML
}
```

تتكرر هذه الحلقة عبر جميع الشرائح في العرض التقديمي.

## الحفظ بصيغة HTML
الجزء الأخير من الكود يتعامل مع حفظ كل شريحة كملف HTML فردي.

```csharp
presentation.Save(dataDir + "Individual Slide" + (i + 1) + "_out.html", new[] { i + 1 }, SaveFormat.Html, htmlOptions);
```

هنا، يقوم الكود بحفظ كل شريحة كملف HTML باسم فريد استنادًا إلى رقم الشريحة.

## الخطوة 5: التنسيق المخصص (اختياري)
إذا كنت ترغب في تطبيق تنسيق مخصص على مخرجات HTML الخاصة بك، فيمكنك استخدام `CustomFormattingController` يسمح لك هذا القسم بالتحكم في تنسيق الشرائح الفردية.
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

معالجة الأخطاء مهمة لضمان معالجة تطبيقك للاستثناءات بسلاسة. يمكنك استخدام كتل try-catch لمعالجة الاستثناءات المحتملة التي قد تحدث أثناء عملية التحويل.

## وظائف إضافية

يوفر Aspose.Slides لـ .NET مجموعة واسعة من الوظائف الإضافية، مثل إضافة النصوص والأشكال والرسوم المتحركة وغيرها إلى عروضك التقديمية. اطلع على الوثائق لمزيد من المعلومات: [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net).

## خاتمة

تحويل شرائح العروض التقديمية الفردية أصبح سهلاً للغاية مع Aspose.Slides لـ .NET. فمجموعته الشاملة من الميزات وواجهة برمجة التطبيقات سهلة الاستخدام تجعله الخيار الأمثل للمطورين الذين يرغبون في العمل مع عروض PowerPoint التقديمية برمجيًا. سواء كنت تُنشئ حلاً مخصصًا للعروض التقديمية أو تحتاج إلى أتمتة تحويل الشرائح، فإن Aspose.Slides لـ .NET يُلبي احتياجاتك.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لـ .NET؟

يمكنك تنزيل مكتبة Aspose.Slides لـ .NET من الموقع الإلكتروني: [تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net).

### هل Aspose.Slides مناسب للتطوير عبر الأنظمة الأساسية؟

نعم، يدعم Aspose.Slides for .NET التطوير عبر الأنظمة الأساسية، مما يسمح لك بإنشاء تطبيقات لنظامي التشغيل Windows وmacOS وLinux.

### هل يمكنني تحويل الشرائح إلى تنسيقات أخرى غير الصور؟

بالتأكيد! يدعم Aspose.Slides لـ .NET التحويل إلى صيغ متعددة، بما في ذلك PDF وSVG وغيرها.

### هل يوفر Aspose.Slides توثيقًا وأمثلة؟

نعم، يمكنك العثور على وثائق مفصلة وأمثلة التعليمات البرمجية على صفحة وثائق Aspose.Slides لـ .NET: [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net).

### هل يمكنني تخصيص تخطيطات الشرائح باستخدام Aspose.Slides؟

نعم، يمكنك تخصيص تخطيطات الشرائح وإضافة الأشكال والصور وتطبيق الرسوم المتحركة باستخدام Aspose.Slides لـ .NET، مما يتيح لك التحكم الكامل في العروض التقديمية الخاصة بك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}