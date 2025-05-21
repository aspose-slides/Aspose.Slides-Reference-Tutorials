---
"description": "تعرّف على كيفية تحسين شرائح العرض التقديمي باستخدام كائنات OLE الديناميكية باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس."
"linktitle": "استبدال عنوان الصورة لإطار كائن OLE في شرائح العرض التقديمي"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "دليل تضمين كائنات OLE باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# دليل تضمين كائنات OLE باستخدام Aspose.Slides لـ .NET

## مقدمة
غالبًا ما يتطلب إنشاء شرائح عروض تقديمية ديناميكية وجذابة دمج عناصر وسائط متعددة متنوعة. في هذا البرنامج التعليمي، سنستكشف كيفية استبدال عنوان صورة إطار كائن OLE (ربط الكائنات وتضمينها) في شرائح العرض التقديمي باستخدام مكتبة Aspose.Slides for .NET القوية. تُبسط Aspose.Slides عملية التعامل مع كائنات OLE، مما يوفر للمطورين الأدوات اللازمة لتحسين عروضهم التقديمية بسهولة.
## المتطلبات الأساسية
قبل أن نتعمق في الدليل خطوة بخطوة، تأكد من أن لديك المتطلبات الأساسية التالية:
- مكتبة Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [توثيق Aspose.Slides .NET](https://reference.aspose.com/slides/net/).
- بيانات نموذجية: جهّز ملف Excel نموذجيًا (مثل "ExcelObject.xlsx") لتضمينه ككائن OLE في العرض التقديمي. بالإضافة إلى ذلك، أحضِر ملف صورة (مثل "Image.png") ليكون رمزًا لكائن OLE.
- بيئة التطوير: قم بإعداد بيئة تطوير بالأدوات اللازمة، مثل Visual Studio أو أي بيئة تطوير متكاملة مفضلة أخرى لتطوير .NET.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، تأكد من استيراد المساحات المطلوبة للعمل مع Aspose.Slides:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## الخطوة 1: إعداد دليل المستندات
```csharp
string dataDir = "Your Document Directory";
```
تأكد من استبدال "دليل المستندات الخاص بك" بالمسار الفعلي لدليل المستندات الخاص بك.
## الخطوة 2: تحديد مسارات ملف المصدر OLE وملف الأيقونات
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
قم بتحديث هذه المسارات باستخدام المسارات الفعلية لملف Excel وملف الصورة الخاصين بك.
## الخطوة 3: إنشاء نسخة عرض تقديمي
```csharp
using (Presentation pres = new Presentation())
{
    // سيتم وضع الكود للخطوات اللاحقة هنا
}
```
تهيئة مثيل جديد من `Presentation` فصل.
## الخطوة 4: إضافة إطار كائن OLE
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
أضف إطار كائن OLE إلى الشريحة، مع تحديد موضعه وأبعاده.
## الخطوة 5: إضافة كائن الصورة
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
اقرأ ملف الصورة وأضفه إلى العرض التقديمي ككائن صورة.
## الخطوة 6: تعيين التسمية التوضيحية إلى أيقونة OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
قم بتعيين التسمية التوضيحية المطلوبة لأيقونة OLE.
## خاتمة
دمج كائنات OLE في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET عملية سهلة وبسيطة. يرشدك هذا البرنامج التعليمي خلال الخطوات الأساسية، من إعداد مجلد المستندات إلى إضافة كائنات OLE وتخصيصها. جرّب أنواع ملفات وتعليقات توضيحية مختلفة لتحسين المظهر المرئي لعروضك التقديمية.
## الأسئلة الشائعة
### هل يمكنني تضمين أنواع أخرى من الملفات ككائنات OLE باستخدام Aspose.Slides؟
نعم، يدعم Aspose.Slides تضمين أنواع مختلفة من الملفات، مثل جداول بيانات Excel، ومستندات Word، والمزيد.
### هل يمكن تخصيص أيقونة كائن OLE؟
بالتأكيد. يمكنك استبدال الأيقونة الافتراضية بأي صورة من اختيارك لتناسب موضوع عرضك التقديمي بشكل أفضل.
### هل يوفر Aspose.Slides الدعم للرسوم المتحركة باستخدام كائنات OLE؟
اعتبارًا من الإصدار الأحدث، يركز Aspose.Slides على تضمين كائنات OLE وعرضها، ولا يتعامل بشكل مباشر مع الرسوم المتحركة داخل كائنات OLE.
### هل يمكنني التعامل مع كائنات OLE برمجيًا بعد إضافتها إلى شريحة؟
بالتأكيد. لديك تحكم برمجي كامل بكائنات OLE، مما يسمح لك بتعديل خصائصها ومظهرها حسب الحاجة.
### هل هناك أي قيود على حجم كائنات OLE المضمنة؟
على الرغم من وجود قيود على الحجم، إلا أنها عادةً ما تكون سخية. يُنصح باختبارها مع حالة استخدامك الخاصة لضمان الأداء الأمثل.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}