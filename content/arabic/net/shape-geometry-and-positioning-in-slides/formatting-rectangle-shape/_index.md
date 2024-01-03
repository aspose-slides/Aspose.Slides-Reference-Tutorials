---
title: تحسين العروض التقديمية - تنسيق الأشكال المستطيلة باستخدام Aspose.Slides
linktitle: تنسيق الشكل المستطيل في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعلم كيفية تنسيق الأشكال المستطيلة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. ارفع مستوى شرائحك باستخدام العناصر المرئية الديناميكية.
type: docs
weight: 12
url: /ar/net/shape-geometry-and-positioning-in-slides/formatting-rectangle-shape/
---
## مقدمة
Aspose.Slides for .NET هي مكتبة قوية تسهل العمل مع عروض PowerPoint التقديمية في بيئة .NET. إذا كنت ترغب في تحسين العروض التقديمية الخاصة بك عن طريق تنسيق الأشكال المستطيلة ديناميكيًا، فهذا البرنامج التعليمي مناسب لك. في هذا الدليل خطوة بخطوة، سنرشدك خلال عملية تنسيق شكل مستطيل في عرض تقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- بيئة تطوير مع تثبيت Aspose.Slides لـ .NET.
- المعرفة الأساسية بلغة البرمجة C#.
- - الإلمام بإنشاء عروض PowerPoint التقديمية ومعالجتها.
الآن، دعونا نبدأ مع البرنامج التعليمي!
## استيراد مساحات الأسماء
في كود C# الخاص بك، تحتاج إلى استيراد مساحات الأسماء اللازمة لاستخدام وظائف Aspose.Slides. أضف مساحات الأسماء التالية في بداية التعليمات البرمجية الخاصة بك:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
```
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
 ابدأ بإعداد الدليل الذي تريد حفظ ملف عرض PowerPoint التقديمي فيه. يستبدل`"Your Document Directory"` مع المسار الفعلي إلى الدليل الخاص بك.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## الخطوة 2: إنشاء كائن العرض التقديمي
 إنشاء مثيل`Presentation`فئة لتمثيل ملف PPTX. سيكون هذا هو الأساس لعرض PowerPoint التقديمي الخاص بك.
```csharp
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك يذهب هنا
}
```
## الخطوة 3: احصل على الشريحة الأولى
قم بالوصول إلى الشريحة الأولى في العرض التقديمي الخاص بك، لأنها ستكون اللوحة القماشية التي تضيف إليها شكل المستطيل وتنسيقه.
```csharp
ISlide sld = pres.Slides[0];
```
## الخطوة 4: إضافة شكل مستطيل
 استخدم ال`Shapes` خاصية الشريحة لإضافة شكل تلقائي من النوع المستطيل. حدد موضع المستطيل وأبعاده.
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
## الخطوة 5: تطبيق التنسيق على شكل المستطيل
الآن، دعونا نطبق بعض التنسيق على الشكل المستطيل. قم بتعيين لون التعبئة ولون الخط وعرض الشكل لتخصيص مظهره.
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
## الخطوة 6: احفظ العرض التقديمي
 اكتب العرض التقديمي المعدل على القرص باستخدام الملف`Save` الطريقة، مع تحديد تنسيق الملف كـ PPTX.
```csharp
pres.Save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
تهانينا! لقد نجحت في تنسيق شكل مستطيل في عرض تقديمي باستخدام Aspose.Slides لـ .NET.
## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية أساسيات العمل مع الأشكال المستطيلة في Aspose.Slides لـ .NET. لقد تعلمت كيفية إعداد مشروعك وإنشاء عرض تقديمي وإضافة شكل مستطيل وتطبيق التنسيق لتحسين جاذبيته البصرية. مع استمرارك في استكشاف Aspose.Slides، ستكتشف المزيد من الطرق للارتقاء بعروض PowerPoint التقديمية.
## الأسئلة الشائعة
### س1: هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات .NET الأخرى؟
نعم، يدعم Aspose.Slides لغات .NET الأخرى مثل VB.NET وF# بالإضافة إلى C#.
### س2: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides؟
 يمكنك الرجوع إلى الوثائق[هنا](https://reference.aspose.com/slides/net/).
### س3: كيف يمكنني الحصول على الدعم لـ Aspose.Slides؟
 للحصول على الدعم والمناقشات، قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### س4: هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س5: أين يمكنني شراء Aspose.Slides لـ .NET؟
 يمكنك شراء Aspose.Slides لـ .NET[هنا](https://purchase.aspose.com/buy).