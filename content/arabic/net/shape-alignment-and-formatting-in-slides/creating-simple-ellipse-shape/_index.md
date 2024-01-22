---
title: قم بإنشاء شكل بيضاوي بسهولة باستخدام Aspose.Slides .NET
linktitle: إنشاء شكل بيضاوي بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء أشكال بيضاوية مذهلة في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. خطوات سهلة للتصميم الديناميكي!
type: docs
weight: 11
url: /ar/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---
## مقدمة
في عالم تصميم العروض التقديمية الديناميكي، يمكن أن يضيف دمج الأشكال مثل الأشكال البيضاوية لمسة من الإبداع والاحترافية. يقدم Aspose.Slides for .NET حلاً قويًا لمعالجة ملفات العرض التقديمي برمجيًا. سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء شكل بيضاوي بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيله من[صفحة الإصدارات](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET على جهازك.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
توفر مساحات الأسماء هذه الفئات والأساليب الأساسية المطلوبة للعمل مع شرائح العرض التقديمي وأشكاله.
## الخطوة 1: إعداد العرض التقديمي
ابدأ بإنشاء عرض تقديمي جديد والوصول إلى الشريحة الأولى. أضف الكود التالي لتحقيق ذلك:
```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// إنشاء فئة العرض التقديمي
using (Presentation pres = new Presentation())
{
    // احصل على الشريحة الأولى
    ISlide sld = pres.Slides[0];
```
يقوم هذا الرمز بتهيئة عرض تقديمي جديد وتحديد الشريحة الأولى لمزيد من المعالجة.
## الخطوة 2: إضافة شكل القطع الناقص
الآن، دعونا نضيف شكلًا بيضاويًا إلى الشريحة باستخدام`AddAutoShape` طريقة:
```csharp
// إضافة شكل تلقائي لنوع القطع الناقص
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
يقوم سطر التعليمات البرمجية هذا بإنشاء شكل بيضاوي عند الإحداثيات (50، 150) بعرض 150 وحدة وارتفاع 50 وحدة.
## الخطوة 3: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل على القرص باسم ملف محدد باستخدام الكود التالي:
```csharp
// اكتب ملف PPTX على القرص
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
تضمن هذه الخطوة استمرار تغييراتك، ويمكنك عرض العرض التقديمي الناتج بالشكل القطع الناقص المضاف حديثًا.
## خاتمة
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## الأسئلة الشائعة
### هل يمكنني تخصيص شكل القطع الناقص بشكل أكبر؟
نعم، يمكنك تعديل الخصائص المختلفة لشكل القطع الناقص، مثل اللون والحجم والموضع، لتلبية متطلبات التصميم المحددة الخاصة بك.
### هل Aspose.Slides متوافق مع أحدث أطر عمل .NET؟
نعم، يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث أطر عمل .NET.
### أين يمكنني العثور على المزيد من البرامج التعليمية والأمثلة لـ Aspose.Slides؟
 قم بزيارة[توثيق](https://reference.aspose.com/slides/net/) للحصول على أدلة وأمثلة شاملة.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 اتبع ال[رابط الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) لطلب ترخيص مؤقت لأغراض الاختبار.
### هل تحتاج إلى المساعدة أو لديك أسئلة محددة؟
 قم بزيارة[منتدى دعم Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة من المجتمع والخبراء.