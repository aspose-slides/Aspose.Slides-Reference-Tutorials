---
"description": "حسّن عروضك التقديمية مع Aspose.Slides لـ .NET! تعلّم كيفية تطبيق تأثيرات الدوران ثلاثية الأبعاد على الأشكال في هذا البرنامج التعليمي. أنشئ عرضًا تقديميًا ديناميكيًا ومذهلًا بصريًا."
"linktitle": "تطبيق تأثير الدوران ثلاثي الأبعاد على الأشكال في شرائح العرض التقديمي"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إتقان الدوران ثلاثي الأبعاد في العروض التقديمية باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إتقان الدوران ثلاثي الأبعاد في العروض التقديمية باستخدام Aspose.Slides لـ .NET

## مقدمة
يُعد إنشاء شرائح عرض تقديمي جذابة وديناميكية جانبًا أساسيًا للتواصل الفعال. يوفر Aspose.Slides for .NET مجموعة أدوات فعّالة لتحسين عروضك التقديمية، بما في ذلك إمكانية تطبيق تأثيرات دوران ثلاثية الأبعاد على الأشكال. في هذا البرنامج التعليمي، سنشرح عملية تطبيق تأثير دوران ثلاثي الأبعاد على الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [موقع إلكتروني](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET، مثل Visual Studio، لكتابة التعليمات البرمجية الخاصة بك وتشغيلها.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، استورد مساحات الأسماء اللازمة للاستفادة من وظائف Aspose.Slides. أدرج مساحات الأسماء التالية في بداية الكود:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## الخطوة 1: إعداد مشروعك
أنشئ مشروعًا جديدًا في بيئة تطوير .NET المُفضّلة لديك. تأكّد من إضافة مرجع Aspose.Slides إلى مشروعك.
## الخطوة 2: تهيئة العرض التقديمي
قم بإنشاء فئة عرض تقديمي لبدء العمل بالشرائح:
```csharp
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة الشكل التلقائي
أضف شكلًا تلقائيًا إلى الشريحة، مع تحديد نوعه وموقعه وأبعاده:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## الخطوة 4: ضبط تأثير الدوران ثلاثي الأبعاد
تكوين تأثير الدوران ثلاثي الأبعاد للشكل التلقائي:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل باستخدام تأثير الدوران ثلاثي الأبعاد المطبق:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## الخطوة 6: كرر ذلك للأشكال الأخرى
إذا كان لديك أشكال إضافية، كرر الخطوات من 3 إلى 5 لكل شكل.
## خاتمة
إضافة تأثيرات دوران ثلاثية الأبعاد للأشكال في شرائح العرض التقديمي تُحسّن جاذبيتها البصرية بشكل ملحوظ. مع Aspose.Slides لـ .NET، تُصبح هذه العملية سهلة، مما يُتيح لك إنشاء عروض تقديمية آسرة.
## الأسئلة الشائعة
### هل يمكنني تطبيق التدوير ثلاثي الأبعاد على مربعات النص في Aspose.Slides لـ .NET؟
نعم، يمكنك تطبيق تأثيرات الدوران ثلاثية الأبعاد على الأشكال المختلفة، بما في ذلك مربعات النص، باستخدام Aspose.Slides.
### هل هناك نسخة تجريبية من Aspose.Slides لـ .NET متاحة؟
نعم يمكنك الوصول إلى النسخة التجريبية [هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
نعم يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على وثائق مفصلة لـ Aspose.Slides لـ .NET؟
الوثائق متاحة [هنا](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}