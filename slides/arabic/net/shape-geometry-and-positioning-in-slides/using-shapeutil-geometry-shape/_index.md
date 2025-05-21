---
"description": "اكتشف قوة Aspose.Slides لـ .NET مع ShapeUtil للأشكال الهندسية الديناميكية. أنشئ عروضًا تقديمية جذابة بسهولة. حمل الآن! تعلّم كيفية تحسين عروض PowerPoint التقديمية باستخدام Aspose.Slides. استكشف ShapeUtil لمعالجة الأشكال الهندسية. دليل خطوة بخطوة مع شفرة المصدر لـ .NET. حسّن عروضك التقديمية بفعالية."
"linktitle": "استخدام ShapeUtil للشكل الهندسي في شرائح العرض التقديمي"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إتقان الأشكال الهندسية باستخدام ShapeUtil - Aspose.Slides .NET"
"url": "/ar/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إتقان الأشكال الهندسية باستخدام ShapeUtil - Aspose.Slides .NET

## مقدمة
يُعد إنشاء شرائح عرض تقديمي جذابة بصريًا وديناميكية مهارة أساسية، ويوفر Aspose.Slides for .NET مجموعة أدوات فعّالة لتحقيق ذلك. في هذا البرنامج التعليمي، سنستكشف استخدام ShapeUtil للتعامل مع الأشكال الهندسية في شرائح العرض التقديمي. سواء كنت مطورًا محترفًا أو مبتدئًا في استخدام Aspose.Slides، سيرشدك هذا الدليل خلال عملية استخدام ShapeUtil لتحسين عروضك التقديمية.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- فهم أساسي لبرمجة C# و.NET.
- تم تثبيت مكتبة Aspose.Slides لـ .NET. إذا لم يكن مثبتًا، يمكنك تنزيله. [هنا](https://releases.aspose.com/slides/net/).
- بيئة تطوير تم إعدادها لتشغيل تطبيقات .NET.
## استيراد مساحات الأسماء
في شيفرة C#، تأكد من استيراد مساحات الأسماء اللازمة للوصول إلى وظائف Aspose.Slides. أضف ما يلي في بداية النص البرمجي:
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
الآن، دعنا نقسم المثال المقدم إلى خطوات متعددة لإنشاء دليل خطوة بخطوة لاستخدام ShapeUtil للأشكال الهندسية في شرائح العرض التقديمي.
## الخطوة 1: إعداد دليل المستندات الخاص بك
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي الذي تريد حفظ العرض التقديمي فيه.
## الخطوة 2: تحديد اسم ملف الإخراج
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
حدد اسم ملف الإخراج المطلوب، بما في ذلك امتداد الملف.
## الخطوة 3: إنشاء عرض تقديمي
```csharp
using (Presentation pres = new Presentation())
```
قم بتهيئة كائن عرض تقديمي جديد باستخدام مكتبة Aspose.Slides.
## الخطوة 4: إضافة شكل هندسي
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
أضف شكل مستطيل إلى الشريحة الأولى من العرض التقديمي.
## الخطوة 5: الحصول على مسار الهندسة الأصلي
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
استرداد مسار هندسة الشكل وتعيين وضع التعبئة.
## الخطوة 6: إنشاء مسار رسومي بالنص
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
إنشاء مسار رسومي بالنص الذي سيتم إضافته إلى الشكل.
## الخطوة 7: تحويل مسار الرسومات إلى مسار هندسي
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
استخدم ShapeUtil لتحويل مسار الرسومات إلى مسار هندسي وتعيين وضع التعبئة.
## الخطوة 8: تعيين مسارات الهندسة المجمعة للشكل
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
قم بدمج مسار الهندسة الجديد مع المسار الأصلي وضبطه على الشكل.
## الخطوة 9: حفظ العرض التقديمي
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدّل باستخدام الشكل الهندسي الجديد.
## خاتمة
تهانينا! لقد نجحتَ في استخدام ShapeUtil لمعالجة الأشكال الهندسية في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. تتيح لك هذه الميزة الفعّالة إنشاء عروض تقديمية ديناميكية وجذابة بسهولة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات برمجة أخرى؟
يدعم Aspose.Slides بشكل أساسي لغات .NET. ومع ذلك، يوفر Aspose مكتبات مشابهة لمنصات ولغات أخرى.
### أين يمكنني العثور على وثائق مفصلة لـ Aspose.Slides لـ .NET؟
الوثائق متاحة [هنا](https://reference.aspose.com/slides/net/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
نعم، يمكنك العثور على النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
قم بزيارة منتدى دعم المجتمع [هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
نعم يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}