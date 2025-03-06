---
title: قم بإنشاء عروض تقديمية ديناميكية باستخدام إطارات تكبير Aspose.Slides
linktitle: إنشاء إطار تكبير/تصغير في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعلم كيفية إنشاء عروض تقديمية جذابة باستخدام إطارات التكبير/التصغير باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة للحصول على تجربة شرائح جذابة.
weight: 17
url: /ar/net/image-and-video-manipulation-in-slides/creating-zoom-frame/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في عالم العروض التقديمية، تعتبر الشرائح الجذابة هي المفتاح لترك انطباع دائم. يوفر Aspose.Slides for .NET مجموعة أدوات قوية، وفي هذا الدليل، سنرشدك خلال عملية دمج إطارات التكبير/التصغير الجذابة في شرائح العرض التقديمي.
## المتطلبات الأساسية
قبل الشروع في هذه الرحلة، تأكد من توفر ما يلي:
-  Aspose.Slides لـ .NET Library: قم بتنزيل المكتبة وتثبيتها من[Aspose.Slides الوثائق](https://reference.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET المفضلة لديك.
- صورة لإطار التكبير/التصغير: قم بإعداد ملف الصورة الذي ترغب في استخدامه لتأثير التكبير/التصغير.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروعك. يتيح لك هذا الوصول إلى الوظائف التي يوفرها Aspose.Slides.
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: قم بإعداد مشروعك
قم بتهيئة مشروعك وحدد مسارات الملفات لمستنداتك، بما في ذلك ملف العرض التقديمي الناتج والصورة التي سيتم استخدامها لتأثير التكبير/التصغير.
```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Documents Directory";
// ضع اسم الملف
string resultPath = Path.Combine(dataDir, "ZoomFramePresentation.pptx");
// المسار إلى الصورة المصدر
string imagePath = Path.Combine(dataDir, "aspose-logo.jpg");
```
## الخطوة 2: إنشاء شرائح العرض التقديمي
استخدم Aspose.Slides لإنشاء عرض تقديمي وإضافة شرائح فارغة إليه. هذا يشكل اللوحة القماشية التي ستعمل عليها.
```csharp
using (Presentation pres = new Presentation())
{
    // إضافة شرائح جديدة إلى العرض التقديمي
    ISlide slide2 = pres.Slides.AddEmptySlide(pres.Slides[0].LayoutSlide);
    ISlide slide3 = pres.Slides.AddEmptySlide(pres.Slides[0].LayoutSlide);
    // ... (تابع إنشاء شرائح إضافية)
}
```
## الخطوة 3: تخصيص خلفيات الشرائح
قم بتعزيز المظهر المرئي لشرائحك من خلال تخصيص خلفياتها. في هذا المثال، قمنا بتعيين خلفية سماوية صلبة للشريحة الثانية.
```csharp
// قم بإنشاء خلفية للشريحة الثانية
slide2.Background.Type = BackgroundType.OwnBackground;
slide2.Background.FillFormat.FillType = FillType.Solid;
slide2.Background.FillFormat.SolidFillColor.Color = Color.Cyan;
// ... (تابع تخصيص الخلفيات للشرائح الأخرى)
```
## الخطوة 4: إضافة مربعات نص إلى الشرائح
دمج مربعات النص لنقل المعلومات على الشرائح الخاصة بك. هنا، نضيف مربع نص مستطيلًا إلى الشريحة الثانية.
```csharp
// قم بإنشاء مربع نص للشريحة الثانية
IAutoShape autoshape = slide2.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
autoshape.TextFrame.Text = "Second Slide";
// ... (تابع إضافة مربعات النص للشرائح الأخرى)
```
## الخطوة 5: دمج ZoomFrames
تقدم هذه الخطوة الجزء المثير، وهو إضافة ZoomFrames. تقوم هذه الإطارات بإنشاء تأثيرات ديناميكية، مثل معاينات الشرائح والصور المخصصة.
```csharp
// أضف كائنات ZoomFrame مع معاينة الشرائح
var zoomFrame1 = pres.Slides[0].Shapes.AddZoomFrame(20, 20, 250, 200, slide2);
// أضف كائنات ZoomFrame بصورة مخصصة
IPPImage image = pres.Images.AddImage(Image.FromFile(imagePath));
var zoomFrame2 = pres.Slides[0].Shapes.AddZoomFrame(200, 250, 250, 100, slide3, image);
// ... (تابع تخصيص ZoomFrames حسب الحاجة)
```
## الخطوة 6: احفظ العرض التقديمي الخاص بك
تأكد من الحفاظ على جميع جهودك عن طريق حفظ العرض التقديمي الخاص بك بالتنسيق المطلوب.
```csharp
// احفظ العرض التقديمي
pres.Save(resultPath, SaveFormat.Pptx);
```
## خاتمة
لقد نجحت في تصميم عرض تقديمي بإطارات تكبير/تصغير جذابة باستخدام Aspose.Slides لـ .NET. ارفع مستوى عروضك التقديمية وحافظ على تفاعل جمهورك مع هذه التأثيرات الديناميكية.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص مظهر ZoomFrames؟
نعم، يمكنك تخصيص جوانب مختلفة مثل عرض الخط ولون التعبئة ونمط الشرطة، كما هو موضح في البرنامج التعليمي.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك الوصول إلى النسخة التجريبية[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على دعم إضافي أو مناقشات مجتمعية؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للدعم والمناقشات.
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني شراء الإصدار الكامل من Aspose.Slides لـ .NET؟
 يمكنك شراء النسخة الكاملة[هنا](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
