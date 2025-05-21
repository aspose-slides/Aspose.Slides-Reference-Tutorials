---
"description": "تعرّف على كيفية تحسين تطبيقات .NET باستخدام Aspose.Slides. يرشدك هذا البرنامج التعليمي إلى كيفية إضافة مقاطع إلى الأشكال الهندسية لعروض تقديمية جذابة."
"linktitle": "إضافة أجزاء إلى شكل هندسي في العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إتقان العناصر المرئية - إضافة المقاطع باستخدام Aspose.Slides في .NET"
"url": "/ar/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إتقان العناصر المرئية - إضافة المقاطع باستخدام Aspose.Slides في .NET

## مقدمة
في عالم تطوير .NET، يُعد إنشاء عروض تقديمية جذابة بصريًا مطلبًا شائعًا. Aspose.Slides for .NET هي مكتبة فعّالة تُسهّل التكامل السلس لإمكانيات إنشاء العروض التقديمية القوية في تطبيقات .NET. يُركز هذا البرنامج التعليمي على جانب مُحدد من تصميم العروض التقديمية، وهو إضافة مقاطع إلى الأشكال الهندسية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio على جهازك.
- تم تنزيل Aspose.Slides لمكتبة .NET والإشارة إليها في مشروعك.
## استيراد مساحات الأسماء
في شيفرة C#، تأكد من استيراد مساحات الأسماء اللازمة للوصول إلى وظائف Aspose.Slides. أضف الأسطر التالية إلى شيفرتك:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
الآن، دعونا نقسم المثال إلى خطوات متعددة.
## الخطوة 1: إعداد مشروعك
ابدأ بإنشاء مشروع C# جديد في Visual Studio. تأكد من وجود مكتبة Aspose.Slides في مشروعك.
## الخطوة 2: إنشاء عرض تقديمي
أنشئ كائن عرض تقديمي جديد باستخدام مكتبة Aspose.Slides. سيُستخدم هذا الكائن كلوحة رسم لشكلك الهندسي.
```csharp
using (Presentation pres = new Presentation())
{
    // يظهر هنا الكود الخاص بإنشاء العرض التقديمي
}
```
## الخطوة 3: إضافة شكل هندسي
أنشئ شكلًا هندسيًا داخل العرض التقديمي. على سبيل المثال، لنضف مستطيلًا إلى الشريحة الأولى.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## الخطوة 4: الحصول على مسار الهندسة
استرداد مسار الهندسة للشكل الذي تم إنشاؤه للتحكم في أجزائه.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## الخطوة 5: إضافة المقاطع
أضف أجزاءً (خطوطًا) إلى مسار الهندسة. في هذا المثال، تمت إضافة خطين إلى المسار.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## الخطوة 6: تعيين مسار الهندسة المحرر
قم بتعيين مسار الهندسة المعدل إلى الشكل لتطبيق التغييرات.
```csharp
shape.SetGeometryPath(geometryPath);
```
## الخطوة 7: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل في الموقع المطلوب.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
باستخدام هذه الخطوات، تكون قد نجحت في إضافة أجزاء إلى شكل هندسي في عرض تقديمي باستخدام Aspose.Slides لـ .NET.
## خاتمة
يُمكّن Aspose.Slides for .NET المطورين من تحسين تطبيقاتهم بإمكانيات متقدمة لإنشاء العروض التقديمية. تُتيح إضافة مقاطع إلى الأشكال الهندسية إمكانية تخصيص العناصر المرئية لعروضك التقديمية.
### الأسئلة الشائعة
### هل يمكنني إضافة أنواع مختلفة من الأشكال باستخدام Aspose.Slides؟
نعم، يدعم Aspose.Slides أنواعًا مختلفة من الأشكال، بما في ذلك المستطيلات والدوائر وأشكال الهندسة المخصصة.
### هل يلزم الحصول على ترخيص لاستخدام Aspose.Slides في مشروعي؟
نعم، يلزم ترخيص ساري المفعول. يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار أو شراء ترخيص كامل للإنتاج.
### كيف يمكنني الحصول على الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
### هل هناك دروس تعليمية أخرى متاحة لـ Aspose.Slides؟
استكشف [التوثيق](https://reference.aspose.com/slides/net/) للحصول على أدلة وأمثلة شاملة.
### هل يمكنني تجربة Aspose.Slides مجانًا قبل الشراء؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}