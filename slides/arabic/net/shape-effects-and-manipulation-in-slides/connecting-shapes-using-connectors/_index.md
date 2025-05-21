---
"description": "استكشف قوة Aspose.Slides لـ .NET، وربط الأشكال بسلاسة في عروضك التقديمية. ارتقِ بعروضك التقديمية باستخدام موصلات ديناميكية."
"linktitle": "ربط الأشكال باستخدام الموصلات في العرض التقديمي"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "Aspose.Slides - ربط الأشكال بسلاسة في .NET"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - ربط الأشكال بسلاسة في .NET

## مقدمة
في عالم العروض التقديمية المتغير، تُضفي إمكانية ربط الأشكال باستخدام الموصلات لمسةً من التطور على شرائحك. يُمكّن Aspose.Slides for .NET المطورين من تحقيق ذلك بسلاسة. سيرشدك هذا البرنامج التعليمي خلال العملية، مُفصّلاً كل خطوة لضمان فهم واضح.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بلغة C# وإطار عمل .NET.
- Aspose.Slides لـ .NET مُثبّت. إذا لم يكن مُثبّتًا، نزّله. [هنا](https://releases.aspose.com/slides/net/).
- تم إعداد بيئة التطوير.
## استيراد مساحات الأسماء
في كود C# الخاص بك، ابدأ باستيراد المساحات الأساسية الضرورية:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. إعداد دليل المستندات
ابدأ بتحديد الدليل للمستند الخاص بك:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. إنشاء فئة عرض تقديمي
قم بإنشاء مثيل لفئة العرض التقديمي لتمثيل ملف PPTX الخاص بك:
```csharp
using (Presentation input = new Presentation())
{
    // الوصول إلى مجموعة الأشكال للشريحة المحددة
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. إضافة الأشكال إلى الشريحة
أضف الأشكال اللازمة إلى الشريحة الخاصة بك، مثل القطع الناقص والمستطيل:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. إضافة شكل الموصل
تضمين شكل موصل في مجموعة أشكال الشريحة:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. ربط الأشكال باستخدام الموصل
حدد الأشكال التي سيتم توصيلها بواسطة الموصل:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. إعادة توجيه الموصل
اتصل بطريقة إعادة التوجيه لتعيين أقصر مسار تلقائي بين الأشكال:
```csharp
connector.Reroute();
```
## 7. حفظ العرض التقديمي
احفظ العرض التقديمي الخاص بك لعرض الأشكال المتصلة:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## خاتمة
تهانينا! لقد نجحت في ربط الأشكال باستخدام الموصلات في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. حسّن عروضك التقديمية بهذه الميزة المتقدمة واجذب جمهورك.
## الأسئلة الشائعة
### هل Aspose.Slides for .NET متوافق مع أحدث إطار عمل .NET؟
نعم، يتم تحديث Aspose.Slides for .NET بانتظام لضمان التوافق مع أحدث إصدارات إطار عمل .NET.
### هل يمكنني ربط أكثر من شكلين باستخدام موصل واحد؟
بالتأكيد، يمكنك ربط أشكال متعددة عن طريق توسيع منطق الموصل في الكود الخاص بك.
### هل هناك أي قيود على الأشكال التي يمكنني توصيلها؟
يدعم Aspose.Slides لـ .NET ربط الأشكال المختلفة، بما في ذلك الأشكال الأساسية والفن الذكي والأشكال المخصصة.
### كيف يمكنني تخصيص مظهر الموصل؟
استكشف وثائق Aspose.Slides للتعرف على طرق تخصيص مظهر الموصل، مثل نمط الخط واللون.
### هل يوجد منتدى مجتمعي لدعم Aspose.Slides؟
نعم، يمكنك العثور على المساعدة ومشاركة تجاربك في [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}