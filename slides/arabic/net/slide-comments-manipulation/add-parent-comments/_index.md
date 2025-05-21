---
"description": "تعرّف على كيفية إضافة تعليقات وردود تفاعلية إلى عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. عزّز التفاعل والتعاون."
"linktitle": "إضافة تعليقات الوالدين إلى الشريحة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إضافة تعليقات الوالدين إلى الشريحة باستخدام Aspose.Slides"
"url": "/ar/net/slide-comments-manipulation/add-parent-comments/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة تعليقات الوالدين إلى الشريحة باستخدام Aspose.Slides


هل ترغب في تحسين عروض PowerPoint التقديمية بميزات تفاعلية؟ يتيح لك Aspose.Slides for .NET دمج التعليقات والردود، مما يخلق تجربة تفاعلية وجذابة لجمهورك. في هذا البرنامج التعليمي المفصل، سنوضح لك كيفية إضافة تعليقات رئيسية إلى الشرائح باستخدام Aspose.Slides for .NET. لنبدأ باستكشاف هذه الميزة الشيقة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. Aspose.Slides لـ .NET: تأكد من تثبيت Aspose.Slides لـ .NET. يمكنك تنزيله. [هنا](https://releases.aspose.com/slides/net/).

2. Visual Studio: ستحتاج إلى Visual Studio لإنشاء تطبيق .NET وتشغيله.

3. المعرفة الأساسية بلغة C#: يفترض هذا البرنامج التعليمي أن لديك فهمًا أساسيًا لبرمجة C#.

الآن بعد أن قمنا بتغطية المتطلبات الأساسية، فلننتقل إلى استيراد مساحات الأسماء الضرورية.

## استيراد مساحات الأسماء

أولاً، ستحتاج إلى استيراد مساحات الأسماء ذات الصلة إلى مشروعك. توفر هذه المساحات الأسماء الفئات والطرق اللازمة للعمل مع Aspose.Slides لـ .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

بعد وضع المتطلبات الأساسية ومساحات الأسماء في مكانها، دعنا نقسم العملية إلى خطوات متعددة لإضافة تعليقات رئيسية إلى شريحة.

## الخطوة 1: إنشاء عرض تقديمي

للبدء، عليك إنشاء عرض تقديمي جديد باستخدام Aspose.Slides لـ .NET. سيكون هذا العرض التقديمي بمثابة لوحة لإضافة تعليقاتك.

```csharp
// المسار إلى دليل الإخراج.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // سيتم وضع الكود الخاص بإضافة التعليقات هنا.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

في الكود أعلاه، استبدل `"Output Path"` مع المسار المطلوب لعرض الإخراج الخاص بك.

## الخطوة 2: إضافة مؤلفي التعليقات

قبل إضافة التعليقات، يجب تحديد مؤلفيها. في هذا المثال، لدينا مؤلفان، "Author_1" و"Author_2"، يُمثَّل كلٌّ منهما بمثيل من `ICommentAuthor`.

```csharp
// أضف تعليقًا
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// أضف ردًا على التعليق 1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

في هذه الخطوة، نقوم بإنشاء مؤلفين للتعليق وإضافة التعليق الأولي والرد على التعليق.

## الخطوة 3: إضافة المزيد من الردود

لإنشاء هيكل هرمي للتعليقات، يمكنك إضافة المزيد من الردود على التعليقات الحالية. هنا، نضيف ردًا ثانيًا إلى "التعليق ١".

```csharp
// أضف ردًا على التعليق 1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

يؤدي هذا إلى إنشاء تدفق للمحادثة ضمن العرض التقديمي الخاص بك.

## الخطوة 4: إضافة الردود المتداخلة

يمكن أن تحتوي التعليقات على ردود متداخلة أيضًا. لتوضيح ذلك، نضيف ردًا إلى "الرد ٢ للتعليق ١"، مما يُنشئ ردًا فرعيًا.

```csharp
// أضف ردًا إلى الرد
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

تسلط هذه الخطوة الضوء على تنوع Aspose.Slides لـ .NET في إدارة التسلسلات الهرمية للتعليقات.

## الخطوة 5: المزيد من التعليقات والردود

يمكنك الاستمرار في إضافة المزيد من التعليقات والردود حسب الحاجة. في هذا المثال، نضيف تعليقين إضافيين وردًا على أحدهما.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

توضح هذه الخطوة كيفية إنشاء محتوى جذاب وتفاعلي لعروضك التقديمية.

## الخطوة 6: عرض التسلسل الهرمي

لتصوّر تسلسل التعليقات، يمكنك عرضه على وحدة التحكم. هذه الخطوة اختيارية، ولكنها قد تكون مفيدة لتصحيح الأخطاء وفهم هيكلها.

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

في بعض الحالات، قد تحتاج إلى حذف التعليقات وردودها. يوضح الكود التالي كيفية حذف "comment1" وجميع ردوده.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

تعتبر هذه الخطوة مفيدة لإدارة محتوى العرض التقديمي الخاص بك وتحديثه.

بهذه الخطوات، يمكنك إنشاء عروض تقديمية تتضمن تعليقات وردودًا تفاعلية باستخدام Aspose.Slides لـ .NET. سواءً كنت ترغب في التفاعل مع جمهورك أو التعاون مع أعضاء فريقك، توفر هذه الميزة إمكانيات واسعة.

## خاتمة

يوفر Aspose.Slides for .NET مجموعة أدوات فعّالة لتحسين عروض PowerPoint التقديمية. بفضل إمكانية إضافة التعليقات والردود، يمكنك إنشاء محتوى ديناميكي وتفاعلي يجذب جمهورك. يوضح لك هذا الدليل التفصيلي كيفية إضافة التعليقات الرئيسية إلى الشرائح، وإنشاء تسلسلات هرمية، وحتى إزالة التعليقات عند الحاجة. باتباع هذه الخطوات وتصفح وثائق Aspose.Slides [هنا](https://reference.aspose.com/slides/net/)يمكنك أخذ عروضك التقديمية إلى المستوى التالي.

## الأسئلة الشائعة

### هل يمكنني إضافة تعليقات إلى شرائح محددة ضمن العرض التقديمي الخاص بي؟
نعم، يمكنك إضافة تعليقات إلى أي شريحة في العرض التقديمي الخاص بك عن طريق تحديد الشريحة المستهدفة عند إنشاء تعليق.

### هل من الممكن تخصيص مظهر التعليقات في العرض التقديمي؟
يتيح لك Aspose.Slides for .NET تخصيص مظهر التعليقات، بما في ذلك نصها ومعلومات المؤلف وموضعها على الشريحة.

### هل يمكنني تصدير التعليقات والردود إلى ملف منفصل؟
نعم، يمكنك تصدير التعليقات والردود إلى ملف عرض تقديمي منفصل، كما هو موضح في الخطوة 7.

### هل Aspose.Slides for .NET متوافق مع أحدث إصدارات PowerPoint؟
تم تصميم Aspose.Slides for .NET للعمل مع مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق مع أحدث الإصدارات.

### هل هناك أي خيارات ترخيص متاحة لـ Aspose.Slides لـ .NET؟
نعم، يمكنك استكشاف خيارات الترخيص، بما في ذلك التراخيص المؤقتة، على موقع Aspose الإلكتروني [هنا](https://purchase.aspose.com/buy) أو جرب النسخة التجريبية المجانية [هنا](https://releases.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}