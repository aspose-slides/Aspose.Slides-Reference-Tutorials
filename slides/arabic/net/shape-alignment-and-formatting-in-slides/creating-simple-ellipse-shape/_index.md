---
"description": "تعلّم كيفية إنشاء أشكال بيضاوية رائعة في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. خطوات سهلة لتصميم ديناميكي!"
"linktitle": "إنشاء شكل بيضاوي بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء شكل القطع الناقص بسهولة باستخدام Aspose.Slides .NET"
"url": "/ar/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء شكل القطع الناقص بسهولة باستخدام Aspose.Slides .NET

## مقدمة
في عالم تصميم العروض التقديمية المتغير، يُضفي دمج أشكال مثل القطع الناقص لمسةً من الإبداع والاحترافية. يُقدم Aspose.Slides for .NET حلاً فعّالاً للتعامل مع ملفات العروض التقديمية برمجياً. سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء شكل قطع ناقص بسيط في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [صفحة الإصدارات](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET على جهازك.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، ابدأ باستيراد المساحات الأساسية الضرورية:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
توفر هذه المساحات الأسماء الفئات والطرق الأساسية المطلوبة للعمل مع شرائح العرض والأشكال.
## الخطوة 1: إعداد العرض التقديمي
ابدأ بإنشاء عرض تقديمي جديد والوصول إلى الشريحة الأولى. أضف الكود التالي لتحقيق ذلك:
```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// إنشاء فئة عرض تقديمي
using (Presentation pres = new Presentation())
{
    // احصل على الشريحة الأولى
    ISlide sld = pres.Slides[0];
```
يقوم هذا الكود بتهيئة عرض تقديمي جديد وتحديد الشريحة الأولى لمزيد من التعديل.
## الخطوة 2: إضافة شكل القطع الناقص
الآن، دعنا نضيف شكل القطع الناقص إلى الشريحة باستخدام `AddAutoShape` طريقة:
```csharp
// إضافة شكل تلقائي من نوع القطع الناقص
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
يقوم هذا السطر من التعليمات البرمجية بإنشاء شكل بيضاوي عند الإحداثيات (50، 150) بعرض 150 وحدة وارتفاع 50 وحدة.
## الخطوة 3: حفظ العرض التقديمي
وأخيرًا، قم بحفظ العرض التقديمي المعدّل على القرص باسم ملف محدد باستخدام الكود التالي:
```csharp
// اكتب ملف PPTX على القرص
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
تضمن هذه الخطوة استمرار التغييرات التي أجريتها، ويمكنك عرض العرض التقديمي الناتج باستخدام شكل القطع الناقص المضاف حديثًا.
## خاتمة
تهانينا! لقد نجحت في إنشاء شكل بيضاوي بسيط في شريحة عرض تقديمي باستخدام Aspose.Slides لـ .NET. يوفر هذا البرنامج التعليمي فهمًا أساسيًا للتعامل مع الأشكال، وإعداد العروض التقديمية، وحفظ الملفات المعدّلة.
---
## الأسئلة الشائعة
### هل يمكنني تخصيص شكل القطع الناقص بشكل أكبر؟
نعم، يمكنك تعديل خصائص مختلفة لشكل القطع الناقص، مثل اللون والحجم والموضع، لتلبية متطلبات التصميم الخاصة بك.
### هل Aspose.Slides متوافق مع أحدث أطر عمل .NET؟
نعم، يتم تحديث Aspose.Slides بانتظام لضمان التوافق مع أحدث أطر عمل .NET.
### أين يمكنني العثور على المزيد من البرامج التعليمية والأمثلة لـ Aspose.Slides؟
قم بزيارة [التوثيق](https://reference.aspose.com/slides/net/) للحصول على أدلة وأمثلة شاملة.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
اتبع [رابط الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) لطلب ترخيص مؤقت لأغراض الاختبار.
### هل تحتاج إلى مساعدة أو لديك أسئلة محددة؟
قم بزيارة [منتدى دعم Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة من المجتمع والخبراء.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}