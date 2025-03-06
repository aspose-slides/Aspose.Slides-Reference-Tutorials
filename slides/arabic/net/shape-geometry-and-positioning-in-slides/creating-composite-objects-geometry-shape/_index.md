---
title: إتقان الأشكال الهندسية المركبة في العروض التقديمية
linktitle: إنشاء كائنات مركبة في شكل هندسي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء عروض تقديمية مذهلة بأشكال هندسية مركبة باستخدام Aspose.Slides for .NET. اتبع دليلنا خطوة بخطوة للحصول على نتائج مبهرة.
weight: 14
url: /ar/net/shape-geometry-and-positioning-in-slides/creating-composite-objects-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان الأشكال الهندسية المركبة في العروض التقديمية

## مقدمة
أطلق العنان لقوة Aspose.Slides لـ .NET لتحسين العروض التقديمية الخاصة بك عن طريق إنشاء كائنات مركبة في أشكال هندسية. سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء شرائح جذابة بصريًا ذات هندسة معقدة باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي للغة البرمجة C#.
-  تم تثبيت Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[Aspose.Slides الوثائق](https://reference.aspose.com/slides/net/).
- بيئة تطوير تم إعدادها باستخدام Visual Studio أو أي أداة تطوير أخرى لـ C#.
## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء الضرورية في كود C# الخاص بك للاستفادة من وظائف Aspose.Slides. قم بتضمين مساحات الأسماء التالية في بداية التعليمات البرمجية الخاصة بك:
```csharp
using System.IO;
using Aspose.Slides.Export;
```
الآن، دعنا نقوم بتقسيم كود المثال إلى خطوات متعددة لإرشادك خلال إنشاء كائنات مركبة في شكل هندسي باستخدام Aspose.Slides for .NET:
## الخطوة 1: إعداد البيئة
```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
string resultPath = Path.Combine(dataDir, "GeometryShapeCompositeObjects.pptx");
```
في هذه الخطوة، نقوم بتهيئة البيئة من خلال إعداد الدليل ومسار النتيجة لعرضنا التقديمي.
## الخطوة 2: إنشاء عرض تقديمي وشكل هندسي
```csharp
using (Presentation pres = new Presentation())
{
    // إنشاء شكل جديد
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
هنا، نقوم بإنشاء عرض تقديمي جديد وإضافة مستطيل كشكل هندسي.
## الخطوة 3: تحديد المسارات الهندسية
```csharp
// إنشاء المسار الهندسي الأول
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.MoveTo(0, 0);
geometryPath0.LineTo(shape.Width, 0);
geometryPath0.LineTo(shape.Width, shape.Height / 3);
geometryPath0.LineTo(0, shape.Height / 3);
geometryPath0.CloseFigure();
// إنشاء المسار الهندسي الثاني
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.MoveTo(0, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height);
geometryPath1.LineTo(0, shape.Height);
geometryPath1.CloseFigure();
```
في هذه الخطوة، نحدد مسارين هندسيين سيشكلان شكلنا الهندسي.
## الخطوة 4: تعيين هندسة الشكل
```csharp
// قم بتعيين هندسة الشكل كتكوين لمسارين هندسيين
shape.SetGeometryPaths(new GeometryPath[] { geometryPath0, geometryPath1 });
```
الآن، قمنا بتعيين هندسة الشكل كتركيبة لمسارين هندسيين محددين سابقًا.
## الخطوة 5: احفظ العرض التقديمي
```csharp
// احفظ العرض التقديمي
pres.Save(resultPath, SaveFormat.Pptx);
}
```
وأخيرًا، نحفظ العرض التقديمي بالشكل الهندسي المركب.
## خاتمة
تهانينا! لقد نجحت في إنشاء كائنات مركبة في شكل هندسي باستخدام Aspose.Slides لـ .NET. قم بتجربة أشكال ومسارات مختلفة لإضفاء الحيوية على عروضك التقديمية.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Slides مع لغات البرمجة الأخرى؟
يدعم Aspose.Slides لغات البرمجة المختلفة، بما في ذلك Java وPython. ومع ذلك، يركز هذا البرنامج التعليمي على C#.
### س: أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
 اكتشف ال[Aspose.Slides الوثائق](https://reference.aspose.com/slides/net/) للحصول على معلومات وأمثلة شاملة.
### س: هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك تجربة Aspose.Slides لـ .NET باستخدام[تجربة مجانية](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على الدعم أو طرح الأسئلة؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع ومساعدته.
### س: هل يمكنني شراء ترخيص مؤقت؟
 نعم يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
