---
title: إتقان التأثيرات المجسمة المائلة في Aspose.Slides - برنامج تعليمي خطوة بخطوة
linktitle: تطبيق التأثيرات المجسمة المجسمة على الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بتحسين شرائح العرض التقديمي الخاص بك باستخدام Aspose.Slides لـ .NET! تعرّف على كيفية تطبيق التأثيرات المائلة الجذابة في هذا الدليل المفصّل خطوة بخطوة.
type: docs
weight: 24
url: /ar/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/
---
## مقدمة
في عالم العروض التقديمية الديناميكي، يمكن أن تؤدي إضافة جاذبية مرئية إلى شرائحك إلى تعزيز تأثير رسالتك بشكل كبير. يوفر Aspose.Slides for .NET مجموعة أدوات قوية لمعالجة شرائح العرض التقديمي وتجميلها برمجيًا. إحدى هذه الميزات المثيرة للاهتمام هي القدرة على تطبيق تأثيرات مشطوفة على الأشكال، مما يضيف عمقًا وأبعادًا إلى العناصر المرئية الخاصة بك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Slides for .NET: تأكد من تثبيت مكتبة Aspose.Slides. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة التطوير .NET الخاصة بك، واحصل على فهم أساسي لـ C#.
- دليل المستندات: قم بإنشاء دليل لمستنداتك حيث سيتم حفظ ملفات العرض التقديمي التي تم إنشاؤها.
## استيراد مساحات الأسماء
في كود C# الخاص بك، قم بتضمين مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
تأكد من وجود دليل المستند، وقم بإنشائه إذا لم يكن موجودًا بالفعل.
## الخطوة 2: إنشاء مثيل العرض التقديمي
```csharp
Presentation pres = new Presentation();
ISlide slide = pres.Slides[0];
```
قم بتهيئة مثيل عرض تقديمي وأضف شريحة للعمل عليها.
## الخطوة 3: إضافة شكل إلى الشريحة
```csharp
IAutoShape shape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.FillFormat.FillType = FillType.Solid;
shape.FillFormat.SolidFillColor.Color = Color.Green;
ILineFillFormat format = shape.LineFormat.FillFormat;
format.FillType = FillType.Solid;
format.SolidFillColor.Color = Color.Orange;
shape.LineFormat.Width = 2.0;
```
قم بإنشاء شكل تلقائي (القطع الناقص في هذا المثال) وقم بتخصيص خصائص التعبئة والخط الخاصة به.
## الخطوة 4: تعيين خصائص ThreeDFormat
```csharp
shape.ThreeDFormat.Depth = 4;
shape.ThreeDFormat.BevelTop.BevelType = BevelPresetType.Circle;
shape.ThreeDFormat.BevelTop.Height = 6;
shape.ThreeDFormat.BevelTop.Width = 6;
shape.ThreeDFormat.Camera.CameraType = CameraPresetType.OrthographicFront;
shape.ThreeDFormat.LightRig.LightType = LightRigPresetType.ThreePt;
shape.ThreeDFormat.LightRig.Direction = LightingDirection.Top;
```
حدد الخصائص ثلاثية الأبعاد، بما في ذلك النوع المشطوف، والارتفاع، والعرض، ونوع الكاميرا، ونوع الضوء، والاتجاه.
## الخطوة 5: احفظ العرض التقديمي
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
احفظ العرض التقديمي مع التأثيرات المشطوبة المطبقة على ملف PPTX.
## خاتمة
تهانينا! لقد نجحت في تطبيق التأثيرات المجسمة المائلة على شكل في العرض التقديمي الخاص بك باستخدام Aspose.Slides لـ .NET. قم بتجربة معلمات مختلفة لإطلاق العنان للإمكانات الكاملة للتحسينات المرئية في الشرائح الخاصة بك.
## أسئلة مكررة
### 1. هل يمكنني تطبيق تأثيرات مجسمة مجسمة على أشكال أخرى؟
نعم، يمكنك تطبيق تأثيرات مشطوفة على أشكال مختلفة عن طريق ضبط نوع الشكل وخصائصه وفقًا لذلك.
### 2. كيف يمكنني تغيير لون المجسم المائل؟
 تعديل`SolidFillColor.Color` الممتلكات داخل`BevelTop` خاصية تغيير لون المجسم.
### 3. هل Aspose.Slides متوافق مع أحدث إطار عمل .NET؟
نعم، يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث أطر عمل .NET.
### 4. هل يمكنني تطبيق تأثيرات مجسمة مشطوفة متعددة على شكل واحد؟
على الرغم من أن ذلك ليس أمرًا شائعًا، إلا أنه يمكنك تجربة تكديس أشكال متعددة أو معالجة الخصائص المائلة لتحقيق تأثير مماثل.
### 5. هل هناك تأثيرات ثلاثية الأبعاد أخرى متوفرة في Aspose.Slides؟
قطعاً! يقدم Aspose.Slides مجموعة متنوعة من التأثيرات ثلاثية الأبعاد لإضافة العمق والواقعية إلى عناصر العرض التقديمي الخاص بك.