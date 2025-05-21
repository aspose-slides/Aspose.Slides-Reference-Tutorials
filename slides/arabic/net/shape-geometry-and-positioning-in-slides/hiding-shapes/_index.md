---
"description": "تعرّف على كيفية إخفاء الأشكال في شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. خصّص عروضك التقديمية برمجيًا باستخدام هذا الدليل التفصيلي."
"linktitle": "إخفاء الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إخفاء الأشكال في PowerPoint باستخدام برنامج Aspose.Slides .NET التعليمي"
"url": "/ar/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إخفاء الأشكال في PowerPoint باستخدام برنامج Aspose.Slides .NET التعليمي

## مقدمة
في عالم العروض التقديمية المتغير، يُعد التخصيص أمرًا بالغ الأهمية. يوفر Aspose.Slides for .NET حلاً فعالاً للتعامل مع عروض PowerPoint التقديمية برمجيًا. ومن المتطلبات الشائعة إمكانية إخفاء أشكال محددة داخل الشريحة. سيرشدك هذا البرنامج التعليمي خلال عملية إخفاء الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides. يمكنك تنزيلها. [هنا](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة التطوير المفضلة لديك لـ .NET.
- المعرفة الأساسية بلغة C#: تعرف على لغة C# حيث أن أمثلة التعليمات البرمجية المقدمة موجودة بهذه اللغة.
## استيراد مساحات الأسماء
لبدء العمل مع Aspose.Slides، استورد مساحات الأسماء اللازمة في مشروع C#. هذا يضمن لك الوصول إلى الفئات والأساليب المطلوبة.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
الآن، دعنا نقسم كود المثال إلى خطوات متعددة للحصول على فهم واضح وموجز.
## الخطوة 1: إعداد مشروعك
قم بإنشاء مشروع C# جديد وتأكد من تضمين مكتبة Aspose.Slides.
## الخطوة 2: إنشاء عرض تقديمي
إنشاء مثيل `Presentation` فئة تُمثل ملف PowerPoint. أضف شريحة واحصل على مرجع لها.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## الخطوة 3: إضافة الأشكال إلى الشريحة
أضف الأشكال التلقائية إلى الشريحة، مثل المستطيلات والأقمار، بأبعاد محددة.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## الخطوة 4: إخفاء الأشكال بناءً على النص البديل
حدد نصًا بديلًا وإخفاء الأشكال التي تتطابق مع هذا النص.
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
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي المعدل على القرص بتنسيق PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## خاتمة
تهانينا! لقد نجحت في إخفاء الأشكال في عرضك التقديمي باستخدام Aspose.Slides لـ .NET. هذا يفتح آفاقًا واسعة لإنشاء شرائح ديناميكية ومخصصة برمجيًا.
---
## الأسئلة الشائعة
### هل Aspose.Slides متوافق مع .NET Core؟
نعم، يدعم Aspose.Slides .NET Core، مما يوفر المرونة في بيئة التطوير الخاصة بك.
### هل يمكنني إخفاء الأشكال استنادًا إلى شروط أخرى غير النص البديل؟
بالتأكيد! يمكنك تخصيص منطق الإخفاء بناءً على سمات مختلفة، مثل نوع الشكل أو اللون أو الموضع.
### أين يمكنني العثور على وثائق Aspose.Slides الإضافية؟
استكشف الوثائق [هنا](https://reference.aspose.com/slides/net/) للحصول على معلومات وأمثلة متعمقة.
### هل تتوفر تراخيص مؤقتة لـ Aspose.Slides؟
نعم يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار.
### كيف يمكنني الحصول على دعم المجتمع لـ Aspose.Slides؟
انضم إلى مجتمع Aspose.Slides على [المنتدى](https://forum.aspose.com/c/slides/11) للمناقشة والمساعدة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}