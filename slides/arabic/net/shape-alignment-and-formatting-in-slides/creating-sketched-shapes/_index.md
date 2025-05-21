---
"description": "تعلّم كيفية إضافة أشكال إبداعية إلى شرائح عرضك التقديمي باستخدام Aspose.Slides لـ .NET. حسّن مظهرك بكل سهولة!"
"linktitle": "إنشاء أشكال مرسومة في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء أشكال مذهلة باستخدام Aspose.Slides"
"url": "/ar/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء أشكال مذهلة باستخدام Aspose.Slides

## مقدمة
مرحبًا بكم في دليلنا التفصيلي لإنشاء أشكال تخطيطية في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. إذا كنت ترغب في إضافة لمسة إبداعية إلى عروضك التقديمية، فإن الأشكال التخطيطية تُضفي لمسة جمالية فريدة ومرسومة يدويًا. في هذا البرنامج التعليمي، سنشرح العملية بالتفصيل، ونُقسّمها إلى خطوات بسيطة لضمان تجربة سلسة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها. [هنا](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET باستخدام IDE المفضل لديك.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء اللازمة في مشروع .NET الخاص بك. تضمن هذه الخطوة وصولك إلى الفئات والوظائف اللازمة للعمل مع Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## الخطوة 1: إعداد المشروع
ابدأ بإنشاء مشروع .NET جديد أو افتح مشروعًا موجودًا. تأكد من تضمين Aspose.Slides في مراجع مشروعك.
## الخطوة 2: تهيئة Aspose.Slides
قم بتشغيل Aspose.Slides بإضافة الكود التالي. هذا يُهيئ العرض التقديمي ويُحدد مسارات الإخراج لملف العرض التقديمي والصورة المصغرة.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // انتقل إلى الخطوات التالية...
}
```
## الخطوة 3: إضافة الشكل المرسوم
الآن، لنُضِف شكلًا تخطيطيًا إلى الشريحة. في هذا المثال، سنُضيف مستطيلًا بتأثير رسم يدوي حر.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// تحويل الشكل إلى رسم تخطيطي بأسلوب الرسم الحر
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## الخطوة 4: إنشاء الصورة المصغرة
أنشئ صورة مصغّرة للشريحة لتصوّر الشكل المرسوم. احفظ الصورة المصغّرة كملف PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## الخطوة 5: حفظ العرض التقديمي
احفظ ملف العرض التقديمي بالشكل المرسوم.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
هذا كل شيء! لقد أنشأتَ بنجاح عرضًا تقديميًا بأشكال مرسومة باستخدام Aspose.Slides لـ .NET.
## خاتمة
إضافة أشكال تخطيطية إلى شرائح عرضك التقديمي تُحسّن من جاذبيتها البصرية وتُثير اهتمام جمهورك. مع Aspose.Slides لـ .NET، تُصبح العملية سهلة، مما يُتيح لك إطلاق العنان لإبداعك بكل سهولة.
## الأسئلة الشائعة
### 1. هل يمكنني تخصيص التأثير المرسوم؟
نعم، يوفر Aspose.Slides لـ .NET خيارات تخصيص متنوعة للتأثيرات المرسومة. راجع [التوثيق](https://reference.aspose.com/slides/net/) لمزيد من المعلومات التفصيلية.
### 2. هل هناك نسخة تجريبية مجانية متاحة؟
بالتأكيد! يمكنك تجربة Aspose.Slides مجانًا لـ .NET [هنا](https://releases.aspose.com/).
### 3. أين يمكنني الحصول على الدعم؟
لأي مساعدة أو استفسارات، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. كيف يمكنني شراء Aspose.Slides لـ .NET؟
لشراء Aspose.Slides لـ .NET، قم بزيارة [صفحة الشراء](https://purchase.aspose.com/buy).
### 5. هل تقدمون تراخيص مؤقتة؟
نعم، التراخيص المؤقتة متاحة [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}