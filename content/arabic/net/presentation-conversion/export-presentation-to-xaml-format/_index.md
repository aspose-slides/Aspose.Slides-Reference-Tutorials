---
title: تصدير العرض التقديمي إلى تنسيق XAML
linktitle: تصدير العرض التقديمي إلى تنسيق XAML
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تصدير العروض التقديمية إلى تنسيق XAML باستخدام Aspose.Slides لـ .NET. قم بإنشاء محتوى تفاعلي دون عناء!
type: docs
weight: 27
url: /ar/net/presentation-conversion/export-presentation-to-xaml-format/
---

في عالم تطوير البرمجيات، من الضروري أن يكون لديك أدوات يمكنها تبسيط المهام المعقدة. Aspose.Slides for .NET هي إحدى هذه الأدوات التي تمكنك من العمل مع عروض PowerPoint التقديمية برمجياً. في هذا البرنامج التعليمي خطوة بخطوة، سنستكشف كيفية تصدير عرض تقديمي إلى تنسيق XAML باستخدام Aspose.Slides for .NET. 

## مقدمة إلى Aspose.Slides لـ .NET

قبل أن نتعمق في البرنامج التعليمي، دعنا نقدم بإيجاز Aspose.Slides for .NET. إنها مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها وإدارتها دون الحاجة إلى Microsoft PowerPoint نفسه. باستخدام Aspose.Slides for .NET، يمكنك أتمتة المهام المختلفة المتعلقة بعروض PowerPoint التقديمية، مما يجعل عملية التطوير الخاصة بك أكثر كفاءة.

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، ستحتاج إلى ما يلي:

1. Aspose.Slides for .NET: تأكد من تثبيت مكتبة Aspose.Slides for .NET وجاهزة للاستخدام في مشروع .NET الخاص بك.

2. العرض التقديمي المصدر: احصل على عرض تقديمي لـ PowerPoint (PPTX) تريد تصديره إلى تنسيق XAML. تأكد من أنك تعرف المسار إلى هذا العرض التقديمي.

3. دليل الإخراج: اختر الدليل الذي تريد حفظ ملفات XAML التي تم إنشاؤها فيه.

## الخطوة 1: قم بإعداد مشروعك

في هذه الخطوة الأولى، سنقوم بإعداد مشروعنا والتأكد من أن لدينا جميع المكونات الضرورية جاهزة. تأكد من أنك قمت بإضافة مرجع إلى مكتبة Aspose.Slides for .NET في مشروعك.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// المسار إلى العرض التقديمي المصدر
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

 يستبدل`"Your Document Directory"` مع المسار إلى الدليل الذي يحتوي على عرض PowerPoint التقديمي المصدر. حدد أيضًا دليل الإخراج حيث سيتم حفظ ملفات XAML التي تم إنشاؤها.

## الخطوة 2: تصدير العرض التقديمي إلى XAML

الآن، دعنا ننتقل إلى تصدير عرض PowerPoint التقديمي إلى تنسيق XAML. سوف نستخدم Aspose.Slides لـ .NET لتحقيق ذلك. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // إنشاء خيارات التحويل
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // حدد خدمة توفير المخرجات الخاصة بك
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // تحويل الشرائح
    pres.Save(xamlOptions);

    // احفظ ملفات XAML في دليل الإخراج
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

 في مقتطف الكود هذا، نقوم بتحميل العرض التقديمي المصدر وإنشاء خيارات تحويل XAML وتحديد خدمة مخصصة لحفظ المخرجات باستخدام`NewXamlSaver`. نقوم بعد ذلك بحفظ ملفات XAML في دليل الإخراج المحدد.

## الخطوة 3: فئة حفظ XAML المخصصة

 لتنفيذ موفر XAML المخصص، سنقوم بإنشاء فئة باسم`NewXamlSaver` الذي ينفذ`IXamlOutputSaver` واجهه المستخدم.

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

ستتعامل هذه الفئة مع حفظ ملفات XAML في دليل الإخراج.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تصدير عرض PowerPoint التقديمي إلى تنسيق XAML باستخدام Aspose.Slides لـ .NET. يمكن أن تكون هذه مهارة قيمة عند العمل على المشاريع التي تتضمن التلاعب بالعروض التقديمية.

لا تتردد في استكشاف المزيد من الميزات والإمكانيات في Aspose.Slides for .NET لتحسين مهام أتمتة PowerPoint.

## الأسئلة الشائعة

1. ### ما هو Aspose.Slides لـ .NET؟
Aspose.Slides for .NET هي مكتبة .NET للعمل مع عروض PowerPoint التقديمية برمجيًا.

2. ### أين يمكنني الحصول على Aspose.Slides لـ .NET؟
 يمكنك تنزيل Aspose.Slides لـ .NET من[هنا](https://purchase.aspose.com/buy).

3. ### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET[هنا](https://releases.aspose.com/).

4. ### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

5. ### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
 يمكنك العثور على الدعم والمناقشات المجتمعية[هنا](https://forum.aspose.com/).

لمزيد من الدروس والموارد، قم بزيارة[وثائق Aspose.Slides API](https://reference.aspose.com/slides/net/).