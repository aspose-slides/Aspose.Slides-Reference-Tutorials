---
"description": "تعلّم كيفية إنشاء عروض تقديمية رائعة بأشكال هندسية مركبة باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة للحصول على نتائج مبهرة."
"linktitle": "إنشاء كائنات مركبة في شكل هندسي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إتقان الأشكال الهندسية المركبة في العروض التقديمية"
"url": "/ar/net/shape-geometry-and-positioning-in-slides/creating-composite-objects-geometry-shape/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إتقان الأشكال الهندسية المركبة في العروض التقديمية

## مقدمة
استغلّ إمكانات Aspose.Slides لـ .NET لتحسين عروضك التقديمية من خلال إنشاء كائنات مركّبة بأشكال هندسية. سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء شرائح جذابة بصريًا بأشكال هندسية معقدة باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- فهم أساسي للغة البرمجة C#.
- تم تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/).
- بيئة تطوير تم إعدادها باستخدام Visual Studio أو أي أداة تطوير C# أخرى.
## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء اللازمة في شيفرة C# للاستفادة من وظائف Aspose.Slides. أدرج مساحات الأسماء التالية في بداية شيفرتك:
```csharp
using System.IO;
using Aspose.Slides.Export;
```
الآن، دعنا نقسم كود المثال إلى خطوات متعددة لإرشادك خلال إنشاء كائنات مركبة في شكل هندسي باستخدام Aspose.Slides لـ .NET:
## الخطوة 1: إعداد البيئة
```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
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
هنا، نقوم بإنشاء عرض تقديمي جديد ونضيف مستطيلًا كشكل هندسي.
## الخطوة 3: تحديد مسارات الهندسة
```csharp
// إنشاء أول مسار هندسي
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.MoveTo(0, 0);
geometryPath0.LineTo(shape.Width, 0);
geometryPath0.LineTo(shape.Width, shape.Height / 3);
geometryPath0.LineTo(0, shape.Height / 3);
geometryPath0.CloseFigure();
// إنشاء مسار هندسي ثانٍ
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.MoveTo(0, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height);
geometryPath1.LineTo(0, shape.Height);
geometryPath1.CloseFigure();
```
في هذه الخطوة، نقوم بتحديد مسارين هندسيين سيشكلان شكلنا الهندسي.
## الخطوة 4: تعيين هندسة الشكل
```csharp
// تعيين هندسة الشكل كتركيبة لمسارين هندسيين
shape.SetGeometryPaths(new GeometryPath[] { geometryPath0, geometryPath1 });
```
الآن، قمنا بتعيين هندسة الشكل كتركيبة من مساري الهندسة اللذين تم تعريفهما سابقًا.
## الخطوة 5: حفظ العرض التقديمي
```csharp
// حفظ العرض التقديمي
pres.Save(resultPath, SaveFormat.Pptx);
}
```
وأخيرًا، نحفظ العرض التقديمي باستخدام شكل الهندسة المركبة.
## خاتمة
تهانينا! لقد نجحت في إنشاء كائنات مركبة بشكل هندسي باستخدام Aspose.Slides لـ .NET. جرّب أشكالًا ومسارات مختلفة لإضفاء الحيوية على عروضك التقديمية.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Slides مع لغات برمجة أخرى؟
يدعم Aspose.Slides لغات برمجة متنوعة، بما فيها Java وPython. مع ذلك، يُركز هذا البرنامج التعليمي على C#.
### س: أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
استكشف [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/) للحصول على معلومات شاملة وأمثلة.
### س: هل هناك نسخة تجريبية مجانية متاحة؟
نعم، يمكنك تجربة Aspose.Slides لـ .NET باستخدام [نسخة تجريبية مجانية](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على الدعم أو طرح الأسئلة؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على الدعم والمساعدة المجتمعية.
### س: هل يمكنني شراء ترخيص مؤقت؟
نعم يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}