---
title: إتقان الأشكال الهندسية باستخدام ShapeUtil - Aspose.Slides .NET
linktitle: استخدام ShapeUtil للأشكال الهندسية في شرائح العرض التقديمي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: اكتشف قوة Aspose.Slides لـ .NET باستخدام ShapeUtil للأشكال الهندسية الديناميكية. قم بإنشاء عروض تقديمية جذابة دون عناء. قم بالتنزيل الآن! تعرف على كيفية تحسين عروض PowerPoint التقديمية باستخدام Aspose.Slides. استكشف ShapeUtil لمعالجة الأشكال الهندسية. دليل خطوة بخطوة مع كود مصدر .NET. تحسين العروض التقديمية بشكل فعال.
weight: 17
url: /ar/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان الأشكال الهندسية باستخدام ShapeUtil - Aspose.Slides .NET

## مقدمة
يعد إنشاء شرائح عرض تقديمي ديناميكية وجذابة بصريًا مهارة أساسية، ويوفر Aspose.Slides for .NET مجموعة أدوات قوية لتحقيق ذلك. في هذا البرنامج التعليمي، سوف نستكشف استخدام ShapeUtil للتعامل مع الأشكال الهندسية في شرائح العرض التقديمي. سواء كنت مطورًا متمرسًا أو بدأت للتو في استخدام Aspose.Slides، سيرشدك هذا الدليل خلال عملية استخدام ShapeUtil لتحسين عروضك التقديمية.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي لبرمجة C# و.NET.
-  تم تثبيت Aspose.Slides لمكتبة .NET. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
- بيئة تطوير تم إعدادها لتشغيل تطبيقات .NET.
## استيراد مساحات الأسماء
في كود C# الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Slides. أضف ما يلي في بداية البرنامج النصي الخاص بك:
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
الآن، دعنا نقسم المثال المقدم إلى خطوات متعددة لإنشاء دليل خطوة بخطوة لاستخدام ShapeUtil للأشكال الهندسية في شرائح العرض التقديمي.
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
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
أضف شكلاً مستطيلاً إلى الشريحة الأولى من العرض التقديمي.
## الخطوة 5: احصل على المسار الهندسي الأصلي
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
استرجع المسار الهندسي للشكل واضبط وضع التعبئة.
## الخطوة 6: إنشاء مسار رسومات مع النص
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
قم بإنشاء مسار رسومات يحتوي على نص لإضافته إلى الشكل.
## الخطوة 7: تحويل مسار الرسومات إلى مسار هندسي
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
استخدم ShapeUtil لتحويل مسار الرسومات إلى مسار هندسي وتعيين وضع التعبئة.
## الخطوة 8: قم بتعيين المسارات الهندسية المدمجة للشكل
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
قم بدمج المسار الهندسي الجديد مع المسار الأصلي وقم بتعيينه على الشكل.
## الخطوة 9: احفظ العرض التقديمي
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدل بالشكل الهندسي الجديد.
## خاتمة
تهانينا! لقد نجحت في استكشاف استخدام ShapeUtil للتعامل مع الأشكال الهندسية في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. تتيح لك هذه الميزة القوية إنشاء عروض تقديمية ديناميكية وجذابة بسهولة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات البرمجة الأخرى؟
يدعم Aspose.Slides بشكل أساسي لغات .NET. ومع ذلك، يوفر Aspose مكتبات مماثلة لمنصات ولغات أخرى.
### أين يمكنني العثور على وثائق مفصلة عن Aspose.Slides لـ .NET؟
 الوثائق متاحة[هنا](https://reference.aspose.com/slides/net/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك العثور على النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على دعم Aspose.Slides لـ .NET؟
 قم بزيارة منتدى دعم المجتمع[هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 نعم يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
