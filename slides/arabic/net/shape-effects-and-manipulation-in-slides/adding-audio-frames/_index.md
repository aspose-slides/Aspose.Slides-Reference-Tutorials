---
title: إضافة إطارات صوتية إلى شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: إضافة إطارات صوتية إلى شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تحسين العروض التقديمية باستخدام Aspose.Slides لـ .NET! تعلم كيفية إضافة الإطارات الصوتية بسلاسة، وإشراك جمهورك بشكل لم يسبق له مثيل.
weight: 14
url: /ar/net/shape-effects-and-manipulation-in-slides/adding-audio-frames/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في عالم العروض التقديمية الديناميكي، يمكن أن يؤدي دمج العناصر الصوتية إلى تحسين التجربة الشاملة لجمهورك بشكل كبير. يعمل Aspose.Slides for .NET على تمكين المطورين من دمج الإطارات الصوتية بسلاسة في شرائح العرض التقديمي، مما يضيف طبقة جديدة من المشاركة والتفاعل. سيرشدك هذا الدليل خطوة بخطوة خلال عملية إضافة إطارات صوتية إلى شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Slides لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Slides لمكتبة .NET من[رابط التحميل](https://releases.aspose.com/slides/net/).
2. بيئة التطوير: تأكد من أن لديك بيئة تطوير عمل لـ .NET، مثل Visual Studio.
3. دليل المستندات: قم بإنشاء دليل حيث ستقوم بتخزين المستندات الخاصة بك، وقم بتدوين المسار.
## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للوصول إلى وظيفة Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إنشاء العرض التقديمي والشريحة
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    ISlide sld = pres.Slides[0];
    // الكود الخاص بك لإنشاء الشرائح موجود هنا
}
```
## الخطوة 2: تحميل الملف الصوتي
```csharp
FileStream fstr = new FileStream(dataDir + "sampleaudio.wav", FileMode.Open, FileAccess.Read);
```
## الخطوة 3: إضافة إطار الصوت
```csharp
IAudioFrame audioFrame = sld.Shapes.AddAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## الخطوة 4: تكوين خصائص الصوت
```csharp
audioFrame.PlayAcrossSlides = true;
audioFrame.RewindAudio = true;
audioFrame.PlayMode = AudioPlayModePreset.Auto;
audioFrame.Volume = AudioVolumeMode.Loud;
```
## الخطوة 5: حفظ العرض التقديمي
```csharp
pres.Save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```
باتباع هذه الخطوات، تكون قد نجحت في دمج الإطارات الصوتية في العرض التقديمي الخاص بك باستخدام Aspose.Slides for .NET.
## خاتمة
يؤدي دمج العناصر الصوتية في عروضك التقديمية إلى تحسين تجربة المشاهد بشكل عام، مما يجعل المحتوى الخاص بك أكثر ديناميكية وجاذبية. يعمل Aspose.Slides for .NET على تبسيط هذه العملية، مما يسمح للمطورين بدمج الإطارات الصوتية بسلاسة مع بضعة أسطر فقط من التعليمات البرمجية.
## الأسئلة الشائعة
### هل يتوافق Aspose.Slides for .NET مع تنسيقات الصوت المختلفة؟
يدعم Aspose.Slides for .NET العديد من تنسيقات الصوت، بما في ذلك WAV وMP3 والمزيد. تحقق من الوثائق للحصول على قائمة شاملة.
### هل يمكنني التحكم في إعدادات التشغيل لإطار الصوت المضاف؟
نعم، يوفر Aspose.Slides المرونة في تكوين إعدادات التشغيل مثل مستوى الصوت ووضع التشغيل والمزيد.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك استكشاف ميزات Aspose.Slides لـ .NET باستخدام[تجربة مجانية](https://releases.aspose.com/).
### أين يمكنني العثور على دعم لـ Aspose.Slides لـ .NET؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لطلب المساعدة والتفاعل مع المجتمع.
### كيف يمكنني شراء Aspose.Slides لـ .NET؟
 يمكنك شراء المكتبة من[متجر أسبوز](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
