---
"description": "تعلّم كيفية إضافة إطارات صور بارتفاع مقياس نسبي في Aspose.Slides لـ .NET. اتبع هذا الدليل خطوة بخطوة لإنشاء عروض تقديمية سلسة."
"linktitle": "إضافة إطارات صور ذات ارتفاع مقياس نسبي في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "دورة تعليمية حول إضافة إطارات الصور باستخدام Aspose.Slides .NET"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# دورة تعليمية حول إضافة إطارات الصور باستخدام Aspose.Slides .NET

## مقدمة
Aspose.Slides for .NET مكتبة فعّالة تُمكّن المطورين من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها بسهولة تامة في تطبيقات .NET. في هذا البرنامج التعليمي، سنتعمق في عملية إضافة إطارات صور بارتفاع مقياس نسبي باستخدام Aspose.Slides for .NET. اتبع هذا الدليل خطوة بخطوة لتطوير مهاراتك في إنشاء العروض التقديمية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio أو أي بيئة تطوير C# مفضلة أخرى.
- تمت إضافة مكتبة Aspose.Slides لـ .NET إلى مشروعك.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء اللازمة إلى شيفرة C#. تضمن هذه الخطوة وصولك إلى الفئات والوظائف التي توفرها مكتبة Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## الخطوة 1: إعداد مشروعك
ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك. تأكد من إضافة مكتبة Aspose.Slides for .NET إلى مشروعك بالرجوع إليها.
## الخطوة 2: تحميل العرض التقديمي والصورة
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // تحميل الصورة المراد إضافتها إلى مجموعة صور العرض التقديمي
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
في هذه الخطوة نقوم بإنشاء كائن عرض تقديمي جديد ونقوم بتحميل الصورة التي نريد إضافتها إلى العرض التقديمي.
## الخطوة 3: إضافة إطار الصورة إلى الشريحة
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
الآن، أضف إطار صورة إلى الشريحة الأولى من العرض التقديمي. عدّل المعلمات، مثل نوع الشكل والموضع والأبعاد، وفقًا لمتطلباتك.
## الخطوة 4: تعيين العرض والارتفاع النسبيين للمقياس
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
قم بتعيين الارتفاع والعرض النسبيين لإطار الصورة لتحقيق تأثير القياس المطلوب.
## الخطوة 5: حفظ العرض التقديمي
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
أخيرًا، احفظ العرض التقديمي بإطار الصورة المضاف بتنسيق الإخراج المحدد.
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة إطارات صور بارتفاع مقياس نسبي باستخدام Aspose.Slides لـ .NET. جرّب صورًا ومواضع ومقاييس مختلفة لإنشاء عروض تقديمية جذابة بصريًا مصممة خصيصًا لاحتياجاتك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات برمجة أخرى؟
يدعم Aspose.Slides بشكل أساسي لغات .NET، ولكن يمكنك استكشاف منتجات Aspose الأخرى للتوافق مع منصات مختلفة.
### أين يمكنني العثور على وثائق مفصلة لـ Aspose.Slides لـ .NET؟
راجع إلى [التوثيق](https://reference.aspose.com/slides/net/) للحصول على معلومات شاملة وأمثلة.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
نعم يمكنك الحصول على [نسخة تجريبية مجانية](https://releases.aspose.com/) لتقييم قدرات المكتبة.
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ .NET؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لطلب المساعدة من المجتمع وخبراء Aspose.
### أين يمكنني شراء Aspose.Slides لـ .NET؟
يمكنك شراء Aspose.Slides لـ .NET من [صفحة الشراء](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}