---
title: إضافة خطوط عادية إلى شرائح العرض التقديمي باستخدام Aspose.Slides
linktitle: إضافة خطوط عادية إلى شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: قم بتحسين عروض PowerPoint التقديمية الخاصة بك في .NET باستخدام Aspose.Slides. اتبع دليلنا خطوة بخطوة لإضافة خطوط واضحة دون عناء.
type: docs
weight: 16
url: /ar/net/shape-effects-and-manipulation-in-slides/adding-plain-lines/
---
## مقدمة
غالبًا ما يتضمن إنشاء عروض PowerPoint التقديمية الجذابة والجذابة بصريًا دمج أشكال وعناصر مختلفة. إذا كنت تعمل مع .NET، فإن Aspose.Slides هي أداة قوية تعمل على تبسيط العملية. يركز هذا البرنامج التعليمي على إضافة خطوط عادية إلى شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. تابع لتحسين عروضك التقديمية باستخدام هذا الدليل سهل المتابعة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة .NET.
- تثبيت Visual Studio أو أي بيئة تطوير .NET مفضلة.
-  تم تثبيت Aspose.Slides لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للوصول إلى وظيفة Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## الخطوة 1: إعداد دليل المستندات
ابدأ بتحديد المسار إلى دليل المستندات الخاص بك:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## الخطوة 2: إنشاء مثيل لفئة PresentationEx
 إنشاء مثيل لـ`Presentation` فئة تمثل ملف PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // سيتم وضع الرمز الخاص بك للخطوات التالية هنا.
}
```
## الخطوة 3: احصل على الشريحة الأولى
الوصول إلى الشريحة الأولى من العرض التقديمي:
```csharp
ISlide sld = pres.Slides[0];
```
## الخطوة 4: إضافة خط الشكل التلقائي
إضافة شكل تلقائي للخط إلى الشريحة:
```csharp
sld.Shapes.AddAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
اضبط المعلمات (يسار، أعلى، عرض، ارتفاع) بناءً على متطلباتك.
## الخطوة 5: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل على القرص:
```csharp
pres.Save(dataDir + "LineShape1_out.pptx", SaveFormat.Pptx);
```
بهذا نختتم الدليل خطوة بخطوة حول إضافة خطوط عادية إلى شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## خاتمة
يمكن أن يؤدي دمج خطوط بسيطة في عروض PowerPoint التقديمية إلى تحسين المظهر المرئي بشكل كبير. يوفر Aspose.Slides for .NET طريقة مباشرة لتحقيق ذلك. قم بتجربة الأشكال والعناصر المختلفة لإنشاء عروض تقديمية جذابة.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص مظهر الخط؟
ج: نعم، يمكنك ضبط اللون والسمك والنمط باستخدام Aspose.Slides API.
### س: هل Aspose.Slides متوافق مع أحدث أطر عمل .NET؟
ج: بالتأكيد، يدعم Aspose.Slides أحدث أطر عمل .NET.
### س: أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
 ج: اكتشف الوثائق[هنا](https://reference.aspose.com/slides/net/).
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 زيارة[هنا](https://purchase.aspose.com/temporary-license/) للتراخيص المؤقتة.
### س: تواجه المشاكل؟ أين يمكنني الحصول على الدعم؟
 ج: اطلب المساعدة في[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).