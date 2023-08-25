---
title: تصدير الأشكال إلى تنسيق SVG من العرض التقديمي
linktitle: تصدير الأشكال إلى تنسيق SVG من العرض التقديمي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تصدير الأشكال من عرض PowerPoint التقديمي إلى تنسيق SVG باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع كود المصدر متضمن. استخراج الأشكال بكفاءة لمختلف التطبيقات.
type: docs
weight: 16
url: /ar/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
سيرشدك هذا الدليل خلال عملية تصدير الأشكال من عرض تقديمي إلى تنسيق SVG باستخدام مكتبة Aspose.Slides for .NET. Aspose.Slides عبارة عن واجهة برمجة تطبيقات قوية تتيح لك العمل مع ملفات Microsoft PowerPoint برمجيًا. ستتعلم في هذا البرنامج التعليمي كيفية استخراج الأشكال من العرض التقديمي وحفظها بتنسيق SVG باستخدام لغة C#.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Visual Studio
- الفهم الأساسي للبرمجة C#
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## دليل خطوة بخطوة

اتبع هذه الخطوات لتصدير الأشكال إلى تنسيق SVG من العرض التقديمي:

### 1. إنشاء مشروع جديد

افتح Visual Studio وقم بإنشاء مشروع C# جديد.

### 2. أضف مرجعًا إلى Aspose.Slides

في مشروعك، انقر بزر الماوس الأيمن على "المراجع" في مستكشف الحلول، ثم انقر على "إضافة مرجع". استعرض وحدد ملف Aspose.Slides DLL الذي قمت بتنزيله.

### 3. قم بتحميل العرض التقديمي

```csharp
using Aspose.Slides;

// قم بتحميل العرض التقديمي
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. التكرار من خلال الأشكال

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    // تحقق مما إذا كان الشكل عبارة عن شكل مجموعة
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            // تصدير الشكل إلى SVG
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        // تصدير الشكل إلى SVG
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5. حفظ ملفات SVG

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); // حفظ التغييرات على العرض التقديمي
```

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل مكتبة Aspose.Slides for .NET من[هنا](https://releases.aspose.com/slides/net/). اتبع تعليمات التثبيت المتوفرة في الوثائق.

### كيف أقوم بتحميل عرض PowerPoint التقديمي باستخدام Aspose.Slides؟

 يمكنك تحميل العرض التقديمي باستخدام`Presentation` منشئ الطبقة. قم بتوفير المسار إلى ملف PowerPoint كمعلمة.

### كيف يمكنني تصدير شكل إلى تنسيق SVG؟

 يمكنك استخدام ال`WriteAsSvg` طريقة على`IShape` كائن لتصديره إلى تنسيق SVG. تحتاج إلى تحديد اسم الملف لمخرجات SVG.

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية تصدير الأشكال من عرض PowerPoint التقديمي إلى تنسيق SVG باستخدام مكتبة Aspose.Slides for .NET. يمكن أن يكون هذا مفيدًا عندما تحتاج إلى استخراج أشكال فردية لاستخدامها في تطبيقات أو أنظمة أساسية أخرى تدعم رسومات SVG. يوفر Aspose.Slides طريقة بسيطة وفعالة لتحقيق ذلك برمجيًا.

 لمزيد من التفاصيل والميزات المتقدمة، راجع[Aspose.Slides لمرجع .NET API](https://reference.aspose.com/slides/net/).