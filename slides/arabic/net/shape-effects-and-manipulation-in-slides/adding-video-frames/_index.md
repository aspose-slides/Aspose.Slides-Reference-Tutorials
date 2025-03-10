---
title: إضافة برنامج تعليمي لإطارات الفيديو باستخدام Aspose.Slides لـ .NET
linktitle: إضافة إطارات الفيديو إلى شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بتنشيط العروض التقديمية باستخدام إطارات الفيديو الديناميكية باستخدام Aspose.Slides لـ .NET. اتبع دليلنا للتكامل السلس وخلق التفاعل.
weight: 19
url: /ar/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة برنامج تعليمي لإطارات الفيديو باستخدام Aspose.Slides لـ .NET

## مقدمة
في المشهد الديناميكي للعروض التقديمية، يمكن أن يؤدي دمج عناصر الوسائط المتعددة إلى زيادة التأثير العام والمشاركة. يمكن أن تؤدي إضافة إطارات فيديو إلى شرائحك إلى تغيير قواعد اللعبة، حيث تجذب انتباه جمهورك بطريقة لا يستطيع المحتوى الثابت القيام بها. يوفر Aspose.Slides for .NET حلاً قويًا لدمج إطارات الفيديو بسلاسة في شرائح العرض التقديمي.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي لبرمجة C# و.NET.
-  تم تثبيت Aspose.Slides لمكتبة .NET. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
- إعداد بيئة تطوير مناسبة.
## استيراد مساحات الأسماء
للبدء، تأكد من استيراد مساحات الأسماء الضرورية إلى مشروعك:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إنشاء كائن العرض التقديمي
 ابدأ بإنشاء مثيل لـ`Presentation` فئة تمثل ملف PPTX:
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    // الرمز الخاص بك هنا
}
```
## الخطوة 2: الوصول إلى الشريحة
استرجاع الشريحة الأولى من العرض التقديمي:
```csharp
ISlide sld = pres.Slides[0];
```
## الخطوة 3: إضافة إطار الفيديو
الآن، قم بإضافة إطار فيديو إلى الشريحة:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
اضبط المعلمات (يسار، أعلى، عرض، ارتفاع) وفقًا لتفضيلات التخطيط الخاصة بك.
## الخطوة 4: ضبط وضع التشغيل ومستوى الصوت
قم بتكوين وضع التشغيل وحجم إطار الفيديو المدرج:
```csharp
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
لا تتردد في تخصيص هذه الإعدادات بناءً على متطلبات العرض التقديمي الخاص بك.
## الخطوة 5: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل على القرص:
```csharp
pres.Save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
الآن، يشتمل العرض التقديمي الخاص بك على إطار فيديو متكامل بسلاسة!
## خاتمة
يعد دمج إطارات الفيديو في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET عملية مباشرة تضيف لمسة ديناميكية إلى المحتوى الخاص بك. قم بتحسين عروضك التقديمية من خلال الاستفادة من عناصر الوسائط المتعددة، وجذب جمهورك وتقديم تجربة لا تُنسى.
## الأسئلة الشائعة
### س1: هل يمكنني إضافة إطارات فيديو متعددة إلى شريحة واحدة؟
نعم، يمكنك إضافة إطارات فيديو متعددة إلى شريحة واحدة عن طريق تكرار العملية الموضحة في البرنامج التعليمي لكل إطار فيديو.
### س2: ما هي تنسيقات الفيديو التي يدعمها Aspose.Slides لـ .NET؟
يدعم Aspose.Slides for .NET العديد من تنسيقات الفيديو، بما في ذلك AVI وWMV وMP4.
### س3: هل يمكنني التحكم في خيارات التشغيل للفيديو المدرج؟
قطعاً! لديك التحكم الكامل في خيارات التشغيل، مثل وضع التشغيل ومستوى الصوت، كما هو موضح في البرنامج التعليمي.
### س4: هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك استكشاف إمكانيات Aspose.Slides لـ .NET عن طريق تنزيل الإصدار التجريبي[هنا](https://releases.aspose.com/).
### س5: أين يمكنني العثور على دعم Aspose.Slides لـ .NET؟
 لأية استفسارات أو مساعدة، قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
