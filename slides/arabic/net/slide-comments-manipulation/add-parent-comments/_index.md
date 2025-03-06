---
title: أضف تعليقات الوالدين إلى الشريحة باستخدام Aspose.Slides
linktitle: إضافة تعليقات الوالدين إلى الشريحة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة التعليقات والردود التفاعلية إلى عروض PowerPoint التقديمية باستخدام Aspose.Slides for .NET. تعزيز المشاركة والتعاون.
weight: 12
url: /ar/net/slide-comments-manipulation/add-parent-comments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


هل تتطلع إلى تحسين عروض PowerPoint التقديمية الخاصة بك بميزات تفاعلية؟ يسمح لك Aspose.Slides for .NET بدمج التعليقات والردود، وإنشاء تجربة ديناميكية وجذابة لجمهورك. في هذا البرنامج التعليمي خطوة بخطوة، سنوضح لك كيفية إضافة تعليقات الوالدين إلى الشرائح باستخدام Aspose.Slides for .NET. دعنا نتعمق ونستكشف هذه الميزة المثيرة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Slides for .NET: تأكد من تثبيت Aspose.Slides for .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).

2. Visual Studio: ستحتاج إلى Visual Studio لإنشاء تطبيق .NET وتشغيله.

3. المعرفة الأساسية بـ C#: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا لبرمجة C#.

الآن بعد أن قمنا بتغطية المتطلبات الأساسية، فلنتابع استيراد مساحات الأسماء الضرورية.

## استيراد مساحات الأسماء

أولاً، ستحتاج إلى استيراد مساحات الأسماء ذات الصلة إلى مشروعك. توفر مساحات الأسماء هذه الفئات والأساليب المطلوبة للعمل مع Aspose.Slides لـ .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

مع توفر المتطلبات الأساسية ومساحات الأسماء، دعنا نقسم العملية إلى خطوات متعددة لإضافة تعليقات الوالدين إلى الشريحة.

## الخطوة 1: إنشاء عرض تقديمي

للبدء، تحتاج إلى إنشاء عرض تقديمي جديد باستخدام Aspose.Slides لـ .NET. سيكون هذا العرض التقديمي بمثابة اللوحة القماشية التي ستضيف تعليقاتك عليها.

```csharp
// المسار إلى دليل الإخراج.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // سيتم وضع الكود الخاص بك لإضافة التعليقات هنا.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 في الكود أعلاه، استبدل`"Output Path"` بالمسار المطلوب لعرض الإخراج الخاص بك.

## الخطوة 2: إضافة مؤلفي التعليق

قبل إضافة التعليقات، تحتاج إلى تحديد مؤلفي هذه التعليقات. في هذا المثال، لدينا مؤلفان، "Author_1" و"Author_2"، يتم تمثيل كل منهما بمثيل من`ICommentAuthor`.

```csharp
// أضف تعليق
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// إضافة الرد على التعليق1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

في هذه الخطوة، نقوم بإنشاء مؤلفين للتعليق ونضيف التعليق الأولي والرد على التعليق.

## الخطوة 3: إضافة المزيد من الردود

لإنشاء بنية هرمية للتعليقات، يمكنك إضافة المزيد من الردود على التعليقات الموجودة. وهنا نضيف ردًا ثانيًا على "التعليق1".

```csharp
// إضافة الرد على التعليق1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

يؤدي هذا إلى إنشاء تدفق للمحادثة داخل العرض التقديمي الخاص بك.

## الخطوة 4: إضافة ردود متداخلة

يمكن أن تحتوي التعليقات على ردود متداخلة أيضًا. لتوضيح ذلك، أضفنا ردًا على "الرد 2 للتعليق 1"، مما أدى إلى إنشاء رد فرعي.

```csharp
// إضافة الرد على الرد
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

تسلط هذه الخطوة الضوء على تعدد استخدامات Aspose.Slides لـ .NET في إدارة التسلسلات الهرمية للتعليقات.

## الخطوة 5: المزيد من التعليقات والردود

يمكنك الاستمرار في إضافة المزيد من التعليقات والردود حسب الحاجة. في هذا المثال، نضيف تعليقين إضافيين وردًا على أحدهما.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

توضح هذه الخطوة كيف يمكنك إنشاء محتوى جذاب وتفاعلي لعروضك التقديمية.

## الخطوة 6: عرض التسلسل الهرمي

لتصور التسلسل الهرمي للتعليق، يمكنك عرضه على وحدة التحكم. هذه الخطوة اختيارية ولكنها يمكن أن تكون مفيدة لتصحيح الأخطاء وفهم البنية.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## الخطوة 7: إزالة التعليقات

في بعض الحالات، قد تحتاج إلى إزالة التعليقات والردود عليها. يوضح مقتطف الشفرة أدناه كيفية إزالة "comment1" وجميع ردوده.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

هذه الخطوة مفيدة لإدارة وتحديث محتوى العرض التقديمي الخاص بك.

باستخدام هذه الخطوات، يمكنك إنشاء عروض تقديمية تحتوي على تعليقات وردود تفاعلية باستخدام Aspose.Slides for .NET. سواء كنت تتطلع إلى إشراك جمهورك أو التعاون مع أعضاء الفريق، فإن هذه الميزة توفر نطاقًا واسعًا من الإمكانيات.

## خاتمة

يوفر Aspose.Slides for .NET مجموعة قوية من الأدوات لتحسين عروض PowerPoint التقديمية. مع إمكانية إضافة التعليقات والردود، يمكنك إنشاء محتوى ديناميكي وتفاعلي يأسر جمهورك. يوضح لك هذا الدليل خطوة بخطوة كيفية إضافة تعليقات الوالدين إلى الشرائح، وإنشاء تسلسلات هرمية، وحتى إزالة التعليقات عند الضرورة. باتباع هذه الخطوات واستكشاف وثائق Aspose.Slides[هنا](https://reference.aspose.com/slides/net/)، يمكنك الارتقاء بعروضك التقديمية إلى المستوى التالي.

## الأسئلة الشائعة

### هل يمكنني إضافة تعليقات إلى شرائح معينة في العرض التقديمي الخاص بي؟
نعم، يمكنك إضافة تعليقات إلى أي شريحة في العرض التقديمي الخاص بك عن طريق تحديد الشريحة المستهدفة عند إنشاء تعليق.

### هل من الممكن تخصيص مظهر التعليقات في العرض التقديمي؟
يسمح لك Aspose.Slides for .NET بتخصيص مظهر التعليقات، بما في ذلك النص ومعلومات المؤلف والموضع على الشريحة.

### هل يمكنني تصدير التعليقات والردود إلى ملف منفصل؟
نعم، يمكنك تصدير التعليقات والردود إلى ملف عرض تقديمي منفصل، كما هو موضح في الخطوة 7.

### هل يتوافق Aspose.Slides for .NET مع أحدث إصدارات PowerPoint؟
تم تصميم Aspose.Slides for .NET للعمل مع مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق مع أحدث الإصدارات.

### هل هناك أي خيارات ترخيص متاحة لـ Aspose.Slides for .NET؟
 نعم، يمكنك استكشاف خيارات الترخيص، بما في ذلك التراخيص المؤقتة، على موقع Aspose[هنا](https://purchase.aspose.com/buy) أو جرب النسخة التجريبية المجانية[هنا](https://releases.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
