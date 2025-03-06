---
title: إخفاء الأشكال في PowerPoint باستخدام البرنامج التعليمي Aspose.Slides .NET
linktitle: إخفاء الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إخفاء الأشكال في شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. قم بتخصيص العروض التقديمية برمجيًا باستخدام هذا الدليل التفصيلي خطوة بخطوة.
weight: 21
url: /ar/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في عالم العروض التقديمية الديناميكي، يعد التخصيص أمرًا أساسيًا. يوفر Aspose.Slides for .NET حلاً قويًا لمعالجة عروض PowerPoint التقديمية برمجيًا. أحد المتطلبات الشائعة هو القدرة على إخفاء أشكال معينة داخل الشريحة. سيرشدك هذا البرنامج التعليمي خلال عملية إخفاء الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Slides for .NET: تأكد من تثبيت مكتبة Aspose.Slides. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة التطوير المفضلة لديك لـ .NET.
- المعرفة الأساسية بـ C#: تعرف على C# حيث أن أمثلة التعليمات البرمجية المتوفرة بهذه اللغة.
## استيراد مساحات الأسماء
لبدء العمل مع Aspose.Slides، قم باستيراد مساحات الأسماء الضرورية في مشروع C# الخاص بك. وهذا يضمن أن لديك حق الوصول إلى الفئات والأساليب المطلوبة.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
الآن، دعونا نقسم رمز المثال إلى خطوات متعددة لفهم واضح وموجز.
## الخطوة 1: قم بإعداد مشروعك
قم بإنشاء مشروع C# جديد وتأكد من تضمين مكتبة Aspose.Slides.
## الخطوة 2: إنشاء عرض تقديمي
 إنشاء مثيل`Presentation` فئة تمثل ملف PowerPoint. أضف شريحة واحصل على مرجع لها.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## الخطوة 3: إضافة الأشكال إلى الشريحة
قم بإضافة أشكال تلقائية إلى الشريحة، مثل المستطيلات والأقمار، بأبعاد محددة.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## الخطوة 4: إخفاء الأشكال بناءً على النص البديل
تحديد نص بديل وإخفاء الأشكال التي تطابق هذا النص.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## الخطوة 5: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل على القرص بتنسيق PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## خاتمة
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## الأسئلة الشائعة
### هل Aspose.Slides متوافق مع .NET Core؟
نعم، يدعم Aspose.Slides .NET Core، مما يوفر المرونة في بيئة التطوير الخاصة بك.
### هل يمكنني إخفاء الأشكال بناءً على شروط أخرى غير النص البديل؟
قطعاً! يمكنك تخصيص منطق الإخفاء بناءً على سمات مختلفة مثل نوع الشكل أو اللون أو الموضع.
### أين يمكنني العثور على وثائق Aspose.Slides الإضافية؟
 استكشف الوثائق[هنا](https://reference.aspose.com/slides/net/)للحصول على معلومات وأمثلة متعمقة.
### هل التراخيص المؤقتة متاحة لـ Aspose.Slides؟
 نعم يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/)لأغراض تجريبية.
### كيف يمكنني الحصول على دعم المجتمع لـ Aspose.Slides؟
 انضم إلى مجتمع Aspose.Slides على[المنتدى](https://forum.aspose.com/c/slides/11) للمناقشات والمساعدة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
