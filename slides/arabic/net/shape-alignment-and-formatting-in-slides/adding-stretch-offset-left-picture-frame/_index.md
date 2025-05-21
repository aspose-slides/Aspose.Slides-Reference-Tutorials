---
"description": "تعرّف على كيفية تحسين عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة لإضافة إزاحة امتداد إلى اليسار لإطارات الصور."
"linktitle": "إضافة إزاحة التمدد إلى اليسار لإطار الصورة في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إضافة إزاحة التمدد إلى اليسار في PowerPoint باستخدام Aspose.Slide"
"url": "/ar/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إزاحة التمدد إلى اليسار في PowerPoint باستخدام Aspose.Slide

## مقدمة
Aspose.Slides for .NET مكتبة فعّالة تُمكّن المطورين من التعامل مع عروض PowerPoint التقديمية بسهولة. في هذا البرنامج التعليمي، سنستكشف عملية إضافة إزاحة امتداد إلى اليسار لإطار صورة باستخدام Aspose.Slides for .NET. اتبع هذا الدليل خطوة بخطوة لتحسين مهاراتك في التعامل مع الصور والأشكال في عروض PowerPoint التقديمية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من تثبيت المكتبة. إذا لم تكن كذلك، فقم بتنزيلها من [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/).
- بيئة التطوير: توفر بيئة تطوير عمل مع إمكانيات .NET.
## استيراد مساحات الأسماء
ابدأ باستيراد المساحات الأسماء الضرورية في مشروع .NET الخاص بك:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد مشروعك
أنشئ مشروعًا جديدًا أو افتح مشروعًا موجودًا. تأكد من وجود مكتبة Aspose.Slides في مشروعك.
## الخطوة 2: إنشاء كائن العرض التقديمي
إنشاء مثيل `Presentation` الفئة التي تمثل ملف PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // سيتم وضع الكود الخاص بالخطوات اللاحقة هنا.
}
```
## الخطوة 3: الحصول على الشريحة الأولى
استرجاع الشريحة الأولى من العرض التقديمي:
```csharp
ISlide slide = pres.Slides[0];
```
## الخطوة 4: إنشاء صورة
قم بتحميل الصورة التي تريد استخدامها:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## الخطوة 5: إضافة شكل مستطيل تلقائي
إنشاء شكل تلقائي من نوع المستطيل:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## الخطوة 6: تعيين نوع التعبئة ووضع تعبئة الصورة
قم بتكوين نوع تعبئة الشكل ووضع تعبئة الصورة:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## الخطوة 7: تعيين الصورة لملء الشكل
حدد الصورة لملء الشكل:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## الخطوة 8: تحديد إزاحات التمدد
قم بتحديد إزاحات الصورة من الحواف المقابلة لمربع الشكل المحدد:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## الخطوة 9: حفظ العرض التقديمي
اكتب ملف PPTX على القرص:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
تهانينا! لقد نجحتَ في إضافة إزاحة امتداد إلى اليسار لإطار الصورة باستخدام Aspose.Slides لـ .NET.
## خاتمة
في هذا البرنامج التعليمي، استكشفنا عملية معالجة إطارات الصور في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. باتباع هذا الدليل خطوة بخطوة، اكتسبت فهمًا أعمق لكيفية التعامل مع الصور والأشكال والإزاحات.
## الأسئلة الشائعة
### س: هل يمكنني تطبيق إزاحات التمدد على أشكال أخرى بالإضافة إلى المستطيلات؟
ج: على الرغم من أن هذا البرنامج التعليمي يركز على المستطيلات، إلا أنه يمكن تطبيق إزاحات التمدد على الأشكال المختلفة التي يدعمها Aspose.Slides.
### س: كيف يمكنني ضبط إزاحات التمدد للحصول على تأثيرات مختلفة؟
ج: جرّب قيم إزاحة مختلفة لتحقيق التأثير البصري المطلوب. عدّل القيم لتناسب احتياجاتك الخاصة.
### س: هل Aspose.Slides متوافق مع أحدث إطار عمل .NET؟
ج: يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث إصدارات إطار عمل .NET.
### س: أين يمكنني العثور على أمثلة وموارد إضافية لـ Aspose.Slides؟
أ: استكشف [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/) للحصول على أمثلة وإرشادات شاملة.
### س: هل يمكنني تطبيق إزاحات تمدد متعددة على شكل واحد؟
ج: نعم، يمكنك الجمع بين إزاحات التمدد المتعددة لتحقيق تأثيرات بصرية معقدة ومخصصة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}