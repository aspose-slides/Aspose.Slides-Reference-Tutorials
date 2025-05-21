---
"description": "استغل قوة Aspose.Slides لـ .NET! تعلّم كيفية إنشاء صور مصغرة للأشكال بسهولة مع حدود باستخدام دليلنا المفصل خطوة بخطوة."
"linktitle": "إنشاء صورة مصغرة مع حدود للشكل في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء صورة مصغرة مع حدود للشكل في Aspose.Slides"
"url": "/ar/net/image-and-video-manipulation-in-slides/creating-thumbnail-bounds-shape/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة مع حدود للشكل في Aspose.Slides

## مقدمة
إذا كنت مطور .NET وتبحث عن حل فعال لإنشاء صور مصغرة مع حدود للأشكال في عروض PowerPoint التقديمية، فإن Aspose.Slides for .NET هي أداتك المثالية. توفر هذه المكتبة القوية تكاملاً سلسًا، مما يسمح لك بمعالجة واستخراج المعلومات القيّمة من ملفات PowerPoint بكفاءة. في هذا البرنامج التعليمي، سنشرح عملية إنشاء صورة مصغرة مع حدود لشكل باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مكتبة Aspose.Slides لـ .NET: قم بتنزيل وتثبيت مكتبة Aspose.Slides لـ .NET من [هنا](https://releases.aspose.com/slides/net/).
2. دليل المستندات الخاص بك: استبدل "دليل المستندات الخاص بك" في مقتطف التعليمات البرمجية بالمسار الفعلي إلى دليل المستندات الخاص بك.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء اللازمة للاستفادة من وظائف Aspose.Slides. أضف الكود التالي في بداية مشروعك:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
الآن، دعنا نقسم الكود المقدم إلى خطوات متعددة للحصول على فهم شامل:
## الخطوة 1: إنشاء فئة العرض التقديمي
```csharp
string dataDir = "Your Documents Directory";
// إنشاء فئة عرض تقديمي تمثل ملف العرض التقديمي
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // أصبح الآن كائن العرض جاهزًا لمزيد من المعالجة.
}
```
في هذه الخطوة، نقوم بتهيئة Aspose.Slides `Presentation` الفئة التي تمثل ملف عرض PowerPoint. `using` تضمن العبارة التخلص الصحيح من الموارد بمجرد الخروج من الكتلة.
## الخطوة 2: إنشاء صورة ذات شكل مرتبط
```csharp
// إنشاء صورة ذات شكل مرتبط بالمظهر
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
    // يحتوي كائن الخريطة النقطية الآن على صورة مصغرة ذات حدود محددة.
}
```
تتضمن هذه الخطوة إنشاء صورة مصغّرة لشكل ذي حدود محددة. هنا، `ShapeThumbnailBounds.Appearance` يُستخدم لتحديد حدود المظهر. اضبط المعلمات (1، 1) وفقًا لمتطلباتك.
## الخطوة 3: حفظ الصورة على القرص
```csharp
// حفظ الصورة على القرص بتنسيق PNG
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```
في هذه الخطوة الأخيرة، تُحفظ الصورة المصغرة المُولَّدة على القرص بصيغة PNG. يمكنك تخصيص اسم الملف وصيغته حسب تفضيلاتك.
الآن، نجحت في إنشاء صورة مصغّرة مع حدود لشكل باستخدام Aspose.Slides لـ .NET! هذه العملية فعّالة ويمكن دمجها بسلاسة في مشاريع .NET الخاصة بك لإدارة عروض PowerPoint التقديمية.
## خاتمة
يُبسّط Aspose.Slides for .NET عملية العمل مع عروض PowerPoint التقديمية، مُزوّدًا المطورين بأدوات فعّالة لمهام مثل إنشاء صور مصغّرة مع حدود للأشكال. باتباع هذا الدليل المُفصّل، ستكتسب رؤىً ثاقبة حول كيفية استخدام هذه المكتبة بكفاءة في مشاريع .NET الخاصة بك.
## الأسئلة الشائعة
### هل Aspose.Slides متوافق مع أحدث إطار عمل .NET؟
نعم، يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث إصدارات .NET Framework.
### هل يمكنني استخدام Aspose.Slides للمشاريع التجارية؟
بالتأكيد! يوفر Aspose.Slides خيارات ترخيص للاستخدام الفردي والتجاري. تفضل بزيارة [هنا](https://purchase.aspose.com/buy) لاستكشاف تفاصيل الترخيص.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides؟
نعم، يمكنك الوصول إلى نسخة تجريبية مجانية [هنا](https://releases.aspose.com/) لاستكشاف الميزات قبل إجراء عملية شراء.
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للتواصل مع المجتمع وطلب المساعدة من المطورين ذوي الخبرة.
### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
نعم يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/) لتلبية احتياجات المشاريع قصيرة الأجل.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}