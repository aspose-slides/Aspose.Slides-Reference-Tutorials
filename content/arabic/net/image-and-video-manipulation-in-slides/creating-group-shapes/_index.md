---
title: إنشاء أشكال جماعية في شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: إنشاء أشكال جماعية في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء شرائح عرض تقديمي جذابة بأشكال جماعية باستخدام Aspose.Slides for .NET. اتبع دليلنا خطوة بخطوة ومثال التعليمات البرمجية المصدر لإضافة الأشكال وتجميعها وتحويلها بسهولة، مما يؤدي إلى تحسين العروض التقديمية.
type: docs
weight: 11
url: /ar/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة شاملة وغنية بالميزات تتيح للمطورين التعامل مع عروض PowerPoint التقديمية برمجياً. سواء كنت تريد إنشاء ملفات العرض التقديمي أو تعديلها أو تحويلها، فإن Aspose.Slides يوفر نطاقًا واسعًا من الأدوات والوظائف لتبسيط العملية.

## المتطلبات الأساسية

قبل البدء في العمل مع Aspose.Slides لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio: قم بتثبيت Visual Studio على جهازك.
-  مكتبة Aspose.Slides: قم بتنزيل مكتبة Aspose.Slides والإشارة إليها في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## إضافة Aspose.Slides إلى مشروعك

1. قم بتنزيل مكتبة Aspose.Slides من الرابط المقدم.
2. أنشئ مشروعًا جديدًا في Visual Studio أو افتح مشروعًا موجودًا.
3. انقر بزر الماوس الأيمن على مشروعك في Solution Explorer وحدد "إدارة حزم NuGet".
4. اختر علامة التبويب "تصفح" وابحث عن "Aspose.Slides".
5. قم بتثبيت حزمة Aspose.Slides في مشروعك.

## إنشاء عرض تقديمي جديد

لنبدأ بإنشاء عرض تقديمي جديد لبرنامج PowerPoint باستخدام Aspose.Slides:

```csharp
using Aspose.Slides;

// إنشاء عرض تقديمي جديد
Presentation presentation = new Presentation();
```

## إضافة أشكال إلى الشريحة

بعد ذلك، دعونا نضيف بعض الأشكال إلى الشريحة. في هذا المثال، سنضيف مستطيلين:

```csharp
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.Slides[0];

// أضف مستطيلات إلى الشريحة
IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);
```

## تجميع الأشكال معاً

الآن، دعونا نجمع الأشكال معًا لإدارتها بشكل جماعي:

```csharp
// أشكال المجموعة
IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });
```

## تطبيق التحويلات على الأشكال المجمعة

يمكنك تطبيق تحويلات مختلفة على الأشكال المجمعة. على سبيل المثال، لنقم بتدوير الأشكال المجمعة بمقدار 45 درجة:

```csharp
// قم بتدوير المجموعة بمقدار 45 درجة
groupShape.Rotation = 45;
```

## مثال على كود المصدر

فيما يلي مثال التعليمات البرمجية المصدر الكامل لإنشاء أشكال المجموعة باستخدام Aspose.Slides:

```csharp
using Aspose.Slides;

namespace GroupShapesExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // إنشاء عرض تقديمي جديد
            Presentation presentation = new Presentation();

            // الوصول إلى الشريحة الأولى
            ISlide slide = presentation.Slides[0];

            // أضف مستطيلات إلى الشريحة
            IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
            IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);

            // أشكال المجموعة
            IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });

            // قم بتدوير المجموعة بمقدار 45 درجة
            groupShape.Rotation = 45;

            // احفظ العرض التقديمي
            presentation.Save("GroupShapesExample.pptx", SaveFormat.Pptx);
        }
    }
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء أشكال جماعية في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. توفر المكتبة طريقة مباشرة لإضافة الأشكال وتجميعها معًا وتطبيق التحويلات لتحسين العروض التقديمية الخاصة بك ديناميكيًا.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ .NET؟

يمكنك تنزيل مكتبة Aspose.Slides من الرابط المقدم:[هنا](https://releases.aspose.com/slides/net/). بمجرد تنزيله، يمكنك إضافته إلى مشروعك باستخدام حزم NuGet.

### هل يمكنني تطبيق تحويلات مختلفة على الأشكال المجمعة؟

نعم، يمكنك تطبيق تحويلات متنوعة مثل التدوير والقياس وتحديد الموضع على الأشكال المجمعة، مما يسمح لك بتخصيص المظهر المرئي لشرائحك.

### هل Aspose.Slides مناسب لإنشاء العروض التقديمية وتعديلها؟

قطعاً! Aspose.Slides for .NET هي مكتبة متعددة الاستخدامات تدعم إنشاء ملفات العروض التقديمية وتعديلها وتحويلها. ويوفر مجموعة واسعة من الميزات لتلبية الاحتياجات المختلفة.

### هل يمكنني تجميع أشكال من أنواع مختلفة معًا؟

 نعم، يمكنك تجميع الأشكال من أنواع مختلفة، مثل المستطيلات والدوائر ومربعات النص، معًا باستخدام`GroupShapes` طريقة. يمكّنك هذا من إدارتها ومعالجتها بشكل جماعي.

### هل Aspose.Slides مناسب لتطبيقات .NET فقط؟

نعم، تم تصميم Aspose.Slides خصيصًا لتطبيقات .NET. ومع ذلك، هناك إصدارات متاحة للغات برمجة أخرى أيضًا، مثل Java.