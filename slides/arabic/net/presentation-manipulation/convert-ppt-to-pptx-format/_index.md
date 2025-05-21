---
"description": "تعلّم كيفية تحويل ملفات PPT إلى PPTX بسهولة باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع أمثلة برمجية لتحويل التنسيقات بسلاسة."
"linktitle": "تحويل تنسيق PPT إلى تنسيق PPTX"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تحويل تنسيق PPT إلى تنسيق PPTX"
"url": "/ar/net/presentation-manipulation/convert-ppt-to-pptx-format/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل تنسيق PPT إلى تنسيق PPTX


إذا كنتَ بحاجةٍ لتحويل ملفات PowerPoint من تنسيق PPT القديم إلى تنسيق PPTX الأحدث باستخدام .NET، فأنتَ في المكان المناسب. في هذا البرنامج التعليمي المُفصّل، سنشرح لك العملية خطوة بخطوة باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ .NET. مع هذه المكتبة القوية، يُمكنك إجراء هذه التحويلات بسهولة ويسر. هيا بنا نبدأ!

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من إعداد ما يلي:

- Visual Studio: تأكد من تثبيت Visual Studio وتجهيزه لتطوير .NET.
- Aspose.Slides لـ .NET: قم بتنزيل وتثبيت مكتبة Aspose.Slides لـ .NET من [هنا](https://releases.aspose.com/slides/net/).

## إعداد المشروع

1. إنشاء مشروع جديد: افتح Visual Studio وقم بإنشاء مشروع C# جديد.

2. إضافة مرجع إلى Aspose.Slides: انقر بزر الماوس الأيمن على مشروعك في مستكشف الحلول، واختر "إدارة حزم NuGet"، ثم ابحث عن "Aspose.Slides". ثبّت الحزمة.

3. استيراد المساحات المطلوبة:

```csharp
using Aspose.Slides;
```

## تحويل PPT إلى PPTX

الآن بعد أن قمنا بإعداد مشروعنا، دعنا نكتب الكود لتحويل ملف PPT إلى PPTX.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// إنشاء كائن عرض تقديمي يمثل ملف PPT
Presentation pres = new Presentation(srcFileName);

// حفظ العرض التقديمي بتنسيق PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

في مقتطف الكود هذا:

- `dataDir` يجب استبداله بمسار الدليل الذي يوجد به ملف PPT الخاص بك.
- `outPath` يجب استبداله بالدليل الذي تريد حفظ ملف PPTX المحول فيه.
- `srcFileName` هو اسم ملف PPT المدخل الخاص بك.
- `destFileName` هو الاسم المطلوب لملف PPTX الناتج.

## خاتمة

تهانينا! لقد نجحت في تحويل عرض تقديمي من PowerPoint من تنسيق PPT إلى PPTX باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ .NET. تُبسط هذه المكتبة القوية المهام المعقدة كهذه، مما يجعل تجربة تطوير .NET أكثر سلاسة.

إذا لم تكن قد فعلت ذلك بالفعل، [تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net/) واستكشاف قدراتها بشكل أكبر.

لمزيد من الدروس والنصائح، قم بزيارة موقعنا [التوثيق](https://reference.aspose.com/slides/net/).

## الأسئلة الشائعة

### 1. ما هو Aspose.Slides لـ .NET؟
Aspose.Slides for .NET هي مكتبة .NET تسمح للمطورين بإنشاء عروض PowerPoint ومعالجتها وتحويلها برمجيًا.

### 2. هل يمكنني تحويل تنسيقات أخرى إلى PPTX باستخدام Aspose.Slides لـ .NET؟
نعم، يدعم Aspose.Slides for .NET تنسيقات مختلفة، بما في ذلك PPT، وPPTX، وODP، والمزيد.

### 3. هل استخدام Aspose.Slides لـ .NET مجاني؟
لا، إنها مكتبة تجارية، ولكن يمكنك استكشافها [نسخة تجريبية مجانية](https://releases.aspose.com/) لتقييم ميزاته.

### 4. هل هناك أي تنسيقات مستندات أخرى يدعمها Aspose.Slides لـ .NET؟
نعم، يدعم Aspose.Slides for .NET أيضًا العمل مع مستندات Word، وجداول بيانات Excel، وتنسيقات الملفات الأخرى.

### 5. أين يمكنني الحصول على الدعم أو طرح الأسئلة حول Aspose.Slides لـ .NET؟
يمكنك العثور على إجابات لأسئلتك وطلب الدعم في [منتديات Aspose.Slides](https://forum.aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}