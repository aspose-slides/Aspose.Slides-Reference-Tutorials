---
"description": "حسّن عروضك التقديمية مع Aspose.Slides لـ .NET! تعلّم كيفية إضافة إطارات صوتية بسلاسة، وتفاعل مع جمهورك بشكل غير مسبوق."
"linktitle": "إضافة إطارات صوتية إلى شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إضافة إطارات صوتية إلى شرائح العرض التقديمي باستخدام Aspose.Slides"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/adding-audio-frames/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إطارات صوتية إلى شرائح العرض التقديمي باستخدام Aspose.Slides

## مقدمة
في عالم العروض التقديمية المتغير باستمرار، يُحسّن دمج العناصر الصوتية تجربة جمهورك بشكل ملحوظ. يُمكّن Aspose.Slides for .NET المطورين من دمج إطارات الصوت بسلاسة في شرائح العرض التقديمي، مما يُضفي مستوى جديدًا من التفاعل والتفاعلية. سيُرشدك هذا الدليل المُفصّل خطوة بخطوة خلال عملية إضافة إطارات الصوت إلى شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مكتبة Aspose.Slides لـ .NET: قم بتنزيل وتثبيت مكتبة Aspose.Slides لـ .NET من [رابط التحميل](https://releases.aspose.com/slides/net/).
2. بيئة التطوير: تأكد من أن لديك بيئة تطوير عمل لـ .NET، مثل Visual Studio.
3. دليل المستندات: قم بإنشاء دليل لتخزين مستنداتك، ولاحظ المسار.
## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، ابدأ باستيراد المساحات الأساسية اللازمة للوصول إلى وظيفة Aspose.Slides:
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
    // يظهر رمز إنشاء الشريحة هنا
}
```
## الخطوة 2: تحميل ملف الصوت
```csharp
FileStream fstr = new FileStream(dataDir + "sampleaudio.wav", FileMode.Open, FileAccess.Read);
```
## الخطوة 3: إضافة إطار صوتي
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
من خلال اتباع الخطوات التالية، تكون قد نجحت في دمج إطارات الصوت في العرض التقديمي الخاص بك باستخدام Aspose.Slides لـ .NET.
## خاتمة
يُحسّن دمج عناصر الصوت في عروضك التقديمية تجربة المشاهد بشكل عام، مما يجعل محتواك أكثر ديناميكية وتفاعلية. يُبسّط Aspose.Slides for .NET هذه العملية، مما يسمح للمطورين بدمج إطارات الصوت بسلاسة من خلال بضعة أسطر من التعليمات البرمجية.
## الأسئلة الشائعة
### هل Aspose.Slides for .NET متوافق مع تنسيقات الصوت المختلفة؟
يدعم Aspose.Slides لـ .NET تنسيقات صوتية متنوعة، بما في ذلك WAV وMP3 وغيرها. راجع الوثائق للاطلاع على قائمة شاملة.
### هل يمكنني التحكم في إعدادات تشغيل إطار الصوت المضاف؟
نعم، يوفر Aspose.Slides المرونة في تكوين إعدادات التشغيل مثل مستوى الصوت ووضع التشغيل والمزيد.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ .NET؟
نعم، يمكنك استكشاف ميزات Aspose.Slides لـ .NET باستخدام [نسخة تجريبية مجانية](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ .NET؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لطلب المساعدة والتفاعل مع المجتمع.
### كيف يمكنني شراء Aspose.Slides لـ .NET؟
يمكنك شراء المكتبة من [متجر أسبووز](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}