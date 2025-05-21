---
"description": "تعرّف على كيفية تحسين عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. اتبع دليلًا خطوة بخطوة لإضافة إزاحة تمدد لتعبئة الصورة."
"linktitle": "إضافة إزاحة التمدد لملء الصور في الشرائح"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إضافة إزاحة التمدد لملء الصور في عروض PowerPoint التقديمية"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إزاحة التمدد لملء الصور في عروض PowerPoint التقديمية

## مقدمة
في عالم العروض التقديمية المتغير باستمرار، تلعب العناصر المرئية دورًا محوريًا في جذب انتباه الجمهور. يُمكّن Aspose.Slides for .NET المطورين من تحسين عروض PowerPoint التقديمية من خلال توفير مجموعة متكاملة من الميزات. من بين هذه الميزات إمكانية إضافة إزاحة امتداد لتعبئة الصور، مما يسمح بإنشاء شرائح إبداعية وجذابة بصريًا.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. Aspose.Slides لمكتبة .NET: قم بتنزيل المكتبة وتثبيتها من [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/).
2. بيئة التطوير: تأكد من إعداد بيئة تطوير .NET عاملة.
الآن، دعونا نبدأ بالدليل خطوة بخطوة.
## استيراد مساحات الأسماء
أولاً، قم باستيراد المساحات الأساسية اللازمة للاستفادة من وظيفة Aspose.Slides داخل تطبيق .NET الخاص بك.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد مشروعك
أنشئ مشروع .NET جديدًا في بيئة التطوير المفضلة لديك. تأكد من صحة مرجع Aspose.Slides for .NET.
## الخطوة 2: تهيئة فئة العرض التقديمي
إنشاء مثيل `Presentation` الفئة لتمثيل ملف PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك يذهب هنا
}
```
## الخطوة 3: الحصول على الشريحة الأولى
استرجاع الشريحة الأولى من العرض التقديمي للعمل عليها.
```csharp
ISlide sld = pres.Slides[0];
```
## الخطوة 4: إنشاء مثيل لفئة ImageEx
إنشاء مثيل لـ `ImageEx` الفئة للتعامل مع الصورة التي تريد إضافتها إلى الشريحة.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## الخطوة 5: إضافة إطار الصورة
استخدم `AddPictureFrame` طريقة لإضافة إطار صورة إلى الشريحة. حدد أبعاد الإطار وموقعه.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## الخطوة 6: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل على القرص.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
هذا كل شيء! لقد نجحت في إضافة إزاحة امتداد لملء الصور في الشرائح باستخدام Aspose.Slides لـ .NET.
## خاتمة
أصبح تحسين عروض PowerPoint التقديمية أسهل من أي وقت مضى مع Aspose.Slides لـ .NET. باتباع هذا البرنامج التعليمي، ستتعلم كيفية دمج إزاحة التمدد لتعبئة الصور، مما يضفي مستوى جديدًا من الإبداع على شرائحك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ .NET في تطبيقات الويب الخاصة بي؟
نعم، يعد Aspose.Slides for .NET مناسبًا لكل من تطبيقات سطح المكتب والويب.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع.
### أين يمكنني العثور على الوثائق الكاملة لـ Aspose.Slides لـ .NET؟
راجع إلى [التوثيق](https://reference.aspose.com/slides/net/) لمزيد من المعلومات التفصيلية.
### هل يمكنني شراء Aspose.Slides لـ .NET؟
نعم يمكنك شراء المنتج [هنا](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}