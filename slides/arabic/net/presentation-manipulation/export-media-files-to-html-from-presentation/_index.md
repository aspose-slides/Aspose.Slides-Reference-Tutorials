---
"description": "حسّن مشاركة عرضك التقديمي باستخدام Aspose.Slides لـ .NET! تعرّف على كيفية تصدير ملفات الوسائط إلى HTML من عرضك التقديمي في هذا الدليل المفصل."
"linktitle": "تصدير ملفات الوسائط إلى HTML من العرض التقديمي"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تصدير ملفات الوسائط إلى HTML من العرض التقديمي"
"url": "/ar/net/presentation-manipulation/export-media-files-to-html-from-presentation/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تصدير ملفات الوسائط إلى HTML من العرض التقديمي


في هذا البرنامج التعليمي، سنشرح لك عملية تصدير ملفات الوسائط إلى HTML من عرض تقديمي باستخدام Aspose.Slides لـ .NET. Aspose.Slides هي واجهة برمجة تطبيقات فعّالة تتيح لك العمل مع عروض PowerPoint التقديمية برمجيًا. بنهاية هذا الدليل، ستتمكن من تحويل عروضك التقديمية إلى تنسيق HTML بسهولة. هيا بنا نبدأ!

## 1. المقدمة

غالبًا ما تحتوي عروض PowerPoint التقديمية على عناصر وسائط متعددة، مثل مقاطع الفيديو، وقد تحتاج إلى تصدير هذه العروض التقديمية بتنسيق HTML لتوافقها مع الويب. يوفر Aspose.Slides لـ .NET طريقة سهلة لإنجاز هذه المهمة برمجيًا.

## 2. المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.Slides لـ .NET: يجب أن تكون مكتبة Aspose.Slides لـ .NET مثبتة لديك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).

## 3. تحميل العرض التقديمي

للبدء، عليك تحميل عرض PowerPoint التقديمي الذي تريد تحويله إلى HTML. ستحتاج أيضًا إلى تحديد مجلد الإخراج الذي سيتم حفظ ملف HTML فيه. إليك الكود لتحميل العرض التقديمي:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// تحميل العرض التقديمي
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // الكود الخاص بك هنا
}
```

## 4. إعداد خيارات HTML

الآن، لنُعِدّ إعدادات HTML للتحويل. سنقوم بتهيئة وحدة تحكم HTML، ومنسق HTML، وتنسيق صورة الشريحة. سيضمن هذا الكود احتواء ملف HTML على المكونات اللازمة لعرض عناصر الوسائط المتعددة.

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// ضبط خيارات HTML
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. حفظ ملف HTML

بعد تكوين خيارات HTML، يمكنك الآن حفظ ملف HTML. `Save` ستقوم طريقة كائن العرض بإنشاء ملف HTML يحتوي على عناصر الوسائط المتعددة المضمنة.

```csharp
// حفظ الملف
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. الخاتمة

تهانينا! لقد نجحت في تصدير ملفات الوسائط إلى HTML من عرض تقديمي في PowerPoint باستخدام Aspose.Slides لـ .NET. يتيح لك هذا مشاركة عروضك التقديمية عبر الإنترنت بسهولة، ويضمن عرض عناصر الوسائط المتعددة بشكل صحيح.

## 7. الأسئلة الشائعة

### س1: هل Aspose.Slides for .NET مكتبة مجانية؟
A1: Aspose.Slides for .NET هي مكتبة تجارية، ولكن يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/) لتجربته.

### س2: هل يمكنني تخصيص إخراج HTML بشكل أكبر؟
ج2: نعم، يمكنك تخصيص مخرجات HTML عن طريق تعديل خيارات HTML في الكود.

### س3: هل يدعم Aspose.Slides for .NET تنسيقات التصدير الأخرى؟
ج3: نعم، يدعم Aspose.Slides for .NET تنسيقات التصدير المختلفة، بما في ذلك تنسيقات PDF وتنسيقات الصور والمزيد.

### س4: أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
A4: يمكنك العثور على الدعم وطرح الأسئلة على منتديات Aspose [هنا](https://forum.aspose.com/).

### س5: كيف يمكنني شراء ترخيص لـ Aspose.Slides لـ .NET؟
أ5: يمكنك شراء ترخيص من [هذا الرابط](https://purchase.aspose.com/buy).

بعد أن أكملتَ هذا البرنامج التعليمي، أصبحتَ تمتلك المهارات اللازمة لتصدير ملفات الوسائط إلى HTML من عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. استمتع بمشاركة عروضك التقديمية الغنية بالوسائط المتعددة عبر الإنترنت!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}