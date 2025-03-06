---
title: Aspose.Slides - ربط الأشكال بسلاسة في .NET
linktitle: ربط الأشكال باستخدام الموصلات في العرض التقديمي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: اكتشف قوة Aspose.Slides لـ .NET، وربط الأشكال بسهولة في عروضك التقديمية. ارفع مستوى شرائحك باستخدام الموصلات الديناميكية.
weight: 29
url: /ar/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في عالم العروض التقديمية الديناميكي، تضيف القدرة على ربط الأشكال باستخدام الموصلات طبقة من التطور إلى شرائحك. يعمل Aspose.Slides for .NET على تمكين المطورين من تحقيق ذلك بسلاسة. سيرشدك هذا البرنامج التعليمي خلال العملية، مع تفصيل كل خطوة لضمان فهم واضح.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بـ C# و.NET Framework.
-  تم تثبيت Aspose.Slides لـ .NET. إذا لم يكن الأمر كذلك، قم بتنزيله[هنا](https://releases.aspose.com/slides/net/).
- تم إعداد بيئة التطوير.
## استيراد مساحات الأسماء
في كود C# الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. قم بإعداد دليل المستندات
ابدأ بتحديد الدليل الخاص بمستندك:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. إنشاء مثيل لفئة العرض التقديمي
قم بإنشاء مثيل لفئة العرض التقديمي لتمثيل ملف PPTX الخاص بك:
```csharp
using (Presentation input = new Presentation())
{
    // الوصول إلى مجموعة الأشكال للشريحة المحددة
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. أضف الأشكال إلى الشريحة
أضف الأشكال الضرورية إلى شريحتك، مثل الشكل البيضوي والمستطيل:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. إضافة شكل الموصل
قم بتضمين شكل موصل في مجموعة أشكال الشريحة:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. قم بتوصيل الأشكال بالموصل
حدد الأشكال التي سيتم توصيلها بواسطة الموصل:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. إعادة توجيه الرابط
قم باستدعاء أسلوب إعادة التوجيه لتعيين أقصر مسار تلقائي بين الأشكال:
```csharp
connector.Reroute();
```
## 7. حفظ العرض التقديمي
احفظ العرض التقديمي الخاص بك لعرض الأشكال المتصلة:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## خاتمة
تهانينا! لقد نجحت في توصيل الأشكال باستخدام الموصلات في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. عزز عروضك التقديمية باستخدام هذه الميزة المتقدمة واجذب انتباه جمهورك.
## الأسئلة الشائعة
### هل يتوافق Aspose.Slides for .NET مع أحدث إطار عمل .NET؟
نعم، يتم تحديث Aspose.Slides for .NET بانتظام لضمان التوافق مع أحدث إصدارات إطار عمل .NET.
### هل يمكنني توصيل أكثر من شكلين باستخدام موصل واحد؟
بالتأكيد، يمكنك توصيل أشكال متعددة عن طريق توسيع منطق الموصل في التعليمات البرمجية الخاصة بك.
### هل هناك أي قيود على الأشكال التي يمكنني الاتصال بها؟
يدعم Aspose.Slides for .NET ربط الأشكال المختلفة، بما في ذلك الأشكال الأساسية والفن الذكي والأشكال المخصصة.
### كيف يمكنني تخصيص مظهر الموصل؟
استكشف وثائق Aspose.Slides لمعرفة طرق تخصيص مظهر الموصل، مثل نمط الخط واللون.
### هل يوجد منتدى مجتمعي لدعم Aspose.Slides؟
 نعم، يمكنك الحصول على المساعدة ومشاركة تجاربك في[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
