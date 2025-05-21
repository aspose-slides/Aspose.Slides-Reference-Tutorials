---
"description": "تعرف على كيفية إضافة رؤوس وتذييلات ديناميكية في عروض PowerPoint باستخدام Aspose.Slides لـ .NET."
"linktitle": "إدارة الرأس والتذييل في الشرائح"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إدارة الرأس والتذييل في الشرائح"
"url": "/ar/net/chart-creation-and-customization/header-footer-manager/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إدارة الرأس والتذييل في الشرائح


# إنشاء رؤوس وتذييلات ديناميكية في Aspose.Slides لـ .NET

في عالم العروض التقديمية الديناميكية، يُعد Aspose.Slides for .NET حليفك الموثوق. تتيح لك هذه المكتبة القوية تصميم عروض PowerPoint جذابة بلمسة من التفاعلية. ومن أهم ميزاتها إمكانية إضافة رؤوس وتذييلات ديناميكية، مما يُضفي حيوية على شرائحك. في هذا الدليل التفصيلي، سنستكشف كيفية الاستفادة من Aspose.Slides for .NET لإضافة هذه العناصر الديناميكية إلى عرضك التقديمي. هيا بنا!

## المتطلبات الأساسية

قبل أن نبدأ، ستحتاج إلى بعض الأشياء في مكانها:

1. Aspose.Slides لـ .NET: يجب أن يكون لديك Aspose.Slides لـ .NET مُثبّتًا. إذا لم يكن مُثبّتًا لديك بالفعل، يُمكنك العثور على المكتبة [هنا](https://releases.aspose.com/slides/net/).

2. مستندك: يجب أن يكون ملف PowerPoint الذي ترغب بالعمل عليه محفوظًا في مجلدك المحلي. تأكد من معرفة مسار هذا المستند.

## استيراد مساحات الأسماء

للبدء، عليك استيراد مساحات الأسماء اللازمة إلى مشروعك. توفر هذه المساحات الأدوات اللازمة للعمل مع Aspose.Slides.

### الخطوة 1: استيراد المساحات الاسمية

في مشروع C# الخاص بك، أضف مساحات الأسماء التالية في أعلى ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

## إضافة رؤوس وتذييلات ديناميكية

الآن، دعنا نستعرض عملية إضافة الرؤوس والتذييلات الديناميكية إلى عرض PowerPoint الخاص بك خطوة بخطوة.

### الخطوة 2: تحميل العرض التقديمي الخاص بك

في هذه الخطوة، ستحتاج إلى تحميل عرض PowerPoint الخاص بك إلى مشروع C# الخاص بك.

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "presentation.ppt"))
{
    // سيتم وضع الكود الخاص بإدارة الرأس والتذييل هنا.
    // ...
}
```

### الخطوة 3: الوصول إلى مدير الرأس والتذييل

يوفر Aspose.Slides لـ .NET طريقة سهلة لإدارة الرؤوس والتذييلات. نصل إلى مدير الرؤوس والتذييلات للشريحة الأولى من عرضك التقديمي.

```csharp
IBaseSlideHeaderFooterManager headerFooterManager = presentation.Slides[0].HeaderFooterManager;
```

### الخطوة 4: تعيين رؤية التذييل

للتحكم في رؤية عنصر نائب التذييل، يمكنك استخدام `SetFooterVisibility` طريقة.

```csharp
if (!headerFooterManager.IsFooterVisible)
{
    headerFooterManager.SetFooterVisibility(true);
}
```

### الخطوة 5: تعيين رؤية رقم الشريحة

وبالمثل، يمكنك التحكم في رؤية عنصر نائب رقم صفحة الشريحة باستخدام `SetSlideNumberVisibility` طريقة.

```csharp
if (!headerFooterManager.IsSlideNumberVisible)
{
    headerFooterManager.SetSlideNumberVisibility(true);
}
```

### الخطوة 6: تعيين إمكانية رؤية التاريخ والوقت

لتحديد ما إذا كان عنصر نائب التاريخ والوقت مرئيًا، استخدم `IsDateTimeVisible` الخاصية. إذا لم تكن مرئية، يمكنك جعلها مرئية باستخدام `SetDateTimeVisibility` طريقة.

```csharp
if (!headerFooterManager.IsDateTimeVisible)
{
    headerFooterManager.SetDateTimeVisibility(true);
}
```

### الخطوة 7: تعيين نص التذييل والتاريخ والوقت

أخيرًا، يمكنك تعيين النص الخاص بتذييل الصفحة وعناصر التاريخ والوقت.

```csharp
headerFooterManager.SetFooterText("Footer text");
headerFooterManager.SetDateTimeText("Date and time text");
```

### الخطوة 8: احفظ العرض التقديمي الخاص بك

بعد إجراء كافة التغييرات اللازمة، احفظ العرض التقديمي المحدث.

```csharp
presentation.Save(dataDir + "Presentation.ppt", SaveFormat.Ppt);
```

## خاتمة

إضافة رؤوس وتذييلات ديناميكية إلى عرض PowerPoint التقديمي الخاص بك أمرٌ في غاية السهولة مع Aspose.Slides لـ .NET. تُحسّن هذه الميزة المظهر العام للشرائح وتزيد من سهولة عرض المعلومات، مما يجعلها أكثر جاذبيةً واحترافية.

الآن، أصبحتَ مُجهَّزًا بالمعرفة اللازمة للارتقاء بعروض PowerPoint التقديمية إلى مستوى أعلى. لذا، انطلق واجعل شرائحك أكثر ديناميكيةً وثراءً بالمعلومات وجمالًا بصريًا!

## الأسئلة الشائعة

### س1: هل Aspose.Slides for .NET مكتبة مجانية؟
ج١: Aspose.Slides لـ .NET ليس مجانيًا. يمكنك الاطلاع على تفاصيل الأسعار والترخيص. [هنا](https://purchase.aspose.com/buy).

### س2: هل يمكنني تجربة Aspose.Slides لـ .NET قبل الشراء؟
ج2: نعم، يمكنك استكشاف نسخة تجريبية مجانية من Aspose.Slides لـ .NET [هنا](https://releases.aspose.com/).

### س3: أين يمكنني العثور على وثائق Aspose.Slides لـ .NET؟
أ3: يمكنك الوصول إلى الوثائق [هنا](https://reference.aspose.com/slides/net/).

### س4: كيف يمكنني الحصول على تراخيص مؤقتة لـ Aspose.Slides لـ .NET؟
أ4: يمكن الحصول على تراخيص مؤقتة [هنا](https://purchase.aspose.com/temporary-license/).

### س5: هل يوجد مجتمع أو منتدى دعم لـ Aspose.Slides لـ .NET؟
ج5: نعم، يمكنك زيارة منتدى دعم Aspose.Slides لـ .NET [هنا](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}