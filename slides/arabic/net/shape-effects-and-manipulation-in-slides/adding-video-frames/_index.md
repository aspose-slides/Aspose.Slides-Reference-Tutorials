---
"description": "أضف حيوية إلى عروضك التقديمية بإطارات فيديو ديناميكية باستخدام Aspose.Slides لـ .NET. اتبع دليلنا للتكامل السلس وإنشاء عروض جذابة."
"linktitle": "إضافة إطارات الفيديو إلى شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "برنامج تعليمي لإضافة إطارات الفيديو باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/adding-video-frames/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# برنامج تعليمي لإضافة إطارات الفيديو باستخدام Aspose.Slides لـ .NET

## مقدمة
في ظلّ ديناميكيات العروض التقديمية، يُمكن لدمج عناصر الوسائط المتعددة أن يُعزز التأثير العام والتفاعل. إضافة إطارات الفيديو إلى شرائحك تُحدث نقلة نوعية، إذ تجذب انتباه جمهورك بطريقة لا يُمكن للمحتوى الثابت تحقيقها. يُوفر Aspose.Slides for .NET حلاًّ فعّالاً لدمج إطارات الفيديو بسلاسة في شرائح عرضك التقديمي.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- فهم أساسي لبرمجة C# و.NET.
- تم تثبيت مكتبة Aspose.Slides لـ .NET. إذا لم تكن مثبتة، يمكنك تنزيلها. [هنا](https://releases.aspose.com/slides/net/).
- بيئة تطوير مناسبة تم إعدادها.
## استيراد مساحات الأسماء
للبدء، تأكد من استيراد المساحات الأساسية اللازمة إلى مشروعك:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إنشاء كائن العرض التقديمي
ابدأ بإنشاء مثيل لـ `Presentation` الفئة التي تمثل ملف PPTX:
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    // الكود الخاص بك هنا
}
```
## الخطوة 2: الوصول إلى الشريحة
استرجاع الشريحة الأولى من العرض التقديمي:
```csharp
ISlide sld = pres.Slides[0];
```
## الخطوة 3: إضافة إطار الفيديو
الآن، أضف إطار فيديو إلى الشريحة:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
قم بضبط المعلمات (اليسار، الأعلى، العرض، الارتفاع) وفقًا لتفضيلات التخطيط لديك.
## الخطوة 4: ضبط وضع التشغيل ومستوى الصوت
قم بتكوين وضع التشغيل وحجم إطار الفيديو المدرج:
```csharp
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
لا تتردد في تخصيص هذه الإعدادات استنادًا إلى متطلبات العرض التقديمي لديك.
## الخطوة 5: حفظ العرض التقديمي
حفظ العرض التقديمي المعدل على القرص:
```csharp
pres.Save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
الآن، يتضمن عرضك التقديمي إطار فيديو متكاملًا بسلاسة!
## خاتمة
دمج إطارات الفيديو في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET عملية سهلة تُضفي لمسة ديناميكية على محتواك. عزّز عروضك التقديمية بالاستفادة من عناصر الوسائط المتعددة، وجذب انتباه جمهورك، وتقديم تجربة لا تُنسى.
## الأسئلة الشائعة
### س1: هل يمكنني إضافة إطارات فيديو متعددة إلى شريحة واحدة؟
نعم، يمكنك إضافة إطارات فيديو متعددة إلى شريحة واحدة عن طريق تكرار العملية الموضحة في البرنامج التعليمي لكل إطار فيديو.
### س2: ما هي تنسيقات الفيديو التي يدعمها Aspose.Slides لـ .NET؟
يدعم Aspose.Slides for .NET تنسيقات الفيديو المختلفة، بما في ذلك AVI، وWMV، وMP4.
### س3: هل يمكنني التحكم في خيارات التشغيل للفيديو المدرج؟
بالتأكيد! لديك تحكم كامل بخيارات التشغيل، مثل وضع التشغيل ومستوى الصوت، كما هو موضح في البرنامج التعليمي.
### س4: هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ .NET؟
نعم، يمكنك استكشاف إمكانيات Aspose.Slides لـ .NET عن طريق تنزيل الإصدار التجريبي [هنا](https://releases.aspose.com/).
### س5: أين يمكنني العثور على الدعم لـ Aspose.Slides لـ .NET؟
لأي استفسارات أو مساعدة، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}