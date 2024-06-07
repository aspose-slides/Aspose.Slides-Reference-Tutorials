---
title: ربط الفيديو عبر عنصر تحكم ActiveX في PowerPoint
linktitle: ربط الفيديو عبر تحكم ActiveX
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية ربط مقاطع الفيديو بشرائح PowerPoint باستخدام Aspose.Slides لـ .NET. يتضمن هذا الدليل التفصيلي التعليمات البرمجية المصدرية ونصائح لإنشاء عروض تقديمية تفاعلية وجذابة باستخدام مقاطع الفيديو المرتبطة.
type: docs
weight: 12
url: /ar/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---
ربط مقطع فيديو عبر عنصر تحكم ActiveX في عرض تقديمي باستخدام Aspose.Slides لـ .NET

في Aspose.Slides for .NET، يمكنك ربط مقطع فيديو بشريحة عرض تقديمي برمجيًا باستخدام عنصر تحكم ActiveX. يتيح لك ذلك إنشاء عروض تقديمية تفاعلية حيث يمكن تشغيل محتوى الفيديو مباشرة داخل الشريحة. في هذا الدليل خطوة بخطوة، سنرشدك خلال عملية ربط مقطع فيديو بشريحة عرض تقديمي باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية:
- Visual Studio (أو أي بيئة تطوير .NET أخرى)
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## الخطوة 1: إنشاء مشروع جديد
أنشئ مشروعًا جديدًا في بيئة التطوير .NET المفضلة لديك (على سبيل المثال، Visual Studio) وأضف مراجع إلى مكتبة Aspose.Slides لـ .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية
في مشروعك، قم باستيراد مساحات الأسماء اللازمة للعمل مع Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## الخطوة 3: تحميل العرض التقديمي
قم بتحميل عرض PowerPoint التقديمي حيث تريد إضافة الفيديو المرتبط:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // سيتم وضع الرمز الخاص بك لإضافة الفيديو المرتبط هنا
}
```

## الخطوة 4: إضافة عنصر تحكم ActiveX
 إنشاء مثيل لـ`IOleObjectFrame` واجهة لإضافة عنصر تحكم ActiveX إلى الشريحة:

```csharp
ISlide slide = presentation.Slides[0]; // اختر الشريحة التي تريد إضافة الفيديو إليها
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

في الكود أعلاه، نقوم بإضافة إطار تحكم ActiveX بأبعاد 640 × 480 إلى الشريحة. نقوم بتحديد ProgID لعنصر تحكم ShockwaveFlash ActiveX، والذي يُستخدم بشكل شائع لتضمين مقاطع الفيديو.

## الخطوة 5: تعيين خصائص عنصر تحكم ActiveX
قم بتعيين خصائص عنصر تحكم ActiveX لتحديد مصدر الفيديو المرتبط:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // استبدله بمسار ملف الفيديو الفعلي
oleObjectFrame.AlternativeText = "Linked Video";
```

 يستبدل`"YourVideoPathHere"` مع المسار الفعلي لملف الفيديو الخاص بك. ال`AlternativeText` توفر الخاصية وصفًا للفيديو المرتبط.

## الخطوة 6: حفظ العرض التقديمي
حفظ العرض التقديمي المعدل:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## الأسئلة الشائعة:

### كيف يمكنني تحديد حجم وموضع الفيديو المرتبط على الشريحة؟
يمكنك ضبط أبعاد إطار تحكم ActiveX وموضعه باستخدام معلمات`AddOleObjectFrame` طريقة. تمثل الوسيطات الرقمية الأربعة إحداثيات X وY للزاوية العلوية اليسرى وعرض الإطار وارتفاعه، على التوالي.

### هل يمكنني ربط مقاطع فيديو بتنسيقات مختلفة باستخدام هذا الأسلوب؟
نعم، يمكنك ربط مقاطع الفيديو بتنسيقات مختلفة طالما يتوفر عنصر تحكم ActiveX المناسب لهذا التنسيق. على سبيل المثال، يعد عنصر التحكم ShockwaveFlash ActiveX المستخدم في هذا الدليل مناسبًا لمقاطع فيديو Flash (SWF). بالنسبة للتنسيقات الأخرى، قد تحتاج إلى استخدام ProgIDs مختلفة.

### هل هناك حد لحجم الفيديو المرتبط؟
قد يؤثر حجم الفيديو المرتبط على الحجم الإجمالي للعرض التقديمي وأدائه. يوصى بتحسين مقاطع الفيديو الخاصة بك لتشغيلها على الويب قبل ربطها بالعرض التقديمي.

### خاتمة:
باتباع الخطوات الموضحة في هذا الدليل، يمكنك بسهولة ربط مقطع فيديو عبر عنصر تحكم ActiveX في عرض تقديمي باستخدام Aspose.Slides for .NET. تمكنك هذه الميزة من إنشاء عروض تقديمية جذابة وتفاعلية تتضمن محتوى الوسائط المتعددة بسلاسة.

 لمزيد من التفاصيل والخيارات المتقدمة، يمكنك الرجوع إلى[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net/).