---
title: إزالة شرائح الشكل - البرنامج التعليمي Aspose.Slides .NET
linktitle: إزالة الأجزاء من الشكل الهندسي في شرائح العرض التقديمي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إزالة الأجزاء من الأشكال الهندسية في شرائح العرض التقديمي باستخدام Aspose.Slides API لـ .NET. دليل خطوة بخطوة مع كود المصدر.
weight: 16
url: /ar/net/shape-geometry-and-positioning-in-slides/removing-segments-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
غالبًا ما يتضمن إنشاء عروض تقديمية جذابة بصريًا معالجة الأشكال والعناصر لتحقيق التصميم المطلوب. باستخدام Aspose.Slides for .NET، يمكن للمطورين التحكم بسهولة في هندسة الأشكال، مما يسمح بإزالة أجزاء معينة. في هذا البرنامج التعليمي، سنرشدك خلال عملية إزالة الأجزاء من الشكل الهندسي في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Slides لمكتبة .NET: تأكد من تثبيت Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[صفحة الإصدار](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET، مثل Visual Studio، لدمج Aspose.Slides في مشروعك.
- دليل المستندات: قم بإنشاء دليل حيث ستخزن مستنداتك وقم بتعيين المسار بشكل مناسب في الكود.
## استيراد مساحات الأسماء
للبدء، قم باستيراد مساحات الأسماء الضرورية في مشروع .NET الخاص بك. توفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب المطلوبة للعمل مع شرائح العرض التقديمي.
```csharp
using System.IO;
using Aspose.Slides.Export;
```
## الخطوة 1: إنشاء عرض تقديمي جديد
ابدأ بإنشاء عرض تقديمي جديد باستخدام مكتبة Aspose.Slides.
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
string resultPath = Path.Combine(dataDir, "GeometryShapeRemoveSegment.pptx");
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك لإنشاء شكل وتعيين مساره الهندسي موجود هنا.
    // احفظ العرض التقديمي
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## الخطوة 2: إضافة شكل هندسي
في هذه الخطوة، قم بإنشاء شكل جديد ذو هندسة محددة. في هذا المثال، نستخدم شكل قلب.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Heart, 100, 100, 300, 300);
```
## الخطوة 3: الحصول على مسار الهندسة
استرداد المسار الهندسي للشكل الذي تم إنشاؤه.
```csharp
IGeometryPath path = shape.GetGeometryPaths()[0];
```
## الخطوة 4: إزالة الجزء
إزالة جزء محدد من المسار الهندسي. في هذا المثال، نقوم بإزالة المقطع الموجود في الفهرس 2.
```csharp
path.RemoveAt(2);
```
## الخطوة 5: تعيين مسار هندسي جديد
قم بتعيين المسار الهندسي المعدل مرة أخرى إلى الشكل.
```csharp
shape.SetGeometryPath(path);
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إزالة الأجزاء من الشكل الهندسي في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. قم بتجربة أشكال ومؤشرات مقطعية مختلفة لتحقيق التأثيرات المرئية المطلوبة في عروضك التقديمية.
## الأسئلة الشائعة
### هل يمكنني تطبيق هذه التقنية على أشكال أخرى؟
نعم، يمكنك استخدام خطوات مماثلة لأشكال مختلفة يدعمها Aspose.Slides.
### هل هناك حد لعدد المقاطع التي يمكنني إزالتها؟
لا يوجد حد صارم، ولكن كن حذرا للحفاظ على سلامة الشكل.
### كيف أتعامل مع الأخطاء أثناء عملية إزالة المقطع؟
قم بتنفيذ المعالجة المناسبة للأخطاء باستخدام كتل محاولة الالتقاط.
### هل يمكنني التراجع عن إزالة المقطع بعد حفظ العرض التقديمي؟
لا، لا يمكن التراجع عن التغييرات بعد الحفظ. فكر في حفظ النسخ الاحتياطية قبل التعديل.
### أين يمكنني الحصول على دعم أو مساعدة إضافية؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
