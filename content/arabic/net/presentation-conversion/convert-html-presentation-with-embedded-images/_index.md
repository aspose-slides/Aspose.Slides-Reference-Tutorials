---
title: تحويل عرض HTML مع الصور المضمنة
linktitle: تحويل عرض HTML مع الصور المضمنة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بتحويل عروض HTML التقديمية مع الصور المضمنة بسهولة باستخدام Aspose.Slides لـ .NET. قم بإنشاء ملفات PowerPoint وتخصيصها وحفظها بسلاسة.
type: docs
weight: 11
url: /ar/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---
## مقدمة لتحويل عرض HTML مع الصور المضمنة 

في هذا الدليل، سنتعرف على عملية تحويل عرض تقديمي بتنسيق HTML يحتوي على صور مضمنة إلى تنسيق عرض تقديمي لـ PowerPoint (PPTX) باستخدام Aspose.Slides for .NET. Aspose.Slides هي مكتبة قوية تسمح لك بالعمل مع عروض PowerPoint التقديمية برمجياً. 

## المتطلبات الأساسية
قبل البدء، تأكد من توفر ما يلي:
- تم تثبيت Visual Studio أو أي بيئة تطوير .NET أخرى.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://downloads.aspose.com/slides/net).
- المعرفة الأساسية بتطوير C# و.NET.

## خطوات

1. إنشاء مشروع C# جديد:
   افتح Visual Studio الخاص بك وقم بإنشاء مشروع C# جديد.

2. تثبيت Aspose.Slides لـ .NET:
   قم بتثبيت Aspose.Slides لمكتبة .NET في مشروعك باستخدام NuGet Package Manager أو عن طريق إضافة مرجع إلى ملف DLL الذي تم تنزيله.

3. تضمين مساحات الأسماء الضرورية:
   في ملف التعليمات البرمجية الخاص بك، قم بتضمين مساحات الأسماء الضرورية:
   ```csharp
   using Aspose.Slides;
   using Aspose.Slides.Export;
   using System.IO;
   ```

4. تحميل محتوى HTML:
   قم بتحميل محتوى HTML للعرض التقديمي في سلسلة. يمكنك استرداد HTML من ملف أو مصدر ويب.
   ```csharp
   string htmlContent = File.ReadAllText("path_to_your_html_file.html");
   ```

5. إنشاء عرض تقديمي جديد:
    إنشاء مثيل جديد لـ`Presentation` فصل.
   ```csharp
   using Presentation presentation = new Presentation();
   ```

6. أضف شرائح تحتوي على محتوى HTML:
   أضف شرائح إلى العرض التقديمي وقم بتعيين محتوى HTML لكل شريحة.
   ```csharp
   ISlideCollection slides = presentation.Slides;

   // قم بإنشاء شريحة
   ISlide slide = slides.AddEmptySlide();

   // أضف محتوى HTML إلى الشريحة
   IAutoShape textShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 600, 400);
   textShape.TextFrame.Text = htmlContent;
   ```

7. حفظ العرض التقديمي:
   احفظ العرض التقديمي بتنسيق PPTX.
   ```csharp
   presentation.Save("output_presentation.pptx", SaveFormat.Pptx);
   ```

8. تشغيل التطبيق:
   بناء وتشغيل التطبيق الخاص بك. سيتم تحويل العرض التقديمي بتنسيق HTML مع الصور المضمنة إلى عرض تقديمي لـ PowerPoint.

## رمز المثال

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
using System.IO;

namespace HTMLToPPTConversion
{
    class Program
    {
        static void Main(string[] args)
        {
            // تحميل محتوى HTML من الملف
            string htmlContent = File.ReadAllText("path_to_your_html_file.html");

            // إنشاء عرض تقديمي جديد
            using Presentation presentation = new Presentation();

            // أضف شريحة تحتوي على محتوى HTML
            ISlide slide = presentation.Slides.AddEmptySlide();
            IAutoShape textShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 600, 400);
            textShape.TextFrame.Text = htmlContent;

            // احفظ العرض التقديمي بتنسيق PPTX
            presentation.Save("output_presentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## خاتمة

أصبح تحويل عروض HTML التقديمية التي تحتوي على صور مضمنة إلى PowerPoint أمرًا بسيطًا باستخدام Aspose.Slides for .NET. تعمل هذه المكتبة على تبسيط العملية وتوفر أدوات شاملة لإدارة التحويل بدقة.

## الأسئلة الشائعة

### كيف يمكنني تضمين صور خارجية في العرض التقديمي بتنسيق HTML؟

إذا كان عرض HTML التقديمي الخاص بك يتضمن صورًا خارجية، فتأكد من توفير عناوين URL الصحيحة للصور. سيتعامل Aspose.Slides تلقائيًا مع تضمين هذه الصور عند إضافة محتوى HTML إلى الشريحة.

### هل يمكنني تخصيص مظهر الشرائح المحولة؟

نعم، يمكنك تخصيص مظهر الشرائح المحولة باستخدام الخصائص والأساليب المتنوعة التي توفرها مكتبة Aspose.Slides. يمكنك تعديل الخطوط والألوان والأنماط والمزيد.

### أين يمكنني العثور على الوثائق الكاملة لـ Aspose.Slides لـ .NET؟

يمكنك العثور على الوثائق الكاملة ومرجع واجهة برمجة التطبيقات لـ Aspose.Slides for .NET[هنا](https://reference.aspose.com/slides/net).

### أين يمكنني تنزيل أحدث إصدار من Aspose.Slides لـ .NET؟

 يمكنك تنزيل أحدث إصدار من Aspose.Slides for .NET من صفحة إصدارات Aspose:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net).