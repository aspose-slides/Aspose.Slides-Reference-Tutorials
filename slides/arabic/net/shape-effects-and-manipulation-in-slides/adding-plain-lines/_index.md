---
"description": "حسّن عروض PowerPoint التقديمية في .NET باستخدام Aspose.Slides. اتبع دليلنا خطوة بخطوة لإضافة خطوط بسيطة بسهولة."
"linktitle": "إضافة خطوط عادية إلى شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إضافة خطوط عادية إلى شرائح العرض التقديمي باستخدام Aspose.Slides"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/adding-plain-lines/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة خطوط عادية إلى شرائح العرض التقديمي باستخدام Aspose.Slides

## مقدمة
غالبًا ما يتطلب إنشاء عروض PowerPoint جذابة وجذابة بصريًا دمج أشكال وعناصر متنوعة. إذا كنت تستخدم .NET، فإن Aspose.Slides أداة فعّالة تُبسّط العملية. يُركّز هذا البرنامج التعليمي على إضافة خطوط بسيطة إلى شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. تابع معنا لتحسين عروضك التقديمية باستخدام هذا الدليل السهل.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة .NET.
- تم تثبيت Visual Studio أو أي بيئة تطوير .NET مفضلة.
- تم تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها. [هنا](https://releases.aspose.com/slides/net/).
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، ابدأ باستيراد المساحات الأساسية اللازمة للوصول إلى وظيفة Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد دليل المستندات
ابدأ بتحديد المسار إلى دليل المستند الخاص بك:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## الخطوة 2: إنشاء مثيل لفئة PresentationEx
إنشاء مثيل لـ `Presentation` الفئة التي تمثل ملف PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // سيتم وضع الكود الخاص بالخطوات التالية هنا.
}
```
## الخطوة 3: الحصول على الشريحة الأولى
الوصول إلى الشريحة الأولى من العرض التقديمي:
```csharp
ISlide sld = pres.Slides[0];
```
## الخطوة 4: إضافة خط الشكل التلقائي
إضافة شكل خط تلقائي إلى الشريحة:
```csharp
sld.Shapes.AddAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
قم بضبط المعلمات (اليسار، الأعلى، العرض، الارتفاع) بناءً على متطلباتك.
## الخطوة 5: حفظ العرض التقديمي
حفظ العرض التقديمي المعدل على القرص:
```csharp
pres.Save(dataDir + "LineShape1_out.pptx", SaveFormat.Pptx);
```
هذا يختتم الدليل خطوة بخطوة حول إضافة خطوط عادية إلى شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET.
## خاتمة
إن إضافة خطوط بسيطة إلى عروض PowerPoint التقديمية يُحسّن من جاذبيتها البصرية بشكل ملحوظ. يوفر Aspose.Slides for .NET طريقة سهلة لتحقيق ذلك. جرّب أشكالًا وعناصر مختلفة لإنشاء عروض تقديمية آسرة.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص مظهر الخط؟
ج: نعم، يمكنك ضبط اللون والسمك والنمط باستخدام واجهة برمجة التطبيقات Aspose.Slides.
### س: هل Aspose.Slides متوافق مع أحدث أطر عمل .NET؟
ج: بالتأكيد، يدعم Aspose.Slides أحدث أطر عمل .NET.
### س: أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
أ: استكشف الوثائق [هنا](https://reference.aspose.com/slides/net/).
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
أ: زيارة [هنا](https://purchase.aspose.com/temporary-license/) للحصول على رخص مؤقتة.
### س: هل تواجه مشاكل؟ أين يمكنني الحصول على الدعم؟
أ: اطلب المساعدة بشأن [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}