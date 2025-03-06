---
title: إنشاء صورة مصغرة لملاحظة SmartArt التابعة في Aspose.Slides
linktitle: إنشاء صورة مصغرة لملاحظة SmartArt التابعة في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء صور مصغرة جذابة لـ SmartArt Child Note باستخدام Aspose.Slides لـ .NET. ارفع مستوى عروضك التقديمية باستخدام صور ديناميكية!
type: docs
weight: 15
url: /ar/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---
## مقدمة
في عالم العروض التقديمية الديناميكية، يبرز Aspose.Slides for .NET كأداة قوية توفر للمطورين القدرة على التعامل مع عروض PowerPoint التقديمية وتحسينها برمجيًا. إحدى الميزات المثيرة للاهتمام هي القدرة على إنشاء صور مصغرة لملاحظات SmartArt Child Notes، مما يضيف طبقة من الجاذبية المرئية إلى العروض التقديمية الخاصة بك. سيرشدك هذا الدليل خطوة بخطوة خلال عملية إنشاء صور مصغرة لملاحظات SmartArt Child Notes باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Slides for .NET: تأكد من دمج مكتبة Aspose.Slides في مشروع .NET الخاص بك. إذا لم يكن الأمر كذلك، قم بتنزيله من[صفحة الإصدارات](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET عاملة، واحصل على فهم أساسي لبرمجة C#.
- نموذج عرض تقديمي: قم بإنشاء أو الحصول على عرض تقديمي لـ PowerPoint يحتوي على SmartArt مع ملاحظات فرعية للاختبار.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. توفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب اللازمة للعمل مع Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## الخطوة 1: إنشاء مثيل لفئة العرض التقديمي
 ابدأ بإنشاء مثيل لـ`Presentation` class، يمثل ملف PPTX الذي ستعمل معه.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة SmartArt
 الآن، قم بإضافة SmartArt إلى شريحة داخل العرض التقديمي. في هذا المثال، نستخدم`BasicCycle` تَخطِيط.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## الخطوة 3: الحصول على مرجع العقدة
للعمل مع عقدة معينة في SmartArt، احصل على مرجعها باستخدام الفهرس الخاص بها.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## الخطوة 4: الحصول على الصورة المصغرة
استرجع الصورة المصغرة للملاحظة التابعة داخل عقدة SmartArt.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## الخطوة 5: حفظ الصورة المصغرة
احفظ الصورة المصغرة التي تم إنشاؤها في دليل محدد.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
كرر هذه الخطوات لكل عقدة SmartArt في العرض التقديمي الخاص بك، وقم بتخصيص التخطيط والأنماط حسب الحاجة.
## خاتمة
في الختام، يعمل Aspose.Slides for .NET على تمكين المطورين من إنشاء عروض تقديمية جذابة بسهولة. تعمل القدرة على إنشاء صور مصغرة لـ SmartArt Child Notes على تحسين المظهر المرئي لعروضك التقديمية، مما يوفر تجربة مستخدم ديناميكية وتفاعلية.
## أسئلة مكررة
### س: هل يمكنني تخصيص حجم وتنسيق الصورة المصغرة التي تم إنشاؤها؟
ج: نعم، يمكنك ضبط أبعاد الصورة المصغرة وتنسيقها عن طريق تعديل المعلمات المقابلة في الكود.
### س: هل يدعم Aspose.Slides تخطيطات SmartArt الأخرى؟
ج: بالتأكيد! يقدم Aspose.Slides مجموعة متنوعة من تخطيطات SmartArt، مما يسمح لك باختيار التخطيط الذي يناسب احتياجات العرض التقديمي الخاص بك.
### س: هل الترخيص المؤقت متاح لأغراض الاختبار؟
 ج: نعم، يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/) للاختبار والتقييم.
### س: أين يمكنني طلب المساعدة أو التواصل مع مجتمع Aspose.Slides؟
 ج: قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للتواصل مع المجتمع وطرح الأسئلة وإيجاد الحلول.
### س: هل يمكنني شراء Aspose.Slides لـ .NET؟
 ج: بالتأكيد! استكشاف خيارات الشراء[هنا](https://purchase.aspose.com/buy) لفتح الإمكانات الكاملة لـ Aspose.Slides في مشاريعك.