---
"date": "2025-04-16"
"description": "تعلّم كيفية تحسين عروضك التقديمية بأشكال نجمية مخصصة باستخدام Aspose.Slides لـ .NET. اتبع هذا الدليل خطوة بخطوة لإنشاء عروض مرئية جذابة."
"title": "كيفية إنشاء أشكال النجوم المخصصة وحفظها في عروض تقديمية .NET باستخدام Aspose.Slides"
"url": "/ar/net/shapes-text-frames/create-star-shape-dotnet-presentation-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء أشكال النجوم المخصصة وحفظها في عروض تقديمية .NET باستخدام Aspose.Slides

يُمكنك من خلال دمج أشكال فريدة كالنجوم تحويل شرائح عرضك التقديمي من عادية إلى استثنائية. يُرشدك هذا البرنامج التعليمي إلى كيفية إنشاء وحفظ أشكال هندسية مُخصصة على شكل نجمة باستخدام Aspose.Slides لـ .NET، مما يجعل عروضك التقديمية أكثر جاذبية وجاذبية بصريًا.

## ما سوف تتعلمه:
- إنشاء شكل نجمة مخصص بنصف قطر محدد في C#.
- دمج هذه الميزة في تطبيق .NET.
- حفظ العرض التقديمي بالشكل المخصص الجديد باستخدام Aspose.Slides.

دعونا نغوص في الأمر!

### المتطلبات الأساسية

قبل البدء، تأكد من أن لديك:
- **Aspose.Slides لـ .NET**يلزم توفر الإصدار 23.x أو أحدث. تتيح هذه المكتبة إنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا.
- **بيئة التطوير**:Visual Studio مع إعداد مشروع .NET.
- **المعرفة الأساسية بلغة C#**:ستساعدك المعرفة بمفاهيم برمجة C# على فهم التنفيذ بشكل أفضل.

### إعداد Aspose.Slides لـ .NET

أضف Aspose.Slides إلى مشروعك باستخدام إحدى الطرق التالية:

**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**استخدام مدير الحزم:**
```powershell
Install-Package Aspose.Slides
```

**استخدام واجهة مستخدم NuGet Package Manager:**
1. افتح مربع الحوار "إدارة حزم NuGet" في Visual Studio.
2. ابحث عن "Aspose.Slides".
3. قم بتثبيت الإصدار الأحدث.

#### الحصول على ترخيص
للاستفادة الكاملة من Aspose.Slides، فكر في الحصول على ترخيص:
- **نسخة تجريبية مجانية**:ابدأ باستخدام ترخيص مؤقت لاستكشاف الميزات الكاملة دون قيود.
- **شراء**يزور [شراء Aspose](https://purchase.aspose.com/buy) للحصول على خيارات ترخيص مختلفة تناسب احتياجاتك.

### دليل التنفيذ
سنقوم بإنشاء شكل النجمة وحفظه في عرض تقديمي، مقسمًا إلى ميزتين رئيسيتين.

#### الميزة 1: إنشاء مسار هندسي مخصص
تتضمن هذه الميزة إنشاء مسار هندسي يشكل شكل نجمة باستخدام نصف قطر خارجي وداخلي محدد.

**ملخص**:نحسب النقاط لكل من الحواف الخارجية والداخلية للنجم ونربطها لتشكيل شكل نجمة مغلقة.

##### خطوات التنفيذ:

**الخطوة 1**:تحديد حساب نقاط النجوم
```csharp
using System.Collections.Generic;
using Aspose.Slides.Export;
using System.Drawing;

public static class StarGeometryCreator
{
    public static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
    {
        GeometryPath starPath = new GeometryPath();
        List<PointF> points = new List<PointF>();
        int step = 72; // زاوية الخطوة بالدرجات

        for (int angle = -90; angle < 270; angle += step)
        {
            double radians = angle * (Math.PI / 180f);
            double xOuter = outerRadius * Math.Cos(radians) + outerRadius;
            double yOuter = outerRadius * Math.Sin(radians) + outerRadius;
            points.Add(new PointF((float)xOuter, (float)yOuter));

            radians = Math.PI * (angle + step / 2) / 180.0;
            double xInner = innerRadius * Math.Cos(radians) + outerRadius;
            double yInner = innerRadius * Math.Sin(radians) + outerRadius;
            points.Add(new PointF((float)xInner, (float)yInner));
        }

        starPath.MoveTo(points[0]);
        for (int i = 1; i < points.Count; i++)
        {
            starPath.LineTo(points[i]);
        }
        starPath.CloseFigure();

        return starPath;
    }
}
```
**توضيح**:الطريقة `CreateStarGeometry` يحسب إحداثيات الرؤوس الخارجية والداخلية بناءً على أنصاف أقطار المدخلات. ويستخدم علم المثلثات لتحديد موقع كل نقطة، مما يُنشئ مسارًا متصلًا يُشكل نجمة.

#### الميزة 2: إنشاء عرض تقديمي وحفظه باستخدام الشكل المخصص
هنا نقوم بدمج الهندسة المخصصة في العرض التقديمي وحفظها كملف .pptx.

**ملخص**:أضف شكلاً إلى الشريحة باستخدام مسار الهندسة المخصص الذي تم إنشاؤه في الخطوة السابقة.

##### خطوات التنفيذ:

**الخطوة 1**تهيئة العرض التقديمي
```csharp
using Aspose.Slides;
using System.IO;

public static class PresentationCreator
{
    public static void CreateAndSavePresentation()
    {
        string resultPath = Path.Combine("YOUR_OUTPUT_DIRECTORY\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}