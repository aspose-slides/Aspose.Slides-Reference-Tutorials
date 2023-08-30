---
title: إضافة إزاحة ممتدة إلى اليسار لإطار الصورة في Aspose.Slides
linktitle: إضافة إزاحة ممتدة إلى اليسار لإطار الصورة في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة إزاحة امتداد إلى اليسار لإطار صورة في PowerPoint باستخدام Aspose.Slides for .NET. دليل خطوة بخطوة مع مثال التعليمات البرمجية المصدر الكامل.
type: docs
weight: 14
url: /ar/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

## مقدمة إلى Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة شاملة تمكّن مطوري .NET من العمل مع عروض PowerPoint التقديمية دون الحاجة إلى Microsoft Office. فهو يوفر مجموعة واسعة من الميزات، بما في ذلك إنشاء الشرائح والأشكال والنصوص والصور وتحريرها ومعالجتها والمزيد.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Visual Studio على جهازك.
2. الفهم الأساسي لـ C# و.NET Framework.
3.  Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

## إعداد المشروع

لنبدأ بإعداد مشروع C# جديد في Visual Studio:

1. افتح فيجوال ستوديو.
2. انقر على "إنشاء مشروع جديد".
3. حدد "تطبيق وحدة التحكم (.NET Framework/Core)."
4. اختر الاسم والموقع المناسب لمشروعك.
5. انقر فوق "إنشاء".

بعد ذلك، قم بإضافة مرجع إلى مكتبة Aspose.Slides for .NET في مشروعك. انقر بزر الماوس الأيمن على "المراجع" في مستكشف الحلول، واختر "إدارة حزم NuGet"، وابحث عن "Aspose.Slides"، وقم بتثبيت الحزمة.

## إضافة إزاحة ممتدة إلى اليسار لإطار الصورة

لإضافة إزاحة امتداد إلى اليسار لإطار صورة باستخدام Aspose.Slides لـ .NET، اتبع الخطوات التالية:

1.  قم بتحميل ملف العرض التقديمي باستخدام`Presentation` فصل.
2. حدد الشريحة التي تحتوي على إطار الصورة الذي تريد تعديله.
3. قم بالوصول إلى شكل إطار الصورة من خلال تكرار الأشكال الموجودة على الشريحة.
4.  قم بتطبيق إزاحة التمدد على اليسار باستخدام`PictureFrame` فصل.

## رمز المثال

```csharp
using Aspose.Slides;
using Aspose.Slides.ShapeManagers;

namespace PictureFrameStretchOffsetExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // قم بتحميل العرض التقديمي
            using (Presentation presentation = new Presentation("sample.pptx"))
            {
                // احصل على الشريحة الأولى
                ISlide slide = presentation.Slides[0];

                // كرر من خلال الأشكال الموجودة على الشريحة
                foreach (IShape shape in slide.Shapes)
                {
                    if (shape is IPictureFrame)
                    {
                        IPictureFrame pictureFrame = (IPictureFrame)shape;

                        // تطبيق إزاحة تمتد إلى اليسار
                        pictureFrame.PictureFormat.StretchOffsetX = -10;
                    }
                }

                // احفظ العرض التقديمي المعدل
                presentation.Save("output.pptx", SaveFormat.Pptx);
            }
        }
    }
}
```

في هذا المثال، نقوم بتحميل عرض تقديمي، ونكرر الأشكال الموجودة في الشريحة الأولى، وإذا عثرنا على شكل إطار صورة، فإننا نطبق إزاحة تمدد قدرها -10 إلى اليسار.

## اختبار التطبيق

لاختبار التطبيق، اتبع الخطوات التالية:

1. تأكد من أن لديك نموذجًا لعرض PowerPoint التقديمي (`sample.pptx`) مع إطار صورة واحد على الأقل.
2. قم بتشغيل التطبيق.
3.  سيتم حفظ العرض التقديمي المعدل مع إزاحة التمدد المضافة باسم`output.pptx`.

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إضافة إزاحة امتداد إلى اليسار لإطار صورة في Aspose.Slides باستخدام .NET. يوفر Aspose.Slides for .NET مجموعة قوية من الأدوات لمعالجة عروض PowerPoint التقديمية برمجيًا، مما يتيح للمطورين إنشاء عروض شرائح ديناميكية ومخصصة بسلاسة.

## الأسئلة الشائعة

### كيف يمكنني تثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides for .NET من موقع الويب[هنا](https://releases.aspose.com/slides/net/).

### هل يمكنني استخدام Aspose.Slides لمهام معالجة PowerPoint الأخرى؟

قطعاً! يوفر Aspose.Slides for .NET مجموعة واسعة من الميزات، بما في ذلك إنشاء عروض PowerPoint التقديمية وتحريرها وتحويلها. يمكنك استكشاف وثائقها لمزيد من التفاصيل والأمثلة.

### هل Aspose.Slides متوافق مع تنسيقات PowerPoint المختلفة؟

نعم، يدعم Aspose.Slides تنسيقات PowerPoint المتنوعة، بما في ذلك PPTX وPPT وPOTX والمزيد. كما أنه يدعم التحويل بين الصيغ المختلفة.

### كيف يمكنني تخصيص خصائص أخرى للأشكال في العرض التقديمي؟

يمكنك الوصول إلى خصائص الأشكال المختلفة وتعديلها، بما في ذلك النص والموضع والحجم والتنسيق والمزيد، باستخدام مكتبة Aspose.Slides. تحقق من الوثائق للحصول على معلومات وأمثلة شاملة.

### هل يمكنني استخدام Aspose.Slides مع لغات البرمجة الأخرى؟

نعم، يوفر Aspose.Slides مكتبات لمختلف لغات البرمجة، بما في ذلك Java وPython والمزيد. يمكنك اختيار الخيار الذي يناسب بيئة التطوير الخاصة بك.