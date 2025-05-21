---
"description": "تعلّم كيفية إنشاء صور مصغّرة جذابة لملاحظات SmartArt الفرعية باستخدام Aspose.Slides لـ .NET. ارتقِ بعروضك التقديمية بمؤثرات بصرية ديناميكية!"
"linktitle": "إنشاء صورة مصغرة لملاحظة فرعية في SmartArt في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء صورة مصغرة لملاحظة فرعية في SmartArt في Aspose.Slides"
"url": "/ar/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة لملاحظة فرعية في SmartArt في Aspose.Slides

## مقدمة
في مجال العروض التقديمية الديناميكية، يبرز Aspose.Slides for .NET كأداة فعّالة، تُمكّن المطورين من تعديل عروض PowerPoint التقديمية وتحسينها برمجيًا. ومن الميزات الرائعة إمكانية إنشاء صور مصغّرة لملاحظات SmartArt الفرعية، مما يُضفي لمسةً بصريةً جذابةً على عروضك التقديمية. سيُرشدك هذا الدليل المُفصّل خطوةً بخطوة خلال عملية إنشاء صور مصغّرة لملاحظات SmartArt الفرعية باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من دمج مكتبة Aspose.Slides في مشروع .NET الخاص بك. إذا لم يكن الأمر كذلك، فقم بتنزيلها من [صفحة الإصدارات](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET عاملة، واحصل على فهم أساسي لبرمجة C#.
- عرض تقديمي نموذجي: قم بإنشاء أو الحصول على عرض تقديمي في PowerPoint يحتوي على SmartArt مع ملاحظات فرعية للاختبار.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء اللازمة إلى مشروع C# الخاص بك. تتيح لك هذه المساحات الوصول إلى الفئات والأساليب اللازمة للعمل مع Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## الخطوة 1: إنشاء فئة العرض التقديمي
ابدأ بإنشاء مثيل `Presentation` الفئة التي تمثل ملف PPTX الذي ستعمل عليه.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة SmartArt
الآن، أضف SmartArt إلى شريحة ضمن العرض التقديمي. في هذا المثال، نستخدم `BasicCycle` تَخطِيط.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## الخطوة 3: الحصول على مرجع العقدة
للعمل مع عقدة معينة في SmartArt، احصل على مرجعها باستخدام فهرسها.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## الخطوة 4: الحصول على الصورة المصغرة
استرداد الصورة المصغرة للملاحظة الفرعية داخل عقدة SmartArt.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## الخطوة 5: حفظ الصورة المصغرة
احفظ الصورة المصغرة الناتجة في الدليل المحدد.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
كرر هذه الخطوات لكل عقدة SmartArt في العرض التقديمي الخاص بك، وقم بتخصيص التخطيط والأنماط حسب الحاجة.
## خاتمة
في الختام، يُمكّن Aspose.Slides for .NET المطورين من إنشاء عروض تقديمية جذابة بسهولة. تُحسّن إمكانية إنشاء صور مصغّرة لملاحظات SmartArt الفرعية من جاذبية عروضك التقديمية، مما يوفر تجربة مستخدم ديناميكية وتفاعلية.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص حجم وتنسيق الصورة المصغرة التي تم إنشاؤها؟
ج: نعم، يمكنك تعديل أبعاد وتنسيق الصورة المصغرة عن طريق تعديل المعلمات المقابلة في الكود.
### س: هل يدعم Aspose.Slides تخطيطات SmartArt الأخرى؟
ج: بالتأكيد! يوفر Aspose.Slides مجموعة متنوعة من تخطيطات SmartArt، مما يتيح لك اختيار التصميم الأنسب لاحتياجات عرضك التقديمي.
### س: هل يتوفر ترخيص مؤقت لأغراض الاختبار؟
ج: نعم، يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/) للاختبار والتقييم.
### س: أين يمكنني طلب المساعدة أو التواصل مع مجتمع Aspose.Slides؟
أ: قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للتواصل مع المجتمع وطرح الأسئلة وإيجاد الحلول.
### س: هل يمكنني شراء Aspose.Slides لـ .NET؟
أ: بالتأكيد! استكشف خيارات الشراء [هنا](https://purchase.aspose.com/buy) لإطلاق العنان للإمكانات الكاملة لـ Aspose.Slides في مشاريعك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}