---
"description": "حسّن عروضك التقديمية بمقاطع فيديو مُضمنة باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس."
"linktitle": "Aspose.Slides - إضافة مقاطع فيديو مُضمنة في عروض .NET التقديمية"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "Aspose.Slides - إضافة مقاطع فيديو مُضمنة في عروض .NET التقديمية"
"url": "/ar/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - إضافة مقاطع فيديو مُضمنة في عروض .NET التقديمية

## مقدمة
في عالم العروض التقديمية المتغير، يُعزز دمج عناصر الوسائط المتعددة التفاعل بشكل كبير. يوفر Aspose.Slides for .NET حلاً فعالاً لدمج إطارات الفيديو المُضمنة في شرائح العرض التقديمي. سيرشدك هذا البرنامج التعليمي خلال العملية، مُفصّلاً كل خطوة لضمان تجربة سلسة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- Aspose.Slides لمكتبة .NET: قم بتنزيل المكتبة وتثبيتها من [صفحة الإصدار](https://releases.aspose.com/slides/net/).
- المحتوى الإعلامي: يجب أن يكون لديك ملف فيديو (على سبيل المثال، "Wildlife.mp4") الذي تريد تضمينه في العرض التقديمي الخاص بك.
## استيراد مساحات الأسماء
ابدأ باستيراد المساحات الأسماء الضرورية في مشروع .NET الخاص بك:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد الدلائل
تأكد من أن مشروعك يحتوي على الدلائل المطلوبة للمستندات وملفات الوسائط:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## الخطوة 2: إنشاء فئة العرض التقديمي
إنشاء مثيل لفئة العرض التقديمي لتمثيل ملف PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // احصل على الشريحة الأولى
    ISlide sld = pres.Slides[0];
```
## الخطوة 3: تضمين الفيديو داخل العرض التقديمي
استخدم الكود التالي لتضمين مقطع فيديو داخل العرض التقديمي:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## الخطوة 4: إضافة إطار الفيديو
الآن، أضف إطار فيديو إلى الشريحة:
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
## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، احفظ ملف PPTX على القرص:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
كرر هذه الخطوات لكل مقطع فيديو تريد تضمينه في العرض التقديمي الخاص بك.
## خاتمة
تهانينا! لقد نجحت في إضافة إطار فيديو مُضمّن إلى عرضك التقديمي باستخدام Aspose.Slides لـ .NET. هذه الميزة الديناميكية تُحسّن عروضك التقديمية إلى آفاق جديدة، وتأسر جمهورك بعناصر الوسائط المتعددة المُدمجة بسلاسة في شرائحك.
## الأسئلة الشائعة
### هل يمكنني تضمين مقاطع فيديو في أي شريحة من العرض التقديمي؟
نعم، يمكنك اختيار أي شريحة عن طريق تعديل الفهرس في `pres.Slides[index]`.
### ما هي صيغ الفيديو المدعومة؟
يدعم Aspose.Slides مجموعة متنوعة من تنسيقات الفيديو، بما في ذلك MP4، وAVI، وWMV.
### هل يمكنني تخصيص حجم وموضع إطار الفيديو؟
بالتأكيد! اضبط المعلمات في `AddVideoFrame(x, y, width, height, video)` حسب الحاجة.
### هل هناك حد لعدد مقاطع الفيديو التي يمكنني تضمينها؟
عادةً ما يكون عدد مقاطع الفيديو المضمنة محدودًا بسعة برنامج العرض التقديمي لديك.
### كيف يمكنني طلب المزيد من المساعدة أو مشاركة تجربتي؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}