---
title: إنشاء أشكال مستطيلة باستخدام Aspose.Slides لـ .NET
linktitle: إنشاء شكل مستطيل بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: استكشف عالم عروض PowerPoint التقديمية الديناميكية باستخدام Aspose.Slides for .NET. تعرف على كيفية إنشاء أشكال مستطيلة جذابة في الشرائح باستخدام هذا الدليل التفصيلي خطوة بخطوة.
weight: 12
url: /ar/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء أشكال مستطيلة باستخدام Aspose.Slides لـ .NET

## مقدمة
إذا كنت تتطلع إلى تحسين تطبيقات .NET الخاصة بك من خلال عروض PowerPoint التقديمية الديناميكية والجذابة بصريًا، فإن Aspose.Slides for .NET هو الحل الأمثل لك. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء شكل مستطيل بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- Visual Studio: تأكد من تثبيت Visual Studio على جهاز التطوير الخاص بك.
-  Aspose.Slides for .NET: قم بتنزيل وتثبيت Aspose.Slides for .NET Library من[هنا](https://releases.aspose.com/slides/net/).
- المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# أمر ضروري.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد المشروع
ابدأ بإنشاء مشروع C# جديد في Visual Studio. تأكد من الإشارة إلى Aspose.Slides for .NET بشكل صحيح في مشروعك.
## الخطوة 2: تهيئة كائن العرض التقديمي
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // سيتم وضع الرمز الخاص بك للخطوات التالية هنا.
}
```
## الخطوة 3: احصل على الشريحة الأولى
```csharp
ISlide sld = pres.Slides[0];
```
## الخطوة 4: إضافة الشكل التلقائي للمستطيل
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
يضيف هذا الكود شكل مستطيل عند الإحداثيات (50، 150) بعرض 150 وارتفاع 50.
## الخطوة 5: احفظ العرض التقديمي
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
تقوم هذه الخطوة بحفظ العرض التقديمي بالشكل المستطيل المضاف إلى الدليل المحدد.
## خاتمة
تهانينا! لقد نجحت في إنشاء شكل مستطيل بسيط في شريحة العرض التقديمي باستخدام Aspose.Slides for .NET. هذه مجرد البداية - يقدم Aspose.Slides مجموعة واسعة من الميزات لتخصيص عروضك التقديمية وتحسينها بشكل أكبر.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Slides لـ .NET في بيئات Windows وLinux؟
نعم، Aspose.Slides for .NET مستقل عن النظام الأساسي ويمكن استخدامه في بيئات Windows وLinux.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على دعم Aspose.Slides لـ .NET؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع.
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك شراء ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟
 الرجوع إلى الوثائق[هنا](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
