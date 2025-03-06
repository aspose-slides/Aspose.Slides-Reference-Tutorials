---
title: البرنامج التعليمي لتنسيق الأشكال البيضاوية باستخدام Aspose.Slides لـ .NET
linktitle: تنسيق شكل القطع الناقص في الشرائح باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بإنشاء أشكال بيضاوية مذهلة في PowerPoint باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة للعروض التقديمية الاحترافية.
weight: 11
url: /ar/net/shape-geometry-and-positioning-in-slides/formatting-ellipse-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# البرنامج التعليمي لتنسيق الأشكال البيضاوية باستخدام Aspose.Slides لـ .NET

## مقدمة
يعد تحسين عروض PowerPoint التقديمية بأشكال جذابة بصريًا أمرًا بالغ الأهمية لجذب جمهورك. أحد هذه الأشكال هو الشكل البيضاوي، والذي يمكن أن يضيف لمسة من الأناقة والاحترافية إلى شرائحك. في هذا البرنامج التعليمي، سنرشدك خلال عملية تنسيق أشكال القطع الناقص في PowerPoint باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio على جهازك.
-  Aspose.Slides لمكتبة .NET، والتي يمكنك التنزيل منها[هنا](https://releases.aspose.com/slides/net/).
- تأكد من أن لديك الأذونات اللازمة لإنشاء الملفات وحفظها على نظامك.
## استيراد مساحات الأسماء
للبدء، تحتاج إلى استيراد مساحات الأسماء المطلوبة إلى مشروع C# الخاص بك. وهذا يضمن أن لديك إمكانية الوصول إلى الفئات والأساليب اللازمة للعمل مع Aspose.Slides.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using System.Drawing;
```
الآن، دعنا نقسم المثال إلى خطوات متعددة للحصول على دليل شامل حول تنسيق أشكال القطع الناقص في PowerPoint باستخدام Aspose.Slides for .NET.
## الخطوة 1: قم بإعداد مشروعك
 قم بإنشاء مشروع C# جديد في Visual Studio وأضف مرجعًا إلى مكتبة Aspose.Slides. إذا لم تقم بتنزيله بعد، يمكنك العثور على رابط التنزيل[هنا](https://releases.aspose.com/slides/net/).
## الخطوة 2: تحديد دليل المستندات الخاص بك
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
تأكد من وجود الدليل المحدد أو قم بإنشائه إذا لم يكن كذلك.
## الخطوة 3: إنشاء مثيل لفئة العرض التقديمي
```csharp
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك لتنسيق شكل القطع الناقص موجود هنا
}
```
 إنشاء مثيل لـ`Presentation` فئة تمثل ملف PowerPoint.
## الخطوة 4: احصل على الشريحة الأولى
```csharp
ISlide sld = pres.Slides[0];
```
قم بالوصول إلى الشريحة الأولى من العرض التقديمي الخاص بك.
## الخطوة 5: إضافة الشكل التلقائي للقطع الناقص
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
قم بإدراج شكل تلقائي للقطع الناقص على الشريحة، مع تحديد موضعه وأبعاده.
## الخطوة 6: تنسيق شكل القطع الناقص
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
تطبيق التنسيق على شكل القطع الناقص، وتعيين لون التعبئة وخصائص الخط.
## الخطوة 7: احفظ العرض التقديمي
```csharp
pres.Save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدل على القرص.
اتبع هذه الخطوات بدقة، وسيكون لديك شكل بيضاوي منسق بشكل جميل في عرض PowerPoint التقديمي الخاص بك.
## خاتمة
يمكن أن يؤدي دمج الأشكال الجذابة بصريًا، مثل علامات الحذف، إلى تعزيز المظهر الجمالي لعروض PowerPoint التقديمية بشكل كبير. Aspose.Slides for .NET يجعل هذه العملية سلسة، مما يسمح لك بإنشاء شرائح ذات مظهر احترافي دون عناء.

## الأسئلة الشائعة
### هل Aspose.Slides متوافق مع أحدث إصدارات PowerPoint؟
يضمن Aspose.Slides التوافق مع إصدارات PowerPoint المختلفة، بما في ذلك الإصدارات الأحدث. الرجوع إلى[توثيق](https://reference.aspose.com/slides/net/) للحصول على تفاصيل محددة.
### هل يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ .NET؟
 نعم، يمكنك استكشاف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 يزور[هذا الرابط](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت.
### أين يمكنني العثور على الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
 اطلب المساعدة من المجتمع في[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### هل يوجد خيار شراء مباشر لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك شراء المكتبة مباشرة[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
