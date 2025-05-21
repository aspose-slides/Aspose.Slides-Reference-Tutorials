---
"description": "تعرّف على كيفية إنشاء صور مصغّرة مخصصة من عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. حسّن تجربة المستخدم ووظائفه."
"linktitle": "إنشاء صورة مصغرة بأبعاد مخصصة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء صورة مصغرة في الشرائح باستخدام الأبعاد المخصصة"
"url": "/ar/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة في الشرائح باستخدام الأبعاد المخصصة


إنشاء صور مصغرة مخصصة لعروض PowerPoint التقديمية يُعدّ ميزة قيّمة، سواءً كنت تُنشئ تطبيقًا تفاعليًا، أو تُحسّن تجربة المستخدم، أو تُحسّن المحتوى لمنصات مُختلفة. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء صور مصغرة مخصصة من عروض PowerPoint التقديمية باستخدام مكتبة Aspose.Slides for .NET. تُتيح لك هذه المكتبة الفعّالة معالجة ملفات PowerPoint وتحويلها وتحسينها برمجيًا في تطبيقات .NET.

## المتطلبات الأساسية

قبل أن نتعمق في إنشاء صور مصغرة مخصصة، تأكد من توفر المتطلبات الأساسية التالية:

### 1. Aspose.Slides لـ .NET

يجب تثبيت مكتبة Aspose.Slides for .NET في مشروعك. إذا لم تكن مثبتة بالفعل، يمكنك العثور على الوثائق اللازمة وروابط التنزيل. [هنا](https://reference.aspose.com/slides/net/).

### 2. عرض تقديمي على PowerPoint

تأكد من أن لديك عرض PowerPoint التقديمي الذي تريد إنشاء صورة مصغّرة مخصصة منه. يجب أن يكون هذا العرض التقديمي متاحًا ضمن دليل مشروعك.

### 3. بيئة التطوير

لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك معرفة عملية ببرمجة .NET باستخدام C# وبيئة تطوير جاهزة، مثل Visual Studio.

الآن بعد أن قمنا بتغطية المتطلبات الأساسية، دعنا نقوم بتقسيم عملية إنشاء الصور المصغرة المخصصة إلى تعليمات خطوة بخطوة.

## استيراد مساحات الأسماء

أولاً، عليك تضمين مساحات الأسماء المطلوبة في شيفرة C#. تتيح لك هذه المساحات العمل مع Aspose.Slides ومعالجة عروض PowerPoint التقديمية.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## الخطوة 1: تحميل العرض التقديمي

للبدء، حمّل عرض PowerPoint الذي تريد إنشاء صورة مصغّرة مخصصة منه. يتم ذلك باستخدام مكتبة Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// إنشاء فئة عرض تقديمي تمثل ملف العرض التقديمي
using (Presentation pres = new Presentation(srcFileName))
{
    // سيتم وضع الكود الخاص بإنشاء الصورة المصغرة هنا
}
```

## الخطوة 2: الوصول إلى الشريحة

ضمن العرض التقديمي المُحمّل، عليك الوصول إلى الشريحة المُحددة التي تريد إنشاء الصورة المُصغّرة المُخصصة منها. يمكنك اختيار الشريحة حسب فهرسها.

```csharp
// الوصول إلى الشريحة الأولى (يمكنك تغيير الفهرس حسب الحاجة)
ISlide sld = pres.Slides[0];
```

## الخطوة 3: تحديد أبعاد الصورة المصغرة المخصصة

حدد الأبعاد المطلوبة لصورتك المصغرة المخصصة. يمكنك تحديد العرض والارتفاع بالبكسل وفقًا لمتطلبات تطبيقك.

```csharp
int desiredX = 1200; // عرض
int desiredY = 800;  // ارتفاع
```

## الخطوة 4: حساب عوامل القياس

للحفاظ على نسبة العرض إلى الارتفاع للشريحة، احسب عوامل القياس لأبعاد X وY استنادًا إلى حجم الشريحة والأبعاد المطلوبة.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## الخطوة 5: إنشاء الصورة المصغرة

قم بإنشاء صورة كاملة الحجم للشريحة بالأبعاد المخصصة المحددة واحفظها على القرص بتنسيق JPEG.

```csharp
// إنشاء صورة بالحجم الكامل
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// حفظ الصورة على القرص بتنسيق JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

الآن بعد أن اتبعت هذه الخطوات، يجب أن تكون قد نجحت في إنشاء صورة مصغرة مخصصة من عرض PowerPoint الخاص بك.

## خاتمة

يُعد إنشاء صور مصغرة مخصصة من عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET مهارة قيّمة تُحسّن تجربة المستخدم ووظائف تطبيقاتك. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة إنشاء صور مصغرة مخصصة تلبي احتياجاتك الخاصة.

---

## الأسئلة الشائعة

### ما هو Aspose.Slides لـ .NET؟
Aspose.Slides for .NET هي مكتبة قوية تسمح للمطورين بالعمل مع عروض PowerPoint برمجيًا في تطبيقات .NET.

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟
يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/slides/net/).

### هل استخدام Aspose.Slides لـ .NET مجاني؟
Aspose.Slides لـ .NET هي مكتبة تجارية. يمكنك العثور على معلومات التسعير والترخيص. [هنا](https://purchase.aspose.com/buy).

### هل أحتاج إلى مهارات برمجة متقدمة لاستخدام Aspose.Slides لـ .NET؟
على الرغم من أن بعض المعرفة ببرمجة .NET مفيدة، فإن Aspose.Slides for .NET يوفر واجهة برمجة تطبيقات سهلة الاستخدام تعمل على تبسيط العمل مع عروض PowerPoint.

### هل يتوفر الدعم الفني لـ Aspose.Slides لـ .NET؟
نعم يمكنك الوصول إلى الدعم الفني والمنتديات المجتمعية [هنا](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}