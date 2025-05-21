---
"description": "تعرّف على كيفية استخراج مقاطع فيديو من شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. يُبسّط هذا الدليل المُفصّل العملية عليك."
"linktitle": "استخراج الفيديو من الشريحة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "كيفية استخراج الفيديو من الشريحة باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/audio-and-video-extraction/extract-video/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيفية استخراج الفيديو من الشريحة باستخدام Aspose.Slides لـ .NET


Aspose.Slides for .NET مكتبة فعّالة تتيح لك العمل مع عروض PowerPoint التقديمية في بيئة .NET. من ميزاتها المفيدة إمكانية استخراج مقاطع الفيديو من الشرائح. في هذا الدليل التفصيلي، سنوضح لك كيفية استخراج مقطع فيديو من شريحة PowerPoint باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.Slides لـ .NET: يجب تثبيت Aspose.Slides لـ .NET. يمكنك الحصول عليه من [موقع إلكتروني](https://purchase.aspose.com/buy).

- عرض تقديمي على PowerPoint: قم بإعداد عرض تقديمي على PowerPoint (على سبيل المثال، Video.pptx) يحتوي على الفيديو الذي تريد استخراجه.

## استيراد مساحات الأسماء

يجب عليك استيراد مساحات الأسماء اللازمة للعمل مع Aspose.Slides لـ .NET. إليك كيفية القيام بذلك:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

الآن، دعونا نقوم بتقسيم عملية استخراج مقطع فيديو من شريحة إلى خطوات متعددة.

## الخطوة 1: تعيين دليل المستندات

```csharp
string dataDir = "Your Document Directory";
```

يستبدل `"Your Document Directory"` مع المسار إلى الدليل حيث يوجد عرض PowerPoint الخاص بك.

## الخطوة 2: تحميل العرض التقديمي

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

يقوم هذا الكود بتهيئة كائن عرض تقديمي، يمثل ملف العرض التقديمي PowerPoint الخاص بك.

## الخطوة 3: التكرار عبر الشرائح والأشكال

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

هنا، نقوم بالمرور على كل شريحة في العرض التقديمي ثم نكرر الأشكال في الشريحة الأولى (نعدلها حسب الحاجة).

## الخطوة 4: التحقق مما إذا كان الشكل عبارة عن إطار فيديو

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

تتحقق هذه الخطوة من أن الشكل الموجود على الشريحة هو إطار فيديو.

## الخطوة 5: استخراج بيانات الفيديو

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

يقوم هذا الكود باستخراج المعلومات حول الفيديو، بما في ذلك نوع المحتوى والبيانات الثنائية.

## الخطوة 6: حفظ الفيديو

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

وأخيرًا، تقوم هذه الخطوة بحفظ الفيديو في ملف جديد في الدليل المحدد.

بمجرد إكمال هذه الخطوات، ستتمكن من استخراج مقطع فيديو بنجاح من شريحة PowerPoint باستخدام Aspose.Slides for .NET.

## خاتمة

يُبسّط Aspose.Slides for .NET عملية العمل مع عروض PowerPoint التقديمية، مما يتيح لك تنفيذ مهام مثل استخراج مقاطع الفيديو من الشرائح بسهولة. باتباع هذا الدليل المفصل واستخدام مكتبة Aspose.Slides، يمكنك تحسين تطبيقات .NET لديك بميزات PowerPoint فعّالة.

## الأسئلة الشائعة

### ما هو Aspose.Slides لـ .NET؟
Aspose.Slides for .NET هي مكتبة تتيح لتطبيقات .NET العمل مع عروض PowerPoint، بما في ذلك إنشاء المحتوى وتحريره واستخراجه.

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟
يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/slides/net/).

### هل يتوفر Aspose.Slides لـ .NET للتجربة المجانية؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
يمكنك طلب ترخيص مؤقت من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
يمكنك العثور على الدعم على [منتدى Aspose.Slides](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}