---
title: إنشاء هندسة مخصصة في C# باستخدام Aspose.Slides لـ .NET
linktitle: إنشاء هندسة مخصصة في شكل هندسي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعلم كيفية إنشاء أشكال هندسية مخصصة في Aspose.Slides لـ .NET. ارفع مستوى عروضك التقديمية بأشكال فريدة. دليل خطوة بخطوة لمطوري C#.
weight: 15
url: /ar/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في عالم العروض التقديمية الديناميكي، يمكن أن تؤدي إضافة أشكال وأشكال هندسية فريدة إلى رفع مستوى المحتوى الخاص بك، مما يجعله أكثر جاذبية وجاذبية بصريًا. يوفر Aspose.Slides for .NET حلاً قويًا لإنشاء أشكال هندسية مخصصة داخل الأشكال، مما يسمح لك بالتحرر من التصميمات التقليدية. سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء أشكال هندسية مخصصة في GeometryShape باستخدام Aspose.Slides لـ .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي للغة البرمجة C#.
- Aspose.Slides لمكتبة .NET المثبتة في بيئة التطوير الخاصة بك.
- إعداد Visual Studio أو أي بيئة تطوير مفضلة لـ C#.
## استيراد مساحات الأسماء
للبدء، قم باستيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## الخطوة 1: قم بإعداد مشروعك
قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك. تأكد من تثبيت Aspose.Slides for .NET بشكل صحيح.
## الخطوة 2: تحديد دليل المستندات الخاص بك
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## الخطوة 3: تعيين نصف قطر النجم الخارجي والداخلي
```csharp
float R = 100, r = 50; // نصف قطر النجم الخارجي والداخلي
```
## الخطوة 4: إنشاء مسار هندسة النجوم
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## الخطوة 5: إنشاء عرض تقديمي
```csharp
using (Presentation pres = new Presentation())
{
    // إنشاء شكل جديد
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // قم بتعيين مسار هندسي جديد للشكل
    shape.SetGeometryPath(starPath);
    // احفظ العرض التقديمي
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## الخطوة 6: تحديد طريقة CreateStarGeometry
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إنشاء أشكال هندسية مخصصة في GeometryShape باستخدام Aspose.Slides لـ .NET. وهذا يفتح عالمًا من الإمكانيات لإنشاء عروض تقديمية فريدة ومذهلة بصريًا.
## الأسئلة الشائعة
### 1. هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات البرمجة الأخرى؟
نعم، يدعم Aspose.Slides لغات البرمجة المختلفة، لكن هذا البرنامج التعليمي يركز على لغة C#.
### 2. أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟
 قم بزيارة[توثيق](https://reference.aspose.com/slides/net/) للحصول على معلومات مفصلة.
### 3. هل تتوفر نسخة تجريبية مجانية من Aspose.Slides لـ .NET؟
 نعم، يمكنك استكشاف أ[تجربة مجانية](https://releases.aspose.com/) لتجربة الميزات.
### 4. كيف يمكنني الحصول على دعم Aspose.Slides لـ .NET؟
 اطلب المساعدة وتفاعل مع المجتمع في[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. أين يمكنني شراء Aspose.Slides لـ .NET؟
 يمكنك شراء Aspose.Slides لـ .NET[هنا](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
