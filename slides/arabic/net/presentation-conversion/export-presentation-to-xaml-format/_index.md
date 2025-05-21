---
"description": "تعلّم كيفية تصدير العروض التقديمية إلى صيغة XAML باستخدام Aspose.Slides لـ .NET. أنشئ محتوى تفاعليًا بكل سهولة!"
"linktitle": "تصدير العرض التقديمي إلى تنسيق XAML"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تصدير العرض التقديمي إلى تنسيق XAML"
"url": "/ar/net/presentation-conversion/export-presentation-to-xaml-format/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تصدير العرض التقديمي إلى تنسيق XAML


في عالم تطوير البرمجيات، من الضروري وجود أدوات تُبسّط المهام المعقدة. تُعدّ Aspose.Slides for .NET إحدى هذه الأدوات التي تُمكّنك من العمل مع عروض PowerPoint التقديمية برمجيًا. في هذا البرنامج التعليمي المُفصّل، سنستكشف كيفية تصدير عرض تقديمي إلى صيغة XAML باستخدام Aspose.Slides for .NET. 

## مقدمة إلى Aspose.Slides لـ .NET

قبل الخوض في هذا البرنامج التعليمي، دعونا نُقدّم بإيجاز Aspose.Slides for .NET. إنها مكتبة فعّالة تُمكّن المُطوّرين من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها وإدارتها دون الحاجة إلى Microsoft PowerPoint نفسه. باستخدام Aspose.Slides for .NET، يُمكنك أتمتة مُختلف المهام المُتعلقة بعروض PowerPoint التقديمية، مما يُحسّن عملية التطوير لديك.

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، ستحتاج إلى ما يلي:

1. Aspose.Slides for .NET: تأكد من تثبيت مكتبة Aspose.Slides for .NET وتجهيزها للاستخدام في مشروع .NET الخاص بك.

2. العرض التقديمي المصدر: لديك عرض تقديمي بصيغة PowerPoint (PPTX) وتريد تصديره بتنسيق XAML. تأكد من معرفة مسار هذا العرض التقديمي.

3. دليل الإخراج: اختر الدليل الذي تريد حفظ ملفات XAML المُنشأة فيه.

## الخطوة 1: إعداد مشروعك

في هذه الخطوة الأولى، سنقوم بإعداد مشروعنا والتأكد من تجهيز جميع المكونات اللازمة. تأكد من إضافة مرجع إلى مكتبة Aspose.Slides for .NET في مشروعك.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// المسار إلى عرض المصدر
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

يستبدل `"Your Document Directory"` مع مسار المجلد الذي يحتوي على عرض PowerPoint المصدري. حدّد أيضًا مجلد الإخراج الذي ستُحفظ فيه ملفات XAML المُولّدة.

## الخطوة 2: تصدير العرض التقديمي إلى XAML

الآن، لنبدأ بتصدير عرض PowerPoint التقديمي إلى صيغة XAML. سنستخدم Aspose.Slides for .NET لتحقيق ذلك. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // إنشاء خيارات التحويل
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // قم بتحديد خدمة توفير الإنتاج الخاصة بك
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // تحويل الشرائح
    pres.Save(xamlOptions);

    // حفظ ملفات XAML في دليل الإخراج
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

في مقتطف التعليمات البرمجية هذا، نقوم بتحميل العرض التقديمي المصدر وإنشاء خيارات تحويل XAML وتحديد خدمة مخصصة لحفظ الإخراج باستخدام `NewXamlSaver`نقوم بعد ذلك بحفظ ملفات XAML في دليل الإخراج المحدد.

## الخطوة 3: فئة XAML Saver المخصصة

لتنفيذ موفر XAML المخصص، سنقوم بإنشاء فئة تسمى `NewXamlSaver` الذي ينفذ `IXamlOutputSaver` واجهة.

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

ستتولى هذه الفئة مهمة حفظ ملفات XAML في دليل الإخراج.

## خاتمة

تهانينا! لقد نجحت في تعلّم كيفية تصدير عرض تقديمي من PowerPoint إلى صيغة XAML باستخدام Aspose.Slides لـ .NET. تُعدّ هذه مهارة قيّمة عند العمل على مشاريع تتضمن معالجة العروض التقديمية.

لا تتردد في استكشاف المزيد من الميزات والقدرات التي يوفرها Aspose.Slides لـ .NET لتحسين مهام أتمتة PowerPoint الخاصة بك.

## الأسئلة الشائعة

1. ### ما هو Aspose.Slides لـ .NET؟
Aspose.Slides for .NET هي مكتبة .NET للعمل مع عروض PowerPoint برمجيًا.

2. ### أين يمكنني الحصول على Aspose.Slides لـ .NET؟
يمكنك تنزيل Aspose.Slides لـ .NET من [هنا](https://purchase.aspose.com/buy).

3. ### هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET [هنا](https://releases.aspose.com/).

4. ### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

5. ### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
يمكنك العثور على الدعم ومناقشات المجتمع [هنا](https://forum.aspose.com/).

لمزيد من الدروس والموارد، قم بزيارة [وثائق واجهة برمجة التطبيقات Aspose.Slides](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}