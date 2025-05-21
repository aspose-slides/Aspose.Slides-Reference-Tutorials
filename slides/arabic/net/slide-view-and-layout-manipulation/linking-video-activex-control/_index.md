---
"description": "تعرّف على كيفية ربط مقاطع الفيديو بشرائح PowerPoint باستخدام Aspose.Slides لـ .NET. يتضمن هذا الدليل خطوة بخطوة شفرة المصدر ونصائح لإنشاء عروض تقديمية تفاعلية وجذابة باستخدام مقاطع فيديو مرتبطة."
"linktitle": "ربط الفيديو عبر عنصر التحكم ActiveX"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "ربط الفيديو عبر عنصر التحكم ActiveX في PowerPoint"
"url": "/ar/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ربط الفيديو عبر عنصر التحكم ActiveX في PowerPoint

ربط مقطع فيديو عبر عنصر تحكم ActiveX في عرض تقديمي باستخدام Aspose.Slides لـ .NET

في Aspose.Slides لـ .NET، يمكنك ربط فيديو بشريحة عرض تقديمي برمجيًا باستخدام عنصر تحكم ActiveX. يتيح لك هذا إنشاء عروض تقديمية تفاعلية يمكن تشغيل محتوى الفيديو فيها مباشرةً. في هذا الدليل التفصيلي، سنشرح لك عملية ربط فيديو بشريحة عرض تقديمي باستخدام Aspose.Slides لـ .NET.

## المتطلبات الأساسية:
- Visual Studio (أو أي بيئة تطوير .NET أخرى)
- مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).

## الخطوة 1: إنشاء مشروع جديد
قم بإنشاء مشروع جديد في بيئة تطوير .NET المفضلة لديك (على سبيل المثال، Visual Studio) وأضف مراجع إلى مكتبة Aspose.Slides for .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية
في مشروعك، قم باستيراد المساحات الأساسية اللازمة للعمل مع Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## الخطوة 3: تحميل العرض التقديمي
قم بتحميل عرض PowerPoint حيث تريد إضافة الفيديو المرتبط:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // سيتم وضع الكود الخاص بك لإضافة الفيديو المرتبط هنا
}
```

## الخطوة 4: إضافة عنصر تحكم ActiveX
إنشاء مثيل لـ `IOleObjectFrame` واجهة لإضافة عنصر التحكم ActiveX إلى الشريحة:

```csharp
ISlide slide = presentation.Slides[0]; // اختر الشريحة التي تريد إضافة الفيديو إليها
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

في الكود أعلاه، نضيف إطار تحكم ActiveX بأبعاد 640×480 إلى الشريحة. ونحدد مُعرِّف البرنامج لعنصر تحكم ShockwaveFlash ActiveX، المستخدم عادةً لتضمين مقاطع الفيديو.

## الخطوة 5: تعيين خصائص عنصر التحكم ActiveX
قم بتعيين خصائص عنصر التحكم ActiveX لتحديد مصدر الفيديو المرتبط:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // استبدل بمسار ملف الفيديو الفعلي
oleObjectFrame.AlternativeText = "Linked Video";
```

يستبدل `"YourVideoPathHere"` مع المسار الفعلي لملف الفيديو الخاص بك. `AlternativeText` توفر الخاصية وصفًا للفيديو المرتبط.

## الخطوة 6: حفظ العرض التقديمي
حفظ العرض التقديمي المعدل:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## الأسئلة الشائعة:

### كيف يمكنني تحديد حجم وموضع الفيديو المرتبط بالشريحة؟
يمكنك ضبط أبعاد وموضع إطار التحكم ActiveX باستخدام معلمات `AddOleObjectFrame` الطريقة. تمثل الوسائط الرقمية الأربعة إحداثيات X وY للزاوية العلوية اليسرى وعرض وارتفاع الإطار، على التوالي.

### هل يمكنني ربط مقاطع الفيديو بتنسيقات مختلفة باستخدام هذا النهج؟
نعم، يمكنك ربط مقاطع فيديو بتنسيقات مختلفة طالما توفر عنصر تحكم ActiveX المناسب لكل تنسيق. على سبيل المثال، عنصر تحكم ShockwaveFlash ActiveX المستخدم في هذا الدليل مناسب لمقاطع فيديو Flash (SWF). بالنسبة للتنسيقات الأخرى، قد تحتاج إلى استخدام مُعرِّفات برامج مختلفة.

### هل هناك حد لحجم الفيديو المرتبط؟
قد يؤثر حجم الفيديو المرتبط على الحجم الإجمالي وأداء عرضك التقديمي. يُنصح بتحسين مقاطع الفيديو لتشغيلها على الويب قبل ربطها بالعرض التقديمي.

### خاتمة:
باتباع الخطوات الموضحة في هذا الدليل، يمكنك بسهولة ربط فيديو عبر عنصر تحكم ActiveX في عرض تقديمي باستخدام Aspose.Slides لـ .NET. تُمكّنك هذه الميزة من إنشاء عروض تقديمية جذابة وتفاعلية تتضمن محتوى الوسائط المتعددة بسلاسة.

لمزيد من التفاصيل والخيارات المتقدمة، يمكنك الرجوع إلى [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}