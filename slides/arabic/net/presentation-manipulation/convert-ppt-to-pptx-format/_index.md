---
title: تحويل PPT إلى تنسيق PPTX
linktitle: تحويل PPT إلى تنسيق PPTX
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحويل PPT إلى PPTX بسهولة باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية لتحويل التنسيق بسلاسة.
type: docs
weight: 25
url: /ar/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

إذا كنت بحاجة في أي وقت إلى تحويل ملفات PowerPoint من تنسيق PPT الأقدم إلى تنسيق PPTX الأحدث باستخدام .NET، فأنت في المكان الصحيح. في هذا البرنامج التعليمي خطوة بخطوة، سنرشدك خلال العملية باستخدام Aspose.Slides for .NET API. باستخدام هذه المكتبة القوية، يمكنك التعامل مع مثل هذه التحويلات بسهولة. هيا بنا نبدأ!

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من أن لديك الإعداد التالي:

- Visual Studio: تأكد من تثبيت Visual Studio وجاهز لتطوير .NET.
-  Aspose.Slides for .NET: قم بتنزيل وتثبيت Aspose.Slides for .NET Library من[هنا](https://releases.aspose.com/slides/net/).

## إعداد المشروع

1. إنشاء مشروع جديد: افتح Visual Studio وقم بإنشاء مشروع C# جديد.

2. إضافة مرجع إلى Aspose.Slides: انقر بزر الماوس الأيمن على مشروعك في Solution Explorer، واختر "إدارة حزم NuGet"، وابحث عن "Aspose.Slides". قم بتثبيت الحزمة.

3. استيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Slides;
```

## تحويل PPT إلى PPTX

الآن وبعد أن قمنا بإعداد مشروعنا، فلنكتب الكود لتحويل ملف PPT إلى PPTX.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف PPT
Presentation pres = new Presentation(srcFileName);

//حفظ العرض التقديمي بتنسيق PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

في مقتطف الشفرة هذا:

- `dataDir` يجب استبداله بمسار الدليل حيث يوجد ملف PPT الخاص بك.
- `outPath` يجب استبداله بالدليل الذي تريد حفظ ملف PPTX المحول فيه.
- `srcFileName` هو اسم ملف الإدخال PPT الخاص بك.
- `destFileName` هو الاسم المطلوب لملف الإخراج PPTX.

## خاتمة

تهانينا! لقد نجحت في تحويل عرض تقديمي لـ PowerPoint من تنسيق PPT إلى تنسيق PPTX باستخدام Aspose.Slides for .NET API. تعمل هذه المكتبة القوية على تبسيط المهام المعقدة مثل هذه، مما يجعل تجربة تطوير .NET الخاصة بك أكثر سلاسة.

 إذا لم تكن قد فعلت ذلك بالفعل،[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net/) واستكشاف قدراتها بشكل أكبر.

 لمزيد من الدروس والنصائح، قم بزيارة موقعنا[توثيق](https://reference.aspose.com/slides/net/).

## أسئلة مكررة

### 1. ما هو Aspose.Slides لـ .NET؟
Aspose.Slides for .NET هي مكتبة .NET تسمح للمطورين بإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجيًا.

### 2. هل يمكنني تحويل التنسيقات الأخرى إلى PPTX باستخدام Aspose.Slides لـ .NET؟
نعم، يدعم Aspose.Slides for .NET العديد من التنسيقات، بما في ذلك PPT وPPTX وODP والمزيد.

### 3. هل Aspose.Slides for .NET مجاني للاستخدام؟
 لا، إنها مكتبة تجارية، ولكن يمكنك استكشاف[تجربة مجانية](https://releases.aspose.com/) لتقييم ميزاته.

### 4. هل هناك أي تنسيقات مستندات أخرى يدعمها Aspose.Slides لـ .NET؟
نعم، يدعم Aspose.Slides for .NET أيضًا العمل مع مستندات Word وجداول بيانات Excel وتنسيقات الملفات الأخرى.

### 5. أين يمكنني الحصول على الدعم أو طرح الأسئلة حول Aspose.Slides for .NET؟
 يمكنك العثور على إجابات لأسئلتك وطلب الدعم في[منتديات Aspose.Slides](https://forum.aspose.com/).

