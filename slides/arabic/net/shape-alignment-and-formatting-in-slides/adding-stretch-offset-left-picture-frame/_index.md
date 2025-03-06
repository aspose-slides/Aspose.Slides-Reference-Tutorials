---
title: إضافة إزاحة ممتدة إلى اليسار في برنامج PowerPoint باستخدام Aspose.Slide
linktitle: إضافة إزاحة ممتدة إلى اليسار لإطار الصورة في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة لإضافة إزاحة ممتدة إلى اليسار لإطارات الصور.
type: docs
weight: 14
url: /ar/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---
## مقدمة
Aspose.Slides for .NET هي مكتبة قوية تمكن المطورين من التعامل مع عروض PowerPoint التقديمية بسهولة. في هذا البرنامج التعليمي، سوف نستكشف عملية إضافة إزاحة امتداد إلى اليسار لإطار الصورة باستخدام Aspose.Slides for .NET. اتبع هذا الدليل التفصيلي خطوة بخطوة لتحسين مهاراتك في العمل مع الصور والأشكال داخل عروض PowerPoint التقديمية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Slides for .NET: تأكد من تثبيت المكتبة. إذا لم يكن الأمر كذلك، قم بتنزيله من[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).
- بيئة التطوير: تمتع ببيئة تطوير عمل بقدرات .NET.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية في مشروع .NET الخاص بك:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## الخطوة 1: قم بإعداد مشروعك
إنشاء مشروع جديد أو فتح مشروع موجود. تأكد من أن لديك مكتبة Aspose.Slides المشار إليها في مشروعك.
## الخطوة 2: إنشاء كائن العرض التقديمي
 إنشاء مثيل`Presentation` فئة تمثل ملف PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // سيتم وضع الرمز الخاص بك للخطوات اللاحقة هنا.
}
```
## الخطوة 3: احصل على الشريحة الأولى
استرجاع الشريحة الأولى من العرض التقديمي:
```csharp
ISlide slide = pres.Slides[0];
```
## الخطوة 4: إنشاء مثيل للصورة
قم بتحميل الصورة التي تريد استخدامها:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## الخطوة 5: إضافة الشكل التلقائي للمستطيل
إنشاء شكل تلقائي لنوع المستطيل:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## الخطوة 6: تعيين نوع التعبئة ووضع تعبئة الصورة
تكوين نوع تعبئة الشكل ووضع تعبئة الصورة:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## الخطوة 7: ضبط الصورة لملء الشكل
تحديد الصورة لملء الشكل:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## الخطوة 8: تحديد إزاحات التمدد
حدد إزاحات الصورة من الحواف المقابلة للمربع المحيط بالشكل:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## الخطوة 9: احفظ العرض التقديمي
اكتب ملف PPTX على القرص:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
تهانينا! لقد نجحت في إضافة إزاحة امتداد إلى اليسار لإطار صورة باستخدام Aspose.Slides لـ .NET.
## خاتمة
في هذا البرنامج التعليمي، استكشفنا عملية التعامل مع إطارات الصور في عروض PowerPoint التقديمية باستخدام Aspose.Slides for .NET. باتباع الدليل الموضح خطوة بخطوة، اكتسبت رؤى حول العمل مع الصور والأشكال والإزاحات.
## أسئلة مكررة
### س: هل يمكنني تطبيق إزاحات التمدد على أشكال أخرى إلى جانب المستطيلات؟
ج: بينما يركز هذا البرنامج التعليمي على المستطيلات، يمكن تطبيق إزاحات التمدد على الأشكال المختلفة التي يدعمها Aspose.Slides.
### س: كيف يمكنني ضبط إزاحات التمدد للحصول على تأثيرات مختلفة؟
ج: قم بتجربة قيم الإزاحة المختلفة لتحقيق التأثير البصري المطلوب. قم بضبط القيم لتناسب متطلباتك المحددة.
### س: هل Aspose.Slides متوافق مع أحدث إطار عمل .NET؟
ج: يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث إصدارات إطار عمل .NET.
### س: أين يمكنني العثور على أمثلة وموارد إضافية لـ Aspose.Slides؟
 ج: اكتشف[Aspose.Slides الوثائق](https://reference.aspose.com/slides/net/) للحصول على أمثلة وإرشادات شاملة.
### س: هل يمكنني تطبيق إزاحات امتداد متعددة على شكل واحد؟
ج: نعم، يمكنك الجمع بين إزاحات امتداد متعددة لتحقيق تأثيرات بصرية معقدة ومخصصة.