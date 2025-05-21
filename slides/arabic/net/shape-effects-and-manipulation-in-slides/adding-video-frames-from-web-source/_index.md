---
"description": "تعرّف على كيفية تضمين إطارات الفيديو بسلاسة في شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. حسّن عروضك التقديمية باستخدام الوسائط المتعددة بسهولة."
"linktitle": "إضافة إطارات فيديو من مصدر الويب إلى شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "برنامج تعليمي لتضمين إطارات الفيديو باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# برنامج تعليمي لتضمين إطارات الفيديو باستخدام Aspose.Slides لـ .NET

## مقدمة
في عالم العروض التقديمية المتغير باستمرار، يُمكن لدمج عناصر الوسائط المتعددة أن يُعزز التفاعل بشكل كبير ويُوصل رسائل مؤثرة. ومن الطرق الفعّالة لتحقيق ذلك تضمين إطارات الفيديو في شرائح العرض التقديمي. في هذا البرنامج التعليمي، سنستكشف كيفية تحقيق ذلك بسلاسة باستخدام Aspose.Slides لـ .NET. Aspose.Slides هي مكتبة قوية تُمكّن المطورين من التعامل مع عروض PowerPoint التقديمية برمجيًا، مُوفرةً إمكانيات واسعة لإنشاء الشرائح وتحريرها وتحسينها.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي في مكانه:
1. Aspose.Slides لمكتبة .NET: قم بتنزيل المكتبة وتثبيتها من [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/).
2. ملف فيديو نموذجي: جهّز ملف فيديو ترغب بتضمينه في عرضك التقديمي. يمكنك استخدام المثال المرفق مع فيديو باسم "Wildlife.mp4".
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، قم بتضمين المساحات الأساسية اللازمة للاستفادة من وظائف Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
دعنا نقسم عملية تضمين إطارات الفيديو في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET إلى خطوات قابلة للإدارة:
## الخطوة 1: إعداد الدلائل
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
تأكد من استبدال "دليل المستندات الخاص بك" و"دليل الوسائط الخاص بك" بالمسارات المناسبة في مشروعك.
## الخطوة 2: إنشاء كائن العرض التقديمي
```csharp
using (Presentation pres = new Presentation())
{
    // احصل على الشريحة الأولى
    ISlide sld = pres.Slides[0];
```
قم بإنشاء عرض تقديمي جديد والوصول إلى الشريحة الأولى لتضمين إطار الفيديو.
## الخطوة 3: تضمين الفيديو في العرض التقديمي
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
استخدم `AddVideo` طريقة لتضمين الفيديو في العرض التقديمي، مع تحديد مسار الملف وسلوك التحميل.
## الخطوة 4: إضافة إطار الفيديو
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
إنشاء إطار فيديو على الشريحة، مع تحديد موضعه وأبعاده.
## الخطوة 5: تكوين إعدادات الفيديو
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
قم بربط إطار الفيديو بالفيديو المضمن، وضبط وضع التشغيل، وضبط مستوى الصوت وفقًا لتفضيلاتك.
## الخطوة 6: حفظ العرض التقديمي
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدّل باستخدام إطار الفيديو المضمّن.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تضمين إطارات الفيديو في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. تتيح لك هذه الميزة إمكانيات رائعة لإنشاء عروض تقديمية ديناميكية وجذابة تجذب جمهورك.
## الأسئلة الشائعة
### هل يمكنني تضمين مقاطع فيديو بتنسيقات مختلفة باستخدام Aspose.Slides؟
نعم، يدعم Aspose.Slides مجموعة متنوعة من تنسيقات الفيديو، مما يضمن المرونة في العروض التقديمية الخاصة بك.
### كيف يمكنني التحكم في إعدادات تشغيل الفيديو المضمن؟
ضبط `PlayMode` و `Volume` خصائص إطار الفيديو لتخصيص سلوك التشغيل.
### هل Aspose.Slides متوافق مع أحدث إصدارات .NET؟
يتم تحديث Aspose.Slides بانتظام للحفاظ على التوافق مع أحدث أطر عمل .NET.
### هل يمكنني تضمين مقاطع فيديو متعددة في شريحة واحدة باستخدام Aspose.Slides؟
نعم، يمكنك تضمين مقاطع فيديو متعددة عن طريق إضافة إطارات فيديو إضافية إلى شريحة واحدة.
### أين يمكنني العثور على الدعم للاستعلامات المتعلقة بـ Aspose.Slides؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}