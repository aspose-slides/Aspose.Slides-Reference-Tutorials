---
title: دليل تضمين كائنات OLE باستخدام Aspose.Slides لـ .NET
linktitle: استبدال عنوان الصورة لإطار كائن OLE في شرائح العرض التقديمي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين شرائح العرض التقديمي باستخدام كائنات OLE الديناميكية باستخدام Aspose.Slides for .NET. اتبع دليلنا خطوة بخطوة للتكامل السلس.
weight: 15
url: /ar/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
غالبًا ما يتضمن إنشاء شرائح عرض تقديمي ديناميكية وجذابة دمج عناصر الوسائط المتعددة المختلفة. في هذا البرنامج التعليمي، سوف نستكشف كيفية استبدال عنوان الصورة لإطار كائن OLE (ربط الكائنات وتضمينها) في شرائح العرض التقديمي باستخدام مكتبة Aspose.Slides القوية لـ .NET. يعمل Aspose.Slides على تبسيط عملية التعامل مع كائنات OLE، مما يوفر للمطورين الأدوات اللازمة لتحسين عروضهم التقديمية بسهولة.
## المتطلبات الأساسية
قبل أن نتعمق في الدليل التفصيلي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Slides لمكتبة .NET: تأكد من تثبيت Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[وثائق Aspose.Slides.NET](https://reference.aspose.com/slides/net/).
- نموذج البيانات: قم بإعداد نموذج ملف Excel (على سبيل المثال، "ExcelObject.xlsx") الذي تريد تضمينه ككائن OLE في العرض التقديمي. بالإضافة إلى ذلك، يجب أن يكون لديك ملف صورة (على سبيل المثال، "Image.png") والذي سيكون بمثابة رمز لكائن OLE.
- بيئة التطوير: قم بإعداد بيئة تطوير باستخدام الأدوات اللازمة، مثل Visual Studio أو أي بيئة تطوير متكاملة مفضلة أخرى لتطوير .NET.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، تأكد من استيراد مساحات الأسماء المطلوبة للعمل مع Aspose.Slides:
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
## الخطوة 2: تحديد ملف مصدر OLE ومسارات ملفات الأيقونة
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
قم بتحديث هذه المسارات باستخدام المسارات الفعلية لنموذج ملف Excel وملف الصورة.
## الخطوة 3: إنشاء مثيل العرض التقديمي
```csharp
using (Presentation pres = new Presentation())
{
    // سيتم وضع رمز الخطوات اللاحقة هنا
}
```
 تهيئة مثيل جديد لـ`Presentation` فصل.
## الخطوة 4: إضافة إطار كائن OLE
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
قم بإضافة إطار كائن OLE إلى الشريحة، مع تحديد موضعه وأبعاده.
## الخطوة 5: إضافة كائن الصورة
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
اقرأ ملف الصورة وأضفه إلى العرض التقديمي ككائن صورة.
## الخطوة 6: قم بتعيين التسمية التوضيحية على أيقونة OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
قم بتعيين التسمية التوضيحية المطلوبة لرمز OLE.
## خاتمة
يعد دمج كائنات OLE في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET عملية مباشرة. لقد أرشدك هذا البرنامج التعليمي خلال الخطوات الأساسية، بدءًا من إعداد دليل المستند وحتى إضافة كائنات OLE وتخصيصها. قم بتجربة أنواع مختلفة من الملفات والتسميات التوضيحية لتحسين المظهر المرئي لعروضك التقديمية.
## الأسئلة الشائعة
### هل يمكنني تضمين أنواع أخرى من الملفات ككائنات OLE باستخدام Aspose.Slides؟
نعم، يدعم Aspose.Slides تضمين أنواع مختلفة من الملفات، مثل جداول بيانات Excel ومستندات Word والمزيد.
### هل رمز كائن OLE قابل للتخصيص؟
قطعاً. يمكنك استبدال الرمز الافتراضي بأي صورة من اختيارك لتناسب موضوع العرض التقديمي بشكل أفضل.
### هل يوفر Aspose.Slides الدعم للرسوم المتحركة باستخدام كائنات OLE؟
اعتبارًا من الإصدار الأحدث، يركز Aspose.Slides على تضمين كائن OLE وعرضه، ولا يتعامل مباشرة مع الرسوم المتحركة داخل كائنات OLE.
### هل يمكنني التعامل مع كائنات OLE برمجيًا بعد إضافتها إلى الشريحة؟
بالتأكيد. لديك تحكم برمجي كامل في كائنات OLE، مما يسمح لك بتعديل خصائصها ومظهرها حسب الحاجة.
### هل هناك أي قيود على حجم كائنات OLE المضمنة؟
على الرغم من وجود قيود على الحجم، إلا أنها سخية بشكل عام. يوصى باختباره باستخدام حالة الاستخدام المحددة الخاصة بك لضمان الأداء الأمثل.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
