---
"description": "أنشئ أشكالًا بيضاوية رائعة في PowerPoint باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة لإنشاء عروض تقديمية احترافية."
"linktitle": "تنسيق شكل القطع الناقص في الشرائح باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "دورة تدريبية حول تنسيق الأشكال البيضاوية باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shape-geometry-and-positioning-in-slides/formatting-ellipse-shape/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# دورة تدريبية حول تنسيق الأشكال البيضاوية باستخدام Aspose.Slides لـ .NET

## مقدمة
يُعدّ تحسين عروض PowerPoint التقديمية بأشكال جذابة بصريًا أمرًا بالغ الأهمية لجذب انتباه جمهورك. ومن هذه الأشكال القطع الناقص، الذي يُضفي لمسة من الأناقة والاحترافية على شرائحك. في هذا البرنامج التعليمي، سنرشدك خلال عملية تنسيق أشكال القطع الناقص في PowerPoint باستخدام Aspose.Slides لـ .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio على جهازك.
- مكتبة Aspose.Slides لـ .NET، والتي يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).
- تأكد من أن لديك الأذونات اللازمة لإنشاء الملفات وحفظها على نظامك.
## استيراد مساحات الأسماء
للبدء، عليك استيراد مساحات الأسماء المطلوبة إلى مشروع C# الخاص بك. هذا يضمن لك الوصول إلى الفئات والأساليب اللازمة للعمل مع Aspose.Slides.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using System.Drawing;
```
الآن، دعنا نقسم المثال إلى خطوات متعددة للحصول على دليل شامل حول تنسيق أشكال القطع الناقص في PowerPoint باستخدام Aspose.Slides لـ .NET.
## الخطوة 1: إعداد مشروعك
أنشئ مشروع C# جديدًا في Visual Studio وأضف مرجعًا إلى مكتبة Aspose.Slides. إذا لم تقم بتنزيلها بعد، يمكنك العثور على رابط التنزيل. [هنا](https://releases.aspose.com/slides/net/).
## الخطوة 2: تحديد دليل المستندات الخاص بك
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
تأكد من وجود الدليل المحدد أو قم بإنشائه إذا لم يكن موجودًا.
## الخطوة 3: إنشاء فئة العرض التقديمي
```csharp
using (Presentation pres = new Presentation())
{
    // يظهر الكود الخاص بتنسيق شكل القطع الناقص هنا
}
```
إنشاء مثيل لـ `Presentation` الفئة التي تمثل ملف PowerPoint.
## الخطوة 4: الحصول على الشريحة الأولى
```csharp
ISlide sld = pres.Slides[0];
```
قم بالوصول إلى الشريحة الأولى من العرض التقديمي الخاص بك.
## الخطوة 5: إضافة الشكل البيضاوي التلقائي
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
قم بإدراج شكل بيضاوي تلقائي على الشريحة، مع تحديد موضعه وأبعاده.
## الخطوة 6: تنسيق شكل القطع الناقص
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
تطبيق التنسيق على شكل القطع الناقص، وتعيين لون التعبئة وخصائص الخط.
## الخطوة 7: حفظ العرض التقديمي
```csharp
pres.Save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدّل على القرص.
اتبع هذه الخطوات بدقة، وسوف تحصل على شكل بيضاوي منسق بشكل جميل في عرض PowerPoint الخاص بك.
## خاتمة
إن إضافة أشكال جذابة بصريًا، مثل القطع الناقص، يُحسّن بشكل كبير من جمال عروض PowerPoint التقديمية. يُسهّل Aspose.Slides for .NET هذه العملية، مما يسمح لك بإنشاء شرائح احترافية بكل سهولة.

## الأسئلة الشائعة
### هل Aspose.Slides متوافق مع أحدث إصدارات PowerPoint؟
يضمن Aspose.Slides التوافق مع مختلف إصدارات PowerPoint، بما في ذلك الإصدارات الأحدث. راجع [التوثيق](https://reference.aspose.com/slides/net/) للحصول على تفاصيل محددة.
### هل يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ .NET؟
نعم، يمكنك استكشاف نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
يزور [هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.
### أين يمكنني العثور على الدعم للاستعلامات المتعلقة بـ Aspose.Slides؟
اطلب المساعدة من المجتمع في [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### هل هناك خيار الشراء المباشر لـ Aspose.Slides لـ .NET؟
نعم يمكنك شراء المكتبة مباشرة [هنا](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}