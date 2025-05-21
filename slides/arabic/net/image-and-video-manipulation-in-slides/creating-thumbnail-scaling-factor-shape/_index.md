---
"description": "تعلم كيفية إنشاء صور مصغرة لعروض PowerPoint بحدود محددة باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة لدمج سلس."
"linktitle": "إنشاء صورة مصغرة مع عامل القياس للشكل في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء صورة مصغرة مع عامل القياس للشكل في Aspose.Slides"
"url": "/ar/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة مع عامل القياس للشكل في Aspose.Slides

## مقدمة
أهلاً بكم في دليلنا الشامل حول إنشاء صور مصغرة مع حدود للأشكال في Aspose.Slides لـ .NET. Aspose.Slides مكتبة فعّالة تُمكّن المطورين من العمل بسلاسة مع عروض PowerPoint التقديمية في تطبيقات .NET الخاصة بهم. في هذا البرنامج التعليمي، سنتعمق في عملية إنشاء صور مصغرة مع حدود محددة للأشكال في العرض التقديمي باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير مناسبة لـ .NET، مثل Visual Studio، على جهازك.
## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، ابدأ باستيراد المساحات الأساسية اللازمة للوصول إلى وظائف Aspose.Slides:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## الخطوة 1: إعداد العرض التقديمي
ابدأ بإنشاء فئة عرض تقديمي تمثل ملف عرض PowerPoint الذي تريد العمل به:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // ستجد هنا الكود الخاص بإنشاء الصور المصغرة
}
```
## الخطوة 2: إنشاء صورة بالحجم الكامل
داخل كتلة العرض التقديمي، قم بإنشاء صورة كاملة الحجم للشكل الذي تريد إنشاء صورة مصغرة له:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    // الكود الخاص بك لحفظ الصورة يذهب هنا
}
```
## الخطوة 3: حفظ الصورة على القرص
احفظ الصورة المُنشأة على القرص، مع تحديد التنسيق (في هذه الحالة، PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إنشاء صور مصغّرة مع حدود للأشكال باستخدام Aspose.Slides لـ .NET. هذه الميزة مفيدة للغاية عند الحاجة إلى إنشاء صور بأحجام محددة للأشكال في عروض PowerPoint التقديمية برمجيًا.
## الأسئلة الشائعة
### س1: هل يمكنني استخدام Aspose.Slides مع أطر عمل .NET الأخرى؟
نعم، Aspose.Slides متوافق مع مختلف أطر عمل .NET، مما يوفر المرونة للتكامل مع أنواع مختلفة من التطبيقات.
### س2: هل هناك نسخة تجريبية متاحة لـ Aspose.Slides؟
نعم، يمكنك استكشاف وظائف Aspose.Slides عن طريق تنزيل الإصدار التجريبي [هنا](https://releases.aspose.com/).
### س3: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
يمكنك الحصول على ترخيص مؤقت لـ Aspose.Slides من خلال زيارة [هذا الرابط](https://purchase.aspose.com/temporary-license/).
### س4: أين يمكنني العثور على دعم إضافي لـ Aspose.Slides؟
لأي استفسارات أو مساعدة، لا تتردد في زيارة منتدى دعم Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11).
### س5: هل يمكنني شراء Aspose.Slides لـ .NET؟
بالتأكيد! لشراء Aspose.Slides لـ .NET، يُرجى زيارة صفحة الشراء [هنا](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}