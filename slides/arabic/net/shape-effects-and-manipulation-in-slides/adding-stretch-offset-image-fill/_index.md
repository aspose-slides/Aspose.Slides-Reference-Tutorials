---
title: إضافة إزاحة ممتدة لملء الصور في عروض PowerPoint التقديمية
linktitle: إضافة إزاحة ممتدة لملء الصور في الشرائح
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. اتبع دليل خطوة بخطوة لإضافة إزاحة امتداد لملء الصورة.
weight: 18
url: /ar/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في عالم العروض التقديمية الديناميكي، تلعب العناصر المرئية دورًا محوريًا في جذب انتباه الجمهور. يعمل Aspose.Slides for .NET على تمكين المطورين من تحسين عروض PowerPoint التقديمية الخاصة بهم من خلال توفير مجموعة قوية من الميزات. إحدى هذه الميزات هي القدرة على إضافة إزاحة ممتدة لملء الصورة، مما يسمح بشرائح إبداعية وجذابة بصريًا.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Slides لـ .NET Library: قم بتنزيل المكتبة وتثبيتها من[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).
2. بيئة التطوير: تأكد من إعداد بيئة تطوير .NET صالحة للعمل.
الآن، دعونا نبدأ مع الدليل خطوة بخطوة.
## استيراد مساحات الأسماء
أولاً، قم باستيراد مساحات الأسماء الضرورية للاستفادة من وظيفة Aspose.Slides داخل تطبيق .NET الخاص بك.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## الخطوة 1: قم بإعداد مشروعك
قم بإنشاء مشروع .NET جديد في بيئة التطوير المفضلة لديك. تأكد من الإشارة إلى Aspose.Slides for .NET بشكل صحيح.
## الخطوة 2: تهيئة فئة العرض التقديمي
 إنشاء مثيل`Presentation` فئة لتمثيل ملف PowerPoint.
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
## الخطوة 3: احصل على الشريحة الأولى
استرجع الشريحة الأولى من العرض التقديمي للعمل عليها.
```csharp
ISlide sld = pres.Slides[0];
```
## الخطوة 4: إنشاء مثيل لفئة ImageEx
 إنشاء مثيل لـ`ImageEx`class للتعامل مع الصورة التي تريد إضافتها إلى الشريحة.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## الخطوة 5: إضافة إطار الصورة
 الاستفادة من`AddPictureFrame` طريقة إضافة إطار الصورة إلى الشريحة. حدد أبعاد وموضع الإطار.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## الخطوة 6: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل على القرص.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
هذا كل شيء! لقد نجحت في إضافة إزاحة امتداد لملء الشرائح في الشرائح باستخدام Aspose.Slides لـ .NET.
## خاتمة
أصبح الآن تحسين عروض PowerPoint التقديمية أسهل من أي وقت مضى باستخدام Aspose.Slides for .NET. باتباع هذا البرنامج التعليمي، تعلمت كيفية دمج الإزاحة الممتدة لملء الصورة، مما يوفر مستوى جديدًا من الإبداع لشرائحك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ .NET في تطبيقات الويب الخاصة بي؟
نعم، Aspose.Slides for .NET مناسب لكل من تطبيقات سطح المكتب والويب.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على دعم Aspose.Slides لـ .NET؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع.
### أين يمكنني العثور على الوثائق الكاملة لـ Aspose.Slides لـ .NET؟
 الرجوع إلى[توثيق](https://reference.aspose.com/slides/net/) للحصول على معلومات مفصلة.
### هل يمكنني شراء Aspose.Slides لـ .NET؟
 نعم يمكنك شراء المنتج[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
