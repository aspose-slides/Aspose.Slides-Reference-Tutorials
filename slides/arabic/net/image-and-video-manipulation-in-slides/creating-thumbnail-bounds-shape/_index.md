---
title: إنشاء صورة مصغرة ذات حدود للشكل في Aspose.Slides
linktitle: إنشاء صورة مصغرة ذات حدود للشكل في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: أطلق العنان لقوة Aspose.Slides لـ .NET! تعلم كيفية إنشاء صور مصغرة للأشكال بسهولة وبحدود باستخدام دليلنا خطوة بخطوة.
weight: 10
url: /ar/net/image-and-video-manipulation-in-slides/creating-thumbnail-bounds-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة ذات حدود للشكل في Aspose.Slides

## مقدمة
إذا كنت أحد مطوري برامج .NET وتبحث عن حل قوي لإنشاء صور مصغرة ذات حدود للأشكال في عروض PowerPoint التقديمية، فإن Aspose.Slides for .NET هو أداة الانتقال الخاصة بك. توفر هذه المكتبة القوية تكاملًا سلسًا، مما يسمح لك بمعالجة المعلومات القيمة واستخراجها بكفاءة من ملفات PowerPoint. في هذا البرنامج التعليمي، سنتعرف على عملية إنشاء صورة مصغرة ذات حدود للشكل باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Slides لمكتبة .NET: قم بتنزيل وتثبيت Aspose.Slides لمكتبة .NET من[هنا](https://releases.aspose.com/slides/net/).
2. دليل المستندات الخاص بك: استبدل "دليل المستندات" في مقتطف الشفرة بالمسار الفعلي إلى دليل المستندات الخاص بك.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية للاستفادة من وظائف Aspose.Slides. أضف الكود التالي في بداية مشروعك:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
الآن، دعونا نقسم الكود المقدم إلى خطوات متعددة لفهم شامل:
## الخطوة 1: إنشاء مثيل لفئة العرض التقديمي
```csharp
string dataDir = "Your Documents Directory";
// إنشاء مثيل لفئة العرض التقديمي التي تمثل ملف العرض التقديمي
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // كائن العرض التقديمي جاهز الآن لمزيد من المعالجة.
}
```
 في هذه الخطوة، نقوم بتهيئة Aspose.Slides`Presentation` فئة تمثل ملف العرض التقديمي لـ PowerPoint. ال`using` يضمن البيان التخلص السليم من الموارد بمجرد الخروج من الكتلة.
## الخطوة 2: إنشاء صورة ذات شكل محدد
```csharp
// قم بإنشاء صورة ذات شكل محدد المظهر
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
    // يحتوي كائن الصورة النقطية الآن على الصورة المصغرة ذات الحدود المحددة.
}
```
 تتضمن هذه الخطوة إنشاء صورة مصغرة لشكل بحدود محددة. هنا،`ShapeThumbnailBounds.Appearance` يستخدم لتحديد حدود المظهر. اضبط المعلمات (1، 1) وفقًا لمتطلباتك.
## الخطوة 3: احفظ الصورة على القرص
```csharp
//احفظ الصورة على القرص بتنسيق PNG
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```
في هذه الخطوة الأخيرة، يتم حفظ الصورة المصغرة التي تم إنشاؤها على القرص بتنسيق PNG. يمكنك تخصيص اسم الملف وتنسيقه بناءً على تفضيلاتك.
لقد نجحت الآن في إنشاء صورة مصغرة ذات حدود لشكل ما باستخدام Aspose.Slides لـ .NET! تتميز هذه العملية بالكفاءة ويمكن دمجها بسلاسة في مشاريع .NET الخاصة بك للتعامل مع عروض PowerPoint التقديمية.
## خاتمة
يعمل Aspose.Slides for .NET على تبسيط عملية العمل مع عروض PowerPoint التقديمية، مما يوفر للمطورين أدوات قوية للقيام بمهام مثل إنشاء صور مصغرة ذات حدود للأشكال. باتباع هذا الدليل المفصّل خطوة بخطوة، تكون قد اكتسبت رؤى حول كيفية استخدام هذه المكتبة بكفاءة لمشاريع .NET الخاصة بك.
## أسئلة مكررة
### هل Aspose.Slides متوافق مع أحدث إطار عمل .NET؟
نعم، يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث إصدارات إطار عمل .NET.
### هل يمكنني استخدام Aspose.Slides للمشاريع التجارية؟
 قطعاً! يقدم Aspose.Slides خيارات الترخيص للاستخدام الفردي والتجاري. يزور[هنا](https://purchase.aspose.com/buy) لاستكشاف تفاصيل الترخيص.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/)لاستكشاف الميزات قبل إجراء عملية الشراء.
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للتواصل مع المجتمع وطلب المساعدة من المطورين ذوي الخبرة.
### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 نعم يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) لاحتياجات المشروع على المدى القصير.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
