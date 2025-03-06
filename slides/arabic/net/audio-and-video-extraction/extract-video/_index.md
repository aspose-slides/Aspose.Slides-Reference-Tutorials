---
title: كيفية استخراج الفيديو من الشريحة باستخدام Aspose.Slides لـ .NET
linktitle: استخراج الفيديو من الشريحة
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية استخراج مقاطع الفيديو من شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. هذا الدليل خطوة بخطوة يبسط العملية بالنسبة لك.
weight: 14
url: /ar/net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخراج الفيديو من الشريحة باستخدام Aspose.Slides لـ .NET


Aspose.Slides for .NET هي مكتبة قوية تسمح لك بالعمل مع عروض PowerPoint التقديمية في بيئة .NET. إحدى الميزات المفيدة التي يوفرها هي القدرة على استخراج مقاطع الفيديو من الشرائح. في هذا الدليل خطوة بخطوة، سنوضح لك كيفية استخراج مقطع فيديو من شريحة PowerPoint باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Slides لـ .NET: تحتاج إلى تثبيت Aspose.Slides لـ .NET. يمكنك الحصول عليه من[موقع إلكتروني](https://purchase.aspose.com/buy).

- عرض تقديمي لـ PowerPoint: قم بإعداد عرض تقديمي لـ PowerPoint (على سبيل المثال، Video.pptx) يحتوي على الفيديو الذي تريد استخراجه.

## استيراد مساحات الأسماء

تحتاج إلى استيراد مساحات الأسماء الضرورية للعمل مع Aspose.Slides لـ .NET. وإليك كيف يمكنك القيام بذلك:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

الآن، دعونا نقسم عملية استخراج مقطع فيديو من شريحة إلى خطوات متعددة.

## الخطوة 1: قم بتعيين دليل المستندات

```csharp
string dataDir = "Your Document Directory";
```

 يستبدل`"Your Document Directory"` مع المسار إلى الدليل الذي يوجد به عرض PowerPoint التقديمي الخاص بك.

## الخطوة 2: قم بتحميل العرض التقديمي

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

يقوم هذا الرمز بتهيئة كائن العرض التقديمي، الذي يمثل ملف العرض التقديمي لـ PowerPoint.

## الخطوة 3: التكرار من خلال الشرائح والأشكال

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

هنا، نمر عبر كل شريحة في العرض التقديمي ثم نمر عبر الأشكال الموجودة في الشريحة الأولى (قم بالتعديل حسب الحاجة).

## الخطوة 4: تحقق مما إذا كان الشكل عبارة عن إطار فيديو

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

تتحقق هذه الخطوة مما إذا كان الشكل الموجود على الشريحة عبارة عن إطار فيديو.

## الخطوة 5: استخراج بيانات الفيديو

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

يستخرج هذا الرمز معلومات حول الفيديو، بما في ذلك نوع المحتوى والبيانات الثنائية.

## الخطوة 6: احفظ الفيديو

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

أخيرًا، تقوم هذه الخطوة بحفظ الفيديو في ملف جديد في الدليل المحدد.

بمجرد الانتهاء من هذه الخطوات، ستكون قد نجحت في استخراج مقطع فيديو من شريحة PowerPoint باستخدام Aspose.Slides for .NET.

## خاتمة

يعمل Aspose.Slides for .NET على تبسيط عملية العمل مع عروض PowerPoint التقديمية، مما يسمح لك بتنفيذ مهام مثل استخراج مقاطع الفيديو من الشرائح بسهولة. باتباع هذا الدليل التفصيلي والاستفادة من مكتبة Aspose.Slides، يمكنك تحسين تطبيقات .NET الخاصة بك باستخدام ميزات PowerPoint القوية.

## الأسئلة المتداولة (الأسئلة الشائعة)

### ما هو Aspose.Slides لـ .NET؟
Aspose.Slides for .NET هي مكتبة تتيح لتطبيقات .NET العمل مع عروض PowerPoint التقديمية، بما في ذلك إنشاء المحتوى وتحريره واستخراجه.

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟
 يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/slides/net/).

### هل Aspose.Slides for .NET متاح للتجربة المجانية؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 يمكنك طلب ترخيص مؤقت من[هذا الرابط](https://purchase.aspose.com/temporary-license/).

### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
 يمكنك العثور على الدعم على[منتدى Aspose.Slides](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
