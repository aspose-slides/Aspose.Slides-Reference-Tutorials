---
"description": "استكشف عالم عروض PowerPoint الديناميكية مع Aspose.Slides لـ .NET. تعلّم كيفية إنشاء أشكال مستطيلة جذابة في الشرائح من خلال هذا الدليل المفصل."
"linktitle": "إنشاء شكل مستطيل بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء أشكال مستطيلة باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء أشكال مستطيلة باستخدام Aspose.Slides لـ .NET

## مقدمة
إذا كنت ترغب في تحسين تطبيقات .NET الخاصة بك بعروض PowerPoint ديناميكية وجذابة بصريًا، فإن Aspose.Slides for .NET هو الحل الأمثل. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء شكل مستطيل بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- Visual Studio: تأكد من تثبيت Visual Studio على جهاز التطوير الخاص بك.
- Aspose.Slides لـ .NET: قم بتنزيل وتثبيت مكتبة Aspose.Slides لـ .NET من [هنا](https://releases.aspose.com/slides/net/).
- المعرفة الأساسية بلغة C#: المعرفة بلغة البرمجة C# أمر ضروري.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، ابدأ باستيراد المساحات الأساسية اللازمة للوصول إلى وظائف Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد المشروع
ابدأ بإنشاء مشروع C# جديد في Visual Studio. تأكد من صحة مرجع Aspose.Slides for .NET في مشروعك.
## الخطوة 2: تهيئة كائن العرض التقديمي
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // سيتم وضع الكود الخاص بالخطوات التالية هنا.
}
```
## الخطوة 3: الحصول على الشريحة الأولى
```csharp
ISlide sld = pres.Slides[0];
```
## الخطوة 4: إضافة شكل مستطيل تلقائي
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
يقوم هذا الكود بإضافة شكل مستطيل عند الإحداثيات (50، 150) بعرض 150 وارتفاع 50.
## الخطوة 5: حفظ العرض التقديمي
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
تؤدي هذه الخطوة إلى حفظ العرض التقديمي مع شكل المستطيل المضاف إلى الدليل المحدد.
## خاتمة
تهانينا! لقد نجحت في إنشاء شكل مستطيل بسيط في شريحة عرض تقديمي باستخدام Aspose.Slides لـ .NET. هذه مجرد البداية - يوفر Aspose.Slides مجموعة واسعة من الميزات لتخصيص عروضك التقديمية وتحسينها بشكل أكبر.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ .NET في بيئات Windows وLinux؟
نعم، Aspose.Slides لـ .NET مستقل عن النظام الأساسي ويمكن استخدامه في بيئات Windows وLinux.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع.
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
نعم يمكنك شراء ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟
راجع الوثائق [هنا](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}