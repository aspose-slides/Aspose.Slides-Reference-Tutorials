---
title: تضمين البرنامج التعليمي لإطارات الفيديو باستخدام Aspose.Slides لـ .NET
linktitle: إضافة إطارات فيديو من مصدر الويب في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تضمين إطارات الفيديو بسلاسة في شرائح PowerPoint باستخدام Aspose.Slides for .NET. قم بتحسين العروض التقديمية باستخدام الوسائط المتعددة دون عناء.
weight: 20
url: /ar/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تضمين البرنامج التعليمي لإطارات الفيديو باستخدام Aspose.Slides لـ .NET

## مقدمة
في عالم العروض التقديمية الديناميكي، يمكن أن يؤدي دمج عناصر الوسائط المتعددة إلى تعزيز المشاركة بشكل كبير وتقديم رسائل مؤثرة. إحدى الطرق الفعالة لتحقيق ذلك هي دمج إطارات الفيديو في شرائح العرض التقديمي. في هذا البرنامج التعليمي، سوف نستكشف كيفية تحقيق ذلك بسلاسة باستخدام Aspose.Slides لـ .NET. Aspose.Slides هي مكتبة قوية تسمح للمطورين بمعالجة عروض PowerPoint التقديمية برمجياً، مما يوفر إمكانات واسعة لإنشاء الشرائح وتحريرها وتحسينها.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1.  Aspose.Slides لـ .NET Library: قم بتنزيل المكتبة وتثبيتها من[Aspose.Slides لتوثيق .NET](https://reference.aspose.com/slides/net/).
2. نموذج ملف فيديو: قم بإعداد ملف فيديو تريد تضمينه في العرض التقديمي الخاص بك. يمكنك استخدام المثال المقدم مع مقطع فيديو باسم "Wildlife.mp4".
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، قم بتضمين مساحات الأسماء اللازمة للاستفادة من وظائف Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
دعونا نقسم عملية تضمين إطارات الفيديو في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET إلى خطوات يمكن التحكم فيها:
## الخطوة 1: إعداد الدلائل
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
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
قم بتهيئة عرض تقديمي جديد والوصول إلى الشريحة الأولى لتضمين إطار الفيديو.
## الخطوة 3: تضمين الفيديو في العرض التقديمي
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
 الاستفادة من`AddVideo` طريقة لتضمين الفيديو في العرض التقديمي، مع تحديد مسار الملف وسلوك التحميل.
## الخطوة 4: إضافة إطار الفيديو
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
قم بإنشاء إطار فيديو على الشريحة، مع تحديد موضعه وأبعاده.
## الخطوة 5: تكوين إعدادات الفيديو
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
قم بربط إطار الفيديو بالفيديو المضمن، واضبط وضع التشغيل، واضبط مستوى الصوت وفقًا لتفضيلاتك.
## الخطوة 6: حفظ العرض التقديمي
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
احفظ العرض التقديمي المعدل باستخدام إطار الفيديو المضمن.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تضمين إطارات الفيديو في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. تفتح هذه الميزة إمكانيات مثيرة لإنشاء عروض تقديمية ديناميكية وجذابة تأسر جمهورك.
## الأسئلة الشائعة
### هل يمكنني تضمين مقاطع فيديو بتنسيقات مختلفة باستخدام Aspose.Slides؟
نعم، يدعم Aspose.Slides مجموعة متنوعة من تنسيقات الفيديو، مما يضمن المرونة في العروض التقديمية الخاصة بك.
### كيف يمكنني التحكم في إعدادات تشغيل الفيديو المدمج؟
 أضبط ال`PlayMode` و`Volume` خصائص إطار الفيديو لتخصيص سلوك التشغيل.
### هل Aspose.Slides متوافق مع أحدث إصدارات .NET؟
يتم تحديث Aspose.Slides بانتظام للحفاظ على التوافق مع أحدث أطر عمل .NET.
### هل يمكنني تضمين مقاطع فيديو متعددة في شريحة واحدة باستخدام Aspose.Slides؟
نعم، يمكنك تضمين مقاطع فيديو متعددة عن طريق إضافة إطارات فيديو إضافية إلى الشريحة.
### أين يمكنني العثور على الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
