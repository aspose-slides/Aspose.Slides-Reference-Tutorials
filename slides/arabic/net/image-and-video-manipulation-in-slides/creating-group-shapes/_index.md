---
"description": "تعرّف على كيفية إنشاء أشكال جماعية في PowerPoint باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة لإنشاء عروض تقديمية جذابة بصريًا."
"linktitle": "إنشاء أشكال المجموعات في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "Aspose.Slides - إنشاء أشكال المجموعة في .NET"
"url": "/ar/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - إنشاء أشكال المجموعة في .NET

## مقدمة
إذا كنت ترغب في تحسين المظهر المرئي لشرائح عرضك التقديمي وتنظيم المحتوى بكفاءة أكبر، فإن دمج أشكال المجموعات يُعد حلاً فعالاً. يوفر Aspose.Slides for .NET طريقة سلسة لإنشاء أشكال المجموعات والتحكم بها في عروض PowerPoint التقديمية. في هذا البرنامج التعليمي، سنشرح عملية إنشاء أشكال المجموعات باستخدام Aspose.Slides، مقسمينها إلى خطوات سهلة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides. يمكنك تنزيلها من [موقع إلكتروني](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة عمل باستخدام IDE متوافق مع .NET، مثل Visual Studio.
- المعرفة الأساسية بلغة C#: تعرف على أساسيات لغة البرمجة C#.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، ابدأ باستيراد المساحات الأساسية الضرورية:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## الخطوة 1: إنشاء فئة العرض التقديمي

إنشاء مثيل لـ `Presentation` الفئة وتحديد الدليل الذي سيتم تخزين مستنداتك فيه:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // واصل الخطوات التالية ضمن هذه الكتلة باستخدام
}
```

## الخطوة 2: الوصول إلى الشريحة الأولى

استرجاع الشريحة الأولى من العرض التقديمي:

```csharp
ISlide sld = pres.Slides[0];
```

## الخطوة 3: الوصول إلى مجموعة الأشكال

الوصول إلى مجموعة الأشكال الموجودة على الشريحة:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## الخطوة 4: إضافة شكل المجموعة

إضافة شكل المجموعة إلى الشريحة:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## الخطوة 5: إضافة الأشكال داخل شكل المجموعة

املأ شكل المجموعة بالأشكال الفردية:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## الخطوة 6: إضافة إطار شكل المجموعة

قم بتحديد الإطار لشكل المجموعة بأكملها:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## الخطوة 7: حفظ العرض التقديمي

احفظ العرض التقديمي المعدّل في الدليل المحدد:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

كرر هذه الخطوات في تطبيق C# الخاص بك لإنشاء أشكال المجموعة بنجاح في شرائح العرض التقديمي باستخدام Aspose.Slides.

## خاتمة
في هذا البرنامج التعليمي، استكشفنا عملية إنشاء أشكال المجموعات باستخدام Aspose.Slides لـ .NET. باتباع هذه الخطوات، يمكنك تحسين المظهر العام لعروض PowerPoint التقديمية وتنظيمها.
## الأسئلة الشائعة
### هل Aspose.Slides متوافق مع أحدث إصدار من .NET؟
نعم، يتم تحديث Aspose.Slides بانتظام لدعم أحدث إصدارات .NET. تحقق من [التوثيق](https://reference.aspose.com/slides/net/) للحصول على تفاصيل التوافق.
### هل يمكنني تجربة Aspose.Slides قبل الشراء؟
بالتأكيد! يمكنك تنزيل نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم للاستعلامات المتعلقة بـ Aspose.Slides؟
قم بزيارة Aspose.Slides [المنتدى](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء ترخيص كامل لـ Aspose.Slides؟
يمكنك شراء ترخيص من [صفحة الشراء](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}