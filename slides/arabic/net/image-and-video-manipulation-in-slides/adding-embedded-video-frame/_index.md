---
title: Aspose.Slides - إضافة مقاطع فيديو مضمنة في العروض التقديمية بتنسيق .NET
linktitle: Aspose.Slides - إضافة مقاطع فيديو مضمنة في العروض التقديمية بتنسيق .NET
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بتحسين العروض التقديمية الخاصة بك باستخدام مقاطع الفيديو المضمنة باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 19
url: /ar/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في عالم العروض التقديمية الديناميكي، يمكن لدمج عناصر الوسائط المتعددة أن يعزز المشاركة بشكل كبير. يوفر Aspose.Slides for .NET حلاً قويًا لدمج إطارات الفيديو المضمنة في شرائح العرض التقديمي. سيرشدك هذا البرنامج التعليمي خلال العملية، مع تفصيل كل خطوة لضمان تجربة سلسة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
-  Aspose.Slides لـ .NET Library: قم بتنزيل المكتبة وتثبيتها من[صفحة الإصدار](https://releases.aspose.com/slides/net/).
- محتوى الوسائط: احصل على ملف فيديو (على سبيل المثال، "Wildlife.mp4") تريد تضمينه في العرض التقديمي الخاص بك.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية في مشروع .NET الخاص بك:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد الدلائل
تأكد من أن مشروعك يحتوي على الدلائل المطلوبة لملفات المستندات والوسائط:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## الخطوة 2: إنشاء مثيل لفئة العرض التقديمي
قم بإنشاء مثيل لفئة العرض التقديمي لتمثيل ملف PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // احصل على الشريحة الأولى
    ISlide sld = pres.Slides[0];
```
## الخطوة 3: تضمين الفيديو داخل العرض التقديمي
استخدم الكود التالي لتضمين فيديو داخل العرض التقديمي:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## الخطوة 4: إضافة إطار الفيديو
الآن، قم بإضافة إطار فيديو إلى الشريحة:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## الخطوة 5: تعيين خصائص الفيديو
اضبط الفيديو على إطار الفيديو وقم بتكوين وضع التشغيل ومستوى الصوت:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## الخطوة 6: احفظ العرض التقديمي
وأخيرًا، احفظ ملف PPTX على القرص:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
كرر هذه الخطوات لكل فيديو تريد تضمينه في العرض التقديمي الخاص بك.
## خاتمة
تهانينا! لقد نجحت في إضافة إطار فيديو مضمن إلى العرض التقديمي الخاص بك باستخدام Aspose.Slides for .NET. يمكن لهذه الميزة الديناميكية أن ترفع عروضك التقديمية إلى آفاق جديدة، وتأسر جمهورك بعناصر الوسائط المتعددة المدمجة بسلاسة في شرائحك.
## الأسئلة الشائعة
### هل يمكنني تضمين مقاطع فيديو في أي شريحة من العرض التقديمي؟
 نعم، يمكنك اختيار أي شريحة عن طريق تعديل الفهرس فيها`pres.Slides[index]`.
### ما هي تنسيقات الفيديو المدعومة؟
يدعم Aspose.Slides مجموعة متنوعة من تنسيقات الفيديو، بما في ذلك MP4 وAVI وWMV.
### هل يمكنني تخصيص حجم وموضع إطار الفيديو؟
 قطعاً! ضبط المعلمات في`AddVideoFrame(x, y, width, height, video)` كما هو مطلوب.
### هل هناك حد لعدد مقاطع الفيديو التي يمكنني تضمينها؟
عادةً ما يكون عدد مقاطع الفيديو المضمنة محدودًا بسعة برنامج العرض التقديمي الخاص بك.
### كيف يمكنني طلب المزيد من المساعدة أو مشاركة تجربتي؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
